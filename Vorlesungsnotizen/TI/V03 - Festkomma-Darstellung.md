---
"date:": 2025-10-14
tags:
  - TI
status: rot
---

---

Festkomma-Darstellung

- Fest vorgegeben Anzahl an Vor- und Nachkommastellen
- Getrennt voneinander binär dargestellt
- Häufig aus Performancegründen eingesetzt

funktioniert auch dezimal:

```
03,27
14,41
-----
17,61

macht man, indem man das Komma einfach ignoriert

 327
1441
----
1768

und dann wieder da hinschreibt, wo es vorher auch schon stand

```

Binär werden die *negativen Exponenten verwendet*

$0.110101=1\cdot 2^{-1}+1\cdot 2^{-2}+ 1\cdot \dots.$
```
0.110101 = 1/2 + 1/4 + 1/16 + 1/64
```


Rechnen dabei auch so, als wenn das Komma gar nicht da wäre, bei der man sich einfach nur merkt wo zur Interpretation das Komma stand.

# Konvertierung Dezimalzahl->Festkomma-Darstellung

### Bei Zahlen nur mit Komma-Teil:

Wie im Horner-Schema, nur dass mit 2 Multipliziert wird und nicht durch zwei geteilt.
*Das Ergebnis wird hier aber von oben nach unten abgelesen*


> Mal testen: Kann man hier jede Zahl darstellen ? Was ist mir 1/3 etc. ? (rationale sollten gehen?)

### Bei Zahlen, die Sowohl einen Ganzzahligen, als auch einen Kommateil haben:

$(13,6875)_{10}=(13)_{10}+(0,6875)_{10}$
(Rechnung s.h. PXL-Foto)

Dann kann man die beiden Teile jeweils Nach Original Horner-Schema und der Kommazahlen-Variante umrechnen und dann addieren.