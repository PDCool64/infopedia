---
tags:
  - PROGRA
status: rot
---
---

>[!def] Konstruktor
> Konstruktoren sind methodenähnliche Bestandteile einer Klasse zur Erzeugung neuer Objekte.
> Sie heißen genau wie die Klasse, die sie erzeugen und haben keinen Rückgabetyp.

Zwei Typische Konstruktoren:
```java
class Rechteck{
	public int laenge;
	public int breite;
	
	public Rechteck(int laenge, int breite){
		this.laenge = laenge;
		this.breite = breite;	
	}
	public Rechteck(int flaeche){
		this.laenge = flaeche;
		this.breite = 1;	
	}
	
	
	public static void main(){
		Rechteck r = new Rechteck(10,2);
		Rechteck s = new Rechteck(5);
	}
}
```

# Konstruktoren in Klassenhierarchien

Mit ``this();`` lässt sich ein anderer Konstruktor der gleichen Klasse aufrufen.
Mit ``super();`` lässt sich ein Konstruktor der Oberklasse aufrufen.

```java
public class A {
    int a ;

    A ( int a){
        this.a = a;
    }

}

class B extends A{
   int b;

   B (int a , int b){
       super(a);
       this.b = b;
   }
   
   B (float f, float g){
       this((int) f, (int) g);
   }

   public static void main(){
        B b = new B(1,2);
        B c = new B(1.4f,5.2f);
        
        
        // NICHT MÖGLICH:
        // B d = new B(1);
        // Dieser Konstruktor existiert nur in der Oberklasse
        // Konstruktoren werden NICHT vererbt.
   }
}
```

Wichtig:
	Konstruktoren werden nicht vererbt - sie müssen in Unterklassen neu deklariert werden

# Ablauf: Objekterzeugung in Klassenhierarchien
1. Felder der Oberklasse werden anhand ihrer Deklarationen zugewiesen
2. Konstruktor der Oberklasse wird ausgeführt ``super();`` (explizit ober Implizit)
3. Felder der Unterklasse werden anhand ihrer Deklarationen zugewiesen
4. Konstruktor der Unterklasse wird ausgeführt

```java
class A {
    int x = initX();
    int initX() { System.out.println("A.x zugewiesen"); return 1; }
    A() {
	    //hier wird automatisch super(); von Object eingefügt
	    System.out.println("Konstruktor A() ausgeführt");
	}
}

class B extends A {
    int y = initY();
    int initY() { System.out.println("B.y zugewiesen "); return 2; }
    B() { 
	    //hier wird automatisch super(); von A eingefügt
	    System.out.println("Konstruktor B() ausgeführt");
	}
}
```
Ausgabe:
```
A.x zugewiesen
Konstruktor A() ausgeführt
B.y zugewiesen
Konstruktor B() ausgeführt
```
# Default Constructor und automatisches ``super()``

1. Ein Konstruktor darf genau 1x ``this();`` oder ``super()`` aufrufen. 
   ( ggfs. mit Parametern )
   Solche Aufrufe müssen *ganz am Anfang* des Konstruktors stehen
   
2. Ruft ein Konstruktor weder ``this()`` noch ``super()`` explizit auf, fügt der Compiler automatisch einen Aufruf des Default-Constructors der Oberklasse durch ``super();`` vor dem restlichen Code des Konstruktors ein.

3. Schreibt man selbst keinen Konstruktor, so wird automatisch der parmeterlose sog. "Default-Konstruktor" eingefügt. Dieser ist *fast* leer und macht selbst nicht viel, *aber*: in den Default-Constructor wird -da er es selbst nicht explizit aufruft- auch automatisch ein ``super();`` eingefügt.


> Der Default-Constructor wird *nur* erzeugt wenn man selbst keinen einzigen Konstruktor schreibt.
### Beispiele:

1)Aus 
```java
class A {
}
```
wird implizit
```java
class A {
	A (){        //Canonical Constructor 
		super(); //automatischer super(); aufruf
	}
}
```
(Bei Klassen die nicht explizit erben wird durch ``super()`` der parameterlose Konstruktor von ``Object`` aufgerufen)

2)Aus
```java
class A{
	int a;
	A(int a){
		this.a = a;	
	}
}
```
wird implizit
```java
class A{
	int a;
	A(int a){
		super();   //automatischer super(); aufruf
		this.a = a;	
	}
}
```

## Gefahren durch automatisches super();
Schreibt man in einer Klasse einen eigenen Konstruktor mit Parametern, wird kein Default-Constructor mehr erzeugt.

Schreibt man eine Unterklasse, in deren Konstruktoren man selbst nicht explizit einen Konstruktor der Oberklasse aufruft, kommt es schnell zu Fehlern - der automatische ``super();`` ohne Parameter wird automatisch eingefügt, obwohl ein solcher Konstruktor in der Oberklasse nicht mehr existiert.

```java
public class A {
    int a ;

    A ( int a){
        this.a = a;
    }
}
class B extends A{
   int b;
   
   // FEHLER: So nicht möglich
   B (int b){
	  this.b = b; 
   }
}
```

Denn: ``B(int b)`` ruft selbst keinen Konstruktor der Oberklasse auf - also versucht java automatisch ``super();`` einzufügen. Die Oberklasse ``A`` hat aber keinen parameterlosen Konstruktor - Programm kompiliert nicht.


# Canonical Constructor bei ``record``s
Hier wird automatische ein Konstruktor eingefügt, der die Felder als Parameter nimmt und diese auch setzt. Dieser muss *immer* existieren (auch wenn man selber Konstruktoren mit unterschiedlichen Parameterlisten dazuschreibt). Man kann selber schreiben.
Jeder eigene Konstruktor *muss* diesen Canonical-Konstructor aufrufen.

Aus
```java
record Point (int x, int y) {};
```
wir implizit
```java
record Point (int x, int y){
	Point(int x, int y;){
		super(); //Konstruktor von java.lang.Record
		this.x = x;
		this.y = y;
	}
}
```
