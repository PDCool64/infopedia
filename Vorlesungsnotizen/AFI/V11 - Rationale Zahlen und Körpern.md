---
date: 2025-10-24
tags:
  - AFI
status: rot
Vorlesungsfolien:
Skriptfolien: "[[Altes Skript AFI.pdf]]"
---
---

# Rationale Zahlen
$\mathbb{Q}:x=\frac{p}{q},p\in \mathbb{Z},q\in \mathbb{Z}\setminus\{ 0 \}$ 

$x$ ist nicht eindeutig, weil $\frac{p}{q}=r\cdot s\iff p\cdot s=q\cdot r$

## Addition

$$\frac{p}{1}\cdot \frac{r}{s}=\frac{ps+rq}{qs}$$
## Multiplikation
$\frac{p}{q}\cdot \frac{r}{s}\implies \frac{pr}{qs}$

## Wann ist ein Bruch positiv:
$\frac{p}{q}>0\iff p\cdot q>0$


# Warum das Ganze?
> Aus einer "Beobachtung" über rationale Zahlen,  wollen wir Definitionen machen.
> Kann man diese Definition von $\mathbb{Q}$ auf andere Dinge übertragen?
> Wollen mal das Schulwissen untermauern und begründen - Es ist nicht vom Himmel gefallen.
> 
> Später, bei komplexeren Themen kommt man mit seiner Intuition nicht mehr weiter - dann braucht man solche formalen Definitionen, um damit arbeiten zu können.


# Körperaxiome
Verweis auf [[Körper]]


Ein Körper muss mindestens zwei Elemente haben.

Das hier ist noch komisch: AFAIK wird die eindeutigkeit nicht sofort eingefordert, folgt aber schnell in [[#Folgerungen/Satz]]
Es kann auch mehrere neutrale Elemente geben. (sowohl für addition und Multiplikation)

## Assoziativgesetze
$$
\begin{align}
\forall _{a,b,c\in K}:&(a+b)+c=a+( b+ c) \\
&(a\cdot b)\cdot c = a\cdot(b\cdot c)
\end{align}
$$
## Kommutativgesetze

## Neutrale Elemente

## Inverse Elemente

## Distributivgesetze

# Beispiele für Körper:
- $\mathbb{Q}$ die Rationalen Zahlen
- $\mathbb{R}$ die reellen Zahlen.

Der kleinstmögliche Körper ist $\{ 0,1 \}$:

| +   | 0   | 1   |
| --- | --- | --- |
| 0   | 0   | 1   |
| 1   | 1   | 0   |

| *   | 0   | 1   |
| --- | --- | --- |
| 0   | 0   | 0   |
| 1   | 0   | 1   |

# Folgerungen/Satz
> All das Zeug hier kann man direkt aus den Körperaxiome folgern

Sei $K$ ein Körper, dann gilt $\forall a,b,c,c\in K$

- Es existiert *genau* ein $x\in K:a+x=b$, nämlich $x=b+(-a)$, Schreibweise $x=b-a\;,\;-0=0$ und $-(a+b)=-a+(-b)$. Das element $0$ ist eindeutig.
- $a+c=b+c\implies a=b$
- Ist $a\neq 0$, gibt es genau ein $y\in K$ mit $a\cdot y=b,y=b\cdot a^{-1}$, Schreibweise $y=\frac{b}{a}=b/a$. Es gilt $1^{-1}=1$ Das Element $1$ ist eindeutig.
- $a\cdot c=b\cdot c$ und $c\neq 0\implies a=b$
- $a\cdot 0=0$
- Es gilt $1\neq 0$ und $a\cdot b=0\implies a=0\vee b=0$
- $(-a)\cdot b=-(a\cdot b),-(-a)=a,(-1)\cdot a=a,(-a)\cdot(-b)=a\cdot b$
- $a\neq 0\wedge b\neq 0\implies a\cdot b \neq 0,(a\cdot b)^{-1}=a^{-1}\cdot b^{-1}$ und $a^{-1}\neq 0$
- $b\neq 0$,$c\neq 0\implies a\cdot b^{-1}=(a\cdot c)\cdot(b\cdot c)^{-1}=\frac{a}{b}=\frac{a\cdot c}{b\cdot c}$

(Diese Axiome erlauben es uns, mit Gleichungen zu hantieren)
# Angeordneter Körper

Mann nennt $K$ einen angeordneten Körper, wenn $P\subset K$ existiert, und die folgenden Drei Bedingungen erfüllt:
(P.1)  $\forall x\in K$ ist genau eine der Aussagen $x\in P,x=0,-x\in P$ wahr.
(P.2) $\forall x,y\in P:x+y\in P$ d.h. $P+P\subset P$
(P.3) $\forall x,y\in P:x\cdot y\in P$ d.h. $P\cdot P\subset P$

>$P$ wird auch Positivitätsbereich genannt.

>[!def]
> Definition der Relation  $<$ ist dann:
> $$x<y:\iff y-x\in P$$
> 

$K=P\overset{\cdot}{\cup}\{ 0 \}\overset{\cdot}{\cup}\{ -P \}$
wobei "$\overset{\cdot}{\cup}$" hervorhebt, das die Mengen welche vereinigt werden disjunkt sind.

Die Schreibweisen für kleiner gleich/größer gleich sind nur Vereinbarungen
![[Pasted image 20251024091212.png|400]]


> NEU: Im Vorkurs wurden diese Aussagen noch als notwendige Bedingungen in die Definition für einen angeordneten Menge geschrieben. Hier heißt es: **Diese folgen bloß aus den Axiomen und sind selbst keine!**
![[Pasted image 20251024091827.png]]
![[Pasted image 20251024092107.png]]

(Diese Gesetze erlauben es uns, mit Ungleichungen zu hantieren)
(Sind eigentlich nur die üblichen Regeln aus der Schule, z.B. das sich die Ungleichheit beim Multiplizieren mit einer negativen Zahl umkehrt.)

## Beispielbeweise:
a)
$b-a\in P,c-b\in P\implies c-a=\underbrace{ c-b }_{ \in P }+\underbrace{ b-a }_{ \in P }\overbrace{ \in }^{ (P.2) } P$
b2)
Fallunterscheidung:
- $c=d\overbrace{ = }^{ b 1) }a+c<b+c=b+d$

