---
date: 2025-10-17
tags:
  - DS
status: gelb
Vorlesungsfolien:
Skriptfolien:
---
---

## Affenproblem
Gegeben: $100$ Affen, $1600$ Kokusnüsse
### Behauptung
$\exists k \in \mathbb{N}_{0}:$ $4$ Affen haben $k$ Kokusnüsse

### Beweis
Angenommen, die Aussage ist falsch, dann folgt: 
$\forall k \in \mathbb{N}_{0}:$ höchstens $3$ Affen haben k Kokusnüsse
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

---

# Subjunktion vs. Implikation

Subjunktion vs. Implikation und die verschiedene Ebenen auf denen beide jeweils agieren.

Antwort:
TL:DR : Für unsere Zwecke ist uns der feine Unterschied ziemlich egal. 
Nur bitte beim Schreiben drauf achten, ob man eine neue Zusammengesetzte Aussage erhalten will oder ob man "auf Metaebene" über Aussagen reden will.

Außerdem: (wir werden später fast nur $\iff$ benutzen)
$\iff = \;\equiv$

$A\iff B$ ist definiert als: Bei $A\leftrightarrow B$ kommt der Wahrheitswert wahr raus.

Für eine aufgearbeitete Unterscheidung: [[Aussagenlogik#Unterscheidung Subjunktion vs. Implikation bzw. Bijunktion vs. Äquivalenz]]
