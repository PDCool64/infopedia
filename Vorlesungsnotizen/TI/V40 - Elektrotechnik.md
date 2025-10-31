---
date: 2025-10-28
tags:
  - TI
status: rot
Vorlesungsfolien: "[[Kapitel 04 - EtechnGrundlagen.pdf]]"
Skriptfolien:
---
---

Einheit einer Größe:
- Sei U die Elektrische Spannung (eine Physikalische Größe)
- Dann ist $[U]=V$ (Volt) die Einheit der Größe
# Elektrische Ladung
Wir fangen hier mit der Elektrischen Ladung als Basis für die E-Technik an.

 In unserem Modell können wir Elektronen und Protonen weder erzeugen noch vernichten.
 $\to$ Ladung von Körpern entstehen durch Ortswechseln von Elementarladung

Es genügt hier, die Verschiebung von Elektronen zu betrachten, z.B. in metallischen Leitern, wo die Atome ein Kristallgitter bilden, in dem sich Elektronen frei bewegen können.

Die elektrische Ladung eines Körpers ist quantisiert. Sie ist immer ein Vielfaches der Elementarladung $e$ : $$
Q=n\cdot e\;,\;n\in \mathbb{N}
$$ 
>[!def] Coulomb Kraft
> Körper mit gleicher Ladung stoßen sich ab. 
> Ungleich geladene Körper ziehen sich an.
>$$\vec{F}=K\cdot \frac{Q_{1}\cdot Q_{2}}{r^{2}}\cdot \vec{r_{0}}$$
>---
>$r$ als Distanz, $Q_{1}$ und $Q_{2}$ als Ladung der Körper , $K$ ist eine Konstante. $\vec{r_{0}}$ ist der Richtungsvektor zwischen den beiden Körpern.

> Arbeit/Energie hat als Einheit den Buchstabe $\text{W}$.
> Die Einheit der Energie ist Joule $[\text{W}]=\text{J}$
>

$U=\frac{W}{Q}$

Spannung ist die Menge an Potentialenergie die zur Verfügung steht relativ zur Anzahl der Elektronen die dafür verantwortlich sind.

Spannung wirkt zwischen zwei Punkten eines Schaltkreises

In der Regel gibt man die Spannung eines Punktes $p$ in einem Schaltkreis immer in Bezug auf einen *festen* Nullpunkt an.
Man spricht dann auch vom Potential des Punktes $p$


Die Stromstärke $I$ ist die Menge der bewegten Ladungen pro Zeiteinheit.
$$
I=\frac{\Delta Q}{\Delta t}
$$

Die Einheit der Stromstärke $[I]=A$ für "Ampere"

Ein Ampere ist Ein Coulomb pro Sekunde.
$$
1A = \frac{1C}{1s}
$$


Elektrischer Widerstand $R$ 

$[R]=\Omega$ für "Ohm"

$$
1\Omega = \frac{1V}{1A}
$$
>[!def] Ohmsches Gesetz
> 
> Der durch einen Widerstand $R$ fließende Strom $I$ wächst linear mit dem Wert der am Widerstand abfallenden Spannung.
> 
> $$U=R\cdot I$$
> 
