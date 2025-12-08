---
tags:
  - DS
status: rot
---
---

>[!def] Relationen
> Es seien $M\;,\;N$ [[Mengen]].
> Eine **Relation** $R$ zwischen $M$ und $N$ ist eine (beliebige) Teilmenge des [[Mengen#Kartesisches Produkt|kartesischen Produkts]]:
> $$
> R \subseteq M\times N
> $$
> Im Fall $M=N$ sagen wir: $R$ ist Relation auf $M$.
> 
> ---
> Für $(x,y)\in R$ schreiben wir auch $xRy$ und sagen "$x$ steht in Relation zu $y$ bezüglich $R$".
> 
> Neben $R$ ist auch $\sim$ ein oft gebräuchliches Symbol für eine Relation.


- [[Abbildungen]] sind ein Spezialfall von Relationen.

# Eigenschaften von Relationen

>[!def] Eigenschaften von Relationen
> $M$ Menge, $R$ Relation auf $M$. Dann heißt $R$ ... , wenn für **alle** $x,y,z\in M$ gilt:
> 
> | (R) - Reflexiv            | $xRx$                        |
> | ------------------------- | ---------------------------- |
> | **(S) - Symmetrisch**     | $xRy \implies yRx$           |
> | **(A) - Antisymmetrisch** | $xRy\land yRx \implies x=y$  |
> | **(T) - Transitiv **      | $xRy \land yRz \implies xRz$ |
> | **(V) - Vollständig**     | $xRy \lor yRx$<br>           | 
> 

- Vollständig bedeutet, dass jedes beliebige Paar an Elementen bzgl. der Relation vergleichbar ist.
- Bei Transitiven Relationen schreibt man für $(x,y)\in R\;,\;(y,z)\in R$ auch kurz:$$x\,R\,y\,R\,z$$ bzw. für $(x_{k},x_{k+1})\in M\; \forall_{k\in \{ 1 ,\dots,n\}}$  kurz: $$x_{1}\,R\,x_{2}\,R\,x_{3}\,R\,\cdots\,R\,x_{n}$$
## Bemerkungen
- wir betrachten hier nur $M=N$ d.h. $R\subseteq M\times M$
- Die allermeisten Relationen haben keine der obigen Eigenschaften. Solche, die manche der Eigenschaften haben sind aber besonders interessant.
# Klassifikation von Relationen

>[!def] Klassifikation von Relationen
> Eine Relation, die ... erfüllt, heißt:
> 
> | (R)-(S)-(T)     | **Äquivalenzrelation**                |
> | --------------- | ------------------------------------- |
> | **(R)-(T)**     | Präordnung                            |
> | (R)-(A)-(T)     | Ordnung oder auch *partielle* Ordnung |
> | (R)-(A)-(T)-(V) | Totale Ordnung                        |
> 

---
# Äquivalenzrelationen: Details

## Äquivalenzklassen
>[!def] Äquivalenzklasse
> Es sei $C$ eine *Äquivalenzrelation* auf $M$. Für $x\in M$ heißt
> $$
> \left[ x \right] :=\left[ x \right] _{C}:=\{ y\in M \mid xCy\}= \{ y\in M \mid yCx \}
> $$
> die **Äquivalenzklasse** von $C$ zu $x$. 
> 
> ---
> 
> Es gilt für alle $x,y\in M$
> - $x\in \left[ x \right]_{C}$
> - $y\in \left[ x \right]_{C}\iff x\in \left[ y \right]_{C}$
> - $y\in \left[ x \right]_{C} \implies \left[ y \right]_{C}=\left[ x \right]_{C}$
>  
>  Man bezeichnet deshalb, *jedes* Element einer Äquivalenzklasse als Repräsentant derselben.
>  
>  Es folgt der Satz: Für alle $x,y\in M$ gilt:
>  $$xCy \iff \left[ x \right] _{C}= \left[ y \right] _{C} \iff \left[ x \right] _{c} \subseteq \left[ y \right] _{C}$$
>  
>  Somit sind zwei Äquivalenzklassen entweder gleich oder disjunkt.
>  

## Quotientenmenge als und Partitionen
 > [!def] Quotientenmenge
>  Die Menge aller Äquivalenzklassen von $M$ unter der Relation $C$ wird mit $M/ C$ bezeichnet. 
>  $$M / C := \{ \left[ x \right] _{C} \mid x \in M \}$$
>  Sie wird **Quotientenmenge von $M$ modulo $C$** genannt.
> >(Nicht zu verwechseln mit $A\setminus B$ für ``\setminus``) 
> 

> [!def]Haut
> Die Quotientenmenge $S / C$ jeder Äquivalenzrelation bildet eine [[Mengen#Partition einer Menge|Partition]] von $M$.
> 
> Ist $\mathcal{P}$ eine [[Mengen#Partition einer Menge|Partition]] von $M$, so existiert eine Äquivalenzrelation $C$ auf $M$ mit $M / C = \mathcal{P}$.




 ---
# Abschlüsse
Die Meisten Relationen haben keine der [[#Eigenschaften von Relationen|interessanten Eigenschaften]] - Man kann sie aber so erweitern, dass sie diese erfüllen.

> Die obigen Eigenschaften - *abgesehen von der **Antisymmetrie***- verlangen nur die Existenz besonderer Paare : Es wird von ihnen nicht verlangt, dass besondere Paare *nicht* existieren. Man kann somit jede Relation allein durch Hinzufügen bestimmter Paare erweitern, um eine gewünschte Eigenschaft zu erzeugen, solange es sich nicht um die Antisymmetrie handelt.
> 
> (Insbesondere erfüllt $R=M\times N$ alle der obigen Eigenschaften abgesehen von der Antisymmetrie)

>[!def] Abschlüsse
> Abschlüsse einer Relation sind Relationen auf derselben Menge, welche kleinstmögliche Obermengen der gegebenen Relation sind und die gewünschte Eigenschaft erfüllen.
> 
>
> $M$ Menge, $R$ Relation auf $M$:
> 
> >[!def] Transitiver Abschluss
> > Die Relation $S$ auf $M$ mit
> > - $S$ transitiv
> > - $R\subseteq S$
> > - $S$ minimal groß: Für alle transitiven Relationen $T$ auf $M$ gilt: $R\subseteq T \implies S \subseteq T$ bzw. $\left| T \right|\ge \left| S \right|$
> >   
> > heißt **transitiver Abschluss** von $R$.
> > 
> > ---
> > Der transitive Abschluss $S$  von $R$ lässt aufschreiben durch: $x,y\in M$
> > $$ rSy \iff\text{ es gibt }n\in \mathbb{N}_{0}\;,\;x_{0},\dots,x_{n}\in M : {\color{lime}{x}}R\,x_{0}Rx_{1}R\cdots Rx_{n}\,R{\color{lime}{y}}$$
> > 
> > In der Praxis:
> > - Erstelle für jedes $x$ eine Liste der $y$ mit denen es in Relation steht, also für die $xRy$ gilt
> > - Gehe für jedes $x$ die Listeneinträge $y$ durch. Schaue in die Liste von $y$ selbst. Wenn die Liste von $y$ Einträge hat, die $x$ noch nicht hat, füge diese bei $x$ hinzu.
> > - Wiederhole so lange für alle $x$, bis man über alle iterieren kann, ohne noch neue Paare zu finden.
> >
> 
> 
> >[!def] Reflexiver Abschluss
> > Die Relation $S$ auf $M$ mit
> > - $S$ reflexiv
> > - $R\subseteq S$
> > - $S$ minimal groß: Für alle reflexiven Relationen $T$ auf $M$ gilt: $R\subseteq T \implies S \subseteq T$ bzw. $\left| T \right|\ge \left| S \right|$
> >   
> > heißt **reflexiver Abschluss** von $R$.
> >   --- 
> > Der Reflexive Abschluss ist sehr leicht zu erzeugen, indem man $S$ mit der Menge der Diagonalpaare vereinigt:$$R=S \cup \{ (x,x) \mid x\in M \}$$
> > Gleichbedeutend ist für $x,y\in M$: $$xSy \iff xRy \lor x=y$$
> 
> 
> >[!def] Symmetrischer Abschluss
> > Die Relation $S$ auf $M$ mit
> > - $S$ symmetrisch
> > - $R\subseteq S$
> > - $S$ minimal groß: Für alle symmetrischen Relationen $T$ auf $M$ gilt: $R\subseteq T \implies S \subseteq T$ bzw. $\left| T \right|\ge \left| S \right|$
> >   
> > heißt **symmetrischer Abschluss** von $R$.
> > 
> > ---
> > Der symmetrische Abschluss lässt sich leicht bestimmen. Für $x,y\in M$:
> > $$xSy \iff xRy \lor yRx$$
>
> Jeder dieser Abschlüsse ist *eindeutig* bestimmt und immer existent.







