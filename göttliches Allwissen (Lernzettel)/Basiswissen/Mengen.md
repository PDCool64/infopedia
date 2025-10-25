
>[!def] Mengen
>Eine Menge ist eine Ansammlung von *unterscheidbaren* Objekten, genannt *Elemente* der Menge. Eine Menge wird durch eine Vorschrift festgelegt, die eindeutig bestimmt, ob ein gegebenes Objekt ein Element der Menge ist oder nicht. Die Elemente der Menge haben *keine* Reihenfolge und werden *nicht* mehrfach gezählt. (grob nach *[Georg Cantor](https://de.wikipedia.org/wiki/Georg_Cantor), 1895*)
>
>---
>Das einzige was eine Menge ausmacht ist, dass man für jedes Beliebige Objekt entscheiden kann, ob es zur Menge gehört oder nicht.
>
>---
>Im Rahmen der DS-Vorlesung schließen wir uns der [*Zermelo-Fraenkel-Mengenlehre*](https://de.wikipedia.org/wiki/Zermelo-Fraenkel-Mengenlehre) an.
#### Beispiele:
- Die Menge der [[Zahlenräume#Natürliche Zahlen $ mathbb{N}$|Natürlichen Zahlen]] $1,2,3,4,\dots$
- Die Menge der Zahlen $1,3,18,\pi$.
- Die Menge der Buchstaben $a,b,\sigma,k.$
- Die Menge der Orangen und Zitronen (Es geht um die *Idee* der Zitronen bzw. Orangen, nicht um alle einzelnen Früchte. Die Menge hat 2 Elemente)

### Verbindung zur [[Aussagenlogik]]
Der Satz der Definition *"Das einzige was eine Menge ausmacht ist, dass man für jedes Beliebige Objekt entscheiden kann, ob es zur Menge gehört oder nicht."* bedeutet, dass Mengen genau dadurch gekennzeichnet sind, dass $(x\in M)$ für jedes konkrete Objekt $x$ eine [[Aussagenlogik|Aussage]] mit eindeutigem Wahrheitswert ist.

Umgekehrt ist für *jede* [[Aussagenlogik#Aussageformen|Aussageform]] $A(x)$ die Zusammenfassung aller $x$, für die $A(x)$ wahr ist, eine Menge.
## Probleme mit dieser Mengendefinition
Mit dieser einfachen Mengendefinition sind einige Konstrukte als Menge zulässig, die zu Widersprüchen führen. Wenn man tiefer in die Theorie hinabsteigen würde, gäbe es eine rigorosere Definition die wir aber nicht behandeln werden (vielleicht in MaLo oder so idk).
In seinem Mathematischen System will man eigentlich keine Widersprüche drin haben.

Eine solche Konstruktion ist: $M=$"Die Menge aller Mengen, die sich nicht selbst enthalten"
- wenn sich $M$ nicht selbst enthält, gehört $M$ zu der Gruppe der sich nicht selbst enthaltenden Mengen. $M$ muss sich also selbst enthalten ... 
- symbolisch aufgeschrieben: Angenommen es gäbe eine Menge $A$ aller Mengen. Dann betrachten wir $T:=\{ M\in A \mid M \not\in M \}$. Es stellt sich nun die Frage $T\in T$ ? Diese Frage stellt einen Widerspruch dar. 

> Wenn man viel Zeit hat, kann man zu diesem Thema, der [Russelschen Antinomie](https://de.wikipedia.org/wiki/Russellsche_Antinomie) was nachlesen. Auch Interessant ist hier [[Skript Diskrete Strukturen.pdf#page=13|Seite 11 des Skripts für DS]].

$\to$ Für ein rigoroseres System sollte man einige Mengenkonstruktionen ausschließen.

---
# Aufschreiben einer Menge
Neben den oben gelisteten [[#Beispiele|Beispielen]], bei denen eine Menge durch *Aufzählung aller Elemente* definiert wurde, kann man Mengen auch wie folgt konstruieren:
## Durch Aussondern
$$
M:=\{ x\in N\mid S(x) \}
$$
was bedeutet : "$M$ ist die Menge aller $x$ aus $N$, welche die Eigenschaft $S(x)$ erfüllen."

> Formal ist diese "Vorschrift" eine [[Aussagenlogik#Aussageformen|Aussageform]]. (s.h. ebenfalls [[#Verbindung zur Aussagenlogik]])

z.B. ist die Menge der ungeraden natürlichen Zahlen wie folgt definierbar:
$$
M:=\{ x \in \mathbb{N}\mid x=2n+1 \text{ für ein }n\in \mathbb{N} \}
$$
## Durch Abbilden
Sei $f$ eine [[Abbildungen|Abbildung]], die jedem $x\in N$ ein Element aus $L$ zuordnet, dann ist $$
M:=\{ f(x) \mid x\in N\}
$$ eine neue Menge (und eine Teilmenge von $L$).

z.B. ist die Menge der Quadratzahlen wie folgt definierbar:
$M:=\{ n^{2} \mid n\in \mathbb{N} \}$

## Beides gemischt:
Man kann z.B. die Menge der Quadrate ungerader Zahlen schreiben als:
$M:=\{ n^{2} \mid (n\in \mathbb{N} )\wedge(\text{"n ist ungerade"}) \}$


# Schreibweisen:

| Schreibweise  | Bedeutung                      | Veranschaulichung                                    |
| ------------- | ------------------------------ | ---------------------------------------------------- |
| $m\in A$      | $m$ ist ein Element von $A$    | ![[Mengenlehre 2025-07-20 18.45.14.excalidraw\|200]] |
| $m \not\in A$ | $m$ ist *kein* Element von $A$ | ![[Mengen 2025-09-08 17.13.35.excalidraw\|200]]      |

# Grundliegende Operatoren:

## Bilden neuer Mengen

| Schreibweise   | Definition                                                                | Bedeutung                                                             | Veranschaulichung                               |
| -------------- | ------------------------------------------------------------------------- | --------------------------------------------------------------------- | ----------------------------------------------- |
| $A \cup B$     | $A\cup B:=\{ x \mid (x\in A)\vee(x\in B) \}$<br><br>($A\cup B=B\cup A$)   | Vereinigungsmenge                                                     | ![[Mengenlehre 2025-07-20 18.49.58.excalidraw]] |
| $A \cap B$     | $A\cup B:=\{ x \mid (x\in A)\wedge(x\in B) \}$<br><br>($A\cap B=B\cap A$) | Schnittmenge<br>(aka. "Durschschnitt")                                | ![[Mengenlehre 2025-07-20 21.21.02.excalidraw]] |
| $A\setminus B$ | $A\setminus B:=\{ x \mid (x\in A)\wedge(x \not\in B) \}$                  | Differenz<br>(aka "Komplement von $A$ in $B$",<br>aka "$A$ ohne $B$") | ![[Mengen 2025-09-08 17.29.49.excalidraw]]      |
| $A\times B$    | $A\times B:=\{ (a,b)\mid a\in ,b\in B \}$                                 | [[#Kartesisches Produkt]] von $A$ und $B$                             |                                                 |

^d190a1
^ec070c

>[!def] Vereinigung und Schnitt mehrerer Mengen
> Vereinigungs- und Schnittmenge können auch allgemeiner für beliebig viele Mengen geschrieben werden:
> Für eine endliche Indexmenge $I$ und Mengen $M_{i}$ bezeichnen wir
> $$\bigcup_{i\in I}M_{i}:=\{ x \mid \exists_{j\in I}:x\in M_{j} \}$$ als *Vereinigung* alle Mengen $M_{i}$ für $i\in I$ und
> $$\bigcap_{i\in I}M_{i}:=\{ x \mid \forall _{j\in I}:x\in M_{j} \}$$
> als *Schnitt* über alle Mengen $M_{i}$ für $i\in I$.


## Verknüpfen zu einer [[Aussagenlogik|Aussage]]:

| $A \subseteq B$ | $A\subseteq B \iff \forall_{x\in A}: x\in B$<br>bzw.<br>$A\subseteq B \iff(x\in a\to x\in B)$ | $A$ ist Teilmenge von oder gleich $B$.<br><br>($B$ ist eine Obermenge von $A$) | ![[Mengen 2025-09-08 17.32.00.excalidraw]] |
| --------------- | --------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ | ------------------------------------------ |
| $A⊊ B$          | $A⊊ B \iff (\forall_{x\in A}:x\in B)\wedge (A\neq B)$                                         | $A$ ist eine echte Teilmenge von $B$                                           | ![[Mengen 2025-09-08 17.44.31.excalidraw]] |
>[!wip]
> 
> Hier muss man -je nach Prof/Modul- die Schreibweisen für Teilmengen unterscheiden.

|     | "Teilmenge von oder gleich"                     | "echte Teilmenge"                               |
| --- | ----------------------------------------------- | ----------------------------------------------- |
| DS  | ![[Mengen 2025-10-19 15.18.53.excalidraw\|100]] | Noch nicht bekannt<br>(AFAIK)                   |
| AFI | ![[Mengen 2025-10-19 15.18.53.excalidraw\|100]] | ![[Mengen 2025-10-19 15.18.12.excalidraw\|100]] |
# Leere Menge
> [!def] Leere Menge
> Die Menge, die keine Elemente enthält, heißt *leere Menge* $\emptyset$ oder $\{ \; \}$.

Die Leere Menge ist [[#^ec070c|Teilmenge]] jeder Menge, also $\emptyset \subseteq M$ für jede Menge $M$.


# Mächtigkeit einer Menge

>[!def] Mächtigkeit einer Menge
> Sei $M$ eine nicht-leere Menge. Gibt es [[paarweise verschiedene]] Elemente $x_{1},\dots,x_{n}$ mit $n\in \mathbb{N}$, sodass $M=\{ x_{1},x_{2},\dots,x_{n} \}$, so definiert man die **Mächtigkeit** $\#M$, auch geschrieben als $|M|$ als:
> $$
> \#M:=n
> $$ 
> 
> Andernfalls setzt man $\#M=\infty$ .
> Man definiert $\#\emptyset:=0$ 
> 
> ---
> Man nennt die **Mächtigkeit** einer Menge auch **Ordnung** einer Menge.

# Potenzmenge

>[!def] Potenzmenge
>Die [[#^ec070c|Teilmengen]] $A\subseteq M$ einer gegebenen Menge $M$ bilden ebenfalls eine Menge, die **Potenzmenge** $\mathcal{P}(M):= \{ A \mid A\subseteq M \}$ von $M$. 
>
>---
>Eine weitere Schreibweise ist $\text{Pot}(M)$

Zu beachten:
- Da die [[#Leere Menge]] Teilmenge *aller* Mengen ist, enthält jede Potenzmenge die leere Menge.
  $\emptyset\in\mathcal{P}(M)$
  (Dies sieht man an der Teilmengenbeziehung und der Def. der [[Aussagenlogik#Implikation und Äquivalenz|Implikation]]: 
  $(\emptyset\subseteq M)\iff(x\in \emptyset\implies x\in M)\iff(\text{ f}\implies x \not\in A)$ was eine wahre Aussage ist.
  
- $M\in \mathcal{P}(M)$
  
Ist die [[#Mächtigkeit einer Menge|Mächtigkeit]] von $M$ endlich, etwa $\#M=n$, so ist die Mächtigkeit der Potenzmenge
$\#\mathcal{P}(M)=2^n.$
	(Intuition dahinter: Beim Bilden einer Teilmenge von $M$ hat man für jedes Element von $M$ die Option 1. Das Element zu nehmen oder 2. Das Element nicht zu nehmen. - Damit entstehen $2^{n}$ Optionen.)

Beispiel:
	Sei $M=\{ 1,2,3 \}$. Dann ist 
	$\mathcal{P}(M)=\{ \emptyset,\{ 1 \},\{ 2 \},\{ 3 \},\{ 1,2 \},\{ 1,3 \},\{ 2,3 \},\{ 1,2,3 \} \}$

# Kartesisches Produkt
>[!def] Kartesisches Produkt
>Sind $A$ und $B$ zwei Mengen, so heißt die Menge aller *geordneten Paare*
>$$A\times B:=\{ (a,b)\mid a \in A,b\in B \}$$
>das *kartesische Produkt der Mengen A und B*.
>
>Für *mehr als zwei* Mengen:
>Sind $n$ Mengen $A_{1},A_2,A_{n}$ gegeben, so bilden die *geordneten* $n$-Tupel das kartesische Produkt
>$$A_{1}\times\dots\times A_{n}:=\{ (a_{1},a_{2},\dots,a_{n})\mid a_{i} \in A_{i} \text{ für }i=1,\dots,n \}$$
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
