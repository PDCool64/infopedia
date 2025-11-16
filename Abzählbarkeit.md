---
tags:
  - AFI
  - DS
status: rot
---
---
>[!def] Abzählbarkeit
> Definition:
> >[!def] von $\mathbb{N}$ surjektiv.
> Eine Menge $M$ heißt abzählbar, wenn $M=\emptyset$ oder wenn eine [[Abbildungen#Injektiv, Surjektiv, Bijektiv|surjektive]] Abbildung $f:\mathbb{N}\to M$ existiert.
> 
> Ableitbar:
> >[!def] nach $\mathbb{N}$ injektiv.
> Eine Menge $M\neq \emptyset$ ist genau dann abzählbar, wenn eine [[Abbildungen#Injektiv, Surjektiv, Bijektiv|injektive]] Abbildung $g:M\to \mathbb{N}$ existiert.
> ($\emptyset$ ist abzählbar, der Beweis für diese Richtung funktioniert aber sonst nicht)
> 
> 
 Eine abzählbare Menge, die nicht endlich ist, heißt abzählbar unendlich. 
> Eine nicht abzählbare Menge nennt man **überabzahlbar**.


Intuitiv Menge ist somit Abzählbar wenn
- die natürlichen Zahlen ausreichen um mit ihnen alle Elemente zu treffen
- die Menge klein genug ist, damit man keine natürliche Zahl doppelt treffen muss.

Es gibt kein "unterabzählbar" - Man kann keine Unendlichkeit kleiner als $\mathbb{N}$ konstruieren.

Jede endliche Menge ist abzählbar.
## Verwandt: [[Mengen#Mächtigkeit einer Menge|Mächtigkeit von Mengen]]
findet man sogar eine [[Abbildungen#Injektiv, Surjektiv, Bijektiv|bijektive]] Abbildung zwischen einer Menge und $\mathbb{N}$, dann ist diese nicht nur abzählbar sondern auch gleichmächtig zu $\mathbb{N}$.

---

# Wichtige Abzählbare Mengen

## Die Ganzen Zahlen $\mathbb{Z}$ sind abzählbar

Idee:

| $\mathbb{N}$ | $\mathbb{Z}$ |
| ------------ | -----------: |
| 1            |            0 |
| 2            |           -1 |
| 3            |            1 |
| 4            |           -2 |
| 5            |            2 |
| 6            |           -3 |
| 7            |            3 |
| 8            |           -4 |
| 9            |            4 |
als Abbildung:
$$
f:\mathbb{N}\to \mathbb{Z}\;,\;n\mapsto \begin{cases}
-\frac{n}{2} &,n\text{ gerade} \\
\frac{n-1}{2} &,n \text{ ungerade}
\end{cases}
$$
Diese Abbildung ist sogar *bijektiv*, womit nicht nur gezeigt ist, dass $\mathbb{Z}$ abzählbar ist, sondern auch gleichmächtig wie $\mathbb{N}$.


# Cantor'sches Diagonalargument: das kartesische Produkt $\mathbb{N}\times \mathbb{N}$ ist abzählbar




# Verständniss: Warum funktioniert das:
## Graphisch
![[Pasted image 20251116122406.png|400]]

Das Durchlaufen alle Elemente $(m,n)\in \mathbb{N}\times \mathbb{N}$ wird gut deutlich: Man kann eine bijektive Abbildung aufstellen, womit $\mathbb{N}\times \mathbb{N}$ abzählbar ist.
## Die explizite Abbildung

## $\mathbb{N}\to \mathbb{N}\times \mathbb{N}$


## $\mathbb{N}\times \mathbb{N}\to \mathbb{N}$
Alle Tupel $(j,k)$ auf einer $m$-ten Diagonale haben die gleiche Summe $j+k$ ihrer Komponenten. Wir verschieben die Indizierung der Diagonalen aber um $-2$, damit das Tupel $(1,1)$ die $0$-te Diagonale bildet.
$$
m=j+k-2
$$
**Wir bilden die Tupel einer Diagonalen zusammen auf ein Intervall der natürlichen Zahlen ab.** 

Jede Diagonale hat ein Element mehr als die Vorherige. - den "Block" der natürlichen Zahlen, auf den sie abgebildet werden soll, muss also eins größer als der Vorherige Block sein.

Wo kann der $m$-te Block anfangen: Genau bei der Summe der Länge aller vorherigen Blöcke. Also bei:$$\sum_{i=0}^{m}i=\frac{m(m+1)}{2}$$
Also bilden wir jedes der Tupel $(j,k)$ die in der $j+k-2$-ten Diagonale liegen ab auf:
- Den Start des Intervalls auf $\mathbb{N}$ dieser diagonale: $\frac{m(m+1)}{2}$ mit $m=j+k-2$
- Addiert mit der Position des jeweiligen Elements in der Diagonale: $j$ 
  (man könnte anstatt $j$ auch $k$ wählen, dann wäre die Sortierung innerhalb der einzelnen Diagonalen umgekehrt)

Also:$$n= \frac{(j+k-2)(j+k-2)}{2}+j$$
> Es gibt also eine injektive Abbildung, die jedem Tupel $(j,k)\in \mathbb{N}\times \mathbb{N}$ eine natürliche Zahl $n$ zuordnet.

Achtung: *WARUM AUCH IMMER* hat man uns ins Skript ein Diagramm gepackt, in dem Die Diagonalen gespiegelt gewählt worden sind. In dem Diagramm hier wird innerhalb der einzelnen Diagonalen nach steigender zweiter Komponente sortiert, während die Formeln im Skript nach steigender erster Komponente sortieren.
![[Abzählbarkeit 2025-11-16 13.04.05.excalidraw|800]]

![[Abzählbarkeit 2025-11-16 12.28.03.excalidraw|600]]


