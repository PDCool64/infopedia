---
tags:
  - PROGRA
status: rot
---
---
## Warum?

Will man Datenstrukturen programmieren, welche auf verschiedene Datentypen anwendbar seien sollen, will man nicht mehrfach die gleiche Klasse ``ListeBruch`` , ``ListeZahl`` usw. neu implementieren.


 Warum nicht einfach die Linked-List-Klasse mit Elementen vom Typ `Object` schreiben?
 1. Wir können keine Anforderung an Werte ausdrücken. 
    **Lösung:** Verwende abstrakte Klassen oder Interfaces.
 2. Verschiedene Objekt-Typen in der gleichen Liste könnten auftreten und Fehler erzeugen.
    *Ist auch durch Interfaces nicht gut abdeckbar*.
 3. Zugriff auf Elemente der Liste gibt immer Objekte vom Typ `Object` aus - um mit ihnen zu arbeiten muss man sie dann immer manuell und explizit wieder zu Instanzen der Unterklasse casten.
    (und Lauter `isinstanceof` Unterscheidungen bauen um dies zu ermöglichen)

Die Lösung für Problem 2) und 3) sind *Generische Typen*:

---
# Generische Typen

Eine generische Klasse ``Element<T>`` definiert viele Typen
- ``Element<Bruch>
- ``Element<Zahl>
- ...

Idee:
	Eine *Typvariable* (hier ``T``) kann mit jedem beliebigen [[Speicher in Java - Stack und Heap|nichtprimitiven]] Datentyp instanziiert werden
Dies stellt sicher, dass eine Liste vom Typ ``Liste<Bruch`` nur Werte vom Typ Bruch enthalten kann.


Eine Klasse - Viele Typen

## Erzeugen von Objekten generischer Typen

```java
class Element<T>{

		// referenziert den Typparameter T der Klasse
    public T value;
    public Element<T> next;

	public Element(T value){
        this.value = value;
    }

    public static void main(){           //Autoboxing int->Integer
        Element<Integer> a = new Element<Integer>(10);
        Element<Integer> b = new Element<Integer>(10);
        
        a.next = b; //Erlaubt : a hat Typ Element<Integer> 
                    //          b hat Typ Element<Integer>
                    
                    
					            //Kurzschreibweise
        Element<Double> c = new Element<>(20.5);
        
        Element<String> d = new Element<>("hallo");
        Element<String> e = new Element<>("moin");
        
        d.next = e; // Erlaubt

        System.out.println(a.value); 
        System.out.println(b.value);
        System.out.println(c.value);
    }
}
```

#### Erreich Ziel: Typfehler werden statisch abgefangen:
``a.next = b;`` ist erlaubt, weil ``a.next`` ein Element vom Typ ``Element<Integer>`` erwartet und ``b`` ein solches ist.

Hingegen wäre ``b.next=c;`` ein Typfehler : ``b`` erwartet ``Element<Integer>`` aber ``c`` ist ``Element<Double>``


# Statische Methoden in Generischen Klassen




# Generische Klassen als Polymorphismus: Parametrischer Polymorphismus
Dieselbe Implementierung einer Methode kann für Objekte/Argumente verschiedener Typen ausgeführt werden.

