---
date: 2025-10-28
tags:
  - DS
status: rot
Vorlesungsfolien:
Skriptfolien: "[[Skript Diskrete Strukturen.pdf]]"
---
---

>Fachschafts-Info:
>Vollversammlung am 04.11 10:15-14:15 im H03

Neu:
hier wurde die "Verknüpfung" von jedem x zu einem eindeutigen $y$ dargestellt als Tupel:

>[!def] Abbildung
> 
> - $M$ Menge
> - $N$ Menge
> - $f\subseteq M\times N$
> 
> so, dass gilt:
> für jedes $x\in M$ existiert *genau ein* $y\in N$ mit $(x,y)\in f$
> 
> 

Das passt auch recht **schön** an die Schreibweise, eine Abbildung durch explizites Aufzählen der "Paare":
$$
\{ 1,2,3 \}\to \{ 4,5,6 \}\;,\;1\mapsto 4\;,\;2\mapsto 5\;,\; 3\mapsto 4
$$

Dann kann man die Gleichheit von zwei Abbildungen mit $A=A'$ und $B=B'$ und der Bedingung $f=g$ schreiben - weil die "Abbildungsvorschrift" hier einfach nur Mengen an Tupel sind, die man einfach wie ganz Normale Mengen vergleichen kann.

z.B.:
$$f:\mathbb{R}\to \mathbb{R},g:\mathbb{R}\to \mathbb{R}$$
$$f(x):\begin{cases}
\frac{1}{x+1}&x\in \mathbb{R}\setminus\{- 1 \} \\
0 &x=-1
\end{cases}$$
$$h(x):\begin{cases}
\frac{1}{x+1}&x\in \mathbb{R}\setminus\{- 1 \} \\
1 &x=-1
\end{cases}$$
sind ungleich, weil $(-1,0)\neq(-1,1)$

---
Es seien $M$,$N$ Mengen
- Menge der Abbildungen von $M$ nach $N$:
  $\text{Abb}(M,N)$
  oder $N^{M}$

 ---
# Identitätsabbildung
$$
\text{id}_{M}:M\to M,x\mapsto x
$$


---

## Abbildungen aus der leeren Menge
Sei $N$ eine Menge (die auch leer seien darf), Dann existiert *genau eine* Abbildung: $\emptyset\to N$ , nämlich $f=\emptyset$
(Weil man keine Tupel bilden kann: $\emptyset \times N=\emptyset$ und somit $f\subseteq \emptyset \times N$ die leere Menge seien muss)

## Abbildung in die leere Menge?
Es existiert keine Abbildung $M\to \emptyset$


---
