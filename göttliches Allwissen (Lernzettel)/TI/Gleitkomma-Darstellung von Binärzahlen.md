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
> Die im Speicher stehenden Werte werden mit Dach $\hat{}$  geschrieben: $\hat{s},\hat{e},\hat{m}$
> Die zur Berechnung von $z=s\cdot m\cdot b^{e}$ verwendeten werte werden ohne Dach geschrieben

Die Daten werden in drei Feldern gespeichert: 
- Vorzeichen $\hat{s}$ : $1$-Bit am Anfang
- Exponent $\hat{e}$ : $k$-Bit in der Mitte
- Mantisse $\hat{m}$ : $n$-Bit am Ende

Bei $32$-Bit haben wir $k=8$ und $n=23$
Bei $64$-Bit haben wir $k=11$ und $n=52$

Aufteilung bei $32$-Bit:
![[Pasted image 20251019170832.png]]
# Fallunterscheidungen:

![[Gleitkomma-Darstellung von Binärzahlen 2025-10-19 17.08.48.excalidraw|900]]
