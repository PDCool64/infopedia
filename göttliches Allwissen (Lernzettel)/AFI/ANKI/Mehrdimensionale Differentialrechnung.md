
TARGET DECK: AFI::Differentialrechnung:Mehrdimensional
FILE TAGS: differentialrechnung

Für das Intervall $I$ ist die Kurve 
$$\varphi:I\to \mathbb{R}^{n}\;,\;t\mapsto \begin{pmatrix}
\varphi_{1}(t) \\
\vdots \\
\varphi_{n}(t)
\end{pmatrix}$$
stetig (bzw. differenzierbar), in $t_{0}\in I$, wenn alle {{c1:: $\varphi_{1},\dots,\varphi_{n}$ dort stetig (bzw. differenzierbar) sind.}}

Die Euklidische Norm ist für $x\in \mathbb{R}^{n}$ definiert als: #flashcard
$$\left| \left| x \right| \right|=\left| \left| x \right| \right|_{2}=\sqrt{ x_{1}^{2}+\dots+x_{n}^{2} }$$

Nenne die drei definierenden Eigenschaften einer Norm: #flashcard
Für alle $x,y\in \mathbb{R}^{n}$ gilt
1. $\left| \left| x \right| \right|\ge{0}$ und $\left| \left| x \right| \right|=0\iff x=0$
2. $\left| \left| c\cdot x \right| \right|=\left| c \right|\cdot \left| \left| x \right| \right|$ 
3. Die Dreicksungleichung gilt:
	   $\left| \left| x+y \right| \right|\le \left| \left| x \right| \right|+\left| \left| y \right| \right|$


Definiere Stetigkeit einer Abbildung mit Mehrdimensionalem Definitions- und Zielbereich #flashcard
Sei $M\subseteq \mathbb{R}^{m}\;,\;a\in M\;,\;f:M\to \mathbb{R}^{n}$.
$f$ ist stetig in $a$, wenn $\forall_{\varepsilon>0}\exists_{\delta>0}$ sodass
$$
\forall_{x\in D}\text{ mit }\left|\left| x-x_{0} \right|\right|<\delta\text{ gilt :} \\
$$
$$ \left| \left| f(x)-f(a) \right|  \right| <\varepsilon$$


