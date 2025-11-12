>[!def] Körper
> Eine [[Mengen|Menge]] $\mathbb{K}$ bildet einen **Körper**, wenn zu je zwei Zahlen $x,y\in \mathbb{K}$
> - eine **Summe** $+\;:K\times K\to K\;,\;(a,b)\mapsto a+b$ 
> - und ein **Produkt** $\cdot\;:K\times K\to K\;,\;(a,b)\mapsto a\cdot b$
>
>definiert sind, welche die folgenden Rechenregeln erfüllen:
>
> ---
> 
> Für die *Addition*:
> - (A.1) $x+y=y+x$                   (Kommutativgesetz)<br><br>
> - (A.2) $x+(y+z)=(x+y)+z$ (Assoziativgesetz) <br><br>
> - (A.3) Es gibt ein Element $0\in \mathbb{K}$ mit $\forall_{x\in \mathbb{K}}:0+x=x$ 
> 		("$0$" ist hier eher als Name/Bezeichnung und nicht als die $0\in \mathbb{R}$ zu lesen)
> 		 ->  **Nullelement** bzw. **neutrales Element der Addition**. <br><br>
>  - (A.4) Zu jedem Element $x\in \mathbb{K}$ gibt es ein Element $(-x)\in \mathbb{K}$ mit $x+(-x)=0$
> 		-> **Inverses Element der Addition** <span id="additiv-invers"></span>
> 
> ---
> 
> Für die *Multiplikation*:
> - (M.1) $x\cdot y=y\cdot x$               (Kommutativgesetz)<br><br>
> - (M.2) $x\cdot (y\cdot z)=(x\cdot y)\cdot z$ (Assoziativgesetz)<br><br>
> - (M.3) Es gibt ein Element $1\in \mathbb{K}\;,1\neq 0$ mit $\forall_{x\in \mathbb{K}}:1\cdot x=x$ 
> 		("$1$" ist hier eher als Name/Bezeichnung und nicht als die $1\in \mathbb{R}$ zu lesen)
> 		 ->  Einselement** bzw. **neutrales Element der Multiplikation**.<br><br>
> - (M.4) Zu jedem Element $x\in \mathbb{K}\;,x\neq 0$ gibt es ein Element $(x^{-1})\in \mathbb{K}$ mit $x\cdot (x^{-1})=1$
> 		-> **Inverses Element der Multiplikation**
> 
>---
>Die Multiplikation und die Addition sind im folgenden Sinne verträglich:
>- (A.M) $x\cdot(y+z)=(x\cdot y)+(x\cdot z)$   (Distributivgesetz)

^a3c120

## Bemerkungen:
- Sowohl das neutrale als auch das inverse Element der Addition sowie der Multiplikation sind jeweils *eindeutig*. (Es kann in einem Körper z.B. nicht zwei neutrale Elemente geben) Dies ist nicht Teil der Definition, kann aber schnell gefolgter werden.
  
- $\mathbb{N}$ ist *kein* Körper, weil u.A. kein Inverses Element der Addition besteht. ($2+n\neq 0\;,\;n\in \mathbb{N}$)
  
