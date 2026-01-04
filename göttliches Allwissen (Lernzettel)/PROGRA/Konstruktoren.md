---
tags:
status: rot
---
---

>[!def] Konstruktor
> Konstruktoren sind Methoden zur Erzeugung neuer Objekte.
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

# Ablauf
Was passiert beim Konstruktoraufruf

1. Parameter werden auf die Werte ihrer Variablendeklaration gesetzt
2. Konstruktor wird ausgeführt

```java
class Rechteck{
    public int laenge=5;
    public int breite=1;

    public Rechteck(){
        this.breite +=1;
        this.laenge -=1;
    }
    public static void main(){
        Rechteck2  = new Rechteck();
        IO.println(r.laenge); // 4
        IO.println(r.breite); // 2
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

# Canonical Constructor und automatisches super()

1. Ein Konstruktor darf genau 1x ``this();`` oder ``super()`` aufrufen. 
   ( ggfs. mit Parametern )
   Solche Aufrufe müssen *ganz am Anfang* des Konstruktors stehen
   
2. Ruft ein Konstruktor weder ``this()`` noch ``super()`` explizit auf, fügt der Compiler automatisch einen Aufruf des canonical-Constructors der Oberklasse durch ``super();`` vor dem restlichen Code des Konstruktors ein.

3. Schreibt man selbst keinen Konstruktor, so wird automatisch der parmeterlose sog. "Canonical-Konstruktor" eingefügt. Dieser ist *fast* leer und macht selbst nicht viel, *aber*: in den Canonical Constructor wird -da er es selbst nicht explizit aufruft- auch automatisch ein ``super();`` eingefügt.


> Der Canonical Constructor wird *nur* erzeugt wenn man selbst keinen einzigen Konstruktor schreibt.
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
Schreibt man in einer Klasse einen eigenen Konstruktor mit Parametern, wird kein Canonical Constructor mehr erzeugt.

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

Denn: ``B(int b)`` ruft selbst keinen Konstruktor der Oberklasse auf - also versucht java automatisch ``super();`` einzufügen. Die Oberklasse ``A`` hat aber keinen parameterlosen Fehler - Programm kompiliert nicht.
