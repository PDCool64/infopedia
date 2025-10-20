---
"date:": 2025-10-15
tags:
  - AFI
status: rot
Ab Folie: 10
Bis Folie: 14
---
---

Wir machen hier nur eine "naive" Definition von Mengen - (Eine Richtige Definition kriegen wir erst in MALO oder so später)
>[!def] Menge (Arbeitsdefinition)
> Eine Menge ist eine Zusammenfassung von wohl bestimmten Objekten zu einem Ganzen. Die Objekte nennt man Elemente der Menge. Die Wohlbestimmtheit besagt, dass man bei jedem Objekt genau entscheiden kann, ob es zur Menge gehört oder nicht.

Für den AFI Prof werden mengen immer mit GROẞBUCHSTABEN bezeichnet: $M=\{ x,y,\mathbf{z}\dots \}$

## Definieren von Mengen
- Auflisten der Elemente, ggfs. mit $\dots$ (wenn intuitiv / eindeutig klar ist, was gemeint ist)
- Mengenbauen: $M=\{ x \mid x \text{ hat Eigenschaft E} \}$ d.h. $M$ besteht aus allen Elementen, die die Aussage erfüllen d.h. für die eine Aussage zutrifft.

Dann $\in$ , $\not\in$ sowie $\emptyset=\{  \}=\{ x \mid x\neq x \}$ eingeführt.


# Zahlenbereiche in Mengenschreibweise

natürliche Zahlen hier -solange nicht explizit erwähnt- hier immer ohne $0$
ganze Zahlen wie gehabt

Auf unserem Niveau - wir werden hier nicht auf die Fundamente der Mathematik zurückgehen - nehmen wir die natürlichen Zahlen als von Gott gegeben an.

Rationalen Zahlen hier schön:
$\mathbb{Q}=\left\{  x\mid\text{ es gibt ganze Zahlen }a,b,b\neq_{0},x=\frac{a}{b}  \right\}$
$\mathbb{Q}=\left\{  x=\frac{a}{b}\mid b\in \mathbb{Z},b\neq 0 , a\in \mathbb{Z}  \right\}$

### Reelle Zahlen

$\mathbb{R}=\{ x \mid x \text{ ist eine Dezimalzahl, mit endlich oder unendlich vielen Nachkommastellen} \}$

Richtige Definition kommt noch

Schreibweisen: (findet der Prof selbst Scheiße - Lieber Explizit $\mathbb{R} \setminus \{ 0 \}$ usw explizit und unmissverständlich schreiben)
$\mathbb{R}_{+}$ sind die nicht negativen reellen Zahlen
$\mathbb{R}_{+}^{*}$ sind positive reelle Zahle
$\mathbb{R}^{*}$ sind die reellen Zahlen ohne $0$

# Unendlichkeit
$\infty$ ist keine Zahl
$\infty \not\in \mathbb{R}$

Es ist ein Symbol, Schall und Rauch, Notation usw. ,,, das eigentlich nur für Limits steht.
"Keine Schranke nach Oben"


# Intervalle
- geschlossenes Intervall
- offenes Intervall
- halboffene Intervalle

Weil $\infty$ keine Zahl ist :
$(-\infty,a]=\{ x\in \mathbb{R} \mid x\leq a \}$
... und die weiteren Kombinationen

Interessanter:
$(-\infty,\infty)=\mathbb{R}$


## höher-dimensionaler Zahlenräume

$\mathbb{R}^{2},\mathbb{R}^{3}$

$$
\mathbb{R}^{2}=\{  \begin{pmatrix}
a \\
b
\end{pmatrix} \mid a,b\in \mathbb{R} \}
$$
d.h. Menge aller *geordneten* Paare reeller Zahlen (vgl. Kartesisches Produkt)

$$
\mathbb{R}^{3}=\{ \begin{pmatrix}
a \\
b \\
c
\end{pmatrix} \mid a,b,c \in \mathbb{R} \}
$$

d.h. Menge aller *geordneten* Triple 

geht für beliebige natürliche Zahlen anstatt 2 oder 3 genauso

## Mächtigkeit von Mengen

Mächtigkeit = Ordnung = Kardinalität alles Begriffe für die Anzahl der Elemente einer Menge![[Pasted image 20251015152535.png]]![[Pasted image 20251015152543.png]]

paarweise verschieden muss man ein bsl grübeln

Ich will sagen: Anzahl der Elemente der Menge
Wie kriege ich aber aus der Komischen Mengendefinition eine natürliche Zahl als Mächtigkeit raus.


# Differenz, Vereinigung Durchschnitt

> $:=$ bedeutet "definiert als"

nix neues

disjunkte Mengen nochmal explizit erwähnt
# Teilmengenzeichen
Für den Zweck dieser Vorlesung
$\subset=\subseteq$
Wenn es um echte Teilmengen geht, wird EXPLIZIT der _ durchgestrichen:

![[V03 - Mengen 2025-10-15 15.59.14.excalidraw|50]]

---
Wdh. Frage aus dem Plenum von de letzten Vorlesung: ^884841

Teilemenge: $A \subset B := x\in A \implies x\in B$

Frage: $\emptyset\subset A$ ? 

Mit dem Fakt, dass aus Falschen Aussagen alles gefolgert werden kann:
$x\in \emptyset \implies x\in A$ wobei $x\in \emptyset$ eine falsche Aussage ist.

Alternativ mit Kontraposition: $(A\implies B)\iff \neg A\implies \neg B$
$x \not\in B \implies x \not\in \emptyset$


