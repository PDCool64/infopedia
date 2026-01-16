---
tags:
  - TI
status: rot
---
---

Hat man eine Boolesche Funktion in Hardware aus Gattern realisiert, kann diese Hardware auch kaputt gehen. Zur Fehlerdiagnose verwendet man [[Darstellung boolescher Funktionen#4. DAG - Directed Acyclic Graph|DAGs]], die Äquivalent zum zu untersuchenden Schaltnetzt sind.

---
>Wir gehen hier von einem einzelnen Fehler aus, der darin besteht das ein Draht zwischen zwei Gattern/zwei Knoten im DAG "reißt" und entweder "Stuck At Zero" oder "Stuck at One" ist - d.h. eine konstante Ausgabe von 0 der 1 liefert. Hier wird nur der "Stuck at One" Fehler explizit besprochen - für einen Stuck at Zero Fehler müsste man seine Fehlermatrix komplett neu aufstellen.

---
Gegeben sie folgender DAG:
![[Pasted image 20251030104018.png]]

# Aufstellung der neuen Booleschen Funktionen für jeden gerissenen Draht.
durch logisches Schlussfolgern und anzeichnen am Graph erhält man für jeden defekten Draht eine neue Boolesche Funktion, die das Verhalten des Graphen beim jeweiligen Fehler wiedergibt.

![[Pasted image 20251030104226.png]]

# Ausfallmatrix
Stellt man all diese Funktionen als Tabelle dar, sieht man für jede Eingabemöglichkeit wie der jeweilige Fehler sich verhalten würde.
![[Pasted image 20251030104433.png]]

# Zusammenfassen zu Fehlerklassen
Viele Drähte werden ein und die selbe boolesche Funktion erzeugen - d.h. ihr Fehler äußert sich auf genau die gleiche Art und Weise. Man fasst alle identischen Funktionen zu jeweils einer Fehlerklasse zusammen.

> Wenn man genau rausfinden will, welche Fehler innerhalb einer Fehlerklasse vorliegt, kommt man nur mit dem Anlegen verschiedener Eingaben und dem vergleichen der Ausgabe nicht weiter. Dann muss man wirklich die Hardware selbst inspizieren - *weiß aber schonmal, welche Drähte überhaupt in Frage kommen*.

Reduzierte Ausfallmatrix:
![[Pasted image 20251030104456.png]]

# Bilden einer Fehlermatrix.
bildet man von jeder Spalte der Ausfallmatrix das $\text{xor}$ mit dem gewünschten Verhalten, erhält man eine Tabelle die genau dann 1 ist, wenn sich die jeweilige Fehlerklasse für diese Eingabe vom gewünschten Verhalten von $f$ unterscheidet. Man kann in den Zeilen außerdem direkt ablesen, welche Fehlerklassen sich durch welche Eingabekombinationen unterscheiden lassen und so durch das Testen mehrerer Kombinationen schnell auf eine einzelne Fehlerklasse schließen.
![[Pasted image 20251030104939.png]]