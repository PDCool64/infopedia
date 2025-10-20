>[!def]
> Eine **Polynomfunktion** $p:\mathbb{R}\to \mathbb{R}$ vom Grad $n\in \mathbb{N}_{0}$ ist eine [[Abbildungen|Funktion]] mit 
> $$
> x\mapsto p(x):= a_{n}x^{n} \;+\;a_{n-1}x^{n-1}\;+\;a_{n-2}x^{n-2} \;+\; \cdots + \;a_{1}x \;+\; a_{0} 
> $$
> bzw. als Summe geschrieben:
> $$x\mapsto p(x):= \sum_{k=0}^{n}a_{k}x^{k}$$
> mit festen Koeffizienten $a_{0},a_{1},\dots,a_{n}\in \mathbb{R}\mid a_{n}\neq 0$.
> 
> ---
> Der Grad $n$ des Polynoms $p$ wird geschrieben als $n=\text{grad}(p)$.
> 
> ---
> Die einzelnen Summanden $a_{i}x^{i}$ werden Monomere genannt.

^8147e2



# Eigenschaften von Polynomfunktionen
- Polynomfunktionen haben die gesamten [[Zahlenräume#Reelle Zahlen $ mathbb{R}$|reellen Zahlen]] als Definitionsbereich.
- Polynomfunktionen sind überall [[Stetigkeit von Funktionen|stetig]].
- Eine Polynomfunktion $p$ hat *höchstens* $n=\text{grad}(p)$ reelle Nullstellen.
- Polynomfunktionen sind überall beliebig oft [[Ableitungen|differenzierbar]]
- Polynome von ungeraden $\text{grad}$ haben mindestens eine Nullstelle:
  Grenzwerte unterschiedlich + Zwischenwertsatz


# Polynomaddition
Sei $p(x)=\sum_{k=0}^{n}a_{k}x^{k}$ und $q(x)=\sum_{k=0}^{m}b_{k}x^{k}$, dann ist
$$
(p+q)(x)=\sum_{k=0}^{\text{max}(m,n)}(a_{k}+b_{k})x^{k}
$$
Beispiel:
$$
(x^{2}-1)+(3x^{4}+7x^{2}+1)=(0+3)x^{4}+(1+7)x^{2}+(-1+1)\cdot x^{0}
$$
# Polynommultiplikation
Sei $p(x)=\sum_{k=0}^{n}a_{k}x^{k}$ und $q(x)=\sum_{k=0}^{m}b_{k}x^{k}$, dann ist
$$
(p\cdot q)(x)=\sum_{j=0}^{n+m}\left( \sum _{k=0}^{j}a_{k}b_{j-k} \right) x^{j}
$$
Beispiel:
$(x^{3}+2x^{2}-1)\cdot(x^{4}-x^{3}+x+1)=1\cdot x^{7}+(-1+2)x^{6}+(-2x^{5}+(1-1)x^{4})+(1+2+1)x^{3}+(2)x^{2}+(-1)x+(-1)$

# Polynomdivision

>[!def] Polynomdivision
> Sind $p$ und $q\neq 0$ zwei Polynome, dann gibt es eindeutig bestimmte Polynome $f$ und $r$, so dass
> $$
> p=f\cdot q+r
> $$
> wobei $\text{grad}(r)<\text{grad}(q)$ oder sogar $r=0$ gilt.

## Nullstellen und Polynomdivision
Alle Nullstellen eines Polynoms können als Linearfaktor durch Polynomdivision abgespalten werden, *ohne* dass dabei ein Rest $r$ entsteht.

Sei $x_{0}$ ein [[Zahlenräume#Reelle Zahlen $ mathbb{R}$|reelle]] Nullstelle von $p(x)$, dann kann $p(x)$ immer geschrieben werden als:
$$
p(x)=f(x)\cdot\underbrace{ (x-x_{0}) }_{ \text{Linearfaktor} }
$$
Dabei ist $\text{grad}(f)$ immer genau um $1$ kleiner als der von $p$.

Wenn man also eine Nullstelle errät / schnell erkennt, kann man diese Nullstelle durch Polynomdivision abspalten und es genügt die Nullstellen von $f$ zu finden. Dies ist einfacher, da $f$ nun einen niedrigeren Grad hat.

Das Abspalten einzelner Nullstellen lässt sich rekursiv anwenden - auch von $f$ lassen sich ggfs. weitere Nullstellen abspalten-
$\implies$ Alle Nullstellen können als Linearfaktoren von einem Polynom abgespalten werden. Es bleiben bei [[Zahlenräume#Reelle Zahlen $ mathbb{R}$|reellen]] Funktionen aber ggfs. weitere Faktoren übrig, welche durch Quadrate nie Null werden.

Entsprechen $k$ viele der Linearfaktoren der gleichen Nullstelle $x_{0}$ ,dann nennt man $x_{0}$ eine $k$-fache Nullstelle.

Beweis:
	Sei $x_{0}$ Nullstelle von $p(x)$, dann gilt wie bei jeder [[#Polynomdivision]]: Es gibt Polynome $f,r$ mit
	$p(x)=f(x)\cdot(x-x_{0})+r(x)$
	Weil $x_{0}$ aber eine Nullstelle ist, gilt:
	$0=\underbrace{ f(x)\cdot\underbrace{ (x-x_{0}) }_{ =0 } }_{ =0 }+r(x)$
	$0=r(x)$
	d.h. es bleibt nie ein Rest.


# Polynome als Vektoren
Die Menge der Polynomfunktionen bilden einen [[Vektorraum]].

Wir betrachten -da die Vektoren die gleiche Länge haben sollen- den Vektorraum der Polynome vom [[#^8147e2|Grad]] $\le n$:
$\{ P(x)\mid\text{grad}(P)\le n \}$

Es lässt sich jedes Polynom auch als Zeilenvektor seiner Koeffizienten schreiben:
$$\{ P(x)\mid\text{grad(P)}\le n \}\to \mathbb{R}^{n+1}\quad,\quad
a_{n}x^{n}+a_{n-1}x^{n-1}+\dots+a_{1}x^{1}+a_{o} \quad \mapsto \quad \begin{pmatrix}
a_{n} \\
a_{n-1} \\
\vdots \\
a_{1} \\
a_{0}
\end{pmatrix}
$$
Diese [[Abbildungen|Abbildung]] von Monomsumme zu Koeffizientenvektor ist [[Abbildungen#^381681|bijektiv]] : Jedem Polynom ist *eindeutig* ein Vektor zugewiesen, genauso umgekehrt jedem Vektor ein Polynom.

Die Definitionen für die [[#Polynomaddition]], sowie der [[Vektorraum#^44084b|Skalarmultiplikation]] funktionieren genau wie erwartet egal wie zwischen den Schreibweisen gewechselt wird, weil diese Abbildung eine [[Abbildungen#Lineare Abbildung|Lineare Abbildung]] ist:

Sei $p$ ein Beliebiges Polynom vom Grad $n$: 
 $a_{n}x^{n}+a_{n-1}x^{n-1}+\dots+a_{1}x^{1}+a_{o}$ 


Man kann beide Schreibweisen somit *äquivalent* verwenden.

