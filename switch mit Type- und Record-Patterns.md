---
tags:
  - PROGRA
status: rot
---
---
Bekannt ist, dass [[Kontrollstrukturen in Java#``switch``-Anweisung und Ausdruck|switch]] über Werte von primitiven Datentypen sowie String anwendbar ist:

```java
void f(int x){
	switch (x){
		case 0,1  -> IO.println("Die Zahl ist 0 oder 1");
		case 13 -> {	
			IO.println("Unglück geschehe");
			IO.println("Komme die Verdammniss über dich");
			}
		default -> IO.println("eine andere Zahl halt");
	}
}
```

----
# Switch mit Type-Patterns
Möglich ist auch ``switch`` über beliebige Klassen-Datentypen zu verwenden. Die Unterscheidung wird jetzt danach gefällt, um welche *Unterklasse* es sich handelt.

> Hier ist meistens ein `default`-case Notwendig, damit eine Fallunterscheidung vollständig wird. Ausnahmen sind Enums und sealed-classes.

Neu dazu kommen:
- Patterns: Muster erkennen und automatisch Variable zuweisen
	- ``case <Klassen-Datentyp> <Variable> {...};``
		- Trifft der Datentyp zu, wir die Variable mit dem Wert aus dem ``switch`` belegt. Sie hat den Typ der aus der Pattern hervorgeht.
	- "guarded" case-labels: mit
	   ``case <Klassendatenyp> <Variable> when <boolean> {...};`` können weitere Anforderungen an die Eigenschaften eines Objekts gestellt werden

- Neben ``default`` auch ein ``null``-case, da es sich um Objekte handelt.
### Syntax:
```java
class Person {
    public String name;
    public Person(String name) {
        this.name = name;
    }
}

class Student extends Person {
    public String uni;
    public Student(String name, String uni) {
        super(name);
        this.uni = uni;
    }
}


class Angestellter extends Person{
    public String chef;
    public Angestellter(String name,String chef){
        super(name);
        this.chef =chef;
    }
}
class Sklave extends Person {
    public Sklave(String name, String chef) {
        super(name);
    }
};

public class Switch {
    void f (Person p){

        switch(p){
            case null -> {
                IO.println("Dummer Aufruf");
                throw new NullPointerException();
                // hier kann man machen was man will
                // Diese Exception passt aber gut
            }

            //guarded case: WHEN
            case Angestellter a when a.chef.equals("RWTH") -> {
                IO.println("Ein Angestellter der RWTH");
                IO.println("Sag Hallo!");
            }
            //unbenannte pattern-Variable, mehrere Patterns
            case Angestellter _ , Sklave _-> IO.println("Ein Arbeiter");

            default -> IO. println("Ein Dude halt");
        }
    }

    void main(){
        f(new Angestellter("Hans","KIT")) ;
        f(new Student("Tom","RWTH"));
        f(new Person("Dieter"));
        f(null);
    }
}

```


# Record Patterns

Syntax:
``<EinRecord>(<Type oder RecordPattern> , <Type oder RecordPattern> , ...)

Zum Beispiel:
```java

```
