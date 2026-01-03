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


# Compile- vs. Laufzeit
Generische Typen existieren ausschließlich zur Compilezeit - sie sind sozusagen glorifizierte Compileranweisungen, die dafür sorgen, dass Typfehler erkannt und abgefangen werden.

> Generische Typen gibt es erst seit Java 5 - Um Rückwärtskompatibilität zu erhalten ist ihre Implementierung so gewählt.

Zur Laufzeit / Im Bytecode werden alle Generischen Typen zu einem einzigen "Raw Type" neo denen die Typvariablen durch ``Object`` ersetzt werden. Zur Laufzeit existieren also nicht mehr ``Element<Bruch>`` und `Element<Zahl>` sondern nur noch ``Element``.

Dies hat wichtige Konsequenzen:
- [[#Statische Methoden]]
- [[#Nichtstatische Methoden]]
- [[#Type Bounds Typparameter darf nur mit bestimmten Typen instantiiert werden|Type Bounds]]
- ``isinstanceof Element<Bruch>`` geht nicht - zur Laufzeit ist nur ``isinstanceof Element`` möglich

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


# Nichtstatische Methoden
Sie können auf die Typvariable der Klasse zugreifen.

#### Warum:
Nichtstatische Methoden hängen vom einzelnen Objekt ab. Sie werden also ausschließlich mit ``einObjekt.funktion();`` aufgerufen, womit insbesondere der (generische)*Typ* des aufrufenden Objekts immer bekannt ist.

Der Compiler kann somit statisch überprüfen, ob Typfehler auftreten würden und diese Abfangen:

```java
public class Element<T>{

    public T value;
    public Element<T> next;

	public Element(T value){
        this.value = value;
    }
    public T getValue(){
        return value;
    }
    public void setValue(T value){
        this.value = value;
    }
    public Element<T> getNext(){
        return next;
    }
    public void setNext(Element<T> next){
        this.next = next;
    }
    
    
    public static void main(){
		Element<Integer> a = new Element<Integer>(10);
		Element<String>  b = new Element<String>("hallo");
		
		// TYPFEHLER:
		a.setNext(b);
    } 
}
```

Denn: Da die Methode vom spezifischen Objekt ``a`` aus aufgerufen wird, und `a` statisch als ``Element<Integer>`` getypt ist, kann der Compiler den Typfehler abfangen. Alles funktioniert wie gedacht, auch ohne dass die Generischen Typen zur Laufzeit wirklich existieren.

# Statische Methoden
Können nicht auf den Typparameter der Klasse zugreifen.
#### Warum:
Statische Methoden hängen *nicht* von einzelnen Objekten ab. 

Insbesondere können statische Methoden ohne weiteren Kontext direkt auf der Klasse aufgerufen werden.

Wollte man nun z.B. Funktionsparameter mit generischem Typ in einer statischen Methode anlegen, hätte der Compiler






# Type Bounds : Typparameter darf nur mit bestimmten Typen instantiiert werden

```java
    public T value;
    public Element<T> next;
    public String name;

	public Element(T value, String name){
        this.value = value;
        this.name = name;
    }

    public <U extends SomeInterface> Element<U> CopyWithNewValue(U newValue){
       Element<U> out = new Element<U>(newValue, this.name);
       return out;
    }

    public static void main(){
        MyInteger a = new MyInteger(20);
        MyInteger b = new MyInteger(30);

        Element<MyInteger> x = new Element<>(a,"x");
        Element<MyInteger> y = new Element<>(b,"y");

        Element<MyInteger> z = x.CopyWithNewValue(new MyInteger(2));

        System.out.println(x.value.number);
        System.out.println(y.value.number);
        System.out.println(z.value.number);
    }

}

class MyInteger implements SomeInterface{
   public Integer number;
   public MyInteger(Integer value){
       this.number = value;
   }
}
```



# Generische Klassen als Polymorphismus: Parametrischer Polymorphismus
Dieselbe Implementierung einer Methode kann für Objekte/Argumente verschiedener Typen ausgeführt werden.

