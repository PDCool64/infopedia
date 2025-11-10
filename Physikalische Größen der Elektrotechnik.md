---
tags:
  - TI
status: rot
---
---

# Elektrische Ladung
Symbol: $Q$
Einheit: $C$ (Coulomb)

### Definition
Elektronen und Protonen sind **Ladungsträger**, die jeweils den positiven oder negativen Betrag der Elementarladung tragen.

> **Elementarladung** : $e\approx 1.602 \cdot 10^{-19}C$ 

Ladung eines Elektrons: $e$
Ladung eines Protons: $-e$

Da Elektronen/Protonen für unsere Zwecke nicht gespalten werden können, ist dies die kleinste Einheit in die sich Ladung aufteilen lässt: Sie liegt somit **quantisiert** vor.
Die Ladung eines Körpers ist somit immer ein Vielfaches der Elementarladung:
$Q=e\cdot n\mid n\in \mathbb{N}$

## Entstehen der Ladung eines Körpers
Elektronen und Protonen können weder erzeugt noch vernichtet werden.
$\to$ Ladung entsteht durch Ortswechsel von Elementarladungen. (Meist den Elektronen)

In Metallgittern und anderen *Leitern* lösen sich die Elektronen leicht aus den äußeren Schalen der Atome. Es bleiben somit positiv geladen Atomrümpfe und eine Menge an beweglichen Elektronen im Kristallgitter.
![[Pasted image 20251110100429.png]]

## Coulomb-Kraft
Die Elektrische Ladung lässt sich beobachten als Kraftwirkungen zwischen Materie, die sich nicht durch die anderen Grundkräfte (Gravitation, schwache Wechselwirkung, Starke Wechselwirkung) erklären lässt.

> Körper mit gleicher Ladung stoßen sich ab.
> Körper mit ungleicher Ladung ziehen sich an.


Diese Kraft heißt **Coulomb-Kraft**
$$
\vec{F}=K \cdot \frac{Q_{1}\cdot Q_{2}}{r^{2}}\cdot \vec{r_{0}}
$$
Dabei ist:
- $\vec{F}$ der entstehende Kraftvektor an $Q_{1}$
- $Q_{1}$ und $Q_{2}$ die Ladungen der beiden Körper
- $r^{2}$ die Distanz zwischen beiden Körpern.
- $\vec{r_{0}}$ der Richtungsvektor von $Q_{0}$ zu $Q_{1}$ (Einheitsvektor)


![[Physikalische Größen der Elektrotechnik 2025-11-10 10.15.39.excalidraw]]

Hier zeigt der Kraftvektor $\vec{F}$ in die selbe Richtung wie $\vec{r_{0}}$ weil beide Körper negativ geladen sind und sich bei der Multiplikation der Ladungen somit beide negativen Vorzeichen aufheben. 
Wäre hingegen ein Vorzeichen positiv und eins negativ, würde ein Vektor entgegengesetzt zu $\vec{r_{0}}$ entstehen: Ungleiche Ladung zieht sich an.

## Folgen
Ungleichmäßig verteilte Ladungsträger suchen Ausgleich.




---
# Energie
Symbol: $W$
Einheit: $J$ (Joule)



---
# Elektrische Spannung
Symbol: $U$
Einheit: $V$ (Volt)

## Herleitung

Gedankenexperiment:
1. Verschieben von Elektronen in Ungleichgewichtszustand
2. Unterbrechen des Leiters
![[Pasted image 20251110102243.png|400]]

- Zum Verschieben von Ladungsträgern in eine ungleiche Verteilung muss [[#Energie|Arbeit/Energie]] $W$ aufgebracht werden. Dabei ist $W$ proportional zur bewegten [[#Elektrische Ladung]].
- Nach dem Unterbrechen des Leiters steht die aufgebrachte Energie nun als **potentielle Energie** (zum angestrebten [[#Folgen|Ladungsausgleich]]) zu Verfügung.

Es wird die **Spannung** definiert als:
Durch Ladungsverschiebung zur Verfügung stehende Energie, bezogen auf die Menge der verschobenen Energie.

$$U=\frac{W}{Q}$$
Man teilt durch die Menge an Ladungsträgern, um herauszufinden, wie viel _potentielle Energie pro Ladungsträger_ vorliegt.

> $U$ ist praktisch die S
