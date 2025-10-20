Eine Auflistung von mehr oder minder formell schönen Beweisen mit [[Vollständige Induktion|Vollständiger Induktion]] -Die zu beachtenden Formalien sind im verlinkten Lernzettel besser sichtbar-
# Bsp.1 : Binomischer Satz
>[!def] Binomischer Satz
>$\forall_{x\in \mathbb{R}}:$$$
>(1+x)^{n}=\sum_{k=0}^{n}\binom{n}{k}x^{k}
>$$

Gegeben sei / verwendet wird: $$\frac{n!}{(n-k)!\cdot k!}=\binom{n}{k}$$
sowie
$\forall_{n,k\in \mathbb{N}_{0}}:$
$$
\binom{n+1}{k+1}=\binom{n}{k}+\binom{n}{k+1}
$$
bzw. in diesem Fall leicht verschoben: $a=k+1$ und $a-1=k$
$$
\binom{n+1}{a}=\binom{n}{a-1}+\binom{n}{a}
$$


Als Aussage ist also zu zeigen:
Für alle $n\in \mathbb{N}$:
$A(n):$ Für alle $x\in \mathbb{R}$ gilt $(1+x)^{n}=\sum_{k=0}^{n}\binom{n}{k}x^{k}$
# 1. Induktionsanfang
Für $n=1$ gilt:
$$
\begin{align}
(1+x)^{1}&= \sum_{k=0}^{1}\binom{1}{k}x^{k} \\ \\

&=\binom{1}{0}x^{0} \;+\;\binom{1}{1}x^{1} \\
 \\
&= \frac{1!}{(1-0)!\cdot 0!}\cdot 1 \;+\; \frac{1!}{(1-1)!\cdot 1!}\cdot x \\ \\

1+x&=1+x
\end{align}
$$
Damit gilt $A(1)$


## 2. Induktionsvoraussetzung: 
Gelte $A(n): \forall_{x\in \mathbb{R}}:(1+x)^{n}=\sum_{k=0}^{n}\binom{n}{k}x^{k}$ für ein beliebiges aber festes $n\in \mathbb{N}$.

## 3.Induktionsschluss:
Zuerst kann man die Aussage $A(n+1)$ so umformen, dass sie auf relativ zu $A(n)$ geschrieben werden kann:
$$
\begin{align}
(1+x)^{n+1}=(1+x)(1+x)^{n}
\end{align}
$$

Angenommen $A(n)$ ist wahr, dann kann man $(1+x)^{n}$ durch die Formel ausdrücken: (Die Induktionsvoraussetzung wird verwendet/eingesetzt)
$$
\begin{align}
(1+x)^{n+1}=(1+x)\;\cdot\sum_{k=0}^{n}\binom{n}{k}x^{k}
\end{align}
$$
Nun kann man auf der rechten Seite die Klammer $(1+x)$ ausmultiplizieren:
$$
\begin{align}
(1+x)^{n+1}&=1\cdot\sum_{k=0}^{n}\binom{n}{k}x^{k} \quad+\quad x\cdot\sum_{k=0}^{n}\binom{n}{k}x^{k}
\end{align}
$$
in der zweiten Summe lässt sich der außenstehende Faktor $x$ in die Summe hineinschreiben:
$$
\begin{align}
(1+x)^{n+1}&=\sum_{k=0}^{n}\binom{n}{k}x^{k} \quad+\quad \sum_{k=0}^{n}\binom{n}{k}x^{k+1}
\end{align}
$$
Indexverschiebung in der zweiten Summe : setzte $j=k+1$ bzw. $k=j-1$
Dann läuft $j$ von $1$ bis $n+1$ 
$$
\begin{align}
(1+x)^{n+1}&=\sum_{k=0}^{n}\binom{n}{k}x^{k} \quad+\quad \sum_{j=1}^{n+1}\binom{n}{j-1}x^{j}
\end{align}
$$
Weil die Indexvariablen beliebig benannt werden können, kann man $j$ auch einfach wieder durch ein "neues" $k$ ersetzen:
$$
\begin{align}
(1+x)^{n+1}&=\sum_{k=0}^{n}\binom{n}{k}x^{k} \quad+\quad \sum_{k=1}^{n+1}\binom{n}{k-1}x^{k}
\end{align}
$$
Die erste der beiden Summen, kann man ebenfalls bei $k=1$ beginnen lassen, in dem man dem Fall für $k=0$ getrennt addiert:
$$
\begin{align}
(1+x)^{n+1} &= \left(\binom{n}{0}\cdot x^{0}+\sum_{k=1}^{n}\binom{n}{k}x^{k} \right) \quad+\quad \sum_{k=1}^{n+1}\binom{n}{k-1}x^{k} \\
 \\
