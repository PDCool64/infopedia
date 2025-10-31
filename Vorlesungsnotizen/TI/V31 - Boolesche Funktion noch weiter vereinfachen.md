---
date: 2025-10-27
tags:
  - TI
status: gelb
Vorlesungsfolien: "[[Kapitel 3 - Vereinfachung Boolescher Funktionen.pdf]]"
Skriptfolien:
---
---
# Vereinfachung mit Karnaugh-Diagrammen
- Die Blöcke dürfen nur Einsen enthalten
-  Die Kantenlängen der Blöcke müssen Zweierpotenzen sein
- Die Blöcke müssen maximale Größe haben


![[Pasted image 20251021194958.png]]

Die Reihenfolge wie die Variablen hier aufgetragen wird, ist der Gray-Code - damit haben Benachbarte Zellen immer genau eine Variable Unterschied und die Idee "redundante variablen" mit Resolutionsregel funktioniert überhaupt erst. - Zwei benachbarte Zellen kodieren Somit Minterem, die sich in nur  *einem* Minterm unterscheiden und man kann die Resolutionsregel anwenden.

Hat man dann zwei Zweierblöcke, unterscheiden die sich wieder nur von der Zeile/Spalte her um einen Minterm - man kann sie also wieder zusammenfügen.



> (In der Prüfung kann bis zu 5 Variablen vorkommen) -> GrayCode lernen


Man sieht: Blöcke dürfen sich überlappen.

> Fand die Erklärung von Herr Teuschler viel schöner. Sollte nochmal in 1note suchen

Man kann eigentlich einfach pro Block eine oder mehrere Variablen ablesen, die für diesen Block *egal* sind - je größer der Block desto mehr variablen sind für ihn egal.

d.h. in dem Blauen Block oben links sind x1 und x3 egal. (s.h. PXL FOto)


Um die Kanten herum, d.h. beim Überlauf im Gray-Code unterscheidet sich ebenfalls nur eine Variable - mann kann/muss also auch über die kanten hinaus malen.
![[Pasted image 20251027150028.png]]![[Pasted image 20251027150124.png]]

---

# Implikant

>[!def]
> Ein Term, der die Funktion impliziert.
> (Implikation, keine Äquivalenz. Wenn der Implikant falsch ist, sagt dies nichts über den Wert der Funktion aus.)
> 

Minterme sind z.b. Implikanten
Die Blöcke im Karnaugh-Diagramm sind Implikanten.

Vereinfachung einer Booleschen Funktion:
	Die Suche nach einer Menge an möglichst kleinen Implikanten, die die Boolesche Funktion vollständig "abdecken" oder so

>[!def] Primimplikant
> 
> Primimplikant ist ein Implikant von $f$, falls keine echte Verkürzung von $M$ noch Implikant von $f$ ist.

Unser Ziel: Primimplikanten finden.


>[!def]
> Kernimplikant $M$ von $f$ falls $M$ in jedem Minimalpolynom von $f$ vorkommt.
> (Es kann mehrere gleichlange Polynome von minimaler Länge geben, die alle Minimalpolynom ist)

![[Pasted image 20251027151209.png]]
Die Vertikale Box ist *kein* Kernimplikant, weil sie nicht für das Minimalpolynom notwendig ist - man kann alle Einsen auch ohne sie abdecken d.h. es gibt ein Minimalpolynom, in dem die Box nicht drin ist.

---
# Ausnutzung von Don't Cares

Beispiel ist, eine BCD-Zahl auf einer 7-Segment Anzeige darzustellen.
Dann macht man boolesche Funktionen, die aus den 4Bit der BCD entscheidet, ob das Feld an sein muss oder nicht. im BCD mit  $2^{4}=16$ Optionen werden aber 6 nicht genutzt - Man kann diese also ignorieren.

An einem Karnaugh-Diagramm
- Alle Einsen abdecken MÜSSEN
- Ds abdecken DÜRFEN

![[Pasted image 20251027151817.png]]



---

# Quine-McCluskey-Verfahren
Karnaugh-Diagramm ist von Hand zwar ganz schön - das einem Computer beizubringen ist aber nicht so einfach (Datenstruktur; Nachbarschaft; ....)



Gruppe gibt die Anzahl der Negationen der Minterme an.

Minterme, die sich laut Resolutionsregel vereinfachen lassen sind immer in benachbarten Gruppen - weil sie sich in nur einem Minterm unterscheiden.

Man muss also um alle Resolutionen für einen Term zu finden immer nur mit den Mintermen in den benachbarten Gruppen vergleichen.

Bsp. s.h. PXL foto

Nach einer Runde an Anwendungen kann man dann eine neue Tabelle aufschreiben.

> Wir haben einfach nur alle möglichen Resolutionen systematisch nach einander durchgeführt.


Das Quine-McCluskey-Verfahren liefert *sicher* die Menge der Primimplikanten.
> Indexschalter sind die Einschlägigen Indizes die jeweils dargestellt werden

Will man daraus dann ein Minimalpolynom erstellen, muss man sich die Primimplikanten so zusammensuchen, dass jeder Einschlägige Index abgedeckt ist. Man sucht dann eine möglichst kleine Menge der Primimplikanten zu finden, welche alle einschlägigen Indizes abdeckt. 
(Man findet/sucht die Kernimplikanten)
![[V31 - Boolesche Funktion noch weiter vereinfachen 2025-10-27 15.35.55.excalidraw]]
(hier sind alle Kernimplikanten - man braucht alle)

Hier auch ein Beispiel, bei dem man nicht alle braucht - hier eine kleinstmögliche Menge zu finden ist schon schwieriger.

![[Pasted image 20251027153704.png]]
(Alle Optionen ausprobieren. Besser: versuchen zuerst möglichst restriktive Implikaten mitzunehmen. Greedy Algorithmus und so)

Bei der verkleinerten Tabelle hat man schon alle Kernimplikanten (die man braucht, weil keiner eine seiner Spalten/ einen seiner einschlägigen Indizes) sowie die Spalten, die sie eh schon erzeugen weggelassen. Dann muss man nurnoch aus den Primimplikanten aussuchen um den Rest abzudecken:
![[Pasted image 20251027154122.png]]


Im KV-Diagramm sind Kernimplikanten genau die Boxen, die man *immer* auf diese eine art un weise Wahlen muss:
![[Pasted image 20251027154341.png]]


---
> Mann kann *all* diesen Kram auch mit KNF machen und Boxen um die Nullen drumherum malen. S.h. PXL Foto. Machen wir üblicherweise nicht (ob es in der Klausur drankommt? kp)

---
Sidenote: Wenn man zu viel Zeit hat:

Die Schaltfunktion x2 x1 x0 -> negx2 negx1 negx0 bauen, aber nur genau 2 Nicht Gatter verwenden (beliebig viele ODER und UND)
Minimallösung hat 18Gatter. Händische Lösung vom Prof hat 30.

