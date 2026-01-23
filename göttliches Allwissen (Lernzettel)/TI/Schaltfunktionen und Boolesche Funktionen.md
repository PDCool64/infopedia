---
tags:
  - TI
status: rot
---
---
# Schaltfunktionen

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

^efa64a

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

---
# Boolesche Funktionen

>[!def] Boolesche Funktion
> 
> **Boolesche Funktionen** sind [[#^efa64a|Schaltfunktionen]], welche genau einen booleschen Wert als Ausgabe liefern. Eine Schaltfunktion $$
> f:B^{n}\to B^{1}
> $$ heißt $n$-stellige **Boolesche Funktion**.
> ---
> Für Boolesche Funktionen nutzt man als  Funktionsnamen meist *Kleinbuchstaben* wie $f$.

^8e41bd

## Reduzierbarkeit von [[#^efa64a|Schaltfunktionen]] auf [[#^8e41bd|Boolesche Funktionen]]

>[!def] Reduzierbarkeit von [[#^efa64a|Schaltfunktionen]] auf [[#^8e41bd|Boolesche Funktion]]
> Sei $F:B^{n}\to B^{m}$ mit $F(x_{n-1}\;,\;\dots\;,\;x_{1}\;,\;x_{0})=(y_{m-1}\;,\;\dots\;,\;y_{1}\;,\;y_{0})$ eine [[#^efa64a|Schaltfunktion]], dann kann man für jedes $i\in \{ m-1\;,\;\dots\;,\;0 \}$ eine separate [[#^8e41bd|Boolesche Funktion]] $$
> f_{i}:B^{n}\to B\;,\;f_{i}(x_{n-1}\;,\;\dots\;,\;x_{1}\;,\;x_{0})=y_{i}
> $$definieren, welche den jeweiligen Bit $y_{i}$ des Ergebnisses liefert.
> Somit ist jede Schaltfunktion $F$ wie folgt darstellbar:$$F(x_{n-1},\dots\,x_{1},x_{0})= \bigg( f_{m-1}(x_{n-1},\dots,x_{1},x_{0}) \;,\; f_{m-2}(x_{n-1},\dots,x_{1},x_{0}) \;,\; \dots \;,\;f_{0  }(x_{n-1},\dots,x_{1},x_{0})\bigg)$$
> 

![[Schaltfunktionen und Boolesche Funktionen 2025-10-23 11.06.07.excalidraw|500]]

## Verschiedene Boolesche Funktionen

>[!def] Anzahl an unterschiedlichen booleschen Funktionen
> Es gibt $2^{(2^{n})}$ $n$-Stellige boolesche Funktionen.
> 
> ---
> Erklärung: Es gibt $2^{n}$ Eingabekombinationen, für die jeweils eine booelsche Funktion mit Ausgabe $0$ sowie eine mit Ausgabe $1$ existiert.


Für die Wahrheitstafeln, Namen und Verwendungszwecke verschiedener Boolescher Funktionen  gibt es eine Übersicht : [[Übersicht verschiedener Boolesche Funktionen]]
