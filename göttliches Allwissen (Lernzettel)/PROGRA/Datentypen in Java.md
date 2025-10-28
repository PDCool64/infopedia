---
tags:
  - PROGRA
status: rot
---
---



---
# Ganze Zahlen
Speicher [[Zahlenräume#Ganze Zahlen $ mathbb{Z}$|Ganze Zahlen]] im [[Negative Binärzahlen durch Komplement - Ganze Zahlen im Binärsystem#Negative Zahlen als Zweier-Komplement|Zweier-Komplement]].
Mit $n$ Bits können die Zahlen von $-2^{n-1}$ bis $2^{m-1}-1$ (beide inklusive) darstellen.

|           | min                                          | max                                          | Speicher |
| --------- | -------------------------------------------- | -------------------------------------------- | -------- |
| ``byte``  | $-2^{8-1}=-128$                              | $2^{8-1}-1=127$                              | 8Bit     |
| ``short`` | $-2^{16-1}=-32\,768$                         | $2^{16-1}-1=32\,767$                         | 16Bit    |
| ``int``   | $-2^{32-1}=-2\,147\,483\,648$                | $2^{32-1}-1=2\,147\,483\,647$                | 32Bit    |
| ``long``  | $-2^{64-1}=-9\,223\,372\,036\,854\,775\,808$ | $2^{64-1}-1=9\,223\,372\,036\,854\,775\,807$ | 64Bit    |

---
# Gleitkomma Zahlen
Werden nach den [[Gleitkomma-Darstellung von Binärzahlen|IEEE754]]-Standard als Gleitkommazahlen gespeichert.
in Java gibt es die beiden Varianten:

| Java      | IEE754                       |
| --------- | ---------------------------- |
| ``float`` | IEEE754 ``single`` mit 32Bit |
| `double`  | IEEE754 ``double`` mit 64Bit |
Zahlen die mit einem Punkt ``.`` geschrieben werden, sind standardmäßig ein ``double``, mit ``f`` kann man aber einen ``float`` erzwingen:
- ``12.3`` $\to$ double
- ``.4`` $\to$ double
- ``10.0`` $\to$ double
- ``5.`` $\to$ double
- ``12.3f`` $\to$ float
---
# char 
Einzelne Zeichen, in *einfachen* Anführungszeichen.
``'a'`` aber auch Steuerzeichen wie `\n`

---

# String
Ketten von Zeichen, in *doppelten* Anführungszeichen.
`"a"` oder `"Hallo Welt!"`

> Strings sind in Java *keine* primitiven Datentypen - sie sind stattdessen aus anderen Datentypen konstruiert und werden wie alle Klassen mit Großbuchstaben geschrieben.
---
# boolean
Entweder ``true`` oder ``false``

> Achtung: die Integers `1` und `0` sind in Java nicht mit Booleans austauschbar!
