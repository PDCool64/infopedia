---
tags:
  - PROGRA
status: rot
---
---

Objekte sind Instanzen von Klassen und haben
- Attribute
- Methoden
- [[Konstruktoren]]

Grundlage für die Umsetzung im Speicher ist [[Speicher in Java - Stack und Heap]].

Wichtiges Prinzip bei der Softwareentwicklung mit OOP ist die [[Datenkapselung und Datenabstraktion]]

---
# Syntax in Java:

```java
public class Rechteck {
	double laenge, breite;
	int strichstaerke;
	
	public double flaeche() {
		return laenge*breite;		
	}
	
	private void mySecretSauce() {
		IO.println("secret")
	}
	
	void main(){
	
		Rechteck R = new Rechteck();
	}
	
}
```


---
# Erstellen von Objekten: [[Konstruktoren]]
> Hier nur ein TL:DR. Ausführliche Version in [[Konstruktoren]]

Konstruktoren sind Methoden zur Erzeugung von Objekten
Ein Konstruktor heißt genau wie die Klasse, die er erzeugt. 

Was macht ein Konstruktor:
- Erzeugt ein neues Objekt
- Setzt die Attribute des neuen Objekts auf bestimmte Werte, die er gegebenenfalls als Parameter erhält
- hat keinen Rückgabetyp

> Man kann den standardmäßig erzeugten Konstruktor mit einem eigenen überschreiben.

*Wann* wird der Konstruktor ausgeführt:
1. Die Attribute erhalten zunächst die Initialwerte aus den Variablendeklarationen im Rumpf der Klasse.
2. Anschließend wird der Konstruktor ausgeführt.

z.B.:
```java
class Rechteck {
	int laenge =5;
	
	Rechteck(){
		laenge++;	
		}
}
```
führt dazu, das ``laenge`` für jedes neue Objekt am Ende ``6`` ist.

## Konstruktor mit Parametern

```java
class Rechteck {
	int laenge =5;
	
	Rechteck(){
		laenge++;	
		}
	Rechteck(int l){
		laenge = l;	
	}
}
```

Konstruktoren können wie alle anderen Methoden auch überladen werden, womit die Objekte mit flexiblen Parametern erzeugt werden können.

# Überschreiben des "canonical"-constructors
Wenn man keinen Konstruktor schreibt, dann wird der parameterlose Konstruktor (canonical / default constructor) automatisch erzeugt. Er hat einen leeren Methodenrumpf.

**Achtung**:
- Sobald man einen eigenen Konstruktor implementiert (auch wenn dieser Parameter hat), dann wir für diese Klasse *kein* default-Konstruktor mehr automatisch erzeugt.

Typischer Anwendungsfall für eigene Konstruktoren sind **Kopier-Konstruktoren**, die ein neues Objekt mit den Eigenschaften eines schon existierenden erzeugen:
``Rechteck r = new Rechteck(anderesRechteck);``

---
# Eigenschaften von Attributen und Methoden

# ``static`` vs. nicht-``static``

> nicht-`static` Komponenten sind Eigenheiten der einzelnen Objekte der Klasse.
> 
> `static` Komponenten gibt es nur einmal pro Klasse: Sie hängen an keinem einzelnen Objekt.

Jede Variable die im Rumpf der Klasse deklariert wird und welche nicht explizit ``static`` ist, ist automatisch ein Attribut jedes Objekts: Sie sind nicht-statisch und verändern sich von Objekt zu Objekt. Man kann sie für jedes Objekt mit ``r.breite`` usw. aufrufen.

Will man in der Klasse selbst die nicht-``static`` Attribute verwenden, gilt folgendes:
- In Methoden, die selber nicht-``static`` sind, verwendet man sie direkt, oder besser mit ``this.attributsName`` (so überlädt man sie nicht versehentlich mit Methodenparametern)
- In ``static``-Methoden, muss man sie explizit auf einen bestimmten Objekt aufrufen, also z.B. ``r.laenge``

Statische Methoden sind besonders beim [[Überladen, Verdecken, Überschreiben]] von Bedeutung.

# ``public`` vs. ``private`` vs. ``protected`` vs. garnichts
``public`` Methoden und Attribute können von jeder anderen Klasse aus gesehen/verwendet/aufgerufen/abgeändert werden.

``private`` Komponenten sind ausschließlich in der eigenen Klasse sichtbar.
Sie werden *nicht* vererbt.

``proteced`` Komponenten sind im gesamten eigenen Paket sowie aller Unterklassen bekannt.


---
# Methoden genauer
## Prozedur vs. Funktion
- Man nennt Methoden mit Rückgabetyp `void` oft Prozedur.
  Hier ist kein `return` notwendig. Stattdessen wird `return` einfach zum vorzeitigen Abbrechen verwendet.
## Überladen von Methoden
Es kann in der gleichen Klasse mehrere Methoden mit gleichen Namen geben, solange deren Parameterlisten hinreichend verschieden sind. Genaueres bei [[Überladen, Verdecken, Überschreiben]] 

---
# Realisierung im Speicher
Variablen von Klassendatentypen enthalten als Wert nur eine Adresse für eine Stelle im Heap (Referenz).

Alles zum Thema Seiteneffekte, Garbage Collector etc. ist wie bei Arrays.

Achte also auf [[Call-by-value vs. call-by-reference]]

---
# Arbeiten mit Klassen : ``main``, Dateien, Compact Source File.
- Programme sind Abfolge von Klassendeklarationen
- Jede Datei darf höchstens eine ``public``-Klasse enthalten, welche genau den gleichen Namen wie die Datei haben *muss*.
- ``java Dateiname`` in der Konsole führt die ``main``-Methode der enthaltenen ``public``-Klasse aus.
	- ``main`` sollte meistens ``static`` sein.