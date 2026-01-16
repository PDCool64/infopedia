---
tags:
  - TI
status: rot
---
---

>[!def] Funktional Vollständig
>Ein System, d.h. eine [[Mengen|Menge]] an [[Boolesche Algebra#Grundlegende Verknüpfungen|]]Logischen Operatoren sowie ggfs. Konstanten, ist funktional vollständig, wenn sich *alle* [[Schaltfunktionen und Boolesche Funktionen#Boolesche Funktionen|booleschen Funktionen]] mit ihm darstellen lassen. D.h. wenn sich jede beliebige Wahrheitstabelle ausdrücken lässt.
>
>---
>Man beweist, das ein System funktional vollständig ist, indem man in ihm die Operatoren eines anderen Systems, von dem Bekannt ist, dass es funktional vollständig ist, "nachbaut".
>
>Durch die Existenz von [[DNF und KNF - Disjunktive und Konjunktive Normalform|DNF und KNF]] - welche [[DNF und KNF - Disjunktive und Konjunktive Normalform#Funktionale Vollständigkeit auf Grund von KNF und DNF|alle booleschen Funktionen darstellen können]] ist z.B. gegeben, dass das System $\{ \wedge,\vee,\neg \}$ funktional vollständig ist.

# Wichtige funktional vollständige Systeme
- $\{ \neg,\wedge \}$ ($\vee$ ist herleitbar: $\overline{\overline{x}\wedge\overline{y}}\iff\overline{\overline{x}}\vee\overline{\overline{y}}\iff x\vee y$)
- $\{ \neg,\vee \}$ ($\wedge$ ist herleitbar: $\overline{\overline{x}\vee\overline{y}}\iff\overline{\overline{x}}\wedge \overline{\overline{y}}\iff x\wedge y$)
- $\{ \text{NAND} \}$ (verrückt, aber es geht. s.h. [[Kapitel 02 - Boolesche Funktionen.pdf#page=25]])
- $\{ \text{NOR} \}$


----
Man widerlegt, dass ein System funktional vollständig ist, indem man zeigt, dass sich aus allen Kombinationen der enthaltenen Operatoren keine "neuen" gewinnen lassen und das Ergebnis aller Verknüpfungen nur Elemente sind, die man schon hatte.
z.B: für das System $\{ \to,1 \}$
$1\to 1=1$
$x\to 1=1$
$1\to x=x$
$x\to x=1$
Man sieht: es lässt sich aus dem System sowie beliebigen Variablen nur die Konstante $1$, welche schon Teil des gegebenen Systems ist, sowie die Eingangsvariable selbst wieder erzeugen.


