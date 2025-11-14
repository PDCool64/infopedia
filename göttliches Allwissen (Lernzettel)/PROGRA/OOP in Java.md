---
tags:
  - PROGRA
status: rot
---
---

Objekte sind Instanzen von Klassen und haben
- Attribute
- Methoden

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
# Eigenschaften von Attributen und Methoden

# ``static`` vs. nicht-``static``
Jede Variable die im Rumpf der Klasse deklariert wird und die nicht explizit ``static`` ist, ist automatisch ein Attribut jedes Objekts: Sie sind nicht-statisch und verändern sich von Objekt zu Objekt. Man kann sie für jedes Objekt mit ``R.breite`` usw. aufrufen.

Will man in der Klasse selbst die nicht-``static`` Attribute verwenden, gilt folgendes:
- In Methoden, die selber nicht-``static`` sind, verwendet man sie direkt, oder besser mit ``this.attributsName`` (so überlädt man sie nicht versehentlich mit Methodenparametern)
- In ``static``-Methoden, muss man sie explizit auf einen bestimmten Objekt aufrufen, also z.B. ``r.laenge``



# ``public`` vs. ``private`` vs. ``protected`` 
``public`` Methoden und Attribute können von jeder anderen Klasse aus gesehen/verwendet/aufgerufen/abgeändert werden.


---
# Methoden genauer
## Prozedur vs. Funktion
- Man nennt Methoden mit Rückgabetyp `void` oft Prozedur.
  Hier ist kein `return` notwendig. Stattdessen wird `return` einfach zum vorzeitigen Abbrechen verwendet.
- Man nennt Methoden mit Rückgabetypen meist Prozeduren.
  die haben dann immer ein `return` 

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