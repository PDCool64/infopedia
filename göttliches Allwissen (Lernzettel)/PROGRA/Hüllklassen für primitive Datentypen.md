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
# Autoboxing und Autounboxing, implizite Datentypanpassung

## Autoboxing: ``int->Integer``
Der primitive Typ kann automatisch zum Hüllklassentyp gewandelt werden.
## AutoUnboxing: ``Integer->int``
Der Hüllklassentyp kann automatisch zum primitiven Datentyp gewandelt werden.


*Dies kann beides nicht mit normaler impliziter Datentypanpassung kombiniert werden - es kann nur genau zwischen Hüllklassentyp und genau entsprechendem primitiven Typ autoboxing passieren.* 
## Beispiele
![[Pasted image 20260105144548.png]]

Ebenfalls verboten sind -ebenfalls weil AutoBoxing/Unboxing nicht mit impliziter Datentypanpassung kombinierbar sind:
```java
short s = 3;
Integer i = s; // VERBOTEN

int x = Double.valueOf(1.0);
long l = Byte.valueOf(2);
```


---
# Methodenaufrufe mit Hüllklassen als Parameter
