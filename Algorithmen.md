---
tags:
  - DSAL
status: rot
---
---

>[!def] Algorithmus
> Ein **Algorithmus** ist eine genau definierte Handlungsvorschrift zur Lösung eines [[Probleme und Probleminstanzen|Problems]].

## Eigenschaften von Algorithmen
-  **Korrektheit (soundness):**
	  Jede Ausgabe ist korrekt (d.h., die Ausgabe ist eine Lösung für die Eingabe).
- **Vollständigkeit (completeness):**
	  Bei jeder Eingabe stoppt der Algorithmus nach endlich vielen Schritten.
- **Effizienz:**
	  Wieviel Zeit und Speicherplatz wird benötigt?
- **Eleganz (Schönheit)** 

## Effizienz von Algorithmen

### Elementare Operationen
Man wählt die für den betrachteten Effizienzaspekt maßgebenden Operationen aus. Dabei ignoriert man meist solche Operationen, die unabhängig von der Eingabelänge konstant oft ausgeführt werden.

Die Analyse hängt von der Wahl der *elementaren Operationen* ab.
Z.B sind sinnvoll gewählte elementare Operationen:
- "Vergleich zweier Zahlen" beim Sortieren von Arrays
- "Multiplikation zweier Fließkommazahlen" bei Matrixmultiplikation

Die Anzahl der elementaren Operationen sollte eine gute Abschätzung für die Anzahl der Gesamtoperationen sein.

### Zeitkomplexität
>[!def] Begriffe Algorithmuseffizienz
> $D:=$ Domain (nicht genauer definiert? Hat sie nur mündlich gesagt)
> $D_{n}:=$ Menge aller Eingaben der Länge $n$
> $T(I):=$ Für eine Eingabe $I$ benötigte Anzahl *elementarer Operationen*
> $Pr(I):=$ Wahrscheinlichkeit, dass die Eingabe $I$ auftritt


> Woher sind die Werte dieser Größen überhaupt bekannt?
> - $T(n)$: Durch Analyse des fraglichen Algorithmus
> - $Pr(I)$: Erfahrung, Vermutungen (z.B.:"Alle Eingaben treten mit gleicher Wahrscheinlichkeit auf").

>[!def] Worst-, Best- und Average-Case
> Der *Worst-Case*:
> $$
> W(n)=\max\{ T(I)\mid I\in D_{n} \}
> $$
> Der *Best-Case*:
> $$
> B(n)=\min\{ T(I)\mid I\in D_{n} \}
> $$
> Der *Average-Case*:
> $$
> A(n)= \sum_{I\in D_{n}}Pr(I)\cdot T(I)
> $$
> (=Erwartungswert =gewichteter Durchschnitt)
i

### Konstante Faktoren
Technologie, z.B. ein Rechner der jede Multiplikation 50% schneller durchführen kann, führt nur zur Verbesserung um einen Faktor, welcher über die Eingabelänge *konstant* ist.

Für genügen große Eingaben gewinnt somit *immer* der schnellere Algorithmus auf dem langsameren Rechner.