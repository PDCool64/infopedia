Sei $A(n)\;,\;n\in \mathbb{N}_{0}$ eine [[Aussagenlogik|Aussage]], die von einer [[Zahlenräume#Natürliche Zahlen $ mathbb{N}$|natürlichen Zahl]] $n$ abhängt. Um zu beweisen, dass die Aussage für alle $n\geq n_{0}$ richtig ist, genügt es, zu beweisen:
1. $A(n)$ ist wahr für $n=n_{0}$ (**Induktionsanfang**)
2. $A(n)\implies A(n+1)\;,\;n\geq n_{0}$ (**Induktionsschritt**)
### Bemerkungen:
- $n_{0}$ ist nicht immer gleich $1$. Es kann eine beliebige Zahl, ab welcher die Behauptung gilt, sein.

# Beispiel: Formelle Runterschrift
## Gaußsche Summenformel

0. Zu zeigen ist:
$$
\forall_{n\in \mathbb{N}}:A(n):\sum_{i=1}^{n}i=\frac{n(n+1)}{2}
$$


1. Induktionsanfang: $(\text{I.A.})$
   Mit dem Fall $A(1)$ wird die Aussage für das kleinste $n\in \mathbb{N}$ bewiesen:
   $$\begin{align}
\sum_{i=1}^{1}i&=\frac{1(1+1)}{2} \\
1&=\frac{2}{2} \\ \\

1&=1
\end{align}$$
2. Induktionsvoraussetzung $(\text{I.V.})$ :
   Gelte $A(n)$ für ein beliebiges aber festes $n$.
   
3. Induktionsschritt $(\text{I.S.})$ :
   
   Wir zeigen nun unter der Annahme, der Induktionsvoraussetzung $(\text{I.V.})$, dass $A(n+1)$ ebenfalls wahr ist.

	Zu zeigen ist also:
$$
\begin{align}
\sum_{i=1}^{n+1}i &= \frac{(n+1)\left(\left(n+1\right)+1\right)}{2} 
\end{align}
$$
	Die Summe $\sum_{i=1}^{n+1}$ lässt sich auch relativ zu $A(n)$ ausdrücken: $$
\begin{align}

n\!+\!1+\sum_{i=1}^{n}i &= \frac{(n+1)\left(\left(n+1\right)+1\right)}{2}
\end{align}
$$
	Da wir mit der die Induktionsvoraussetzung $(I.V.)$ annehmen, dass $A(n)$ wahr ist, kann man für $\sum_{i=1}^{n}$ die Formel einsetzen:
 $$
\begin{align}
n\!+\!1+\frac{n(n+1)}{2} &\overset{\color{red}(I.V.)}= \frac{(n+1)\left(\left(n+1\right)+1\right)}{2}
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

Die Behauptung wurde somit durch Vollständige Induktion bewiesen.
