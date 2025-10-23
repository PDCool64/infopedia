---
tags:
  - TI
status: rot
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

^0681ec

>[!def] Disjunktive Normalform
> Jede [[Schaltfunktionen und Boolesche Funktionen#Boolesche Funktionen|Boolesche Funktion]] $f:B^{n}\to B$ ist *eindeutig* darstellbar als **Summe der [[#^0681ec|Minterme]] ihrer [[Darstellung boolescher Funktionen#^bbd58f|einschlägigen Indizes]]. 
> 
> D.h. ist $I\subseteq \{ 0,\dots,2^{n}-1 \}$ die Menge der [[Darstellung boolescher Funktionen#^bbd58f|einschlägigen Indizes]] von $f$, so gilt: $$f=\sum_{i\in I}m_{i}$$
> bzw. ausgeschrieben:$$f=m_{2^{n}-1}\;\vee\; \dots \;\vee\;m_{0}$$

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

