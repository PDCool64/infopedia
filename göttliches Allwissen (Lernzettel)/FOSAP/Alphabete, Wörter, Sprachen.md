---
tags:
  - DS
  - FOSAP
status: rot
---
---
# Mathematische Basis:

## Erzeugendensysteme und Halbgruppen
>[!def] Halbgruppe
>Eine *Halbgruppe* $(H,\circ)$ besteht aus einer Menge $H$ und einer *assoziativen* Verknüpfung $\circ:H\times H\to H$

([[Monoide und Gruppen#Monoid|Monoide]] sind Halbgruppen mit neutralem Element. Bei der Konkatenation von Wörtern ist dies z.B. das leere Wort $\varepsilon$)

>[!def] Erzeugendensystem eines Monoids
> Sei $(M,\circ)$ ein Monoid und $E\subseteq M$.
> $E$ ist ein **Erzeugendensystem** von $(M,\circ)$, falls jedes $m\in M$ als
> $$
> m=e_{1}\circ \cdots \circ e_{n}\quad,\quad e_{i}\in E
> $$
> dargestellt werden kann.

(Konzept ist sehr ähnlich zum [[Erzeugendensysteme und Basen|Erzeugendensystem eines Vektorraums]], nur noch einfacher/kleiner)

>[!def] Freies Erzeugendensystem eines Monoids
> Ein Erzeugendensystem $E$ für ein [[Monoide und Gruppen#Monoid|Monoid]] $(M,\circ)$ ist **frei**, falls jedes $m\in M$ nur auf *eine eindeutige* Art als $m=e_{1}\circ \cdots \circ e_{n}$ mit $e_{i}\in E$ dargestellt werden kann.
> 
> Falls $E$ ein freies Erzeugendensystem für $(M,\circ)$ ist, dann sagen wir, dass $(M,\circ)$ das *bis auf Isomorphie eindeutige* von $E$ frei erzeugte Monoid ist.

### Beispiele:
- Für $(\mathbb{Z},+)$ ist $\{ -1,1 \}$ ein Erzeugendensystem
- Für $(\mathbb{N},+)$ ist $\{ 1 \}$ ein *freies* Erzeugendensystem
- Für $(\mathbb{N}_{0},+)$ ist $\{ 1 \}$ ein *freies* Erzeugendensystem. 
	  (Weil die *leere Summe* -und auch nur diese- die $0$ abdeckt.)
- Für $(\mathbb{Z}_{8},\cdot)$  ist $\{ 3,5,7 \}$ kein Erzeugendensystem.
	  (Man kann keine geraden Zahlen erzeugen)

>Wir wollen für Alphabete/Wörter/Sprachen ein *freies* Erzeugendensystem, weil wir als Erzeugendensystem letztendlich ein Alphabet verwenden wollen, und nicht z.B. redundanterweise auch ganze Wörter in das Erzeugendensystem aufnehmen wollen - Denn diese hätte man selbst schon aus dem eigentlichen Alphabet bilden können.
## Homomorphismen und Isomorphismen zwischen Monoiden

>[!def] Homomorphismen und Isomorphismen zwischen Monoiden
> Ein **Homomorphismus** ist eine Abbildung, welche die Verknüpfungen zweier Monoide respektiert.
> 
> Seien $(M_{1},\circ)\;,\;(M_{2},\bullet)$ zwei Monoide. Gibt es eine Abbildung $h:M_{1}\to M_{2}$ , so dass für alle $u,v\in M_{1}$ gilt, dass
> $$
> h(u\circ v) = h(u) \bullet h(v)
> $$
> Dann nennen wir $h$ einen Homomorphismus.
>
> ---
> Ist $h$ bijektiv, nennen wir $h$ einen **Isomorphismus** und die beiden Monoide **isomorph**.
> ($h^{-1}$ ist dann ebenfalls ein Isomorphismus)
> 


### Beispiel
Sei $M_{1}=(\mathbb{Z}_{3},+)$ mit gewöhnlicher Addition und Modulo 3
und $M_{2}=(\{ 10,11,12 \},\bullet)$ mit der Verknüpfung

| $\bullet$ | 10  | 11  | 12  |
| --------- | --- | --- | --- |
| 10        | 10  | 11  | 12  |
| 11        | 11  | 12  | 12  |
| 12        | 12  | 13  | 10  |
Dann ist $h:M_{1}\to M_{2}: 0\mapsto 10\;,\;1 \mapsto 11 \;,\; 2\mapsto 12$ ein Isomorphismus zwischen beiden Mengen. 

# Alphabete, Wörter, Sprachen

>[!def] Alphabet, Wort, Sprache
> - Ein **Alphabet** $\Sigma$ ist eine *endliche, nichtleere* Menge von Symbolen.
> - Mit der Verknüpfung der **Konkatenation** $\cdot:\Sigma^{*}\times\Sigma^{*}\to \Sigma^{*}$ 
>   ist $(\Sigma^{*},\cdot)$ das eindeutige, von $\Sigma$ frei erzeugte, Monoid.
> 	- Mit $u,v\in\Sigma^{*}$ schreiben wir für $u\cdot v$ auch $uv$
> 	- Das neutrale Element von $(\Sigma^{*},\cdot)$ bezeichnen wir mit $\varepsilon$
> - Die Elemente von $\Sigma^{*}$ nennen wir **Wörter** (über $\Sigma$)
> - Teilmengen $L\subseteq \Sigma^{*}$ nennen wir **Sprachen** (über $\Sigma$)


> Die Symbole aus $\Sigma$ sind somit die "einbuchstabigen" Wörter aus $\Sigma^{*}$ und erzeugen dieses frei. Somit ist jedes Wort aus $\Sigma^{*}$ *eindeutig* als Konkatenation dieser "einbuchstabigen" Wörter erzeugbar.

## Homomorphismen zwischen den Wörtern über Alphabeten

>[!def] Äquivalenz der Wirkung von Homomorphismen auf Wörter und Symbole
> Es seien $\Sigma$ und $\Gamma$ Alphabete. Jede Abbildung $\Sigma\to \Gamma^{*}$ lässt sich eindeutig auf einen Homomorphismus $\Sigma^{*}\to\Gamma^{*}$ erweitern.
> 
> Beweis:
> Es sei $h:\Sigma^{*}\to \Gamma^{*}$ ein Homomorphismus. Dann lässt sich, weil $\Sigma^{*}$ ein frei erzeugtes Monoid von $\Sigma$ ist, jedes $w\in \Sigma^{*}$ schreiben als $w=w_{1} \cdots w_{n}\;,\;w_{i}\in\Sigma$. Es folgt weiter
> $$
> h(w) = h(w_{1}\cdots w_{n}) = h(w_{1}) \cdots h(w_{n})\;\in\;\Gamma^{*}
> $$
> weil $h$ ein Homomorphismus ist. 


>Wenn wir einen Homomorphismus definieren wollen, genügt es somit, seine Wirkung auf die einzelnen Symbole zu beschreiben. 

### Anwendung / Problemstellung:
- Betrachtet wird für zwei Alphabete $\Sigma \;,\;\Gamma$ einen Homomorphismus zwischen den Mengen der jeweils erzeugten Wörter also $\Sigma^{*}\to\Gamma^{*}$
- Es ist dann schwierig, eine Abbildungsvorschrift für die unendlich vielen Wörter unendlich vieler Längen aus $\Sigma^{*}$ aufzuschreiben.
- Aber: Nach dem Satz genügt es, die Wirkung auf jedes Symbol von $\Sigma$ zu definieren.


# Operationen auf Sprachen

>[!def] Operationen auf Sprachen
> Es seien $A,B\subseteq\Sigma^{*}$ und $w\in\Sigma^{*}$.
> - $AB:=\{ uv\mid u\in A \land v\in B\}$
> - $wA:=\{ w \}A$ sowie $Aw:=A\{ w \}$
> - Potenzierung: Genau $n$ viele (auch verschiedene) Wörter aus der Sprache$$
> A^{i} := \begin{cases}
> \{ e \} &,i=0 \\
> A &,i=1 \\
> AA^{i_{1-1}}&,i>1
> \end{cases}
> $$
> - Beliebig viele (auch verschiedene) Wörter aus der Sprache $$A^{*}:= \bigcup_{n\ge_{0}} A^{n}$$
>   Diese Operation heißt auch [Kleenesche Hülle](https://de.wikipedia.org/wiki/Kleenesche_und_positive_H%C3%BClle)
> - Ein oder mehr (auch verschiedene) Wörter aus der Sprache $$A^{+}:= \bigcup_{n\ge_{1}} A^{n}$$
> Diese Operation heißt auch  [positive Hülle](https://de.wikipedia.org/wiki/Kleenesche_und_positive_H%C3%BClle)


### Algebraische Gesetze
Bei den Operationen auf Sprachen gelte folgende Gesetze:

>[!def] Algebraische Gesetze bei Operationen auf Sprachen
> Es seien  $A,B,C\subseteq\Sigma^{*}$.
> - $A(BC)=(AB)C$
> - $\varepsilon A=A\varepsilon=A$
> - $(A^{*})^{*}=A^{*}$
> - $A(B\cup C)=AB \cup AC$
> - $(A\cup B)C=AC\cup BC$
> - $A^{+}\cup \{ \varepsilon \}=A^{*}$