(1+x)^{n+1} &= 1+\sum_{k=1}^{n}\binom{n}{k}x^{k} \quad+\quad \sum_{k=1}^{n+1}\binom{n}{k-1}x^{k}
\end{align}


$$
Damit die Indexe komplett übereinstimmen, muss die zweite der beiden Summen noch bei $n$ und nicht bei $n+1$ enden. Dafür kann man den Fall $k=n+1$ getrennt addieren:
$$
\begin{align}
(1+x)^{n+1} &= 1+\sum_{k=1}^{n}\binom{n}{k}x^{k} \quad+\quad \left( \binom{n}{(n+1)-1}\cdot x^{(n+1)}+\sum_{k=1}^{n}\binom{n}{k-1}x^{k} \right) \\ \\

(1+x)^{n+1} &= 1+\sum_{k=1}^{n}\binom{n}{k}x^{k} \quad+\quad \left(x^{n+1}+\sum_{k=1}^{n}\binom{n}{k-1}x^{k} \right) \\
 \\
(1+x)^{n+1} &= 1+x^{n+1}+\sum_{k=1}^{n}\binom{n}{k}x^{k} \;+\; \sum_{k=1}^{n}\binom{n}{k-1}x^{k} 
\end{align}
$$
Nun können die beiden Summen zusammengefasst werden, weil ihre Indexe gleich sind:
$$
\begin{align}
(1+x)^{n+1} &= 1+x^{n+1}+\sum_{k=1}^{n}\left(\binom{n}{k}x^{k}+\binom{n}{k-1}x^{k} \right)
\end{align}
$$
$x^{k}$ lässt sich ausklammern:
$$
\begin{align}
(1+x)^{n+1} &= 1+x^{n+1}+\sum_{k=1}^{n} x^{k}\left(\binom{n}{k}+\binom{n}{k-1} \right)
\end{align}
$$
Durch Einsetzen des Satzes $\binom{n+1}{a}=\binom{n}{a-1}+\binom{n}{a}$ entsteht:
$$
\begin{align}
(1+x)^{n+1}=1+x^{n+1}+\sum_{k=1}^{n}x^{k}\binom{n+1}{k}
\end{align}
$$
Nun können die Randterme $k=0 \to 1$ und $k=n+1\to x^{n+1}$ wieder in die Summe hineingezogen werden:
$$
\begin{align}
(1+x)^{n+1}=\sum_{k=0}^{n+1}x^{k}\binom{n+1}{k}
\end{align}
$$
Dies entspricht genau der Aussage $A(n+1)$.
Somit konnte aus der Gültigkeit von $A(n)$ abgeleitet werden, dass auch $A(n+1)$ eine wahre Aussage ist.
$$
A(n)\implies A(n+1)
$$

## Verallgemeinerung zu
$$
(a+b)^{n}=\sum_{k=0}^{n} \binom{n}{k}a^{n-k}b^{k}
$$

1. Sonderfall für a=b=0 betrachten
2. $$\begin{align}
(a+b)^{n} &=\left( a+\frac{ab}{a} \right) \\ \\

&=a^{n}\left( 1+\frac{b}{a} \right)^{n} \\ \\

&=a^{n}\cdot\text{(hier die Summe mit x=b/a einsetzen)} \\
 \\
&=a^{n}\cdot\sum_{k=0}^{n}\binom{n}{k}\left( \frac{b}{a} \right)^{k} \\
 \\
&=
\end{align}$$
3. Das $a^{n}$ in die Summe reinziehen


