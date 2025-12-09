---
tags:
  - AFI
status: rot
---
---

>[!def] Betrag
>Sei $K$ ein [[Körper#Angeordneter Körper|Angeordneter Körper]]. Dann wird der **Betrag** oder **Absolutbetrag** $\left| x \right|$ von $x$ definiert durch
>
>$$\left| x \right| := \begin{cases} x &,\text{ falls } x\ge 0 \\ -x &,\text{ falls }x<0\end{cases}$$

Damit lässt sich für alle $x,y\in K$ zeigen:
- $\left| x \right|\ge 0$ sowie $\left| x \right|>0\text{ für }x\neq 0$
- $\left| x \right|=\left| -x \right|$
- $x\le\left| x \right|$
- $\left| x\cdot y \right|=\left| x \right|\cdot \left| y \right|$

- $\left| \frac{1}{y} \right|=\frac{1}{\left| y \right|}$ sowie $\left| \frac{x}{y} \right|=\frac{\left| x \right|}{\left| y \right|}\text{ für }y\neq 0$

- $\left| x+y \right|\le\left| x \right|+\left| y \right|$ (*Dreiecksungleichung*)
> Die **Dreiecksungleichung** wird für viele Beweise wichtig bleiben. Sie erlaubt ein praktisches Abschätzen von größer/kleiner Beziehungen. 
> 
> Eine geometrische Interpretation ist, dass der kürzeste Weg zwischen zwei Punkten eine Gerade ist. Mit Vektoren: Sei $\vec{x}$ der kürzeste Weg von $A$ nach $B$ und $\vec{y}$ der kürzeste Weg von $B$ nach $C$, so ist der direkte Weg $A\to C$ immer kürzer oder gleich dem Weg $A\to B\to C$ d.h.k
> $\left| \vec{x}+\vec{y} \right|\le\left| \vec{x} \right|+\left| \vec{y} \right|$.

- $\left| x+y \right|\ge\left| \left| x \right|-\left| y \right| \right|\ge\left| x \right|-\left| y \right|$ (*2. Dreieckungleichung*)

- $\left| x \right|\le y \implies -y\le x \le y$

