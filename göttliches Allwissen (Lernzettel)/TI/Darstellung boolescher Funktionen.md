---
tags:
  - TI
status: rot
---
---

Ein Überblick über verschiedene Darstellungsformen von [[Schaltfunktionen und Boolesche Funktionen#Boolesche Funktionen|Booleschen Funktionen]]

---

# 1.0 Wahrheitstafeln

Jede boolesche Funktion kann als Warheitstafel geschrieben werden, die für alle Kombinationen der Eingaben eine Ausgabe ausweißt.

z.B. :

| $x_{1}$ | $x_{0}$ | $f(x_{1},x_{0})$ |
| ------- | ------- | ---------------- |
| 0       | 0       | 0                |
| 0       | 1       | 1                |
| 1       | 0       | 1                |
| 1       | 1       | 0                |
wobei es sich hier um die Wahrheitstafel von $\text{xor}$ handelt.

# 1.1 Liste "*einschlägiger Indizes*"

Man nummeriert die Zeilen einer Wahrheitstabelle durch.
Dann speichert man nur noch die Indizes der Spalten welche $1$ als Ausgabe liefern.

![[Darstellung boolescher Funktionen 2025-10-23 13.00.00.excalidraw]]

Basierende darauf, wie im Binärsystem gezählt wird, sind die Zeilenindizes eigentlich nur die ins Dezimalsystem übertragenen Bitmuster, welche als Ausgabe $1$ liefern:

$(3)_{10}=(011)_{2}$
$(5)_{10}=(101)_{2}$
$(7)_{10}=(111)_{2}$

Das Konvertieren aus einer Liste einschlägiger Indizes zu einer Wahrheitstabelle ist somit ebenfalls trivial.

# 1.2 Binärvektorliste und Ternärverktorliste
(heute eher veraltet)

Verwendet wird die Schreibweise mit einem Unterstrich `_` , welcher "Do Not Care" bedeutet - der Eingabebit an dieser Stelle kann also einen beliebigen Wert haben.

Man nimmt sich eine Tabelle der [[#1.1 Liste "*einschlägiger Indizes*"|Einschlägigen Zeilen]] und streicht dan redundante Informationen:
![[Darstellung boolescher Funktionen 2025-10-23 13.08.10.excalidraw]]
Es entsteht also die Form `1_1 , _11` welche beide Eingabeoptionen zeigt, bei denen die Boolesche Funktion $1$ ausgibt:
- die erste und die Letze Eingabe sind $1$
- die letzten beiden Eingabe sind $1$

---
# 3. DNF - Disjunktive Normalform und KNF - Konjunktive Normalform


---
# 4. DAG - Directed Acyclic Graph

---

# 5. OBDD - Ordered Binary Decision Diagram
