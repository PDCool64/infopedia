---
"date:": 2025-10-17
tags:
  - AFI
status: rot
Ab Folie: 14
Bis Folie:
---

# Hierarchie der Zahlenberreiche


$\mathbb{N} \subset \mathbb{N}_{0} \subset \mathbb{Z} \subset \mathbb{Q} \subseteq \mathbb{R}$

## bsp. Gerade und ungerade Zahlen
$2\mathbb{Z}=\{ 2x \mid z\in \mathbb{Z} \}$ gerade Zahlen, 

Mit (Afaik: Komplement) $(2\mathbb{Z})^{C}=C_{\mathbb{Z}}(2\mathbb{Z})=\mathbb{Z} \setminus2\mathbb{Z}$  die ungeraden Zahlen.


# Vereinigungen/Schnitte mehrerer Mengen:

$$\bigcup_{_{i\in I}}M_{i}:=\{ x \mid x\in M_{j}\text{ für EIN }j\in I \} $$

interressant: das "scope" der indexe : vergleiche, wie in der obigen schreibweise i und j unterschiedliche Variablen in unterschiedlichen Kontexten sind. (In der Skript-Version wurden die beide aber einfach gleich benannt)

(sh. Def. 2.21)

# Potenzmenge

$\text{Pot}(M)=\{ A\mid A \subset M \}$

wegen dem Lemma [[V03 - Mengen#^884841]] ist die Leere Menge in jeder Potenzmenge enthalten.

alles wie gehabt

$\text{Pot}(\;\{ \{ \emptyset \} \}\;)=\{ \emptyset\;,\;\{ \{ \emptyset \} \}\; \}$

# Kartesisches Produkt

Haben "Geordnete Paare"/Tuple gemacht.
Zwei geordnete Paare $(a,b)$ und $(x,y)$ sind gleich $\iff$ $a=x\wedge b=y$

$$
M\times N:=\{ (a,b)\mid a\in M , b\in N \}
$$
Für beliebig viele Mengen:

$r\geq 2$  $M_{1},\dots,M_{r}$ dann ist der $r$-Tuple $(a_{1},\dots,a_{r})$   $a_{i}\in M_{i}$   $1\le i le r$

$$M_{1} \times M_{2} \times \dots \times M_{r}= \bigtimes_{i\in I}= \bigtimes_{i=}^{r}=\bigtimes_{1\le i \le r}$$
$I=\{ 1,\dots,r \}$

> vgl. die verschiedenen Schreibweisen für die Indexe, welche alle ok sind


Kurzschreibweise:


kartesisches Produkt zweier Intervalle auf $\mathbb{R}$:
![[V04 -  Mehr Mengenoperationen 2025-10-17 09.03.34.excalidraw]]


# Quantoren

für die Lesbarkeit ist es hier voll fine Quantoren auch *hinter* Aussagen zu schreiben, nicht strikt formal immer an den Anfang.


# Ein Lemma:

Sei $A$ eine Menge und $A(x)$ eine Aussage für $x\in A$ : 
Dann gilt: $\neg(\forall_{x\in A}:A(x)) \iff \exists_{x\in A}:\neg A(x)$


---

# Frage:

$\{ 0,1 \}\times \{ a,b \}\times \{ x,y \}$
vs.
$\big(\{ 0,1 \}\times \{ a,b \}\big)\times \{ x,y \} \;=\; \{ (0,a),(0,b),(1,a),(1,b) \} \times \{ (x,y) \}=\{ ((0,a),x),((0,b),x),\dots \}$

Erklärung: In unserem Kontext sind verschachtelte Tupel irrelevant: Egal wie man Tupel verschachtelt - die *Reihenfolge der Elemente* bleibt eindeutig:

$(a,b,c,d)=((a,b),c,d)=(a,((b,c),d))$#


