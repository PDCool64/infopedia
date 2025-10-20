
>[!def] Erzeugendensystem eines Vektorraums
> Eine [[Mengen|Menge]]  $v_{1},\dots,v_{n}$ an Vektoren aus einem $\mathbb{R}$-[[Vektorraum]] $V$ ist ein **Erzeugendensystem** von $V$, wenn jeder Vektor des Vektorraumes als [[Vektorraum#Linearkombination|Linearkombination]] der Vektoren geschrieben werden kann, d.h. wenn $$\text{span}_{\mathbb{R}}(v_{1},v_{2},\dots ,v_{n})=V$$
> (Das [[Vektorraum#Lineares Erzeugnis|Lineare Erzeugnis]] der Vektoren ist wieder der gesamte Vektorraum)
> ---
> Gibt es ein Erzeugendensystem aus *endlich* vielen Vektoren, so nennt man den Vektorraum $V$ **endlich erzeugt**.

^e58040

## Bemerkungen
- Der Vektorraum der [[Polynomfunktionen]] ist z.B. *nicht* endlich erzeugt, weil für jede Potenz ein eigener Vektor notwendig ist. ($x^{0},x^{1},x^{2},\dots ,x^{\infty}$ wären notwendig um jedes Polynom als [[Vektorraum#Linearkombination|Linearkombination]] erzeugen zu können)
	- Der Vektorraum der stetigen Funktion ist ebenfalls nicht endlich erzeugt.
- Jeder $\mathbb{R}^{n}$ ist stetig erzeugt: s.h. [[#Die Einheitsvektoren als Basis für jeden $ mathbb{R} {n}$|Die Einheitsvektoren als Basis für jeden R^n]] 

^c8e416
# Basis eines Vektorraums
>[!def] Basis eines Vektorraums
> Ist $v_{1},\dots ,v_{n}$ ein [[#^c8e416|Erzeugendensystem]] von $V$, welches aus *linear unabhängigen* Vektoren besteht, so nennt man es eine **Basis** von $V$.
> 
> ---
> In einer Basis lässt sich jeder Vektor $w\in V$ auf *genau eine Weise* als Linearkombination der $v_{1},\dots,v_{n}$ darstellen.
> 
> ---
> Jeder Vektorraum (ausgenommen dem Nullvektorraum) hat *unendlich viele* Basen.
## Bemerkungen
- Die Tatsache, dass jeder Vektorraum unendlich viele Basen hat, lässt sich zeigen:
  Sei $v_{1},\dots,v_{n}$ ein linear unabhängiges Erzeugendensystem -d.h. eine Basis- dann ist jede Menge nach dem Schema $\lambda\cdot v_{1},\dots,\lambda\cdot v_{n}\mid\lambda\in \mathbb{K}\setminus\{ 0 \}$ ebenfalls eine Basis. (Meist gibt es noch viel mehr Optionen andere Basen zu erzeugen. Dies ist nur die einfachste)

## Die Einheitsvektoren als Basis für jeden $\mathbb{R}^{n}$
Die Einheitsvektoren $$
e_{1}:=\begin{pmatrix}
1 \\
0 \\
0 \\
\vdots \\
0
\end{pmatrix} \quad
e_{2}:=\begin{pmatrix}
0 \\
1  \\
0 \\
\vdots \\
0
\end{pmatrix} \quad
e_{3}:=\begin{pmatrix}
0 \\
0 \\
1 \\
\vdots \\
0
\end{pmatrix} \dots \quad
e_{n}:=\begin{pmatrix}
0 \\
0 \\
0 \\
\vdots \\
1
\end{pmatrix}
$$
Bilden eine [[#Basis eines Vektorraums|Basis]] von $\mathbb{R}^{n}$. Die $e_{i}$ werden **Standarderzeuger** genannt.

# Größe der Basen und Dimension von Vektorräumen

Alle [[#Basis eines Vektorraums|Basen]] eines [[#^e58040|endlich erzeugten]] Vektorraumes bestehen aus *gleich vielen* Vektoren.

Die **Dimension** $\text{dim}(V)$ eines [[#^e58040|endlich erzeugten]] Vektorraums $V$ ist die eindeutig bestimmte Anzahl an Vektoren in den Basen von $V$ 