- $\mathbb{Z}$ ist *kein* Körper, weil u.A. kein Inverses Element der Addition besteht. ($2\cdot z\neq 1\;,\;z\in \mathbb{Z}$
  
- in einem Körper ist ein Produkt genau dann Null, wenn einer der Faktoren Null ist:$$
a\cdot b=0\iff(a=0)\vee(b=0)
$$
- Diese Gesetze erlauben es uns, mit [[Gleichungen und Ungleichungen|Gleichungen]] zu arbeiten.

---
# Angeordneter Körper
>[!def] Angeordneter Körper
> Es sei $K$ ein Körper.
> Mann nennt $K$ einen **angeordneten Körper**, wenn es eine Teilmenge $P\subseteq K$ (genannt **Positivitätsbereich**) von $K$ gibt, die die folgenden Eigenschaften erfüllt:
> - Für alle $x\in K$ ist genau eine der Aussagen richtig: $x\in P$ oder $x=0$ oder $-x\in P$
> - Für alle $x,y\in P$ gilt: $x+y\in P$
> - Für alle $x,y\in P$ gilt: $x\cdot y\in P$
> 
> ---
> Durch$$x<y \;:\!\iff y-x\in P$$
> wir eine Relation "$<$" eingeführt, die sog. **Anordnung auf $K$**.
> 
> ---
> Weiter vereinbart man die Schreibweisen:
> - $x\le y \iff x<y \;\lor\; x=0$
> - $x>y\iff y<x$
> - $x\ge y\iff y\le x$
> 
^315cce
## Bemerkungen
- $K=P\overset{\cdot}{\cup}\{ 0 \}\overset{\cdot}{\cup}\{ -P \}$
  wobei "$\overset{\cdot}{\cup}$" hervorhebt, das die Mengen welche vereinigt werden disjunkt sind.
- Diese Gesetze erlauben es uns, mit [[Gleichungen und Ungleichungen|Ungleichungen]] zu arbeiten.
- Der Standard für einen angeordneten Körper sind die [[Zahlenräume#Rationale Zahlen $ mathbb{Q}$|Rationalen Zahlen]]
- Die [[Zahlenräume#Reelle Zahlen $ mathbb{R}$|Reellen Zahlen]] sind z.B. ein angeordneter Körper.


## Folgerungen
Direkt aus dieser Definition folgen die folgenden, intuitiv bekannten Eigenschaften:
Es sei $K$ ein angeordneter Körper.
- Für alle $a,b,c\in K$ gilt: $a<b\wedge b<c\implies a<c$ (*Transitivität*)

Für alle $a,b,c,d\in K$ gilt:
- $a+c<b+c \iff a<b$ (*Monotonie der Addition*)
- $a<b \land c\le d \implies a+c<b+d$ 
- $0<a<b\;\land\; 0<c\le d\;\implies ac<bd$ 
- $0<a<b\implies 0< a^{n }<b^{n}\;\;\forall_{n\in \mathbb{N}}$

- $a>0 \land b<0 \implies ab<0$
   $a<0 \land b<0 \implies ab>0$
- $0\leq a^{2}$; speziell $0<1$
  
- $a>0\iff a^{-1}>0$
- $0<a<b\;\land\; c<0\implies bc<ac<0$

- $$a<b\;,\;a\neq 0,b\neq 0 \implies \begin{cases}
a^{-1}<b^{-1}&,\;ab<0 \\
b^{-1}<a^{-1}&,\;ab>0
\end{cases}$$
  

>[!def] $\mathbb{Q}$ in anderen angeordneten Körpern
> Jeder angeordnete Körper $K$ "enthält" gewissermaßen $\mathbb{Q}$ (also auch $\mathbb{N}$ und $\mathbb{Z}$) in folgendem Sinn: Es gibt eine [[Abbildungen#Injektiv, Surjektiv, Bijektiv|injektive]] Abbildung $$
> \varphi:\mathbb{Q}\to K
> $$ welche die Rechenoperationen und die Anordnung respektiert, d.h. für alle $x,y\in \mathbb{Q}$ gilt:$$\begin{array}{rcl}
> \varphi(x+q)&=&\varphi(x)+\varphi(y) \\
> \varphi(x\cdot y)&=&\varphi (x)\cdot \varphi(y) \\
> x<y &\implies& \varphi(x)<\varphi(y)
> \end{array}$$
> 
> ---
> 
> Es gibt also eine Möglichkeit, für jedes Element aus $\mathbb{Q}$ eine Art Gegenstück in jedem angeordneten Körper $K$ zu finden, so dass sich diese untereinander genauso verhalten wie die Ursprungselemente in $\mathbb{Q}$.

- Der Beweis davon ist schwierig und wird hier nicht versucht.