# Bsp.2 : Gaußsche Summenformel

Zu beweisen:
$$
\forall_{n\in \mathbb{N}}:\sum_{i=1}^{n}i=\frac{n(n+1)}{2}
$$

1. Anker: 
   mit dem Fall $n=1$ wird der kleinste Fall von $A(n)$ bewiesen.$$\begin{align}
\sum_{i=1}^{1}i&=\frac{1(1+1)}{2} \\
1&=\frac{2}{2} \\
1&=1
\end{align}$$
2. Induktionsschritt
   $A(n+1)$ lässt sich relativ zu $A(n)$ schreiben:$$
\sum_{i=1}^{n+1}i=n\!+\!1+\sum_{i=1}^{n}i
$$
	Damit kann $A(1)$ umschreiben:$$
\begin{align}
\sum_{i=}^{n+1}i &= \frac{(n+1)\left(\left(n+1\right)+1\right)}{2} \\
 \\
n\!+\!1+\sum_{i=1}^{n}i &= \frac{(n+1)\left(\left(n+1\right)+1\right)}{2}
\end{align}
$$
	Da wir Annehmen, das $A(n)$ wahr ist, kann man für $\sum_{i=1}^{n}$ die Formel einsetzen:$$
\begin{align}
n\!+\!1+\frac{n(n+1)}{2} &= \frac{(n+1)\left(\left(n+1\right)+1\right)}{2}
\end{align}
$$
	Durch erweitern mit $2$$$
\begin{align}
\frac{2(n+1)}{2}+\frac{n(n+1)}{2} &= \frac{(n+1)\left(\left(n+1\right)+1\right)}{2} \\
 \\
\frac{2(n+1)+n(n+1)}{2} &= \frac{(n+1)\left(\left(n+1\right)+1\right)}{2} \\
 \\
\frac{(n+2)(n+1)}{2} &= \frac{(n+1)(n+2)}{2} \\
 \\
&\square
\end{align}
$$
	Es wurde somit gezeigt, dass $A(n)\implies A(n+1)$


# Bsp.3 : Dritte Potenzen berechnen

Aussage:
	$$\forall_{n\in \mathbb{N}}:A(n):\sum_{j=1}^{n}= \frac{n^{2}\cdot(n+1)^{2}}{4}$$

## 1.Induktionsanfang: $A(1)$
   
   $$
\begin{align}
A(1):\sum_{j=1}^{1}j^{3}=\frac{1^{2}(1+1)^{2}}{4}
\end{align}
$$

## 2. Induktionsschritt: 
   Induktionsvoraussetzung: 
   Sei $A(n)$ wahr für ein beliebiges $n\in \mathbb{N}$
   
   Zeige damit, dass $A(n+1)$ ebenfalls wahr ist:
   $$A(n+1):\sum_{j=1}^{(n+1)}j^{3}= \frac{(n+1)^{2}((n+1)+1)^{2}}{4}$$
	Dazu wird verwendet: $A(n+1)$ lässt sich relativ zu $A(n)$ schreiben:
	$$
\sum_{j=1}^{n+1}j^{3}=\sum_{j=1}^{n}j^{3}+(n+1)^{3}
$$
	Nun kann man die Induktionsvoraussetzung benutzen, und die als wahr angenommene Formel für $A(n)$ einsetzen:
	$$
\begin{align}
\sum_{j=1}^{n+1}j^{3}&=\left( \frac{n^{2}(n+1)^{2}}{4} \right)+(n+1)^{3} \\
 \\
&=\frac{n^{2}(n+1)^{2}\;+\;4(n+1)^{3}}{4} \\ \\

&=\frac{n^{2}(n^{2}+2n+1)+ 4()}{} \\
&=\dots \\
&= \text{funktioniert}
\end{align}

$$

# Bsp.3 geometrische Summenformel

$$
\forall_{n\in \mathbb{N}_{0}}: A(n):\sum_{j=0}^{n}q^{j}=\frac{q^{n+1}-1}{q-1}\quad,\quad q\in \mathbb{R}\setminus \{1  \}
$$

