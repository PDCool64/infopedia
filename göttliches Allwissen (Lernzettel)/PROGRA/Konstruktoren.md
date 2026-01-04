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


# Canonical Constructor und automatische super()
Schreibt man selbst keinen Konstruktor, so wird automatisch der parmeterlose sog. "Canonical-Konstruktor" eingefügt.