- $c<d\;:\;(b+d)-(a+c)=\underbrace{ (b-a) }_{ \in P }+\underbrace{ (d-c) }_{ \in P }\overbrace{ \in }^{ (P.2) } P$

b4)
Fallunterscheidung:
- $c=d\;:\;b=a\in P,c\in P\overbrace{ \implies }^{ (P.3) } (b\cdot a)\cdot c\in P\;,\;b\cdot c-a\cdot c\in P\implies b\cdot d-a\cdot c\in P$
- $c<d$ ähnlich

b5) geht mit Induktion, haben wir aber nicht gezeigt


c1)
einfach

c3) mit Widerspruchsbeweis.
Angenommen $a>0,a^{-1}<0$, Dann $1=a\cdot a^{-1}\overbrace{ < }^{ (C.1) }0\implies 1< 0$, Was ein Widerspruch mit c2) ist.

c5)
$a>0,b>0$ gilt c3)$\implies a^{-1}>0,b^{-1}>0$, da $a\neq b\implies a^{-1}\neq b^{-1}$ Wäre nun $a^{-1}<b^{-1}$ und auch $1=a\cdot a^{-1}<b\cdot b^{-1}=1\implies 1<1$ , Was ein Widerspruch ist.
Die anderen Fälle könnte man ebenfalls mit c1), c3) , c4) abhandeln

> Es empfiehlt sich zur Übung, ein paar von denen mal selbst durchzumachen.

# Bemerkung zu angeordneten Körpern
Jeder angeordneter Körper "enthält $\mathbb{Q}$" in gewissem Sinne (also auch $\mathbb{N},\mathbb{Z}$) in dem Sinne, als das eine [[Abbildungen#Injektiv, Surjektiv, Bijektiv|injektive]] Abbildung $\varphi:\mathbb{Q}\to K$ mit:
	$\varphi(x+y)=\varphi(x)+\varphi(y)\;,\;x,y\in \mathbb{Q}$
	$\varphi(x\cdot y)=\varphi(x)\cdot\varphi(y)\;,\;x,y\in \mathbb{Q}$
	$x<y\implies\varphi(x)<\varphi(y)$
D.h. die Abbildung respektiert die Rechenoperationen (?des Körpers? afaik) und die Anordnung respektiert
(des Körpers weil $\varphi(x)\in K,\varphi(y)\in K$)

> Beweis davon ist schwierig und wird hier nicht versucht.


# Definition Betrag

![[Pasted image 20251024094759.png]]
![[Pasted image 20251024094813.png]]


## Besonders hier hervorgehoben: Dreiecksungleichung
> Die Summe der Katheten ist immer größer als die Länge der Katheten als geometrische Interpretation und Namensvetter
$$
\left| x+y \right|\leq \left| x \right|+\left| y \right|   
$$

Beträge kann man fast immer mit Fallunterscheidungen lösen und schön handhaben.
## Bew: Dreiecksungleichung

1. Fall: $x+y\geq 0$, mit $x\leq \left| x \right|,y\leq \left| y \right|$
   $\left| x+y \right|=x+y\leq \left| x \right|+\left| y \right|$
2. Fall: $x+y<0$ mit $-x\leq \left| -x \right|=\left| x \right|$ und $-y\leq \left| -y \right|=\left| y \right|$
   $\left| x+y \right|=-(x+y)=-x-y\leq \left| x \right|+\left| y \right|$

### Umgekehrte Dreiecksungleichung
$\left| x \right|=\left| x+y+(-y) \right|\overbrace{ \leq }^{ v) }\left| x+y \right|+\left| -y \right|$ rest s.h. pxl Foto



>[!def] Beweistrick, der laut Prof auch später sehr wichtig bleibt: "Schmuggeltrick"
> 
> Man bastelt sich die benötigten Terme zusammen, indem man mit 0 addiert z.b. $a=a+x-x$ oder mit $1$ multipliziert $a=a\cdot x\cdot \frac{1}{x}$ 
