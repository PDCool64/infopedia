
>[!def] Vektorraum
> Eine [[Mengen|Menge]] $V$ heißt **Vektorraum** über dem [[Körper]] $\mathbb{K}$, wenn es zwei abgeschlossene [[Abbildungen]] $$\begin{align}+:V\times V\to V\quad&,\quad(u,v)\mapsto u+v&(\text{Vektoraddition}) \\\cdot\,: \mathbb{K}\times V\to V \quad&,\quad(\lambda,v)\mapsto\lambda\cdot v &(\text{Skalarmultiplikation})\end{align}$$
> gibt, mit den folgenden Eigenschaften: (Vektorraumaxiome)
> 1. Die Vektoraddition ist [[Einfache Rechengesetze#Assoziativgesetz|assoziativ]]: $u+(v+w)=(u+v)+w \quad\forall_{u,v,w}\in V$
> 2. Die Vektoraddition ist [[Einfache Rechengesetze#Kommutativgesetz|kommutativ]]: $u+v=v+u\quad\forall_{u,v}\in V$
> 3. Es gibt ein neutrales Element der Vektoraddition, den *Nullvektor* "$o$" : $\exists_{o\in V}\forall_{v\in V}:o + v=v \quad$
> 4. Es gibt zu jedem Vektor ein inverses Element der Vektoraddition: $\exists_{-v\in V}:v+(-v)=o$
> 5. Es gibt ein neutrales Element der Skalarmultiplikation, das Einselement "$1$": $1\cdot v=v \quad\forall_{v\in V}$
> 6. $\forall_{\lambda,\mu\in \mathbb{K}}\forall_{v\in V}:(\lambda \cdot \mu)\cdot v=\lambda\cdot(\mu\cdot v)$
> 7. $\forall_{\lambda,\mu\in \mathbb{K}}\forall_{v\in V}:(\lambda\!+\!\mu)\cdot v=\lambda\!\cdot\! v+\mu\!\cdot\! v$
> 8. $\forall_{\lambda\in \mathbb{K}}\forall_{u,v\in V}:\lambda\cdot(u\!+\!v)=\lambda\!\cdot\!u+\lambda\!\cdot\!v$
> ---
> Die Elemente $v\in V$ werden **Vektor** genannt.
> Die Elemente $\lambda\in \mathbb{K}$ werden **Skalar** genannt.

^44084b

## Bemerkungen
- "Abgeschlossen" bedeutet, dass das Ergebnis einer Vektoraddition bzw. einer Skalarmultiplikation selbst wieder im Vektorraum liegt. (s.h. [[Abbildungen#^e40e31|Zielbereich]] der Abbildungen)
- Die Vektorraumaxiome ähneln sehr den [[Körper#^a3c120|Körperaxiomen]], aber in einem Vektorraum gibt es die Skalarmultiplikation, welche einen Vektor $v\in V$ *nicht* mit einem weiteren Vektor verknüpft, sondern mit einem *Skalar* $\lambda\in \mathbb{K}$. In Körpern hingegen verknüpft die Multiplikation zwei "gleichartige" Elemente.

# Beispiele für Vektorräume

## Vektorraum der Polynome vom $\text{grad}\leq n$ 

Die Polynome vom $\text{grad}\leq n$ bilden über den reellen Zahlen einen Vektorraum.

### Abgeschlossenheit der Addition:
Sei $P(x)=\sum_{i=0}^{n}a_{i}x^{i}$ und $Q(x)=\sum_{i=0}^{n}b_{i}x^{i}$ Dann ist $(P+Q)(x)$ ebenfalls ein Polynom mit $\text{grad}\le n$
$$
(P+Q)(x)=P(x)+Q(x)=\sum_{i=0}^{n}a_{i}x^{i} + \sum_{i=0}^{n}b_{i}x^{i} = \sum_{i=0}^{n}(a_{i}+b_{i})x^{i}
$$
### Abgeschlossenheit der Skalarmultiplikation:
Sei $P(x)=\sum_{i=0}^{n}a_{i}x^{i}$ und $\lambda\in \mathbb{R}$, dann ist $(\lambda\cdot P)(x)$ ebenfalls ein Polynom mit $\text{grad}\le n$:
$$
(\lambda\cdot P)(x)=\lambda\cdot P(x)=\lambda\cdot \sum_{i=0}^{n}a_{i}x^{i}=\sum_{i=0}^{n}(\lambda\cdot a_{i})x^{i}
$$
### Beispielhaft: (Es müssen alle 8 Kriterien geprüft werden)
### Existenz eines Additiv-Inversen:
Sei $P(x)=\sum_{i=0}^{n}a_{i}x^{i}$, dann existiert ein Polynom$(-P(x))=\sum_{i=1}^{n}(-a_{i})\cdot x^{i}$ , sodass $P(x)+(-P)(x)=0 \;\forall_{x\in \mathbb{R}}$:
$$
P(x)+(-P)(x)= \sum_{i=1}^{n}a_{i}x^{i}+\sum_{i=1}^{n}(-a_{i})\cdot x^{i} =\sum_{i=1}^{n}(a_{i}-a_{i})x^{i}=\sum_{i=1}^{n}0=0
$$
## Vektorraum der stetigen Funktionen
Die Menge der stetigen Funktionen bildet über den reellen Zahlen einen Vektorraum.

## Abgeschlossenheit der Addition:
Seien $f,g$ zwei stetige Funktionen, dann ist auch $(f+g)$ eine stetige Funktion:$$(f+g)(x)=f(x)+g(x)$$was durch die [[Stetigkeit von Funktionen#^108050|Sätze zur Stetigkeit zusammengesetzter Funktionen]] ebenfalls eine stetige Funktion ergibt.

## Abgeschlossenheit der Skalarmultiplikation
Sei $f$ eine stetige Funktion und $\lambda$ ein Skalar, dann ist auch $(\lambda\cdot f)$ eine stetige Funktion:
$$(\lambda\cdot f)(x)=\lambda\cdot f(x)$$was durch die [[Stetigkeit von Funktionen#^108050|Sätze zur Stetigkeit zusammengesetzter Funktionen]] ebenfalls eine stetige Funktion ergibt.

---
# Untervektorraum

>[!def] Untervektorraum
> Sei $V$ ein [[#^44084b|Vektorraum]] über $\mathbb{K}$. Eine nichtleere Teilmenge $\emptyset\neq W \subseteq C$ heißt **Untervektorraum** von $V$, wenn $W$ bezüglich der Vektoraddition sowie der Skalarmultiplikation abgeschlossen ist.
> 
> D.h. wenn gilt:
> $u,v\in W\implies (u+v)\in W$
> $v\in W\implies\forall_{\lambda\in \mathbb{K}}: (\lambda\cdot v)\in W$
## Beispiel für einen Untervektorraum:
$\mathbb{R}^{2}$ ist ein Vektorraum. (Vektorraum der reellen Zahlen über sich selbst)

$G_{1}$ ist ein Untervektorraum von $\mathbb{R}^{2}$ :
$$G_{1}=\{ \lambda\cdot \begin{pmatrix}
1 \\
2
\end{pmatrix}\mid\lambda\in \mathbb{R} \}$$
### Vektoraddition ist abgeschlossen:
Seien $u=\lambda\cdot \begin{pmatrix}1 \\ 2\end{pmatrix}\quad,\quad v= \mu\cdot \begin{pmatrix}1 \\ 2\end{pmatrix}$ zwei beliebige Vektoren aus $G_{1}$, dann ist auch $(u+v)\in G_{1}$:
$$
u+v=\lambda \begin{pmatrix}
1 \\
2 
\end{pmatrix}+\mu \begin{pmatrix}
1 \\
2
\end{pmatrix}=
(\lambda \!+\!\mu)\cdot\begin{pmatrix}
1 \\
2
\end{pmatrix}\in G_{1}\quad\text{ weil } (\lambda\!+\! \mu) \in \mathbb{R}
$$
## Skalarmultiplikation ist abgeschlossen:
Seien $u=\lambda\cdot \begin{pmatrix}1 \\ 2\end{pmatrix}\quad,\quad r\in \mathbb{R}$ dann ist auch $(r\cdot u)\in G_{1}$: $$r\cdot u=r\cdot \left( \lambda \begin{pmatrix}
1 \\
2
\end{pmatrix} \right) =(r\!\cdot \!\lambda)\cdot \begin{pmatrix}
1 \\
2
\end{pmatrix} \quad\text{ weil } (\lambda\!\cdot\! \mu) \in \mathbb{R}$$
## Beispiel dafür, dass eine Teilmenge *keinen* Untervektorraum bildet:
$\mathbb{R}^{2}$ ist ein Vektorraum. (Vektorraum der reellen Zahlen über sich selbst)

$G_{2}$ ist per se kein Vektorraum und auch kein Untervektorraum von $\mathbb{R}^{2}$ :
$$G_{1}=\{ \begin{pmatrix}
0 \\
2
\end{pmatrix}+\lambda\cdot \begin{pmatrix}
1 \\
2
\end{pmatrix}\mid\lambda\in \mathbb{R} \}$$
## Die Vektoraddition ist z.B. nicht abgeschlossen:
$\begin{pmatrix}0 \\ 2 \end{pmatrix}\in G_{2}\quad,\begin{pmatrix}1 \\ 4\end{pmatrix}\in G_{2}$  aber: $\begin{pmatrix}0 \\ 2 \end{pmatrix}+\begin{pmatrix}1 \\ 4\end{pmatrix}=\begin{pmatrix}1 \\ 6 \end{pmatrix} \not\in G_{2}$

weil:
$$
\begin{align}
1&=0+\lambda\cdot 1 &\implies\lambda=1 \\
6&=2+ \lambda\cdot2 &\implies \lambda=2 \\
&&1\neq 2
\end{align}
$$
Außerdem existiert in $G_{2}$ z.B. kein Nullelement, was für jeden Vektorraum Bedingung ist.

---


Bsp. für ein nicht endlich erzeugten Vektorraum: Der Vektorraum der Polynome. Man braucht für jede Potenz einen neuen Erzeuger d.h. die Erzeuger müssten $\{ 1,x,x^{2},x^{3},\dots,x^{\infty} \}$ sein, also nicht endlich viele.


# Linearkombination
>[!def] Linearkombination
> Sei $V$ ein Vektorraum über $\mathbb{R}$. Sind $v_{1},\dots,v_{n}\in V$ Vektoren und $\lambda_{1},\dots,\lambda_{n}\in \mathbb{R}$ Skalare, so nennt man einen Ausdruck der Form $$\lambda_{1}v_{1}+\dots+\lambda_{n}v_{n}\in V$$ eine **Linearkombination** der Vektoren $v_{1},\dots,v_{n}$.

# Lineares Erzeugnis
>[!def] Lineares Erzeugnis / Linearer Spann
> Sind $v_{1},\dots,v_{n}\in V$ Vektoren des $\mathbb{R}$-[[Vektorraum|Vektorraumes]] $V$. Dann ist die [[Mengen|Menge]] aller [[Vektorraum#Linearkombination|Linearkombinationen]] der Vektoren $v_{1},\dots,v_{n}$ $$\text{span}_{\mathbb{R}}(v_{1},\dots,v_{n}):=\{ w\mid w=\lambda_{1} v_{1}+\dots+\lambda_{n}v_{n}\mid\lambda_{1},\dots\lambda_{n}\in \mathbb{R}\}\subseteq V$$
> ein [[Vektorraum#Untervektorräume|Untervektorraum]] von $V$. Mann nennt diese Menge das **lineare Erzeugnis** oder auch den **linearen Spann** der Vektoren $v_{1},\dots ,v_{n}$.

# Lineare Abhängigkeit
>[!def] Lineare Abhängigkeit
> Eine (endliche) [[Mengen|Menge]] von Vektoren $v_{1},\dots,v_{n}$ aus einem $\mathbb{R}$-Vektorraum $V$ heißt **linear unabhängig**, falls es nur eine einzige [[#Linearkombination]] der $v_{1},\dots,v_{n}$ gibt, welche den Nullvektor erzeugt:
> $$ \lambda_{1}v_{1}+\dots+\lambda_{n}v_{n}=o$$
> [[Notwendige vs hinreichende Bedingung#Notwendige Bedingung|Notwendigerweise]] ist dies dann eine [[#Linearkombination]] mit $\lambda_{1}=\lambda_{2}=\dots=\lambda_{n}=0$.
> 
> ---
> Sind Vektoren *nicht* linear unabhängig, so heißen sie **linear abhängig**.
> D.h. sobald der Nullvektor aus einer weiteren Linearkombination erzeugbar ist, in welcher *mindestens ein* Koeffizient ungleich Null ist besteht lineare Abhängigkeit.
> Ebenfalls äquivalent ist die Frage, ob sich mindestens ein Vektor als Linearkombination der anderen darstellen lässt.
## Bemerkungen
- Eine Menge, welche den Nullvektor enthält ist *immer* linear abhängig: Vor dem Nullvektor kann ein beliebiger Skalar gewählt werden und alle anderen Skalare können gleich Null sein.
  Der Nullvektor ist linear abhängig mit sich selbst.
- Klassisches Beispiel für lineare Unabhängigkeit sind die Einheitsvektoren
