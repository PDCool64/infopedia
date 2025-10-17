
>[!def] Mengen
>Eine Menge ist eine Ansammlung von *unterscheidbaren* Objekten, genannt *Elemente* der Menge. Eine Menge wird durch eine Vorschrift festgelegt, die eindeutig bestimmt, ob ein gegebenes Objekt ein Element der Menge ist oder nicht. Die Elemente der Menge haben *keine* Reihenfolge und werden *nicht* mehrfach gezählt.
>
#### Beispiele:
- Die Menge der [[Zahlenräume#Natürliche Zahlen $ mathbb{N}$|Natürlichen Zahlen]] $1,2,3,4,\dots$
- Die Menge der Zahlen $1,3,18,\pi$.
- Die Menge der Buchstaben $a,b,\sigma,k.$
- Die Menge der Orangen und Zitronen (Es geht um die *Idee* der Zitronen bzw. Orangen, nicht um alle einzelnen Früchte. Die Menge hat 2 Elemente)

# Definieren einer Menge
Neben den oben gelisteten [[#Beispiele|Beispielen]], bei denen eine Menge durch *Aufzählung aller Elemente* definiert wurde, kann eine Menge auch durch eine *Vorschrift* definiert werden:
$$
M:=\{ x:S(x) \}
$$
was bedeutet : "$M$ ist die Menge aller $x$, welche die Eigenschaft $S(x)$ erfüllen."

Bsp. ist die Menge der ungeraden natürlichen Zahlen wie folgt definierbar:
$$
M:=\{ x \mid x=2n+1 \text{ für ein }n\in \mathbb{N} \}
$$

# Schreibweisen:

| Schreibweise  | Bedeutung                                                  | Veranschaulichung                               |
| ------------- | ---------------------------------------------------------- | ----------------------------------------------- |
| $m\in A$      | $m$ ist ein Element von $A$                                | ![[Mengenlehre 2025-07-20 18.45.14.excalidraw]] |
| $m \not\in A$ | $m$ ist *kein* Element von $A$                             | ![[Mengen 2025-09-08 17.13.35.excalidraw]]      |
| $\#M$         | Mächtigkeit einer Menge.<br>Anzahl der Elemente der Menge. |                                                 |

^7f5fd0

# Grundliegende Operatoren:

| Schreibweise    | Definition                                                               | Bedeutung                                                                      | Veranschaulichung                               |
| --------------- | ------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ----------------------------------------------- |
| $A \cup B$      | $A\cup B=\{ x \mid (x\in A)\vee(x\in B) \}$<br><br>($A\cup B=B\cup A$)   | Vereinigungsmenge                                                              | ![[Mengenlehre 2025-07-20 18.49.58.excalidraw]] |
| $A \cap B$      | $A\cup B=\{ x \mid (x\in A)\wedge(x\in B) \}$<br><br>($A\cap B=B\cap A$) | Schnittmenge<br>(aka. "Durschschnitt")                                         | ![[Mengenlehre 2025-07-20 21.21.02.excalidraw]] |
| $A\setminus B$  | $A\setminus B=\{ x \mid (x\in A)\wedge(x \not\in B) \}$                  | Differenz<br>(aka "Komplement von $A$ in $B$",<br>aka "$A$ ohne $B$")          | ![[Mengen 2025-09-08 17.29.49.excalidraw]]      |
| $A \subseteq B$ | $A\subseteq B \iff \forall_{x\in A}\mid x\in B$                          | $A$ ist Teilmenge von oder gleich $B$.<br><br>($B$ ist eine Obermenge von $A$) | ![[Mengen 2025-09-08 17.32.00.excalidraw]]      |
| $A\subset B$    | $A\subset B \iff (\forall_{x\in A}\mid x\in B)\wedge (A\neq B)$          | $A$ ist eine echte Teilmenge von $B$                                           | ![[Mengen 2025-09-08 17.44.31.excalidraw]]      |
| $A\times B$     |                                                                          | [[#Kartesisches Produkt]] von $A$ und $B$                                      |                                                 |

^d190a1

^ec070c
# Leere Menge
> [!def] Leere Menge
> Die Menge, die keine Elemente enthält, heißt *leere Menge* $\emptyset$ oder $\{ \; \}$.

Die Leere Menge ist [[#^ec070c|Teilmenge]] jeder Menge, also $\emptyset \subseteq M$ für jede Menge $M$.

# Potenzmenge
>[!def] Potenzmenge
>Die [[#^ec070c|Teilmengen]] $A\subseteq M$ einer gegebenen Menge $M$ bilden ebenfalls eine Menge, die *Potenzmenge* $\mathcal{P}(M):= \{ A \mid A\subseteq M \}$ von $M$. 

Zu beachten:
- Da die [[#Leere Menge]] Teilmenge *aller* Mengen ist, enthält jede Potenzmenge die leere Menge.
  $\emptyset\in\mathcal{P}(M)$
  
- $M\in \mathcal{P}(M)$
  
Ist die [[#^7f5fd0|Mächtigkeit]] von $M$ endlich, etwa $\#M=n$, so ist die Mächtigkeit der Potenzmenge
$\#\mathcal{P}(M)=2^n.$
	(Intuition dahinter: Beim Bilden einer Teilmenge von $M$ hat man für jedes Element von $M$ die Option 1. Das Element zu nehmen oder 2. Das Element nicht zu nehmen. - Damit entstehen $2^{n}$ Optionen.)

Beispiel:
	Sei $M=\{ 1,2,3 \}$. Dann ist 
	$\mathcal{P}(M)=\{ \emptyset,\{ 1 \},\{ 2 \},\{ 3 \},\{ 1,2 \},\{ 1,3 \},\{ 2,3 \},\{ 1,2,3 \} \}$

# Kartesisches Produkt
>[!def] Kartesisches Produkt
>Sind $A$ und $B$ zwei Mengen, so heißt die Menge aller *geordneten Paare*
>$$A\times B:=\{ (a,b):a \in A,b\in B \}$$
>das *kartesische Produkt der Mengen A und B*.
>
>Für *mehr als zwei* Mengen:
>Sind $n$ Mengen $A_{1},A_2,A_{n}$ gegeben, so bilden die *geordneten* $n$-Tupel das kartesische Produkt
>$$A_{1}\times\dots\times A_{n}:=\{ (a_{1},a_{2},\dots,a_{n}):a_{i} \in A_{i} \text{ für }i=1,\dots,n \}$$
>der Mengen $A_{1},\dots,A_{n}$ (in dieser Reihenfolge).
>
>
>
 Sind die Mengen gleich,so schreiben wir
>$$A^n=A\times\dots\times A$$

Zu beachten:
*geordnete* $n$-Tupel bedeutet, dass die Reihenfolge der Einträge wichtig ist.
  (vgl. Tuple in Python usw.)
  
### Beispiele:
- $\{ a,b \}\times \{ 1,2 \}=\{ (a,1),(a,2),(b,1),(b,2) \}$ ist ungleich zu 
- $\{ 1,2 \}\times \{ a,b \}=\{ (1,a),(1,b),(2,a),(2,b) \}$

- Ist $M=\{ a,b,c,\dots,h \}$ und $N=\{ 1,2,3,\dots, 8 \}$, so sind die Elemente von $M\times N$ genau die Felder eines Schachbretts

- Das "*kartesische* Koordinatensystem" der reellen Zahlen $\mathbb{R}^{2}=\mathbb{R}\times \mathbb{R}$ ist das kartesische Produkt der Menge der reellen Zahlen mit sich selbst: Es erzeugt alle Koordinatenkombinationen $(x,y)$.

```tikz
\usepackage{amssymb}  % oder amsfonts
\begin{document}
  \begin{tikzpicture}
    % Achsen
    \draw[->] (-0.5,0) -- (3,0) node[right] {\(\mathbb{R}\)};
    \draw[->] (0,-0.5) -- (0,3) node[above] {\(\mathbb{R}\)};
    
    \fill (1,2) circle (2pt) node[above right] {$(x,y)$};
    \fill (2,1) circle (2pt) node[above right] {$(y,x)$};
    
    \draw[dashed] (0,2) -- (1,2);
    \draw[dashed] (1,2) -- (1,0);
    
    \draw[dashed] (0,1) -- (2,1);
    \draw[dashed] (2,1) -- (2,0);
    
    \node (a) at (1,-0.2) {x};
    \node (a) at (-0.2,2) {y};
    
    \node (a) at (2,-0.2) {y};
    \node (a) at (-0.2,1) {x};
    
    
    
  \end{tikzpicture}
\end{document}
```
