---
tags:
  - TI
status: gelb
---
---
Die [[#Disjunktive Normalform - DNF]] als auch die [[#Konjunktive Normalform - KNF]] sind zwei standardisierte Schreibweisen für [[Schaltfunktionen und Boolesche Funktionen#Boolesche Funktionen|Boolesche Funktionen]]. Es handelt sich jeweils um [[Boolesche Algebra|Boolesche Aussagen]].

---
## Zur Erinnerung:
- $\text{ODER}$ = $\vee$ = $+$ = **[[Boolesche Algebra#Die binären Verknüpfungen *oder* und *und*|Disjunktion]]**
- $\text{UND}$ = $\wedge$ = $\cdot$ = **[[Boolesche Algebra#Die binären Verknüpfungen *oder* und *und*|Konjunktion]]**. Der Malpunkt wird, wie bei der Multiplikation von Zahlen, oft nicht geschrieben.

>[!def] Literal
> 
> **Literale** sind [[Boolesche Algebra|Boolesche Aussagen]] oder Verneinungen solcher.
> Z.B. sind sowohl $x$ als auch $\overline{x}$ beides Literale.

^bc6c85

# Disjunktive Normalform - DNF
>[!def] Minterm
> 
> Ein **Minterm** eine Anzahl von [[#^bc6c85|Literalen]], die alle durch ein $\text{UND}$, d.h. durch die Konjunktion "$\wedge$" bzw. "$\,\cdot\,$", verknüpft sind.
> 
> ---
> $x_{2}\wedge x_{1}\wedge\overline{x_{0}}$ oder $a_{3}\,\overline{a_{2}}\,a_{1}\,\overline{a_{0}}$ sind z.B. Minterme.
> 
> ---
> Minterme schreib man mit einem kleinen $m$.
> Der Minterm der $i$-ten Zeile der Wahrheitstabelle der [[Schaltfunktionen und Boolesche Funktionen#Boolesche Funktionen|Booleschen Funktion]] $f$ heißt "$i-ter$ Minterm von $f$"
> 
> Es gilt: Sei $M_{i}$ der $i$-te [[#^4b83d3|Maxterm]] von $f$, dann ist $m_{i}=\overline{M_{i}}$ der $i$-te Minterm von $f$. (und umgekehrt)


^0681ec

>[!def] Disjunktive Normalform
> Jede [[Schaltfunktionen und Boolesche Funktionen#Boolesche Funktionen|Boolesche Funktion]] $f:B^{n}\to B$ ist *eindeutig* darstellbar als **Summe der [[#^0681ec|Minterme]] ihrer [[Darstellung boolescher Funktionen#^bbd58f|einschlägigen Indizes]]. 
> 
> D.h. ist $I\subseteq \{ 0,\dots,2^{n}-1 \}$ die Menge der [[Darstellung boolescher Funktionen#^bbd58f|einschlägigen Indizes]] von $f$, so gilt: $$f=\sum_{i\in I}m_{i}$$
> bzw. ausgeschrieben:$$f=m_a\;\vee\; \dots \;\vee\;m_b$$

## Intuitiv und viel offensichtlicher:

![[DNF und KNF - Disjunktive und Konjunktive Normalform 2025-10-23 19.55.33.excalidraw|600]]

Man sieht: Jeder [[#^0681ec|Minterm]] stellt genau eine der "einschlägigen", d.h. zu $1$ führenden Optionen dar.
Durch die *Disjunktion* dieser Optionen erhält man alle möglichen Wege, die zu einer $1$ führen.

---
# Konjunktive Normalform - KNF
>[!def] Maxterm
> 
> Ein **Maxterm** eine Anzahl von [[#^bc6c85|Literalen]], die alle durch ein $\text{ODER}$, d.h. durch die Konjunktion "$\vee$" bzw. "$\,+\,$", verknüpft sind.
> 
> ---
> $x_{2}\vee x_{1}\vee\overline{x_{0}}$ oder $a_{3}+\overline{a_{2}}+a_{1}+\overline{a_{0}}$ sind z.B. Maxterme.
> 
> ---
> Maxterme schreib man mit einem großen $M$.
> Der Maxterme der $i$-ten Zeile der Wahrheitstabelle der [[Schaltfunktionen und Boolesche Funktionen#Boolesche Funktionen|Booleschen Funktion]] $f$ heißt "$i-ter$ Maxterm von $f$"
> 
> Es gilt: Sei $m_{i}$ der $i$-te [[#^0681ec|Minterm]] von $f$, dann ist $M_{i}=\overline{m_{i}}$ der $i$-te Maxterm von $f$. (und umgekehrt)

^4b83d3


>[!def] Konjunktive Normalform
> Jede [[Schaltfunktionen und Boolesche Funktionen#Boolesche Funktionen|Boolesche Funktion]] $f:B^{n}\to B$ ist *eindeutig* darstellbar als **Produkt der [[#^0681ec|Minterme]] ihrer *NICHT*-einschlägigen Indizes**. 
> 
> D.h. ist $I\subseteq \{ 0,\dots,2^{n}-1 \}$ die Menge der [[Darstellung boolescher Funktionen#^bbd58f|NICHT-einschlägigen Indizes]] von $f$, so gilt: $$f=\prod_{i\in I}M_{i}$$
> bzw. ausgeschrieben:$$f=M_a\;\wedge\; \dots \;\wedge\;M_b$$

## Intuitiv und viel offensichtlicher
![[DNF und KNF - Disjunktive und Konjunktive Normalform 2025-10-23 20.27.08.excalidraw|600]]


---


---
# [[Funktionale Vollständigkeit]] auf Grund von KNF und DNF.

Wie oben gezeigt, lässt sich für *jede* beliebige [[Schaltfunktionen und Boolesche Funktionen#Boolesche Funktionen|Boolesche Funktion]] eine DNF und keine KNF aufstellen, welche die Funktion genau widergeben. Da sowohl DNF als auch KNF nur aus den Verknüpfungen $\vee,\wedge,\neg$ bestehen, lassen sich also *alle* Booleschen Funktionen nur mit diesen drei Verknüpfungen darstellen. 
Man sagt: 
	Das System $\{ \vee,\wedge,\neg \}$ ist **[[Funktionale Vollständigkeit|funktional vollständig]]**.


---
# Umstellen Maxterme vs. Minterme

## Minterme -> Maxterme
Hier sind genau die Maxterme richtig deren Negation mit *keinem* der gegebenen Minterme übereinstimmt.

z. B wird (2)= $x_{3}+x_{2}+\overline{x_{1}}+x_{0}$ invertiert zu $\overline{x_{3}}\overline{x_{2}}x_{1}\overline{x_{0}}$ , was von keinem der Minterme gedeckt wird.


![[Pasted image 20251025104516.png]]