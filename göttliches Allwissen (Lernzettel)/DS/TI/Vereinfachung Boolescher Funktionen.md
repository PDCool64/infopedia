---
tags:
  - TI
status: rot
---
---
Warum vereinfachen: Will ich eine [[Schaltfunktionen und Boolesche Funktionen#Boolesche Funktionen|Boolesche Funktion]] in Hardware realisieren, ist es günstiger/effizienter/kleiner/schneller/effizienter Weniger Gatter = Verknüpfungen zu brauchen.

---
In diesem Dokument wird fast ausschließlich die Vereinfachung von [[DNF und KNF - Disjunktive und Konjunktive Normalform#Disjunktive Normalform - DNF|disjunktiven Formen]] thematisiert. Prinzipiell ist all dies aber auch mit Konjunktiven Formen möglich wenn man sich der Verneinungen bewusst ist. Beispielsweise kann man im KV Diagram auch Boxen um die Nullen malen und für jede Box einen Maxterm aus den negierten Variablen aufstellen.

---

>[!def] Resolutionsregel
> Dieses ganze Kapitel basiert fasst komplett auf der **Resolutionsregel**
> $$
> ab+\bar{a}b=a(b+\bar{b})=a1=a
> $$
> $$(a+b)(a+\bar{b})=(a+1)(a+0)=a+0=a$$
> 
>---
>Die ganzen Varianten wie Karnaugh-Diagramme oder OBDDs zu vereinfachen sind einfach systematische/übersichtliche Weisen die Resolutionsregel anzuwenden.

## Wichtige Begriffe
>[!def] Implikanten
> Sei $f:B^{n}\to B$ eine [[Schaltfunktionen und Boolesche Funktionen#Boolesche Funktionen|Boolesche Funktion]]. Ein Term $M\neq 0$ heißt **Implikant** von $f$, kurz $M\le f$, falls $M(x)\le f(x)$ für alle $x\in B^{n}$ gilt, d.h.
> $$
> M(x)=1\implies f(x)=1 \;\forall x\in B^{n}
> $$
> 
> Ein Implikant $M$ von $f$ heißt **Primimplikant** (von $f$), falls keine echte Verkürzung von $M$ noch Implikant von $f$ ist.
> 
> Ein Primimplikant $M$ heißt **Kernimplikant** (von $f$), falls $M$ in jedem Minimalpolynom von $f$ vorkommt.

- Jeder [[DNF und KNF - Disjunktive und Konjunktive Normalform#^0681ec|Minterm]] der [[DNF und KNF - Disjunktive und Konjunktive Normalform#Disjunktive Normalform - DNF|DNF]] ist ein Primimplikant. Jeder Block im KV-Diagramm ist Primimplikant.
- Beispielsweise sind in einem KV Diagramm solche Blöcke, die man nicht auf verschiedene Arten und Weisen, sondern nur durch eine einzelne Form, abdecken kann, Kernimplikanten.
- Die Vereinfachung von Booleschen Funktionen ist die Suche nach einer Menge von Primimplikanten, die die gegebene Funktion vollständig abdecken. 

>[!def] Minimalpolynom
> 
> M Minimalpolynom für $f$ wenn es kein Polynom geringerer Länge für $f$ gibt.
> (Polynome = Summe aus Produkten = DNF)
> 

- es kann für eine boolesche Funktion mehrere Minimalpolynome von gleicher Länge geben. (s.h. Uneindeutigkeit bei der Blockwahl im KV-Diagramm oder Uneindeutigkeit bei der Auswahl aus den Primimplikanten beim Quine-McCluskey-Verfahren, Uneindeutigkeit bei der Wahl der Variablenordnung eines OBDD)

---
# Resolutionsregel direkt auf [[DNF und KNF - Disjunktive und Konjunktive Normalform|KNF und DNF]] anwenden.
Danach kann man auch mit den anderen Rechengesetzten der Logik oft noch ausklammern, oft sind aber Disjunkte oder Konjunktive Formen gefordert, weil für diese die Hardware existiert.

---
# Karnaugh-Veich-Diagramme
An den Achsen werden die Variablen nach dem [[Gray-Code]] aufgetragen, weil sie sich so von Zeile zu Zeile und Spalte zu Spalte nur um genau eine Variable unterscheiden und die restlichen gleich bleiben - es lässt sich somit perfekt die Resolutionsregel anwenden.

Man kann an jedem Block also ablesen, welche Variablen in ihm "egal" sind

- Die Blöcke dürfen nur Einsen enthalten
- Die Kantenlängen der Blöcke müssen Zweierpotenzen sein
- Die Blöcke müssen maximale Größe haben
- Blöcke dürfen sich überlappen.
- Blöcke können/müssen auch um die Kanten der Tabelle gebildet werden
  
![[Pasted image 20251021194958.png]]

![[Pasted image 20251021194958.png]]

![[Pasted image 20251030100340.png]]
![[Pasted image 20251030100345.png]]

## Don't Cares:

Beispiel ist, eine BCD-Zahl auf einer 7-Segment Anzeige darzustellen.
Dann macht man boolesche Funktionen, die aus den 4Bit der BCD entscheidet, ob das Feld an sein muss oder nicht. im BCD mit  $2^{4}=16$ Optionen werden aber 6 nicht genutzt - Man kann diese also ignorieren.

An einem Karnaugh-Diagramm
- Alle Einsen abdecken MÜSSEN
- Ds abdecken DÜRFEN
![[Pasted image 20251027151817.png]]


---
# Mit einen OBDD

## Verjüngungsregel / 4-3 Regel
![[Pasted image 20251021194039.png]]

## Eliminationsregel / 2-3 Regel:
![[Pasted image 20251021194145.png]]

Zur bestmöglichen Vereinfachung, muss man beide Regeln so oft anwenden, bis man in einem Zustand ankommt, in dem keine der beiden mehr Anwendbar ist.
Dadurch, dass man die eine Regel anwendet, kann ein Zustand entstehen, der die Anwendung der anderen Regel ermöglicht.

> Für eine gegebene Variablenordnung landet man immer bei dem gleichen Ergebnis - Je nach Variablenordnung landet man aber nicht immer beim gleichen Ergebnis, d.h. auch nicht immer beim Minimalpolynom

## Konvertierung zurück:
Hat man den OBDD nach den beiden obigen Regeln vereinfacht, dann kann man aus dem vereinfachten OBDD schnell eine DNF / KNF erhalten.

aber: Die Anzahl an Knoten im OBDD ist nicht immer "proportional" zur Länge von KNF

*Die durch Vereinfachung des OBDD erreichte KNF/DNF ist nicht zwangsweise ein Minimalpolynom*. Es kann sein, dass man danach noch mit Logikgesetzen weitermachen muss.


---
# Quine-McCluskey-Verfahren
Die anderen beiden Methoden sind sehr schön für Menschen auf Papier, umsetzbar weil sie schön graphisch sind. Für einen Computer sind sie aber eher ungeeignet.
Besser ist hier das Quine-McCluskey-Verfahren.

In diesem Verfahren sortiert man die Minterme zuerst in Gruppen, welch die Anzahl der negierten Literale im Minterm angeben. Minterme, die sich laut Resolutionsregel miteinander kürzen lassen sind somit immer in benachbarten Gruppen, denn sonst würden sie sich um mindestens zwei Literale unterscheiden.

Jetzt geht man einfach stumpf für jeden Minterm alle Minterme in den benachbarten Gruppen durch und testet, ob man diese vereinfachen kann.

Nach einer solchen Runde hat man eine neue Menge von Mintermen, die man wieder nach der Anzahl der verneinten Literale sortieren kann. Man sucht jetzt erneut in benachbarten Gruppen nach Optionen zu kürzen. Man muss nun aber aufpassen, weil nicht alle Minterme die gleichen Variablen mehr enthalten - mal ist $x_{1}$ gekürzt worden, mal $x_{2}$ usw.

![[Pasted image 20251030102829.png]]
![[Pasted image 20251030102839.png]]

Hat man nun eine Menge von Primimplikanten (die zusammen sicher die gesamte Funktion abdecken, weil die Resolutionsregel gilt), versucht man aus diesen eine möglichst kleine Teilmenge zu nehmen, die dies immernoch tut. Dies ist aber algorithmisch schwierig und meist werden Kompromisse wie Greedy-Algorithmen verwendet:
![[Pasted image 20251030102853.png]]
(Kernimplikant, weil dieser Primimplikant als *einziger* den einschlägigen Index 6 erzeugt.)

Eine mögliche Wahl für eine Menge an Primimplikanten (inklusive dem obigen Kernimplikanten), welche recht knapp alle einschlägigen Indizes abdeckt:
![[Pasted image 20251030103103.png]]