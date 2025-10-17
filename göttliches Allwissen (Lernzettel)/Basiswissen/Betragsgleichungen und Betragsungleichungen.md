gesucht sind [[Zahlenräume#Rationale Zahlen $ mathbb{Q}$|reelle]] Lösungen $x$ von [[Gleichungen und Ungleichungen|Gleichungen]] der Form
$$
\begin{array}{rllll}
ax+b=|cx+d|
\end{array}
$$
Den Betrag löst man durch eine **Fallunterscheidung** auf:
$$
|cx+d|=\begin{cases}
cx+d&,cx+d \geq 0 \\
-cx-d&,cx+d<0
\end{cases}
$$
Dabei lässt *Fallbedingung* bei konkreten Werten vereinfachen, wobei aber auf das Vorzeichen von $c$ geachtet werden muss:
$$
\begin{align}
cx+d &\overset{?}{\geq}0 \\
x &\overset{?}{\geq} -\frac{d}{c}
\end{align}
$$
Somit sind zwei verschiedene Fälle zu untersuchen:
1. Der Wert im Betrag ist positiv:
   $$\begin{array}{rllll}
&\underbrace{ cx+d\geq 0 }_{ \text{Fallbedingung} }&\wedge &\underbrace{ ax+b=cx+d }_{ \text{resultierende Gleichung} } \\ \\

\iff& cx+d\geq 0 &\wedge & \left(a\!-\!c\right)x+\left(b\!-\!d\right)=0 \\
 \\
\end{array}$$

$$\to \mathbb{L}_{1}\;\text{als Lösungsmenge für den 1. Fall entsteht}$$ 

2. Der Wert im Betrag ist negativ:
   
   $$\begin{array}{rllll}
&\underbrace{ cx+d< 0 }_{ \text{Fallbedingung} }&\wedge &\underbrace{ ax+b=-cx-d }_{ \text{resultierende Gleichung} } \\ \\

\iff& cx+d< 0                                   &\wedge &       \left(a\!+\!c\right)x+\left(b\!+\!d\right)=0 \\
 \\
\end{array}$$
$$\to \mathbb{L}_{2}\;\text{als Lösungsmenge für den 2. Fall entsteht}$$
Die Gesamtlösungsmenge beträgt dann:
$$
\mathbb{L}=\mathbb{L}_{1} \cup \mathbb{L}_{2}
$$
## 1. Beispiel
Gegeben ist die Gleichung 
$$
x+1=|2-x|
$$
Fallbedingung:
1. Fall : $2-x\geq 0 \iff x\le 2$
   $$
\begin{array}{rlrll}
x\le 2&\wedge& x+1&=2-x &|+x\\
x\le 2&\wedge& 2x+1&=2  &|-1|:2 \\
x\le 2&\wedge& x&=\frac{1}{2} 
\end{array}
$$
$$
\mathbb{L}_{1}=\left\{  x\in \mathbb{R} \mid \left( x\le 2 \right)  \;\wedge\; \left( x=\frac{1}{2} \right) \right\}=\left\{   \frac{1}{2} \right\}
$$
2. Fall : $2-x< 0 \iff x> 2$    $$
\begin{array}{rlrll}
x> 2&\wedge& x+1&=-2+x &|-x\\
x> 2&\wedge& 1&\neq-2  &|-1|:2 \\
\end{array}
$$
$$
\mathbb{L}_{2}=\emptyset
$$

Die Gesamtlösungsmenge beträgt dann:
$$
\mathbb{L}=\mathbb{L}_{1} \cup \mathbb{L}_{2} = \emptyset \cup \left\{  \frac{1}{2}  \right\}=\left\{  \frac{1}{2}  \right\}
$$
Graphisch:
```tikz
\begin{document}
\begin{tikzpicture}

  % ==== Parameter wie bei Desmos ====
  \def\xmin{-1}
  \def\xmax{5}
  \def\ymin{-1}
  \def\ymax{4}

  % ==== Gitter ====
  \draw[very thin, gray] (\xmin,\ymin) grid (\xmax,\ymax);

  % ==== Achsen ====
  \draw[->] (\xmin,0) -- (\xmax+0.5,0) node[right] {$x$};
  \draw[->] (0,\ymin) -- (0,\ymax+0.5) node[above] {$y$};

  % ==== Ticks und Labels (X-Achse) ====
  \foreach \x in {\xmin,...,\xmax}
    \draw (\x,0.1) -- (\x,-0.1) node[below] {\x};

  % ==== Ticks und Labels (Y-Achse) ====
  \foreach \y in {\ymin,...,\ymax}
    \draw (0.1,\y) -- (-0.1,\y) node[left] {\y};

  % ==== Funktionsbereich clippen ====
  \begin{scope}
    \clip (\xmin,\ymin) rectangle (\xmax,\ymax);
    \draw[color=lime, thick, domain=\xmin:\xmax] plot (\x,{\x+1});
    \draw[color=teal, thick, domain=\xmin:\xmax] plot (\x,{abs(2-\x)});
  \end{scope}

  % ==== Funktionsbeschriftungen außerhalb des Clips ====
  \node[color=lime, right] at (2.5,\ymax+0.5) {$g(x)=x+1$};
  \node[color=teal, right] at (\xmax,3) {$f(x)=|2-x|$};
  \fill (0.5,1.5) circle (3pt);


\end{tikzpicture}
\end{document}
```
# Betragsungleichungen
Gesucht sind [[Zahlenräume#Rationale Zahlen $ mathbb{Q}$|reelle]] Lösungen $x$ von [[Gleichungen und Ungleichungen#^4dfb68|Ungleichungen]] der Form $$
\begin{array}{rllll}
|cx+d|\geq a
\end{array}
$$ (Es kann angenommen werden, dass $c> 0$, sonst durch Neudefinition zu $|-cx-d|\ge a$ lösbar)

0. Ist $a<0$, dann ist sofort ersichtlich, dass $\mathbb{L}=\mathbb{R}$

Ist dies nicht der Fall, löst man den Betrag durch eine **Fallunterscheidung** auf:
$$
|cx+d|=\begin{cases}
cx+d&,cx+d \geq 0 \\
-cx-d&,cx+d<0
\end{cases}
$$
Da $c<0$, lässt sich die *Fallbedingung* immer so vereinfachen:
$$
|cx+d|=\begin{cases}
cx+d&,x\ge -\frac{d}{c} \\
-cx-d&,x<-\frac{d}{c}
\end{cases}
$$
Somit sind zwei verschiedene Fälle zu untersuchen:
1. Der Wert im Betrag ist positiv:$$\begin{array}{rllll}
&\underbrace{ x\ge -\frac{d}{c} }_{ \text{Fallbedingung} }&\wedge &\underbrace{ cx+d\geq a }_{ \text{resultierende Gleichung} } \\ \\

\iff & x\ge -\frac{d}{c}                                  &\wedge &       cx+d-a\ge0
\end{array}$$$$\to \mathbb{L}_{1}\;\text{als Lösungsmenge für den 1. Fall entsteht}$$ 
2. Der Wert im Betrag ist negativ:$$\begin{array}{rllll}
&\underbrace{ x< -\frac{d}{c} }_{ \text{Fallbedingung} }&\wedge &\underbrace{ -cx-d\geq a }_{ \text{resultierende Gleichung} } \\ \\

\iff & x< -\frac{d}{c}                                  &\wedge &       -cx-d-a\ge0 
\end{array}$$$$\to \mathbb{L}_{2}\;\text{als Lösungsmenge für den 2. Fall entsteht}$$
Die Gesamtlösungsmenge beträgt dann:$$
\mathbb{L}=\mathbb{L}_{1} \cup \mathbb{L}_{2}
$$

## 2. Beispiel

Gegeben ist die Ungleichung $|2-x|\ge 1$
1. Fall : $2-x\geq 0 \iff x\le 2$
   $$
\begin{array}{rlrll}
x\le 2&\wedge& 2-x&\geq1 &|+x\\
x\le 2&\wedge& 2&\geq x+1  &|-1 \\
x\le 2&\wedge& 1&\geq x
\end{array}
$$
$$
\mathbb{L}_{1}=\left\{  x\in \mathbb{R} \mid \left( x\le 2 \right)  \;\wedge\; (x\le 1) \right\}=(-\infty,1]
$$
2. Fall : $2-x< 0 \iff x> 2$       $$
\begin{array}{rlrll}
x> 2&\wedge& -2+x&\geq1 &|+2\\
x> 2&\wedge& x&\geq 3   \\
\end{array}
$$
$$
\mathbb{L}_{2}=\left\{  x\in \mathbb{R} \mid \left( x> 2 \right)  \;\wedge\; (x\ge 3) \right\}=[3;+\infty)
$$

Die Gesamtlösungsmenge beträgt dann:$$
\mathbb{L}=\mathbb{L}_{1} \cup \mathbb{L}_{2} =(-\infty,1]\cup[3,\infty)
$$
### Graphisch:
```tikz
\begin{document}
\begin{tikzpicture}

  % ==== Parameter wie bei Desmos ====
  \def\xmin{-1}
  \def\xmax{5}
  \def\ymin{-1}
  \def\ymax{4}

  % ==== Gitter ====
  \draw[very thin, gray] (\xmin,\ymin) grid (\xmax,\ymax);

  % ==== Achsen ====
  \draw[->] (\xmin,0) -- (\xmax+0.5,0) node[right] {$x$};
  \draw[->] (0,\ymin) -- (0,\ymax+0.5) node[above] {$y$};

  % ==== Ticks und Labels (X-Achse) ====
  \foreach \x in {\xmin,...,\xmax}
    \draw (\x,0.1) -- (\x,-0.1) node[below] {\x};

  % ==== Ticks und Labels (Y-Achse) ====
  \foreach \y in {\ymin,...,\ymax}
    \draw (0.1,\y) -- (-0.1,\y) node[left] {\y};

  % ==== Funktionsbereich clippen ====
  \begin{scope}
    \clip (\xmin,\ymin) rectangle (\xmax,\ymax);
    \draw[color=orange, thick,dashed, domain=\xmin:\xmax] plot (\x,1);
    \draw[color=teal, thick, domain=\xmin:\xmax] plot (\x,{abs(2-\x)});
  \end{scope}

  % ==== Funktionsbeschriftungen außerhalb des Clips ====
  \node[color=orange, right] at (\xmax+0.1,1) {$a=1$};
  \node[color=teal, right] at (\xmax,3) {$f(x)=|2-x|$};
  
  \draw[color=black,dashed] (1,0)--(1,1);
  \draw[color=black,dashed] (3,0)--(3,1);
  
  \draw[color=lime, thick] (\xmin,0) --(1,0);
  \draw[color=lime, thick] (3,0) --(\xmax,0);
  \fill[color=lime] (1,0) circle (3pt);
  \fill[color=lime] (3,0) circle (3pt);
  
  \node[color=lime] at (1.85,-1.3) {$(-\infty,1]\cup[3,\infty)$};

	

\end{tikzpicture}
\end{document}
```

Analog entsteht durch $\mathbb{R}\setminus\mathbb{L}$ der Lösungsbereich von $|2-x|<1$:
```tikz
\begin{document}
\begin{tikzpicture}

  % ==== Parameter wie bei Desmos ====
  \def\xmin{-1}
  \def\xmax{5}
  \def\ymin{-1}
  \def\ymax{4}

  % ==== Gitter ====
  \draw[very thin, gray] (\xmin,\ymin) grid (\xmax,\ymax);

  % ==== Achsen ====
  \draw[->] (\xmin,0) -- (\xmax+0.5,0) node[right] {$x$};
  \draw[->] (0,\ymin) -- (0,\ymax+0.5) node[above] {$y$};

  % ==== Ticks und Labels (X-Achse) ====
  \foreach \x in {\xmin,...,\xmax}
    \draw (\x,0.1) -- (\x,-0.1) node[below] {\x};

  % ==== Ticks und Labels (Y-Achse) ====
  \foreach \y in {\ymin,...,\ymax}
    \draw (0.1,\y) -- (-0.1,\y) node[left] {\y};

  % ==== Funktionsbereich clippen ====
  \begin{scope}
    \clip (\xmin,\ymin) rectangle (\xmax,\ymax);
    \draw[color=orange, thick,dashed, domain=\xmin:\xmax] plot (\x,1);
    \draw[color=teal, thick, domain=\xmin:\xmax] plot (\x,{abs(2-\x)});
  \end{scope}

  % ==== Funktionsbeschriftungen außerhalb des Clips ====
  \node[color=orange, right] at (\xmax+0.1,1) {$a=1$};
  \node[color=teal, right] at (\xmax,3) {$f(x)=|2-x|$};
  
  \draw[color=black,dashed] (1,0)--(1,1);
  \draw[color=black,dashed] (3,0)--(3,1);
  
  \draw[color=lime, thick] (1,0) --(3,0);
  \fill[color=lime] (1,0) circle (3pt);
  \fill[color=lime] (3,0) circle (3pt);
  \fill[color=white] (1,0) circle (2pt);
  \fill[color=white] (3,0) circle (2pt);
  
  \node[color=lime] at (2,-1.3) {$(1,3)$};

	

\end{tikzpicture}
\end{document}
```


