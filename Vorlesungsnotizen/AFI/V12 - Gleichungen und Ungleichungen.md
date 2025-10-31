---
date: 2025-10-29
tags:
  - AFI
status: rot
Vorlesungsfolien:
Skriptfolien: "[[Altes Skript AFI.pdf]]"
---
---
Arbeitsdefinition:
Sei $K$ ein angeordneter Körper, $D\subseteq K$ ist eine endlliche nichtleere Menge sowie
$f,g:D\to K$
Problemstellung: "Bestimmte alle $x\in D$ welche $f(x)=g(x)$ erfüllen."
(Die Gesamtheit dieser Teile, insbesondere auch der Menge $D$ stellt eine Gleichung dar. Mit einem anderen $D$ kann es ganz andere Lösungen geben)

Die Lösung dieser gleichung ist ein $z\in D$, das $f(z)=g(z)$ erfüllen. Die Menge aller Lösungen heißt Lösungsmenge


## Für die Ungleichung:
Man muss nur die Fälle $f(x)<g(x)$ sowie $f(x)\le g(x)$ betrachten

# Mit dem Lemma vom letzten Mal:
a)
Für Gleichungen:
$$
f(x)=g(x)\iff f(x)+h(x)=g(x)+h(x)
$$
Bei der Multiplikation gilt aber nur:
$$
f(x)=g(x)\implies f(x)\cdot h(x)=g(x)\cdot h(x)
$$
(weil $h(x)$ null seien kann)
Ist aber $h(x)\neq 0$, dann gilt:
$$
f(x)=g(x)\iff f(x)\cdot h(x)=g(x)\cdot h(x)
$$
b)
Für Ungleichungen:

Addition ist genau so.

Für die Multiplikation muss man ebenso zwischen $h(x)\ge 0$ und $h(x)>0$ unterscheiden, um den div-0 Fall auszuschließen.


# Beispiel:

a)
s.h. Skript.
> In der Klausur muss man den Inhalt der Sätze und Lemmas kennen, aber nicht die Zahlen auswendig kennen um über jeden Implikationspfeil "sh. Lemma 3.2 i) zweiter Nebensatz" schreiben zu können.

b)
Ges. alle $x\in K$ mit $\left| x \right|=3x+4$
1. Fall: $x\geq 0$:  $D_{1}=[0,\infty) \; ,\,\left| x \right| =x$ $$ 
\begin{array}{lrcl}

\iff&x&=3x+4 \\
\iff&-2x&-4 \\
\iff&x&=-2
\end{array}
$$ $\implies \mathbb{L}_{1}=\emptyset$ in diesem Fall
2. Fall: $x<0$, $D_{2}=(-\infty,0)$
   $-x=3x+4 \iff -4x=4\iff x=-1$ 
   Die einzige Lösung ist also $\mathbb{L}=\{ -1 \}$

---
#  Geometrische Summenformel
>[!def] Geometrische Summenformel
> Für $n\in \mathbb{N}_{0}$ und jedes $q\in K,q\neq 1$ gilt:$$ \sum_{k=0}^{n}q^{k}=\frac{q^{n+1}-1}{q-1}$$
> und allgemeiner für alle $n\in \mathbb{N}_{0}$ und alle $a,b\in K$ mit $a\neq b$ gilt:$$\sum_{k=0}^{n}a^{k}b^{n-k}=\frac{a^{n+1}-b^{n+1}}{a-b}$$

Beweis mit vollständiger Induktion nach $n$.
	wie immer.

Der Zweite Satz ist interessant, weil man $b=0$ separat betrachtet.


---
# Bernoullische Ungleichung
>[!def] Bernoullische Ungleichung
> Es sei $K$ ein angeordneter Körper. Für alle $n\in \mathbb{N}_{0}$ und $a\in K$,$a\ge -1$ gilt
> $$
> (1+a)^{n}\ge 1+na
> $$
> In diesem Fall gilt $(1+a)^{n}=1$ genau dann, wenn $n=0$ oder $n=1$ oder $a=0$.
> 

> Mann kann also Binomische Formeln nach unten abschätzen, was für die Analysis (untere Schranken und Co.) sehr nützlich ist.

Beweis mal wieder mit Induktion nach $n$.

> Ein **Korollar** ist etwas, das man als "Nebenprodukt" oder als direkte Folge aus einem Satz bekommt.

Ein Korollar aus diesem Satz:
Es sei $q\in \mathbb{Q},q>1$. Dann gibt es zu jedem $M>0$ ein $N\in \mathbb{N}$, so dass
$$
\frac{q^{n}}{n}\ge M
$$
für alle $n\ge N$.


Bei den "wir nehmen $N=1+\left\lceil  \frac{2M}{r^{2}}  \right\rceil$" rechnet man immer von hinten und schreibt dann das ergebnis oben hinn.