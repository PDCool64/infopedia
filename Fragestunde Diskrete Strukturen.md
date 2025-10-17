---
date: 2025-10-17
tags:
  - DS
status: rot
Vorlesungsfolien:
Skriptfolien:
---
---

## Affenproblem
Gegeben: $100$ Affen, $1600$ Kokusnüsse
### Behauptung
$\exists k \in \mathbb{N}:$ $4$ Affen haben $k$ Kokusnüsse

### Beweis
Angenommen, die Aussage ist falsch, dann folgt: 
$\forall k \in \mathbb{N}:$ höchstens $3$ Affen haben k Kokusnüsse
Wir nummerieren alle Affen von 1 bis 100 nach steigender Anzahl an Kokusnüssen. 
$$
\begin{align}
1 \geq 0 \\
2 \geq 0  \\
3 \geq 0 \\
4 \geq 1 \\
5 \geq 1 \\
6 \geq 1 \\
\dots  \\
99 \geq 32 \\
100 \geq 33
\end{align}
$$
Das bedeutet, der Affe $a_{i}$ hat mindest eine Kokusnuss mehr als der Affe $a_{i-3}$ bzw. der Affe $a_{i+3}$ hat eine Kokusnuss mehr als der Affe $a_{i}$. 
Die Anzahl der Kokusnüsse ist damit mindestens $(\sum_{i = 0}^{32}3i) + 33 = 1617$.
