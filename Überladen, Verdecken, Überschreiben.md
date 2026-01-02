---
tags:
  - PROGRA
status: rot
---
---
Finden allesamt statt, wenn in einem Kontext mehrere Attribute/Methoden mit gleichem Namen existieren.
## TL:DR :

|            | [[#Überladen Methoden innerhalb *einer* Klasse (overloading)\|Überladen]] | [[#Verdecken Attribute und Statische Methoden in Unterklassen (hiding)\|Verdecken]] | [[#Überschreiben von *nichtstatischen Methoden* in Unterklassen (overriding)\|Überschreiben]] |
| ---------- | ------------------------------------------------------------------------- | ----------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| Wo?        | innerhalb einer Klasse                                                    | Ober- /Unterklasse                                                                  | Ober-/Unterklasse                                                                             |
| Was?       | Methoden mit unterschiedlicher <br>Signatur                               | - Attribute<br>- Statische Methoden                                                 | nichtstatische<br>Methoden                                                                    |
| Wann?      | Compilezeit                                                               | Compilezeit                                                                         | Laufzeit                                                                                      |
| Auflösung? | spezifischste passende Signatur                                           | statischer Typ der Variable von der aufgerufen wird                                 | Unterklasse des zur Laufzeit tatsächlich vorhandenen Objekts                                  |

---
# Überladen: Methoden innerhalb *einer* Klasse (overloading)
Innerhalb einer Klasse können mehrere **Methoden** mit gleichem Namen aber hinreichend unterschiedlichen Signaturen (=Parametern) auftreten. Dies ermöglicht Ad-Hoc-Polymorphismus.

Genauer bedeutet "hinreichend unterschiedliche Signatur", dass eindeutig ist, welche der Der Implementierungen für jede Parameterkombination (insbesondere ihre Datentypen und Anzahl) klar ist, welche Implementierung zutrifft.

```java
public class Rechteck{
	private int laenge;
	private int breite;
	
	public Rechteck(int breite, int laenge){
		this.breite = breite;
		this.laenge = laenge;	
	}
	
	public Rechteck(int flaeche){
		this.breite = flaeche;
		this.laenge = 1;	
	}
	
	public static void main(){
		Rechteck a = new Rechteck(10,20);
		Rechteck b = new Rechteck(5);
	}

}
```

Sind mehrere Methoden vorhanden, deren Signaturen allesamt durch verschiedene Konversionen zutreffend gemacht werden können, wird die speziellste anwendbare Methode ausgewählt. Dabei ist die Priorität:
0. exakte Übereinstimmung
1. Implizite Datentypanpassung primitiver Datentypen (int->double)
2. AutoBoxing / Unboxing (int -> Integer)
3. Varargs (int ... args)

(1. und 2. schließen sich aus - es wird nicht automatisch ``short -> int -> Integer`` gemacht)

---
# Verdecken: Attribute und Statische Methoden in Unterklassen (hiding)

Existiert ein Attribut mit gleichem Namen aber unterschiedlichem Datentyp sowohl in Ober- und Unterklasse, so entscheidet der *statische* Typ der Variable von der aus aufgerufen wird darüber, welche Variante sichtbar ist.

Existiert eine ``static``-Methode mit gleicher Signatur, entscheidet ebenso der *statische* Typ der Variable von der aus aufgerufen wird.

```java

class Person{
	// Hat die Person einen Hochschulabschluss?
	public boolean hochschule;
	static void info(){
		System.out.println("Ich bin eine Person");
	}
}

class Student extends Person{
	// Name der Hoschule die besucht wird.
	public String hochschule;
	
	static void info(){
		System.out.println("Ich bin ein Student");
	}
}

public class Main{
	public static void main(){
	
		Student s = new Student();
		s.hochschule = "RWTH"; // erlaubt
		s.info(); // -> "Ich bin ein Student"
		
		Person p = s;
		p.hochschule = true; // erlaubt
		p.info(); // -> "Ich bin eine Person"
	}
}

```

Hier also:
- `s` ist statisch als ``Student`` getypt, also ist nur das ``String``-Attribut sichtbar.
- ``p`` ist statisch als ``Person`` getypt, also ist nur das ``boolean``-Attribut sichtbar. Dass ``p`` zur Laufzeit auf ein ``Person``-Objekt zeigt, ist egal.

> Verdecken wird zur Compilezeit aufgelöst.

Methoden die mit ``final`` markiert sind, können nicht verdeckt werden.
(z.B. wenn man in der Klasse ``Person`` stattdessen ein ``static final void info()`` hätte)

---
# Überschreiben von *nichtstatischen Methoden*  in Unterklassen (overriding)

Existiert eine nichtstatische Methode mit gleichem Namen und gleicher Parametersignatur sowohl in Ober- und Unterklasse, wird immer die Methode der Unterklasse ausgeführt.

>Überschreiben wird zur *Laufzeit* ausgewertet und die Methode der tatsächlichen Klasse des Objekts im Speicher verwendet, auch wenn diese statisch als Oberklasse getypt ist.

```java
class Person{
	void mahnung(){
		System.out.println("Sie haben ein Buch nicht zurückgegeben");
	}
}

class Student extends Person{
	@Override
	void mahnung(){
		System.out.println("Das Studiensekretariat wurde informiert, dass sie ein Buch nicht zurückgegeben haben");
	}
}

class Angestellter extends Person{
	@Override
	void mahnung(){
		System.out.println("Ihr Vorgesetzter hat eine Rechnung für das Buch das sie nich zurückgegeben haben erhalten");
	}
}

public class Main{
	public static void main(){
	
		//Array Einträge STATISCH als "Person" getypt
		Person[] schuldner = new Person[3];
		
		Person p = new Person();
		Student s = new Student();
		Angestellter a = new Angestellter();
		
		schuldner[0] = p;
		schuldner[1] = s;
		schuldner[2] = a;
		
		for(Person x : schuldner){
			//einzelne Einträge zeigen Zur LAUFZEIT auf 
			//Objekte der Unterklasse	
			x.mahnung();
			//Es wird jeweils die korrekte Methode der Unterklasse ausgeführt
		}
	}
}
```

Ausgabe:
```
Sie haben ein Buch nicht zurückgegeben
Das Studiensekretariat wurde informiert, dass sie ein Buch nicht zurückgegeben haben
Ihr Vorgesetzter hat eine Rechnung für das Buch das sie nich zurückgegeben haben erhalten
```

Somit kann man eine Datenstruktur die gemischt einzelne Unterklassen enthält verwaltet werden, und es wird jeweils automatisch die korrekte Implementierung aus der spezifischen Unterklasse eines jeweiligen Objekts gefunden.

(Dies zeigt, dass es sehr gut ist, dass bei der impliziten Datentypanpassung von Unter- zur Oberklassen keine Informationen verloren gehen)

Es ist stilistische sehr empfohlen den `@Override` Vermerkt über solche Methoden zu schreiben.

Methoden die mit ``final`` markiert sind, können nicht überschrieben werden.
(z.B. wenn man in der Klasse ``Person`` stattdessen ein ``final void mahnung()`` hätte)


