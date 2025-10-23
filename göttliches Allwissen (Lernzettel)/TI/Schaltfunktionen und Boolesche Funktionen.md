---
tags:
  - TI
status: rot
---
---
>[!def] Tupel aus [[Boolesche Algebra|booleschen Werten]]
> 
> $B^{n},n\in \mathbb{N}$ ist ein Tupel aus $n$ [[Boolesche Algebra|booleschen Werten]] hintereinander.
> 
> ---
> z.B. sind `00`, `01`, `10` und `11` alle verschiedenen Tupel aus booleschen Werten der Länge $2$.
> 
> `0011010` ist z.B. ein solches Tupel der Länge $7$.

^aebb87


>[!def] Schaltfunktion
>Seien $n,n\in \mathbb{N}\mid n,n \ge 1$, dann heißt eine Funktion$$F:B^{n}\to B^{m}$$ **Schaltfunktion**, wobei $B^{n}$ und $B^{m}$ [[#^aebb87|Tupel aus booleschen Werten]] sind.
>
>---
>Für Schaltfunktionen benutzt man als Funktionsnamen meist *Großbuchstaben* wie $F$.

Z.B. eine Schaltfunktion, welche zwei boolesche Werte annimmt und drei boolesche Werte ausgibt.

![[Schaltfunktionen 2025-10-21 10.35.15.excalidraw]]


## Beispiel: Eine Schaltfunktion zur Addition zweier 1Bit Zahlen:
$F:B^{2}\to B^{2}\;,\;(x_{1},x_{0})\mapsto(x_{1}\wedge x_{1}\;,\;x_{0} \text{ xor }x_{0})$

Vgl. als Tabelle:

| $x_{1}$ | $x_{0}$ | Übertrag | Summe |
| ------- | ------- | -------- | ----- |
| 0       | 0       | 0        | 0     |
| 0       | 1       | 0        | 1     |
| 1       | 0       | 0        | 1     |
| 1       | 1       | 1        | 0     |

## Beispiele: Länge der Ein- und Ausgabetupel

|                                                 | Eingabe | Ausgabe                      |
| ----------------------------------------------- | ------- | ---------------------------- |
| Addition von zwei 16-stelligen Dualzahlen       | 32      | 16 (17,mit letztem Übertrag) |
| Multiplikation von zwei 16-stelligen Dualzahlen | 32      | 32                           |
| Sortieren von 30 16-stelligen Dualzahlen        | 480     | 480                          |
| Primzahltest einer 16-steiigen Dualzahl         | 16      | 1                            |



# Reduzierbarkeit auf [[Boolesche Funktionen]]] 

