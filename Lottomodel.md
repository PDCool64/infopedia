---
tags:
  - DS
status: rot
---
---


Wie groß ist die Wahrscheinlichkeit, das man beim Lotto "6 aus 49" mit einem abgegebenen Tipp genau 4 Richtige erzielt?

Insgesamt sind $\binom{49}{6}=139\,836\,816$ Tipps möglich. ([[Kombinatorik#^78a8a9|Binomialkoeffizient]])

![[Lottomodell 2025-07-20 15.47.57.excalidraw - Kopie]]

Ein für $E=\text{"vier Richtige"}$ günstiger Tipp besteht aus **$4$ Gewinnkugeln** und **$2$ Nieten**.

4 von 6 Gewinnkugeln hat $\binom{6}{4}$ Möglichkeiten.
2 von 43 Nieten hat $\binom{43}{2}$ Möglichkeiten.

$$\to\quad \binom{6}{4}\cdot\binom{42}{2} \quad\text{Kombinationen für einen günstigen Tipp}$$

$$\to\quad P(\text{"4 Richtige"})=\frac{\text{günstige Tipps}}{\text{mögliche Tipps}}=\frac{\binom{6}{4}\cdot\binom{43}{2}}{\binom{49}{6}}\approx 0,001$$





