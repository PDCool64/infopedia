---
"date:": 2025-10-15
tags:
  - DS
status: rot
Ab Folie: 0
Bis Folie:
---
>cool und neu war, dass die "Zusammenfassung von bestimmten wohlunterscheidbaren Objekten" von Georg Cantor, 1895 kommt

Dass diese Definition heutzutage nicht mehr perfekt ist, sieht man an der Menge alle Mengen:
	Angenommen, es gäbe eine Menge $\mathcal{M}$ aller Mengen. Dann betrachten wir
	$\mathcal{T}:=\{ M\in\mathcal{M} \mid M \not\in M \}$ (T besteht aus allen Mengen, die sich nicht selbst enthalten)
	Frage: ist $\mathcal{T} \in \mathcal{T}$ ? (Diese Frage ist ein Widerspruch)
	(Wenn man viel Zeit hat, kann man mal zur Russelschen Antinomie nachlesen.)
	
-> Man sollte einige Mengenkonstruktionen auschließen

---

Andere, auch nicht perfekte Definition
>[!def] Schöne Definition für Mengen
> 
> Das Einzige was bei Mengen am Ende zählt:
> Eine Menge ist dann gegeben, wenn klar ist was zur Menge gehört und was nicht.
> ---
> Anders formuliert:
> Eine Menge $M$ ist etwas, zu dem jedes beliebige Objekte $x$ entweder Element der Menge ist, oder nicht.


---
Mengen und Aussagenformen

- Sei $M$ eine Menge
  
  Dann ist "$x\in M$" für jedes Objekt $x$ eine Aussage.
  Anders gesagt,  "$x\in M$" ist eine Aussageform.

- Sei $A(x)$ eine Aussageform.
  Dann ist die Zusammenfassung alle $x$, für die $A(x)$ wahr, ist eine Menge.
  (Es wird verlangt, dass mitgeteilt wird, woher die Objekte $x$ kommen)

---

Schreibweisen von Teilmengen.

Mächtigkeit und Teilmengen

***Frage: wie handhabt der von der Schreibweise Teilemenge vs. echte Teilmenge?***
	Für Teilmengen, bei denen auch gleichheit erlaubt ist, verwendet er $\subseteq$ 
	Ob er für echte Teilmengen $\subset$ oder ![[V03 - Mengen 2025-10-15 15.59.14.excalidraw|50]] schreibt ist noch nicht bekannt.


## Mengen konstruieren

Schön erklärt aber bekannt: Durch Aussondern:
$\{ x\in M \mid A(x)\}$

### Neu: *Durch Abbilden*
$\{ f(x) \mid x\in M\}$

wobei $f$ eine Abbildung ist.
d.h. wir bilden aus dem Bild von $f$ eine Menge
(Müsste, je nach Wahl von $M\subseteq\text{Definitionsberreich}$ nicht immer das ganze Bild sein)

(Hier fehlt noch $N$ desshalb nochmal schauen: ![[Pasted image 20251015174350.png]] )


# besondere Mengen : Standardsymbole
![[Pasted image 20251015174419.png]]

Das ist eine schöne Tabelle, die man gute übernehmen könnte.

### Neu davon:
$\underline{n}$ ist definiert als Menge der natürlichen Zahlen ohne Null die kleiner gleich n sind.
$\underline{n}:=\{ 1,2,3,\dots,n \}$ 
$\underline{0}=\emptyset$

$\mathbb{P}:=$ Menge der Primzahlen

---

# Quantoren

Hier neu mit Aussagenformen bis Folie  11

Man kann mit den Quantoren Mengen konstruieren.

# Mengenoperationen
alles wie immer

etwas seltener gehört aber hier definiert:
- Das Kartesische Produkt
- Die Potenzmenge



