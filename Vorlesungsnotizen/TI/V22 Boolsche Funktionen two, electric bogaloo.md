---
"date:": 2025-10-15
tags:
  - TI
status: rot
Ab Folie: 7
Bis Folie:
---

---

Schreibweise:

>[!def] Kette aus Boolschen Werten
> $B^{n}$ ist eine kette aus $n$ boolschen Werten hintereinander z.b. ist $B^{2}=\{ 00,01,10,11 \}$
> 
> 


>[!def] Schaltfunktion
> Schaltfunktionen sind Funktionen, die eine Kette aus Boolschen Werten auf eine weitere abbildet ist eine **Schaltfunktion**
> $F:B^{n}\to B^m$

# Beispiele:
- Addition von zwei 16-Stelligen Dualzahlen: n=32 (zwei Zahlen gehen rein) m=16 (man bekommt eine Zahl raus)
- Multiplikation von 2x 16bit n=32=m
- Sortieren: nachschauen auf Folienupload mit Notizen
  
>[!def] Boolsche Funktion
> 
> Eine Schaltfunktion, die als Ausgabe nur einen einzelnen Bit ausgibt, heißt **Boolesche Funktion**.
> $F:B^{n}\to B^{1}$
> ---
> *Jede* Schaltfunktion lässt sich als Kette von Booleschen Funktionen berechnen.
> (z.B. Große Schaltfunktion als Tuple aus Boolschen Funktionen darstellen, die jeden Bit einzeln berrechnen)



## Beispiel
Schaltfunktion zur Verdopplung:

$F(x_{1},x_{0})=2\cdot(x_{1},x_{2})=(y_{2},y_{1},y_{0})$

![[V22 Boolsche Funktionen two 2025-10-15 12.00.02.excalidraw]]

$$\begin{align} \\
2\cdot(x_{1}x_{2})&=(y_{2},y_{1},y_{0}) \\
 \\

2\cdot (00)&=(000) \\
2\cdot (01)&=(010) \\
2\cdot (10)&=(100) \\
2\cdot (11)&=(110)
\end{align}$$
Dann kann man für jeden bit eine einzelne Boolsche Funktion aufstellen:

$y_{2}=f_{2}(x_{1},x_{0})=x_{13
$y_{1}=f_{1}(x_{1},x_{0})=x_{0}$
$y_{0}=f_{0}(x_{1},x_{0})=0$

(es sind hier jeweils eine bzw. bei y0 beide Eingaben unnötig. )fjf