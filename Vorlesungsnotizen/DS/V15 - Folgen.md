---
date: 2025-10-28
tags:
  - DS
status: rot
Vorlesungsfolien:
Skriptfolien: "[[Skript Diskrete Strukturen.pdf]]"
---
---
>[!def] Folge
> Eine Abbildung $f:\mathbb{N}\to N$ wird auch *Folge in $N$* genannt.
> 
> Schreibweisen:
> - Die Folge $f:\mathbb{N}\to N$ in $N$ wird auch geschrieben als $a_{1},a_{2},a_{3},\dots$
>   oder $(a_{i}):i\in \mathbb{N}$
> 
> Die Menge aller Folgen in $N:\text{Abb}(\mathbb{N},N)$ oder $N^{\mathbb{N}}$.


## Beispiel
$f:\mathbb{N}\to \mathbb{R},i\mapsto i^{2}$ wird auch geschrieben als $1,4,9,16$ oder $(i^{2})_{i\in \mathbb{N}}$ 

### Mehr Mengen als Zielbereich von Folgen:
$\{ 0,1 \}^{\mathbb{N}}$ ist die Menge der Binärfolgen.

Menge aller reellen Folgen $\mathbb{R}^{\mathbb{N}}$ 

---
# Fibonacci-Folge
$f(1):=1$
$f(2):=1$
$f(n+1):=f(n)+f(n-1)$

also $f(3)=f(2)+f(1)=1+1=2$

und weiter: $1,1,2,3,5,8,13,\dots$

---
# Rekursive Folgen
Folgen auf einer Menge können *rekursiv* definiert werden.

- Auf $\mathbb{R}_{>0}$ existiert genau eine Folge $(a_{n})_{n\in \mathbb{N}}$ mit $$
a:=1 \;,\; a_{n+1}:=1+\frac{1}{a_{n}} \text{ für } n\ge{1}
$$
---
# Tupel mit einer anderen Definition

Es sei $n\in \mathbb{N}$. Erinnerung nochmal $\underline{n}=\{ 1,2,\dots,n \}$ 

Eine Abbildung $f:\underline{n}\to N$ wird auch $n$-Tupel in $N$ genannt.

Schreibweise:
- Das $n$-Tupel $f:\underline{n}\to N$ in $N$ wird auch geschrieben als $(a_{1},a_{2},..,a_{n})$ 
  oder $(a_{i})_{i\in \underline{n}}$ 
  Hier ist $a_{i}:=f(1)$ für $i\in \underline{n}$


Damit kann man auch das Kartesische Produkt mehrerer verschiedener Mengen definiert.

Es sei $n\in \mathbb{N}$ und $M_{i}$ eine Menge für alle $i\in \underline{n}$
Wir setzten $M:=\bigcup_{i\in \underline{n}}$

Um es noch mehr fucked zu machen: angeblich haben wir *geordnete Paare* (das gleiche ?) hier eben *nicht* als Abbildung definiert, sondern als:
$(x,y):=\{ \{ x \},\{ x,y \} \}$ wobei man die Elemente dadurch unterscheiden kann, das das erste Element in der extra einzelnen Menge steht.
Warum man dass nicht auch mit beliebig vielen Elementen Machen kann und dann geordnete Paare mit beliebig vielen Elementen definiert??

