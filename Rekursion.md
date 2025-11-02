---
tags:
  - AFI
status: rot
---
---
>[!def] Rekursion
> Es sei $M$ eine nicht-leere [[Mengen|Menge]]. Für jedes $n\in \mathbb{N}$ sei $g_{n}:M\to M$ eine [[Abbildungen|Abbildung]]. Weiter sei $b\in M$.
> Dann gibt es *genau eine* Abbildung $r:\mathbb{N}\to M$ mit den Eigenschaften
> - $r(1)=b$
> - $r(n+1)=g_{n}(r(n))$
> 

$r$ ist hier die Abbildung, die dem "Anwender" letztendlich für jede natürliche Zahl $n$ als Eingabe, das Ergebnis nach $n$ Rekursionsschritten gibt.

$g_{n}$ hingegen ist die Abbildung, welche den Rekursionsschritt selbst definiert, d.h. definiert wie genau man für diese speziellen Sachverhalt vom $n$-ten auf den $n+1$-ten Wert kommt.

---
# Rekursion für [[Summenzeichen und Produktzeichen]]