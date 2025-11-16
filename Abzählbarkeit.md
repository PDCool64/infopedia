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

## Graphisch
![[Pasted image 20251116122406.png|400]]

Das Durchlaufen alle Elemente $(m,n)\in \mathbb{N}\times \mathbb{N}$ wird gut deutlich: Man kann eine bijektive Abbildung aufstellen, womit $\mathbb{N}\times \mathbb{N}$ abzählbar ist.
## Als explizite Abbildung

### Idee: Gaus'sche Summenformel und Einteilung in Blöcke.

Zu jedem $n\in \mathbb{N}$ gibt es *genau ein* Paar $(m,l)$ mit $m\in \mathbb{N}_{0}$ und $1\le l \le m+1$, so dass
$$
n=\frac{m(m+1)}{2}
+l$$
Wie funktioniert das:
- Der Bruch ist die Gaus'sche Summenformel


![[Abzählbarkeit 2025-11-16 12.28.03.excalidraw]]



![[Abzählbarkeit 2025-11-16 13.04.05.excalidraw]]