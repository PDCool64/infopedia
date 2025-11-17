---
tags:
  - AFI
status: rot
---
---

>[!def] Folge
>Eine (reelle) Folge ist eine Abbildung $\mathbb{N}\to \mathbb{R}$.
>
> ---
>Statt $\mathbb{N}\to \mathbb{R}\;,\;n\mapsto a_{n}$ schreibt man auch $(a_{n})_{n\ge 1}$
>
>Man nennt die Wertemenge dieser Abbildung $W:=\{ a_{n}\mid n\in \mathbb{N} \}$ . Gilt $W\subseteq M$, so spricht man von einer Folge in $M$.

## Leichte Verallgemeinerung
Anstatt $1$ als ersten Index zu verwenden, ist auch ein beliebiges $n_{0}\in \mathbb{Z}$ möglich, also$$ \mathbb{Z}_{\ge n_{0}}\to \mathbb{R}\;,\;n\mapsto a_{n}$$
Man kann also sowohl bei größeren positiven Zahlen $2,3,200$ usw. anfangen, insbesondere aber auch bei negativen Zahlen wie $-20,-4,-1,0$.
Dies ändert nichts an der [[Abzählbarkeit]] der Indexmenge, denn die Indexmenge wird legendlich verschoben.

( Z.B. ist $\mathbb{N}\to \mathbb{R}\;,\;n\mapsto(n-5)^{2}$ praktisch das gleiche wie $\mathbb{Z}_{\ge 5}\to \mathbb{R}\;,\;n\mapsto n^{2}$, nur dass die Indexe für die jeweils identischen Folgenglieder nun um 5 von einander verschoben sind.)
# Gleichheit von Folgen
Zwei Folgen sind genau dann gleich, wenn ale Folgenglieder gleich sind.


# Arithmetische und geometrische Folgen
## Arithmetische Folge:
Bei einer arithmetischen Folge ist die Differenz zwischen aufeinanderfolgenden Folgengliedern konstant: 
$$a_{n+1}-a_{n}=\text{const}$$
Rekursiv schreibt man sie als:
$a_{n+1}=a_{n}+\text{const}$ ; $a_{n_{0}}=x$
Explizit schreibt man sie als:
$a_{n}=a_{n_{0}}+\text{const}\cdot (n-n_{0})$

## Geometrische Folge:
Bei einer geometrischen Folge ist der Quotient zwischen aufeinanderfolgenden Folgengliedern konstant.
$$
\frac{a_{n+1}}{a_{n}}=\text{const}
$$
Rekursiv schreibt man sie als:
$a_{n+1}=a_{n}\cdot const$ ; $a_{n_{0}}=x$
Explizit schreibt man sie als:
$a_{n}=a_{n_{0}}\cdot\text{const}^{n-n_{0}}$

---
# Monotonie von Folgen
