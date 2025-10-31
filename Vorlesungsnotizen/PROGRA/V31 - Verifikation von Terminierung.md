---
date: 2025-10-27
tags:
  - PROGRA
status: rot
Vorlesungsfolien: "[[II14_Verifikation.pdf]]"
Skriptfolien:
---
---
# Terminierung
Finde Variante $V$m die $\ge 0$ ist, wenn die Schleife (=am Anfang jeder durchführungsrunde) ausgeführt wird, und die in jedem Schleifendurchlauf kleiner wird.

Bsp. Variante: Bei dem Fakultäts-Programm

![[V31 - Verifikation von Terminierung 2025-10-27 18.41.49.excalidraw]]

> Programmierer sollte sich zu jeder Schleife Invariante und Variante überlegen.

# Beispiel: Addition

## Partielle Korrektheit
![[V31 - Verifikation von Terminierung 2025-10-27 18.46.47.excalidraw|600]]

Wenn man schon eine Schleifeninvariante gefunden hat, dann aber merkt, dass sie noch nicht stark genug ist, um die nachbedingung zu implizieren, dann muss man sie noch ein bisschen ergänzen. Hier z.B. das $x\ge 0$ dass am Anfang der Invariante noch hinzugefügt wurde.

## Terminierung
Als Variante kann man $x$ wählen.


---
# Beispiel: Subtraktion

> Tipp: Als Schleifeninvariante kann man einfach mal mit der Nachbedingung anfangen, und diese dann so anpassen, dass sie invariant bleibt.

Partielle Korrektheit
![[V31 - Verifikation von Terminierung 2025-10-27 19.03.24.excalidraw|600]]


Terminierung: Variante ist $x-z$
- $x>z\implies x-z\ge 0$
- wird kleiner:
	  $<x-z=m \land x>z>$
	  $<x-(z+1)<m>$
	  `z=z+1;`
	  $<x-z<m>$
	  `res=res+1`
	  $<x-z<m>$

> Im Allgemeinen gibt es Software, die diese