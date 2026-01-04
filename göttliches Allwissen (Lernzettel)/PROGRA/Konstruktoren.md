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
Was passiert bei



