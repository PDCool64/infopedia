
# Teilbarkeit
>[!def] Teiler einer natürlichen Zahl
> Eine [[Zahlenräume#Natürliche Zahlen $ mathbb{N}$|Natürliche Zahl]] $m$ ist ein **Teiler** der natürlichen Zahl $n$, wenn es eine weitere natürliche Zahl $b$ gibt so, dass $$n=mb$$
> "$m$ teilt $n$" wird geschrieben als: $m|n$

Bemerkungen:
- $\forall_{n\in \mathbb{N}}:1|n\wedge n|n$ 
- Weil $b\in \mathbb{N}\implies b\geq 1$ liegt jeder Teiler $m$ von $n$ zwischen $1$ und $n$, also $1\le m \le n$.

### "Transitivität" der Teilerbeziehung:
$$
t|m\wedge m|n\implies t|n
$$
Beweis:
	1. Weil $t|m$, existiert ein $a$ so, dass $m=ta$.
	2. Weil $m|n$ existiert ein $b$ so, dass $n=mb$
	Setzt man 1. in 2. ein, erhält man:
	$n=mb=(ta)b=t(ab)$
	Was zeigt, dass man $n$ als Vielfaches von $t$ mit dem Faktor $ab$ ausdrücken kann.

# Primzahl
>[!def] Primzahl
>Eine *Primzahl* ist eine [[Zahlenräume#Natürliche Zahlen $ mathbb{N}$|Natürliche Zahl]] $p\geq 2$, die nur durch $1$ und sich selbst teilbar ist. 
>
>Wir bezeichnen die Menge der Primzahlen mit $\mathbb{P}$.

Es gibt unendlich viele Primzahlen.

>[!satz] Primfaktorzerlegung
>Jedes $n\in \mathbb{N},n>1$ ist Produkt von Primzahlen.
>
>Die Primfaktorzerlegung ist, abgesehen von der Reihenfolge der Faktoren, *eindeutig*.

^0fe372


# ggT und kgV

>[!def] ggT und kgV
>Es seien $m$ und $n$ zwei [[#Natürliche Zahlen $ mathbb{N}$|natürliche Zahlen]].
>
>1. Die größte natürliche Zahl $t$, welche sowohl $m$ als auch $n$ teilt, heißt der *größte gemeinsame Teiler* $t=\text{ggT}(m,n)$ von $m$ und $n$.
>   Der ggT ist das Produkt der größten auftretenden Primfaktor Potenzen.q
>2. Die kleinste natürliche Zahl $t$, die sowohl von $m$ als auch von $n$ geteilt wird, heißt das *kleinste gemeinsame Vielfache* $t=\text{kgV}(m,n)$ von $m$ und $n$.

### ggT mit dem Euklidischen Algorithmus
Der ggT lässt sich ebenfalls durch den *Euklidischen Algorithmus* bestimmen, was bei großen Zahlen deutlich effizienter ist ([[#^0fe372|Primfaktorzerlegung]] ist np-hart):

ges. : $ggT(a,b)$ mit $a,b\in \mathbb{N}$

Anfang des Algorithmus:
	man tausche ggfs. $a$ und $b$ so, dass $a\ge b$
	$a_{0}=a$
	$b_{0}=b$

Iterationsanweisungen:
	$r_{n}$ ist der Rest der Division von $a_{n}:b_{n}$
	$a_{n+1}=b_{n}$
	$b_{n+1}=r_{n}$
Man führe die Iterationsanweisungen solange durch, bis $r_{z}=0$.
Dann gilt $ggT(a,b)=r_{z-1}$

Beispiel: $a=18$ , $b=4$

| **$a$** | **$b$** | **$r$**     |                     |
| ------- | ------- | ----------- | ------------------- |
| 52      | 6       | 4           | $52=6\!\cdot \!8+4$ |
| 6       | 4       | **2** (ggT) | $6=4\!\cdot \!1+2$  |
| 4       | 2       | 0           |                     |



