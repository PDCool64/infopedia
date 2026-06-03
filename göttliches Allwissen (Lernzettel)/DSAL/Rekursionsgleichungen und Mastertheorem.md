---
tags:
  - DSAL
status: rot
---
---
# Rekursiongleichungen

>[!def] Rekursionsgleichungen
>Eine **Rekursionsgleichung** ist eine Gleichung oder Ungleichung, die eine Funktion durch ihre eigenen Funktionswerte für kleinere Eingaben beschreibt.
>
>---
>Eine häufig auftauchende Form von Rekursionsgleichungen ist diese:
>$$ T(n)= a\cdot T\left(  \frac{n}{b} \right) + f(n) $$
>wobei:
>- Jede Stufe des Problems teilt sich in $a$ Teilprobleme auf
>- Jedes der Teilprobleme hat die Größe $\frac{n}{b}$
>- Die Kosten für das Aufteilen des Problems in Teilprobleme und das darauffolgende Kombinieren der Teillösungen sind $f(n)$

## Lösen von Rekursionsgleichungen

### Scharfes Hinsehen am Rekursionsbaum
- Stelle die rekursiven Aufrufe als Baum da
- notiere für jeden Knoten den momentanen Wert des Eingabeparameters $n$

- Finde eine Formel für den durch Aufteilen + Kombinieren entstehenden Aufwand in jeder Ebene, basierend auf $f$
- Bestimme die Anzahl der Ebenen meist mit $\log_{b}{n}$   
- Bestimme die Anzahl der Blätter (meist mit $a^{\log_{b}{n}}=n^{\log_{b}a}$) und multipliziere mit den Basis-Kosten pro Blatt

Meist entsteht eine Formel wie:
$$
T(n) = 
\underbrace{ c\cdot n^{\log_{b}a}}
_{
  \begin{aligned}
    &\text{Kosten der Blätter}\\
    &\text{mit }T(1)=c
  \end{aligned}
}
+
\underbrace{ \sum_{i=0}^{\log_{b}n-1} }
_{ 
  \begin{aligned}
    &\text{Summe über} \\
    &\text{innere Ebenen}
  \end{aligned} 
}
\underbrace{ a^{i}\cdot f\left( \frac{n}{b^{i}} \right) }_{ \text{Kosten pro Ebene} }
$$
Mit ein wenig Glück, kann man diese Summenformel mit der [[Formelsammlung Summen]] zu einem geschlossenen Ausdruck nach oben/unten abschätzen (je nachdem ob $\mathcal{O},\Omega, \dots$ gesucht ist).
### Substitutionsmethode
Zeige durch vollständige Induktion, dass ein -durch [[#Scharfes Hinsehen am Rekursionsbaum]] als plausibel erkannter- Ausdruck tatsächlich die [[Landau-Notation|Quantor Definitionen]] der gewünschten Laufzeitklasse erfüllt.

Beispiel:
- Gegeben: $$T(n)=\begin{cases} 1&,n\le 1\\2\cdot T\left( \left\lfloor \frac{n}{2}  \right\rfloor \right)+n&,n \ge{2}\end{cases}$$
- Hypothese: $T(n)\in \mathcal{O}(n\cdot \log n)$
- Z.Z. $\exists_{c>0}\exists_{n_{0}\in \mathbb{N}}\forall_{n\ge n_{0}}:T(n)\le c\cdot n\log n$
- Beweis:
  Durch Ausprobieren mit kleinen Werten wähle $c=2,n_{0}=2$
	- Induktionsanfang: 
		  $T(2)=2\cdot T\left( \left\lfloor  \frac{2}{2}  \right\rfloor \right)+2 = 2\cdot T(1)+2=4$ 
		  also $T(2)=4 \le c\cdot 2\log_{2}2=2c=4$
	- Induktionsvoraussetzung:
		- Gelte für ein beliebiges aber festes $n\in \mathbb{N}$:
			  $T\left( \left\lfloor  \frac{n}{2}  \right\rfloor \right)\leq 2\cdot \left\lfloor  \frac{n}{2}  \right\rfloor\log_{2}\left\lfloor  \frac{n}{2}  \right\rfloor$
	- Induktionsschritt:$$
\begin{align}
T(n)&= 2\cdot T\left( \left\lfloor  \frac{n}{2}  \right\rfloor  \right) +n \\
&\overset{(IV)}\le 2\cdot \Big(2\cdot \left\lfloor  \frac{n}{2}  \right\rfloor\log_{2}\left\lfloor  \frac{n}{2}  \right\rfloor \Big) +n \\
&\le 2n \log_{2}\lfloor \frac{n}{2} \rfloor +n \\ 
&\le 2n \log_{2} \frac{n}{2}  +n \\
&= 2n(\log_{2}n-\log_{2}2)+n \\
&= 2n\log_{2}n -2n+n \\
&= 2n\log_{2}n-n \\
&\le 2n \log_{2}n
\end{align}
$$
### Mastertheorem
Gegeben sei
$$
T(n) =a\cdot T\left( \frac{n}{b} \right)+f(n)\;,\;a\ge 1\;,\;b>1
$$
Dann ist die Anzahl der Blätter im Rekursionsbaum
$$
n^{E} \;,\;E:= \log_{b}{a}
$$
(weil $a^{\log_{b}n}=n^{\log_{b}a}=:n^{E}$)


|     | Wenn                                                                                                                                                          | Dann                                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------- |
| 1.  | $f\in \mathcal{O}(n^{E-\varepsilon})$ für ein $\varepsilon>0$                                                                                                 | $T\in\Theta(n^{E})$<br>(Blätter dominieren) |
| 2.  | $f\in\Theta(n^{E})$                                                                                                                                           | $T\in\Theta(n^{E}\cdot \log n)$             |
| 3.  | $f\in\Omega(n^{E}+\varepsilon)$ für ein $\varepsilon>0$ <br>und<br>$a\cdot f\left( \frac{n}{b} \right)\le d\cdot f(n)$ für ein $d<1$ und $n$ hinreichend groß | $T\in\Theta(f)$                             |
> Bemerke, dass das Mastertheorem nicht alle Fälle abdeckt.

