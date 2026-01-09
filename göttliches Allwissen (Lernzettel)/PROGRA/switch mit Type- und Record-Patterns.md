---
tags:
  - PROGRA
status: rot
---
---
Bekannt ist, dass [[Kontrollstrukturen in Java#``switch``-Anweisung und Ausdruck|switch]] über Werte von primitiven Datentypen sowie String und Enums anwendbar ist:

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

> Hier ist meistens ein `default`-case Notwendig, damit eine Fallunterscheidung vollständig wird. Ausnahmen sind Enums und sealed-classes bei denen alle Subtypen abgedeckt sind. Oft auch `null` notwendig, damit vollständig.

Neu dazu kommen:
- Patterns: Muster erkennen und automatisch Variable zuweisen
	- ``case <Klassen-Datentyp> <Variable> {...};``
		- Trifft der Datentyp zu, wir die Variable mit dem Wert aus dem ``switch`` belegt. Sie hat den Typ der aus der Pattern hervorgeht.
	- "guarded pattern": mit
	   ``case <Klassendatenyp> <Variable> when <boolean> {...};`` können weitere Anforderungen an die Eigenschaften eines Objekts gestellt werden

- Neben ``default`` auch ein ``null``-case, da es sich um Objekte handelt.
	- schreibt man einen `null` case, so *muss* dieser der ***erste*** case sein.

Wie immer müssen *spezielle* Fälle vor allgemeinen stehen. Also zuerst Unterklassen, dann Oberklassen usw.
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
    public Sklave(String name) {
        super(name);
    }
};

public class Switch {
    void f (Person p){

        switch(p){
        
	        //null-case muss (wenn existent) der erste case sein
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
Weil bei Records die Form und die Attribute genau fest stehen, kann man auch Patterns über den *Inhalt* von Records schreiben. Jedes Attribut des Records kann dabei selbst wieder durch eine Type- oder Record-Pattern beschrieben werden.

Es sind dabei mit ``_`` sowohl leere Type- als auch leere Record-Patterns möglich:

Syntax:
``<EinRecord>(<Type oder RecordPattern> , <Type oder RecordPattern> , ...)

Zum Beispiel:
```java
record Paar(Person p1, Person p2){};
record Haushalt(Paar P1, Paar P2){};

public class RecordPatterns {

    void f (Paar paar){
        switch (paar){
		  case Paar(Student s1 , Student s2) ->
	           IO.println("Bei"+s1.name+"und"+s2.name+"gibs Bafäg");
           
           case Paar(Angestellter a1 , Student _ ) ->
	           IO.println(a1.name+" zahl alleine die Miete");
           
           case Paar(Sklave _ , _ ) , Paar(_ , Sklave _) ->
	           IO.println("rip");
	           
           default -> IO.println("moin");
        }
    }
    void g(Haushalt haushalt){
        switch (haushalt){
            case Haushalt(
	            Paar(Student s1 , Student s2) ,
	            Paar(Angestellter _ , _)
	            ) -> IO.println("a");
				 
            case Haushalt( _ , Paar( _ , Sklave s))
	            when s.name.equals("Sparatcus") ->
	             IO.println("b");
			
            default  -> IO.println("servus"); 
        }
    }
}

```

Man beachte, dass die Reihenfolge der Attribute bei Records, also auch bei den obigen Patterns, eine entscheidende Rolle spielt.