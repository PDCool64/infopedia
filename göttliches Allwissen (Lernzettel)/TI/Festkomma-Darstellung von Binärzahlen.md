---
tags:
  - TI
  - PROGRA
status: rot
---
---

>[!def] Festkomma-Darstellung
>In der **Festkomma-Darstellung** werden Kommazahlen im Binärsystem mit einer *festen* Anzahl an Stellen vor und nachdem Komma gespeichert.
>
>---
>
>Die Stellen ***vor*** dem Komma werden ganz normal wie bei natürlichen Zahlen behandelt.
>Sei vor dem Komma ein $n$-Bit Wort $(z_{n-1},\dots,z_{0})$) dann ist die Zahl vor dem Komma: $$z=\sum_{i=0}^{n-1}z_{i}\cdot {2}^{i}$$
>
>Die Stellen ***nach*** dem Komma werden hingegen nicht als Potenten  $2^{i}$ interpretiert sondern als$\frac{1}{2^{n}}$ bzw. $2^{-i}$. Sei hinter dem Komma ein $n$-Bit Wort $(z_{1},\dots,z_{n})$:
>$$z=\sum_{i=1}^{n}z_{i}\cdot 2^{-i}$$
>
>Fügt man beides Zusammen, steht die Bitfolge $(z_{n-1},\dots,x_{1},x_{0},x_{-1},\dots,x_{-m})$ , bei der das Komma *zwischen $x_{0}$ und $x_{1}$ liegt*, die folgende Zahl dar: $$z=\sum_{i=-m}^{n-1}x_{i}2^{i}$$

## Anschaulich:
![[Festkomma-Darstellung von Binärzahlen 2025-10-19 13.46.24.excalidraw|600]]

``0110.1101`` ist also: $4+2+\frac{1}{2}+\frac{1}{4}+\frac{1}{16}=6\text{,}8125$

# Umrechnung Dezimalzahl $\to$ Festkommazahl:
