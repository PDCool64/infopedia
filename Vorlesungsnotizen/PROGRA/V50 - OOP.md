---
date: 2025-10-30
tags:
  - PROGRA
status: rot
Vorlesungsfolien: "[[II21_Grundzuege.pdf]]"
Skriptfolien:
---
---

Vorteile von Arrays:
- "Wahlfreier Zugriff" - man kann direkt in O(1) auf jeden Array-Eintrag zugreifen

Nachteile von Arrays:
- alle Einträge haben den gleichen Typ
- Bei der Erzeugung des Arrays (mit "new") steht die Elementanzahl endgültig fest - Man kann sie nicht ändern.
- Ein Array repräsentiert immer nur eine Eigenschaft eines zu modellierenden Gegenstands.
- Arrays sind reine Datenstrukturen - Sie sind getrennt von Programmteilen die Programmteilen, die Berechnungen auf ihren Werten durchführen.

Deshalb: Wir machen OOP.

---

Objekte enthält alle Eigenschaften, sowohl
- **Attribute** (die vorher feststehen), als auch
- **Methoden** (die mit Hilfe der Attribute berechnet werden)

**Klasse** legt fest, welche Eigenschaften Objekte eines bestimmten Typs haben.

Beispiel: Syntax
```java
public class Rechteck {
	double laenge, breite;
	int strichstaerke;
	
	double flaeche() {
		return laenge*breite;	
	
	}
}
```

dann kann man `Rechteck` wie jeden anderen Datentyp verwenden.
```java
public class Rechteck_Programm {
	public static void main() {
	
		Rechteck r = new Rechteck();
		Rechteck s = new Rechteck();
		Rechteck t = new Rechteck();	
	
		r=s;
		double flaeche = r.flaeche();	
	
	}


}


```

> Beim erzeugen wird eigentlich ein Constructor aufgerufen, machen wir aber später.

Zugriff:
```java

r.laenge = 2.5;
r.breite = 2.0;
r.strichstaerke = 3;

r.flaeche() // ergibt 5.0
```

> `flaeche, breite, strichstaerke` sind hier sog. "nicht-statische" Eigenschaft des Objekts, weil jede Instanz hier möglicherweise andere Werte haben kann. (Im Gegensatz zu Eigenschaften, die allen Instanzen gemein sind.)


main sollte eigentlich `static` sein - es hängt meist nicht von bestimmten objekte ab.

`public` bedeutet, dass diese Komponente (Methode oder Klasse) überall zugreifbar ist.

Deshalb schreibt man meist `public static void main()`