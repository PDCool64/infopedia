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
| Wo?        | sowohl in einzelnen Klassen als auch zwischen Ober-/Unterklassen<br>      | Ober- /Unterklasse                                                                  | Ober-/Unterklasse                                                                             |
| Was?       | Methoden mit unterschiedlicher <br>Signatur                               | - Attribute<br>- Statische Methoden                                                 | nichtstatische<br>Methoden                                                                    |
| Wann?      | Compilezeit                                                               | Compilezeit                                                                         | Laufzeit                                                                                      |
| Auflösung? | spezifischste passende Signatur                                           | statischer Typ der Variable von der aufgerufen wird                                 | Unterklasse des zur Laufzeit tatsächlich vorhandenen Objekts                                  |

Man beachte bei Methoden aufrufen, die [[#Reihenfolge der Abarbeitung bei Methodenaufrufen]] von Überladen und Überschreiben: ersteres findet zuerst -zur Compilezeit- statt und beeinflusst somit was vom Überschreiben aus überhaupt gesehen wird.

---
# Überladen: Methoden mit verschiedenen Signaturen (overloading)
Innerhalb einer Klasse und ihren ggfs. existierenden Oberklassen können mehrere **Methoden** mit gleichem Namen aber hinreichend unterschiedlichen Signaturen (=Parametern) auftreten. Dies ermöglicht Ad-Hoc-Polymorphismus.

Genauer bedeutet "hinreichend unterschiedliche Signatur", dass eindeutig ist, welche der Implementierungen für jede Parameterkombination (insbesondere ihre Datentypen und Anzahl) klar ist, welche Implementierung zutrifft.

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

Sind in der Klasse oder der Klasse und ihren Oberklassen mehrere Methoden vorhanden, deren Signaturen allesamt durch verschiedene Konversionen zutreffend gemacht werden können, wird die speziellste anwendbare Methode ausgewählt. Dabei ist die Priorität:
0. exakte Übereinstimmung
1. Implizite Datentypanpassung primitiver Datentypen (int->double)
2. AutoBoxing / Unboxing (int -> Integer)
3. Varargs (int ... args)

(1. und 2. schließen sich aus - es wird nicht automatisch ``short -> int -> Integer`` gemacht)
### Beispiel: Überladen in Klassenhierarchien
Beim Überladen werden Methoden sowohl aus der momentanen Klasse als auch *allen Oberklassen* berücksichtigt.
```java
class A {
	fun(int x){
		IO.println("A");
	}
}
class B extends A {
	fun(double x){
		IO.println("B");
	}
	
	public static void main(){
		B b = new B();
		b.fun(10.0); // -> "B"
		b.fun(3);    // -> "A"
	}
}
```

---
# Verdecken: Attribute und Statische Methoden in Unterklassen (hiding)

Existiert ein Attribut mit gleichem Namen aber unterschiedlichem Datentyp sowohl in Ober- und Unterklasse, so entscheidet der *statische* Typ der Variable von der aus aufgerufen wird darüber, welche Variante sichtbar ist.

Existiert eine ``static``-Methode mit *exakt gleicher Signatur*, entscheidet ebenso der *statische* Typ der Variable von der aus aufgerufen wird.

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


---
# Überschreiben von *nichtstatischen Methoden*  in Unterklassen (overriding)

Existiert eine nichtstatische Methode mit gleichem Namen und ***[[#Überschreiben oder doch nicht? Parametersignatur|exakt gleicher]] Parametersignatur*** sowohl in Ober- und Unterklasse, wird immer die Methode der Unterklasse ausgeführt.

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
		System.out.println("Das Studiensekretariat wurde informiert");
	}
}

class Angestellter extends Person{
	@Override
	void mahnung(){
		System.out.println("Ihr Vorgesetzter bekommt eine Rechnung");
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
			//Es wird jeweils die korrekte
			//Methode der Unterklasse ausgeführt
		}
	}
}
```

Ausgabe:
```
Sie haben ein Buch nicht zurückgegeben
Das Studiensekretariat wurde informiert
Ihr Vorgesetzter bekommt eine Rechnung 
```

Somit kann man eine Datenstruktur verwalten, die Objekte verschiedener Unterklassen enthält, und es wird jeweils automatisch die korrekte Implementierung aus der spezifischen Unterklasse eines jeweiligen Objekts gefunden.

(Dies zeigt, dass es sehr gut ist, dass bei der impliziten Datentypanpassung von Unter- zur Oberklassen keine Informationen verloren gehen)

Es ist stilistisch sehr empfohlen den `@Override` Vermerkt über solche Methoden zu schreiben.

Methoden die mit ``final`` markiert sind, können nicht überschrieben werden.
(z.B. wenn man in der Klasse ``Person`` stattdessen ein ``final void mahnung()`` hätte)


---
# Reihenfolge der Abarbeitung bei Methodenaufrufen

1. Compilezeit
- In der Klasse des *statischen* Typs des Objekts und den Oberklassen dieses nach passenden Methoden suchen:
- Nach dem Prinzip "[[#Überladen Methoden innerhalb *einer* Klasse (overloading)|Überladen]]" dort die Methode mit der spezifischsten passenden Signatur suchen und diese fest setzen.
1. Laufzeit
- Überprüfen ob die gefundene Methode nicht in der tatsächlichen Unterklasse des Objekts durch [[#Überschreiben von *nichtstatischen Methoden* in Unterklassen (overriding)|Überschreiben]] abgeändert wurde: Ist dies der Fall, wird die aus der Unterklasse ausgewählt. Die überschreibende Methode der Unterklasse muss *genau* die gleiche Signatur haben - [[#Überschreiben oder doch nicht? Parametersignatur|sonst wird nicht überschrieben]]. 

```java
class Person{
	void mahnung(){
		System.out.println("Sie haben ein Buch nicht zurückgegeben");
	}
	void mahnung(int x){
		System.out.println("Mahnung aus 'Person' "+x);	
	}
}

class Student extends Person{
	@Override
	void mahnung(){
		System.out.println("Das Studiensekretariat wurde informiert");
	}
	
	void mahnung(double x){
		System.out.println("Mahnung aus 'Student' "+x);
	}
	
}


public class Main{
	public static void main(){
	
		//Array Einträge STATISCH als "Person" getypt
		Person[] schuldner = new Person[2];
		
		Person p = new Person();
		Student s = new Student();
		
		schuldner[0] = p;
		schuldner[1] = s;
		
		for(Person x : schuldner){
			
			//Zur Compilezeit die Methode mahnung() in Person gefunden
			//Zur Laufzeit aber durch mahnung() aus
			//der Unerklasse überschreiben
			x.mahnung();
			
			
			//Zur Compilezeit die Methode mahnung(int x) in Person
			//gefunden. Diese wird in Student NICHT überschrieben,
			//weil die Signatur sich unterscheidet.
			x.mahnung(1);
			//Es wird die Methode aus Person ausgeführt
			
		}
	}
}
```

Ausgabe:
```
Sie haben ein Buch nicht zurückgegeben
Mahnung aus 'Person' 1
Das Studiensekretariat wurde informiert
Mahnung aus 'Person' 1
```

---
# Stolperfallen - Weitere Feinheiten die Tricky sind_

# Methodenaufrufe in Methoden oder Konstruktoren

> Diese Falle kam so in Präsenztests vor

```java
class A{
	int x;
	
	void setX(int x){
		this.x=x;	
	}
	
	A (int x){
		setX(x);
	}
}

class B extends A{
	void setX(int x){
		this.x = x-3;
	}

	B (int x){
		super(x);
	}
	
	
	public static void main {
		B b = new B(5)	
		IO.println(b.x); // -> 2 und NICHT 5
	}
}
```

> Alle Methodenaufrufe nichtstatischer Methoden werden zur Laufzeit anhand des tatsächlichen Objekttyps aufgelöst - selbst in Konstruktoren greift somit das Überschreiben durch Methoden der tatsächlichen Unterklasse.

# Verdecken in überschriebenen Methoden
Interessant, wenn der statisch deklarierte Typ eines Objekts nicht mit dem Laufzeit-Typ übereinstimmt.

```java
class A {
	public double d=1;
	public double getD(){
		return d;	
	}
}

class B extends A{
	public double d=2;
	public double getD(){
		return d;	
	}
	
	public static void main(){
		A a = new A(); IO.println(a.d); // -> 1
		B b = new B(); IO.println(b.d); // -> 2
		A ab = b;
		IO.println(ab.d);      //-> 1 (wie erwartet nach statischem Typ)
		IO.println(ab.getD()); //-> 2 (durch Überschreiben und this.)
	}
}	
```

Warum: 

Ablauf ``ab.d``: 
	Attribute werden statisch nach deklariertem Typ vom Compiler aufgelöst und das Attribut aus ``A`` wird gefunden.

Ablauf ``ab.getD();``
1. Compilezeit: Compiler findet in statischer Klasse ``A`` die Methode ``getD()``. Parameter passen, alles ok.
2. Laufzeit: ``ab`` ist im Speicher ein ``B``-Objekt. Durch Überschreiben wird also die ``getD()``-Methode aus ``B`` ausgeführt.
3. Attributzugriff in der Methode: ``return d`` ist Kurzschreibweise für ``return this.d``. Dabei ist ``this`` immer vom Typ der Klasse in der die momentane Methode deklariert ist - auch wenn ``ab`` von dem aus aufgerufen wurde statisch als ``A`` getypt ist. Es wird also das Attribut ``d`` aus der Klasse ``B`` gefunden.

Man kann sich -*nur in Gedanken*- beim Überschreiben diese Idee merken:
	Wird die Methode überschrieben, dann wird im Methodenrumpf praktisch mit ``(B) ab`` gearbeitet.
	 ``ab.getD()`` wird -wenn die Methode in ``B`` überladen ist- also von den Attributzugriffen ca. wie ``((B) ab).getD()`` behandelt.

Merke:
> Das (implizite als auch explizite) `this.` in Methoden hat für Attributzugriffe immer den Typ der Klasse in welcher die momentane Methode deklariert ist - auch wenn das aufrufende Objekt statisch als eins einer anderen Klasse getypt ist.

Wichtig:
	Vergleiche dies mit: [[#Methodenaufrufe in Methoden oder Konstruktoren]] - hier entschiedet auch in Methoden der Oberklasse immer der tatsächliche Laufzeittyp, auch mit Impliziten ``this.setX();``.
	*Attribute und Methoden verhalten sich grundsätzlich unterschiedlich*.
# Überschreiben oder doch nicht? Parametersignatur

```java
class A {
	public void fun(){
		IO.println("A");
	}

	public void fun(int x){
		IO.println("A");
	}
}

class B extends A {
	public void fun(){
		IO.println("B");
	}
	public void fun(long x){
		IO.println("B");
	}
	
	public static void main(){
		A ab = new B();
		ab.fun();  // -> "B"     (Wird überschrieben)
		ab.fun(1); // -> "A"     (Wird nicht überschrieben)
	}
}
```

Achtung:
 1. Zuerst sucht der Compiler zur Compilezeit in der Klasse des statischen Typs die Methode mit spezifischsten passenden Parametern *und setzt diese fest*.
2. Zur Laufzeit: Überschreiben findet nur statt, wenn die Parametersignatur der überschreibenden Methode *exakt* mit der -vorher in der Oberklasse vom Compiler festgelegten- Methode übereinstimmt.

hier wird bei ``fun(1)`` keine überschreibende Methode gefunden:
- Der Compiler findet in ``A`` eine Methode die ``int`` akzeptiert und setzt diese fest
- In ``B`` existiert nur ``fun(long x)`` - das ist aber nicht das gleiche wie ``fun(int x)`` 