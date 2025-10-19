---
tags:
  - TI
  - PROGRA
status: rot
---
---

>[!def] Gleitkomma-Darstellung
>Die **Gleitkomma** Darstellung ist eine *approximative* Darstellung [[Zahlenräume#Reelle Zahlen $ mathbb{R}$|reeller]] bzw. [[Zahlenräume#Rationale Zahlen $ mathbb{Q}$|rationaler]] Zahlen.
>
>Jede Zahl $z$ wird in der Form $$z=\pm m\cdot b^{\pm e}$$
>dargestellt, wobei wir $m$ **Mantisse**. $e$ **Exponenten** und $b$ **Basis nennen**.
>---
>
>Da rechnerintern im [[Binärsystem]] gearbeitet wird, ist die Basis $b=2$.
>
>---
>*Nicht alle Zahlen in Bereich können exakt dargestellt werden*
>
>---

Die Gleitkomma Darstellung versucht, bei gleicher Anzahl an Speicherbits einen deutlich größeren Zahlenbereich als die [[Festkomma-Darstellung von Binärzahlen]] zu erreichen.

Die Funktionsweise der heute angewendeten Gleitkomma-Formate wurde in der Norm [*IEEE 754*](https://de.wikipedia.org/wiki/IEEE_754) vom *Institute of Electrical and Electronics Engineers* festgelegt

Je nach gewünschter Präzision und Zahlenbereich sowie Speicherlimitierungen gibt es verschiedene Versionen/Größen von Gleitkommaformaten. Häufig sind:
- 16-Bit
- 32-Bit (aka. ``single``)
- 64-Bit (aka. ``double``)
- 128-Bit

## Darstellung im Speicher
> Die im Speicher stehenden Werte werden mit Dach  $\hat{}$  geschrieben: $\hat{s},\hat{e},\hat{m}$
> Die zur Berechnung von $z=\pm m\cdot b^{\pm e}$ verwendeten Werte werden ohne Dach geschrieben.

Die Daten werden in drei Feldern gespeichert: 
- Vorzeichen $\hat{s}$ : $1$-Bit am Anfang
	  ist $\hat{s}=0$ wird die Zahl als positiv interpretiert.
	  ist $\hat{s}=1$ wird die Zahl als negativ interpretiert.
	  
- Exponent $\hat{e}$ : $k$-Bit in der Mitte
	  Der Exponent $e$ kann positiv oder negativ sein. 
	  *Gespeichert* wird aber immer nur ein *positiver* Wert $\hat{e}$, was dadurch erreicht wird, dass $e$ um einen sogenannten *bias*-Wert ins Positive verschoben wird. Man spart sich damit die Kodierung von negativen Exponenten, die sonst z.B. durch das [[Negative Binärzahlen durch Komplement - Ganze Zahlen im Binärsystem#Negative Zahlen als Zweier-Komplement|Zweier-Komplement]] umgesetzt werden müsste.
	  
	 **Wahl des *bias*-Werts:**
	 Die gespeicherten $k$-Bit-Muster $\hat{e}=(000\dots 000)$ und $\hat{e}=(111\dots 111)$ sind für spezielle Interpretationen reserviert (s.h. [[#Fallunterscheidungen]]).
	 Es verbleiben also die restlichen $k$-Bit-Muster von $(\dots0001)_{2}=1$ bis $(0111\dots)_{2}=2^{k}-1$ zur Speicherung des Exponenten. Diese sollen nun zur Hälfte genutzt werden um negative Exponenten zu speichern, während die andere Hälfte positive Exponenten speichert. 
	 Dazu verschiebt man die Exponenten um die Hälfte des in $k$-Bit darstellbaren Maximalwerts: $\frac{2^{k}-1}{2}$ , was aber das nicht ganzzahlige Ergebnis $2^{k-1}-\frac{1}{2}$ liefern würde.
	 Weil Exponenten ganzzahlig kodiert werden wählt man gerundet: $bias=2^{k-1}-1$, weil die Werte so symmetrisch um $0$ liegen.
	 
	 Es gilt also:
	 $e=\hat{e}-bias$
	 $\hat{e}=e+bias$
	 
	 **Eselsbrücke zur Verschiebungsrichtung**: 
	 Das $\hat{e}$ mit Dach ist *visuell größer* als das $e$ ohne Dach.
	 
	 $\hat{e}$ wird dann als ganz normale, positive $k$-Bit Zahl ohne Komastellen oder Sonstiges in den Speicher geschrieben.
 	  
- Mantisse $\hat{m}$ : $n$-Bit am Ende
	  Je nachdem, ob es sich um die [[#Normalisierte Darstellung]] oder die [[#Denormalisierte Darstellung]] handelt, wird die Mantisse unterschiedlich behandelt.

Bei $32$-Bit haben wir $k=8$ und $n=23$
Bei $64$-Bit haben wir $k=11$ und $n=52$

Aufteilung bei $32$-Bit:
>[!wip] Abbildung
> Die Grafik könnte man mal selbst nachbauen - dann wäre sie light/darkmode kompatibel

![[Pasted image 20251019170832.png]]
# Fallunterscheidungen:
Die meisten Zahlen werden in der [[#Normalisierte Darstellung|Normalisierten Darstellung]] gespeichert.
- Diese ermöglicht es, bei 32 Bit Zahlen mit Beträgen von $1.18\cdot 10^{-38}$ zu speichern
- $0$ selbst lässt sich so nicht speichern. sowie Zahlen sehr nah an $0$ lassen außerdem nicht sehr genau speichern.
Für die Zahlen nahe der $0$, sowie die $0$ selbst gibt es die [[#Denormalisierte Darstellung]]

Sonderfälle werden ebenfalls markiert:

![[Gleitkomma-Darstellung von Binärzahlen 2025-10-19 17.08.48.excalidraw|900]]
# Normalisierte Darstellung

## Dezimal -> Gleitkomma


## Gleitkomma -> Dezimal


# Denormalisierte Darstellung

# Sonderfälle
