---
tags:
  - AFI
status: rot
---
---
# Kriterien für die [[Folgen für AFI#Grenzwert von Folgen|Konvergenz]] von Folgen


Grundliegend ist die normale Grenzwertdefinition:
![[Folgen für AFI#Grenzwert von Folgen]]


---
# Kriterien für die Konvergenz:

### Konvergenz mit bekanntem Grenzwert-Kandidaten

>[!def] Konvergenz mit bekanntem Grenwert-Kandidanten
> Sei $(a_{n})_{n\geq 1}$ eine reelle Folge und $a\in \mathbb{R}$. Die Folge konvergiert genau dann gegen $a$, wenn
> $$(a_{n}-a)_{n\geq 1}$$ eine Nullfolge ist.
### Konvergenz mit Beschränktheit und Nullfolge
>[!def] Konvergenz mit Beschränktheit und Nullfolge
> Ist $(a_{n})_{n\geq 1}$ eine *Nullfolge* und $(b_{n})_{n\geq 1}$ eine *beschränkte* Folge, dann ist
> $$(a_{n}\cdot b_{n})_{n\geq 1}$$ eine *Nullfolge*.

## Sandwich-Lemma
>[!def] Sandwich Lemma
> Gegeben seien reelle Folgen $(a_{n})_{n\geq 1}\;,\;(b_{n})_{n\geq 1}\;,\;(c_{n})_{n\geq 1}$ mit der Eigenschaft $\lim_{ n \to \infty }a_{n}= \lim_{ n \to \infty }c_{n}=A$.
> 
> Gibt es ein $N\in \mathbb{N}$, so dass
> $$\forall_{n\ge N} :a_{n} \le b_{n} \le c_{n}$$ so ist auch $(b_{n})_{n\geq 1}$ konvergent mit $\lim_{ n \to \infty }b_{n}=A$.
> ---
> D.h. wenn ein $N$ existiert, ab dem $b_{n}$ zwischen den beiden Folgen $a_{n}$ und $b_{n}$ eingeschränkt ist, dann konvergiert es ebenso gegen $A$.


```tikz
\begin{document}
\begin{tikzpicture}

  % ==== Parameter wie bei Desmos ====
  \def\xmin{0}
  \def\xmax{10}
  \def\ymin{-3}
  \def\ymax{3}

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
    \draw (0.1,\y) -- (-0.1,\y) ;

  % ==== Funktionsbereich clippen ====
  \begin{scope}
    \clip (\xmin,\ymin) rectangle (\xmax,\ymax);
    \draw[color=lime, thick, domain={\xmin+1}:\xmax] plot (\x ,{4/\x},);
    \draw[color=orange, thick, domain={\xmin+1}:\xmax] plot (\x, {1/\x)});
    \draw[color=teal, thick, domain={\xmin+1}:\xmax] plot (\x, {- 2/\x});
  \end{scope}

  % ==== Funktionsbeschriftungen außerhalb des Clips ====
  \node[color=lime, right] at (\xmax,\xmax) {$f(x)=x$};
  \node[color=teal, right] at (\xmax,{sin(\xmax r)}) {$f(x)=\sin x$};


\end{tikzpicture}
\end{document}
```
