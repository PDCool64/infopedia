---
tags:
  - PROGRA
status: rot
---
---
Es gibt für jeden Primitiven Datentyp eine sog. Hüllklasse :
- `boolean` -> `Boolean`
- `char` -> `Character` 
- `int` -> `Interger` 
- ``long`` -> ``Long`` 
- usw.

Diese kapseln jeweils einen Wert ihres primitiven Datentyps als *privates* Attribut.

# Erzeugen von Objekten der Hüllklassen: 
``int->Integer``

> Wie bei jeder Klasse gibt es zwar auch Konstruktoren wie `Integer i = new Integer(2);` diese sind aber seit Java 9 deprecated und sollten nicht mehr benutzt werden - sie existieren aber immernoch für die Rückwärtskompatibilität. 
> 
> Stattdessen sollte man die `.valueOf(...)`-Methoden verwenden, denn diese verwenden u.a. Speicher wieder und sind schneller.
## Die ``<Klasse>.valueOf(<Parameter>)`` Funktionen

Für die Zahlendatentypen:

Parameter möglich
- primitiven Datentyp 
- kleinere primitive Datentypen (durch implizite Datentypanpassung)
- ``String`` - wirf aber ggfs. eine ``NumberFormatException`` falls der String keine gültige Zahl enthält

```java
short s = 24;
Integer i = Integer.valueOf(s);
Long l = Long.valueOf(2);
Double d = Double.valueOf(2.3);
```

``Character`` und ``Boolean`` sind nochmal etwas anders - haben wir aber nicht gemacht.


# Auslesen der gespeicherten Werte
``Ìnteger->int``
## Die ``<Objekt>.intValue()`` Funktionen

``` java
Long l = Long.valueOf(2);
Double d = Double.valueOf(2.3);

int x = l.intValue();
double y = d.doubleValue();
```

# Vergleichen von Hüllklassen-Elementen
Es handelt sich um *Objekte* - also liegen auf dem Stack lediglich Pointer.
*Man sollte Hüllklassen niemals mit `` == `` vergleichen.*

Stattdessen gibt es immer ``<object>.equals(<other>)`` Methoden:
```java
Integer a = Integer.valueOf(10000);
Integer b = Integer.valueOf(10000);

IO.println(a.equals(b));
```

---
# Autoboxing und AutoUnboxing, implizite Datentypanpassung

## Autoboxing: ``int->Integer``
Der primitive Typ kann automatisch zum Hüllklassentyp gewandelt werden.

*Es ist nicht möglich, vor dem Boxing noch implizite Datentypanpassung zu betreiben*
*AutoBoxing ist nur **genau** vom primitiven Typ aus erlaubt*
## AutoUnboxing: ``Integer->int``
Der Hüllklassentyp kann automatisch zum primitiven Datentyp gewandelt werden.

*Hingegen ist es erlaubt, nach dem AutoUnboxing noch implizite Datentypanpassung zu betrtreiben*

```java
void main() {  
	// Autoboxing:
    // VERBOTEN: primitive Widening -> Autoboxing  
    Double d = 1;    //KOMPILIERT NICHT
    Long g = 3;      //KOMPILIERT NICHT

	// AutoUnboxing:	
    // ERLAUBT: Unboxing -> primitve Widening  
    double x = Float.valueOf(2.0f);  
    long l = Integer.valueOf(3);   
```

## Beispiele
![[Pasted image 20260105144548.png]]
