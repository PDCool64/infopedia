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

# Erzeugen von Objekten der Hüllklassen

## Die ``.valueOf(...)`` Funktionen

```java
short s = 24;
Integer i = Integer.valueOf(s);
```
