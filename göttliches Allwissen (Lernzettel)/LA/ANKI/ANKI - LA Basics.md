TARGET DECK: LA::Basics

Paare an multiplikativen inversen in $\mathbb{F}_{7}$ #flashcard
$2 \leftrightarrow 4$
$3 \leftrightarrow 5$
$6 \leftrightarrow 6$
<!--ID: 1786031414982-->

Paare an multiplikativen inversen in $\mathbb{F}_{11}$ #flashcard
$2 \leftrightarrow 6$
$3 \leftrightarrow 4$
$5 \leftrightarrow 9$
$7 \leftrightarrow 8$
$10 \leftrightarrow 10$
<!--ID: 1786031414986-->

Definiere das Signum einer Permutation #flashcard
$\text{sgn}(\pi)=(-1)^{\text{Anzahl Transpositionen}}$
<!--ID: 1786205085809-->


Welchen Effekt haben **Links-** bzw. **Rechtsmultiplikation** mit einer invertierbaren Matrix jeweils auf den Spaltenraum? #flashcard
Rechtsmultiplikation : Spaltenraum bleibt GLEICH
Linksmultiplikation : Spaltenraum bleibt ISOMORPH
<!--ID: 1786205085821-->


An welche Seite einer Matrix werden die Matrizen für **Zeilen**- bzw. **Spaltenoperationen** jeweils multipliziert. #flashcard
Zeilenoperationen = LINKS
Spaltenoperationen = RECHTS
<!--ID: 1786205085837-->

3 Sanity Checks: **Bild und Kern** #flashcard
1. Rangsatz
2. Basisvektoren des Kerns einsetzen: $Av_{i}=0$ ?
3. $\det(A_{a})=0\iff\text{Kern}(A_{a})\neq \{ 0 \}$
<!--ID: 1786376481720-->


2 Sanity Checks: **Determinanten** #flashcard
1. Grad plausibel?
2. Abgleich beide Richtungen:
	1. Nullstellen einsetzen: ensteht lineare Abhängigkeit?
	2. Offensichtliche lineare Abhängigkeiten auch Nullstellen?
<!--ID: 1786376481725-->


4 Sanity Checks: **Eigenwerte** #flashcard
1. Summe der Eigenwerte inkl. *algebraischen* Vielfachheiten = $tr(A)$
2. Produkt der Eigenwerte inkl. algebraischen Vielfachheiten $=\det(A)$
3. Summe der algebraischen Vielfachheiten selbst: $n=\sum m_{e}(A)$
4. Eigenraum-Basisvektoren einsetzten: $Av_{i}=\lambda v_{i}$ ?
<!--ID: 1786376481729-->


4 Sanity Checks: **Charakteristisches Polynom**
1. $deg(X_{a})=n$ bei $n\times n$ Matrix
<!--ID: 1786377428645-->

2. Leitkoeffizient $=1$
3. Zweiter Koeffizient: $-tr(A)=-\sum_{i=1}^{n}a_{ii}$
<!--ID: 1786376481736-->

4. Konstanter Summand: $(-1)^{n}\det(A)$
<!--ID: 1786376481740-->

Wie lautet die Leibniz-Formel #flashcard
$$
\det(A):= \sum_{\pi\in S_{n}}\text{sgn}(\pi) \prod_{i=1}^{n}a_{i,\pi(i)}
$$
<!--ID: 1786622039012-->

Vorgehen, wenn eine zu $A$ ähnliche Diagonalmatrix $D$ und die passenden $T\;,\;T^{-1}$ gesucht sind: #flashcard
Ziel: $D=T^{-1}AT$
Bestimme:
- Eigenwerte $\lambda_{1},\dots,\lambda_{n}$ (mehrfache Verwendung erlaubt)
- **Linear unabhängige** Eigenvektoren $e_{1},\dots, e_{n}$  sodass $Ae_{i}=\lambda_{i}e_{i}$ 
$$D=\begin{pmatrix}\lambda_{1} &  & \dots & 0 \\
 & \lambda_{2} & &\vdots \\
  \vdots&  & \ddots \\
 0 & \dots &  & \lambda_{n}\end{pmatrix}$$
$$
T=\begin{pmatrix}
e_{1} \mid e_{2} \mid \dots\mid e_{n}
\end{pmatrix}
$$ $T^{-1}$ falls gefordert durch normales invertieren bestimmen.
<!--ID: 1786625269236-->


Wie viele Elemente enthält die allgemeine lineare Gruppe $\text{GL}_{n}(\mathbb{F}_{q})$ über einem endlichen Körper mit $q$ Elementen? #flashcard
$$\left| \text{GL}_{n}(\mathbb{F}_{q}) \right|=\prod_{i=0}^{n-1}(q^{n}-q^{i})$$
<!--ID: 1786625269264-->

