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
> 
> 
> >[!def] Reflexiver Abschluss
> > Die Relation $S$ auf $M$ mit
> > - $S$ reflexiv
> > - $R\subseteq S$
> > - $S$ minimal groß: Für alle transitiven Relationen $T$ auf $M$ gilt: $R\subseteq T \implies S \subseteq T$ bzw. $\left| T \right|\ge \left| S \right|$
> >   
> > heißt **reflexiver Abschluss** von $R$.
> >   --- 
> Der Reflexive Abschluss ist sehr leicht zu erzeugen, indem man $S$ mit der Menge der Diagonalpaare vereinigt:$$R=S \cup \{ (x,x) \mid x\in M \}$$
> 
> >[!def] Symmetrischer Abschluss
> > Die Relation $S$ auf $M$ mit
> > - $S$ symmetrisch
> > - $R\subseteq S$
> > - $S$ minimal groß: Für alle transitiven Relationen $T$ auf $M$ gilt: $R\subseteq T \implies S \subseteq T$ bzw. $\left| T \right|\ge \left| S \right|$
> >   
> > heißt **transitiver Abschluss** von $R$.
> > 
> > ---
> > Der symmetrische Abschluss



