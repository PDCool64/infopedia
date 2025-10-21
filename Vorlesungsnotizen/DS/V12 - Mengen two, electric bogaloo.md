---
date: 2025-10-21
tags:
  - DS
status: rot
Vorlesungsfolien:
Skriptfolien: "[[Skript Diskrete Strukturen.pdf]]"
---
---

Varianten um Mengen zu definieren
- Aufzählung  $\{ 1,-12.3 \}$
- Beschreibung durch Worte : Menge der natürlichen Zahlen
- Aussondern : $\{ x\in \mathbb{N}\mid x \text{ ist ungerade} \}$
- Abbilden : $\{ n^{2}\mid n\in \mathbb{N} \}$ (vgl. Bild einer Menge unter einer Abbildung)


# Ergänzung: Quantoren sind Aussagen und keine Aussageformen.

Auch wenn eine variable "x" darin vorkommt, sind Quantoren *Aussagen* (und keine Aussageformen!)  - Denn bei $\forall_{x\in \mathbb{N}}:A(x)$ ist $x$ keine "freie" Variable mehr. s.h. [[Skript Diskrete Strukturen.pdf#page=15]]

# Im Westen nichts neues
Mengen zu neuen Mengen verknüpfen ist wie immer:
$M\cap N=\{ x\mid x\in M\wedge x\in N \}$
$M\cup N$
$M\setminus N$
$M\times N$
$\text{Pot}(M)$

Bei der Teilmengenbeziehung könnte man zur übung nochmal per Kontraposition beweisen, dass $\emptyset \subseteq M\text{ für alle } M$

Zum kartesischen Produkt neu:
Kartesisches Produkt mit der leeren Menge:
$$
\emptyset \times M=M \times \emptyset= \emptyset \text{ für jede Menge }M
$$

> Daily Fun-fact: der Wortstamm "kartesisch" kommt von [René Descartes](https://de.wikipedia.org/wiki/Ren%C3%A9_Descartes) 
> Fände es lustiger, wenn es von Karthago käme.

Haben nochmal erklärt warum die Potenzmenge $2^{n}$ Elemente hat:
Man hat für jedes Element die Entscheidung, ob man das Element in die momentane Teilmenge 1) nimmt 2) weglässt.  Es gibt $2^{n}$ Varianten diese -für jedes Element von einander unabhängige- Entscheidungen zu treffen.

# Rechenregeln beim Verknüpfen von Mengen
$L,M,N$ Mengen
- Assoziativgesetze
- Kommutativgesetze
- Distributivgesetz

>Was daran auch wichtig ist, dass wir diese/solche Gesetze bald auf abstraktere/komischere Objekte anwenden/übertragen/verallgemeinern werden.

# Indexmengen

> Jede Menge kann eine Indexmenge sein. "Indexmenge" sagt nur aus, dass wir die Menge zum *Zweck* der Indizierung *verwenden*.

Es sei $n\in \mathbb{N}$
Für Zahlen $a_{1},\dots,a_{n}$ 
und Mengen $M_{1},\dots M_{n}$
und Aussagen $A_{1},\dots A_{n}$

Summenzeichen: (großes Sigma)
$$
\sum _{i=1}^{n}a_{i}:=a_{1}+a_{2}+\dots+a_{n}
$$
Produktzeichen: (großes Pi)
$$
\prod_{i=1}^{n}a_{i}:=a_{1}\cdot a_{2} \cdot \;\cdots\;\cdot a_{n}
$$
Packt man in ein Produktzeichen Mengen rein, würde man das als Kartesisches Produkt interpretieren. Schöner ist aber $\bigtimes _{i=1}^{n}$ 

Neu:
Für Vereinigungs- und Schnittmengen:

$$
x\in\bigcup_{i\in I}M_{i}:\iff \exists_{i\in I}:x\in M_{i}
$$

$$x\in \bigcap_{i\in I}M_{1}:\iff \forall_{i\in I}:x\in M_{i}$$

# paarweise verschieden:
>[!def] paarweise verschieden
> Sei $I$ eine (Index)Menge und für jedes $i\in I$ sei $x_{i}$ ein Objekt.
> 
> Die Objekte $x_{i},i\in I$ heißen paarweise verschieden, wenn für alle $i,j\in I$ gilt:
> $$
> x_{i}=x_{j}\implies i=j
> $$

Zur Übung: Wir machen daraus mal mit Kontraposition eine neue Interpretation:
$i\neq j\implies x_{i}\neq x_{j}$
Diese ist auch schön intuitiv.

Bsp. :
Indexmenge: $i\in \mathbb{N}$ 

Paarweise verschieden sind:
$x_{i}=i^{2}$
...


# paarweise disjunkt bei Mengen
Sei $I$ eine Menge und für jedes $i\in I$ sei $M_{i}$ eine Menge.
Die $M_{i},i\in I$ heißen paarweise disjunkt, wenn für alle $i,j\in I$ mit
$i\neq j$ gitl: $M_{i} \cap M_{j}=\emptyset$

gutes bsp. s.h. [[#Mengenpartitionen]]

---

# Mengenpartitionen

## Etwas mit Primzahlen

Lesestoff, wenn man zeit hat : "Fundamentalsatz der Arithmetik"

Erinnerungen $\mathbb{P}$: Menge der Primzahlen in $\mathbb{N}$ .
Beispiel:
Für $p\in \mathbb{P}$ sei $M_{p}:=\{ p^{n}\mid n\in N \}$ (d.h. die Menge aller Potenzen von $p$)

Aussage: Die mengen $M_{p},p\in \mathbb{P}$ sind paarweise disjunkt.

Mit Widerspruchsbeweis:
Angenommen, $M_{p}$ und $M_{p'}$ haben ein gemeinsames Element $x$, wobei $p\neq p'\in \mathbb{P}$ 

Dann ist $x=p^{n}$ für ein $n\in \mathbb{N}$ 
und $x=(p')^{m}$ für ein $m\in \mathbb{N}$

$\implies p^{n}=(p')^{m=x}$ ist Widerspruch, da $x\in \mathbb{N}$ nicht zwei verschiedene Primfaktorzerlegung haben kann. (Eindeutigkeit der Primfaktorzerlegung.)

## def: Partition

>[!def] Partition einer Menge
> Eine **Partition** einer Menge $M$ ist eine Menge $\mathcal{P}$ nicht-leerer, paarweise disjunkter Teilmengen von $M$ mit
> $$
> M= \bigcup_{C\in\mathcal{P}}C
> $$
> d.h. wir zerlegen die Menge in Teile, die sich gegenseitig nicht überschneiden.
> 
> ---
> 
Für jede Partition von $M$ ist $\mathcal{P}\subseteq\text{Pot}(M)\setminus\{ \emptyset \}$

z.B. sind mögliche Partitionen  der Menge $M=\{ 1,2,3,4 \}$ 
- $\mathcal{P}=\{ \{ 1,2 \},\{ 3,4 \} \}$
- $\mathcal{P}=\{ \{ 1,4 \},\{ 2,3 \} \}$
- $\mathcal{P}=\{ \{ 2 \},\{ 3,4,1 \} \}$
- $\mathcal{P}=\{ \{ 1 \},\{ 3,4 \} ,\{ 2 \}\}$
- $\mathcal{P}=\{ \{ 2 \},\{ 4 \} ,\{ 1 \},\{ 3 \}\}$

Für jede Partition von $M$ ist $\mathcal{P}\subseteq\text{Pot}\setminus\{ \emptyset \}$

z.B. kann man die Menge der natürlichen Zahlen in die Menge der geraden sowie die Menge der ungeraden Zahlen partitionieren.

Die einzige Partition von $\emptyset$ ist $\mathcal{P}=\emptyset$

## ein paar Folgen aus disjunkten Mengen und Partitionen

sind $M,N$ endliche, disjunkte Mengen, so gilt
$\left| M \cup N \right|=\left| M \right|+\left| N \right|$

Allgemeiner gilt für alle Mengen:
$\left| M \cup M \right|=\left| M \right|+\left| N \right|-\left| N\cap N \right|$, weil man die Elemente welche in beiden Mengen liegt doppelt zählen würde.

Bei den disjunkten Mengen ist Mächtigkeit der Schnittmenge aber 0 -fällt also weg.


Für beliebig viele *paarweise disjunkte* Mengen gilt:
$$\left|  \bigcup_{i=1}^{n} M_{i}\right|=\sum_{i=1}^{n}\left| M_{i} \right|$$

Ist $M$ eine endliche Menge und $\mathcal{P}$ eine Partitionen von $M$, dann ist
$$
\left| M \right| =\sum_{C\in\mathcal{P}}\left| C \right| 
$$
z.B.
$M= \underline{4}=\{ 1,2,3,4 \}$

mit $\mathcal{P}=\{ \{ 1,2 \},\{ 3,4 \} \}$ 

dann ist $\left| \underline{4} \right|=\left| \{ 1,2 \} \right|+\left| \{ 2,3 \} \right|=2+2=4$

---
# Beweisführung

Haben wir nur geradeso angefangen
## Direkter Beweis
Beispiel: 
$$
\forall_{z\in \mathbb{Z}}:\underbrace{ z \text{ ungerade } }_{ =:A } \implies \underbrace{ z^{2}\text{ ungerade} }_{ =:B }
$$
mit den Definitionen:
- gerade: $z=2k$ für ein $k\in \mathbb{Z}$
- ungerade: $z=2k+1$ für ein $k\in \mathbb{Z}$

Beweis:
Sei $z\in Z$ ungerade, dann gibt es ein $k\in \mathbb{Z}$ mit $z=2k+1$ 
Dann gilt also $z^{2}=(2k+1)^{2}=4k^{2}+4k+1=2(\underbrace{ 2k^{2}+2k }_{ \in \mathbb{Z} })+1$ 

 $(2k^{2}+2k)\in \mathbb{Z}$ (Die Ganzen Zahlen sind auf Addition und Multiplikation abgeschlossen)

