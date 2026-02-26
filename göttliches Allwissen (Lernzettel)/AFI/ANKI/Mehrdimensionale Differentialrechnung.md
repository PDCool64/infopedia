
TARGET DECK: AFI::Differentialrechnung:Mehrdimensional
FILE TAGS: differentialrechnung

Für das Intervall $I$ ist die Kurve 
$$\varphi:I\to \mathbb{R}^{n}\;,\;t\mapsto \begin{pmatrix}
\varphi_{1}(t) \\
\vdots \\
\varphi_{n}(t)
\end{pmatrix}$$
stetig (bzw. differenzierbar), in $t_{0}\in I$, wenn alle {{c1:: $\varphi_{1},\dots,\varphi_{n}$ dort stetig (bzw. differenzierbar) sind.}}
<!--ID: 1772122363433-->


Die Euklidische Norm ist für $x\in \mathbb{R}^{n}$ definiert als: #flashcard
$$\left| \left| x \right| \right|=\left| \left| x \right| \right|_{2}=\sqrt{ x_{1}^{2}+\dots+x_{n}^{2} }$$
<!--ID: 1772122363417-->


Nenne die drei definierenden Eigenschaften einer Norm: #flashcard
Für alle $x,y\in \mathbb{R}^{n}$ gilt
1. $\left| \left| x \right| \right|\ge{0}$ und $\left| \left| x \right| \right|=0\iff x=0$
2. $\left| \left| c\cdot x \right| \right|=\left| c \right|\cdot \left| \left| x \right| \right|$ 
3. Die Dreicksungleichung gilt:
	   $\left| \left| x+y \right| \right|\le \left| \left| x \right| \right|+\left| \left| y \right| \right|$
<!--ID: 1772122363420-->



Definiere Stetigkeit einer Abbildung mit Mehrdimensionalem Definitions- und Zielbereich #flashcard
Sei $M\subseteq \mathbb{R}^{m}\;,\;a\in M\;,\;f:M\to \mathbb{R}^{n}$.
$f$ ist stetig in $a$, wenn $\forall_{\varepsilon>0}\exists_{\delta>0}$ sodass
$$
\forall_{x\in D}\text{ mit }\left|\left| x-x_{0} \right|\right|<\delta\text{ gilt :} \\
$$
$$ \left| \left| f(x)-f(a) \right|  \right| <\varepsilon$$
<!--ID: 1772122363422-->


Definiere die Richtungsableitung einer Funktion. #flashcard
Sei $U\subseteq \mathbb{R}^{n}$  und $f:U\to \mathbb{R}^{m}$ mit $a\in U$ und $v\in \mathbb{R}^{n}\setminus\{ 0 \}$.
Gibt es $\rho>0$, sodass $\{ a+tv\mid\left| t \right|<\rho \}\subseteq U$, dann definiere die Kurve
$$
\varphi_{a,v}:(-\rho,\rho)\to \mathbb{R}^{m}\;,\;t\mapsto f(a+tv)
$$
Wenn dann der Grenzwert
$$
D_{v}f(a):= \varphi'_{a,v}(0) = \lim_{ h \to \infty } \frac{1}{h}\Big( f(a+hv)-f(a) \Big) 
$$
existiert, dann heißt dieser Richtungsableitung von $f$ im Punkt $a$ in Richtung $v$.
<!--ID: 1772122363425-->



Definiere die partielle Ableitung einer Funktion. #flashcard
Sei $U\subseteq \mathbb{R}^{n}$ offen, $a\in U$ und $F:U\to \mathbb{R}^{m}$ eine Funktion.
$F$ heißt partiell differenzierbar bezüglich der $k$-ten Koordinate, wenn
$$
D_{k}F(a):= \frac{\partial F}{\partial x_{k}}:= D_{e_{k}}F(a)= \lim_{ t \to 0 } \frac{1}{t} \Big( F(a+t\cdot e_{k})-F(A) \Big)
$$
existiert.
<!--ID: 1772122363427-->



Die einzelnen {{c1::Spalten}} der Jacobi-Matrix (aka. Funktionalmatrix; aka. Differential) sind jeweils die Partiellen Ableitungen nach je einer Variable.
<!--ID: 1772122363435-->


Definiere den Gradienten einer Funktion $F:\mathbb{R}^{m}\to \mathbb{R}$ in einem Punkt. #flashcard
Der Gradient ist das Transponierte der -hier einzeiligen- Jakobi Matrix.
$$
\nabla F(a)=DF(a)^{tr}
$$
Somit ist er einfach der Spaltenvektor, in dem jeder Eintrag die Ableitung nach jeweils einer Variable ist.
<!--ID: 1772122363430-->


Definiere, wann eine Funktion stetig partiell differenzierbar ist. #flashcard
$F$ ist stetig partiell differenzierbar, wenn $F$ partiell differenzierbar ist und alle partiellen Ableitungen $D_{k}F$ stetig sind.
<!--ID: 1772124259899-->
