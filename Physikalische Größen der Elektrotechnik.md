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
> 
> Zur Frage wie diese "Magic Number" zustande kommt: [[#Historisch gewachsen Ampere, Coulomb und Elementarladung]]

Ladung eines Elektrons: $-e$
Ladung eines Protons: $e$

Da Elektronen/Protonen für unsere Zwecke nicht gespalten werden können, ist dies die kleinste Einheit in die sich Ladung aufteilen lässt: Sie liegt somit **quantisiert** vor.
Die Ladung eines Körpers ist somit immer ein ganzes Vielfaches der Elementarladung:
$Q=e\cdot z\mid z\in \mathbb{Z}$

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

- $K$ eine vom Medium abhängige Konstante

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

$$U=\frac{W}{Q}\quad \text{bzw.} \quad V= \frac{J}{C}$$
Man teilt durch die Menge an Ladungsträgern, um herauszufinden, wie viel _potentielle Energie pro Ladungsträger_ vorliegt.

> $U$ ist praktisch der Proportionalitätsfaktor zwischen aufgebrachter Energie und Ladungsmenge in einem bestimmten System zu einem bestimmten Zeitpunkt.

Da es immer um die Energie geht, die aufgebracht werden musste um eine Ladungsungleichverteilung *zwischen zwei Orten* zu erzeugen, besteht die Spannung *relativ* zwischen zwei Punkten.
## Im Schaltkreis
- Ladung wirkt zwischen zwei Punkten im Schaltkreis
- In der Regel gibt man die Spannung eines Punktes $p$ in einem Schaltkreis in Bezug auf einen *festen Nullpunkt* an. Man spricht dann vom **Potential** des Punktes.
  Dieser Nullpunkt heißt im Schaltkreis **Masse**: Symbol ⏚ 


---
# Elektrischer Strom
Symbol: $I$
Einheit: $A$ (Ampere)

Elektrischer Strom ist die gerichtete Bewegung von Ladungsträgern.

> Die **Stromstärke** $I$ ist die Menge der bewegten Ladung pro Zeiteinheit.
$$I=\frac{\Delta Q}{\Delta t}\quad\text{bzw.}\quad 1\text{A}= \frac{1\text{C}}{1\text{s}}$$

![[Pasted image 20251110110022.png|400]]
Gedankenexperiment dazu:
- Man stelle sich an eine Stelle im Leiter und zählt, wie viele Ladungsträger pro Zeiteinheit an einem Vorbeifließen.

## Historisch gewachsen: Ampere, Coulomb und Elementarladung

Die Einheiten Ampere und Coulomb wurden definiert, noch *bevor* wir ein gutes Verständniss der Elementarteilchen hatten. Ihre Werte wurden durch Referenzversuche experimentell festgesetzt und ihre Werte eignen sich gut für menschliche Anwendungen.

Timeline:
- 1785: Coulomb stell einen Zusammenhang zwischen Ladung und Kraft fest: [Torsionswage](https://de.wikipedia.org/wiki/Drehwaage) : Zwei geladene Kugel stoßen sich ab und eine Kraft kann gemessen werden. Er **definiert aber keine Einheiten** für die Größen
  
- 1820: Oversted entdeckt: Strom erzeugt eine Magnetfeld: Kompassnadel wird von Stromdurchflossenem Draht abgelenkt. Strom wird messbar, aber ohne Einheit.
  
- 1827: Ohm formuliert das Ohm'sche Gesetz: Spannung proportional zu Strom und Widerstand. Man fängt an über die "Systematik" und den Zusammenhang zwischen den Größen Nachzudenken.
  
- 1881: Deutsches Reich: **Definition des Amperes als Basiseinheit**: Strom der in einer bestimmten Elektrolyselösung eine feste Menge an Silbernitrat pro Sekunde an der Elektrode entstehen lässt.

- 1893: Chicago Weltkongress: **Neue Definition des Ampere als Basiseinheit**: Mit einem einfachen Versuch (Zwei parallele Drähte, Strom durch sie so einstellen, dass eine bestimme elektromagnetische Kraft entsteht)
  
  Die Elektrische Ladung in Coulomb wir hingegen als **Abgeleitete Einheit** definiert durch:
  $1\text{C}=1\text{A}\cdot 1\text{s}$ 

- 1897: J.J. Thomson entdeckt das Elektron: Beginn des Verständnisses, das Ladung aus "Stückchen" besteht.


  

