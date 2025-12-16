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
\begin{tikzpicture}[scale=1.2, every node/.style={scale=1.2}]

  % ==== Parameter ====
  \def\nmin{1}
  \def\nmax{10}

  % ==== Achsen ====
  \draw[->, thick] (-0.5,0) -- (\nmax+0.5,0) node[right] {$n$};
  \draw[->] (0,-3) -- (0,3);

  % ==== Gitter ====
  \draw[very thin, gray!40] (0,-3) grid (\nmax,3);
  
  % ==== N ====
  \draw[red, thick,dashed] (4,-3) --(4,3);
  \node[red] at (4,3.3) {$N$};
  
  \node[black] at (-1,0) {$A$};

  % ==== Folge 1: c_n = 4/n ====
  \foreach \n in {\nmin,...,\nmax} {
    \fill[lime] ({\n}, {4/(\n+1)}) circle (2pt);
  }

  % ==== Folge 2: b_n = 1/n ====
  \foreach \n in {3,...,\nmax} {
    \fill[orange] (\n, {1/(\n-2.4)}) circle (2pt);
  }
   \fill[orange] (2,3) circle (2pt);

  % ==== Folge 3: a_n = -2/n ====
  \foreach \n in {\nmin,...,\nmax} {
    \fill[teal] (\n, {-2/\n}) circle (2pt);
  }

  % ==== Labels ====
  \node[lime]   at (-1, 2)   [right] {$c_n$};
  \node[orange] at (-1, 3)   [right] {$b_n$};
  \node[teal]   at (-1, -2)  [right] {$a_n$};
  
  

\end{tikzpicture}

\end{document}
```

## Mit Teilfolgen
![[Folgen für AFI#Teilfolgen]]

Resultierendes Konvergenzkriterium:
>[!def] Konvergenz von Teilfolgen
> Sei $(a_n)_{n\ge 1}$ eine [[Folgen für AFI#Grenzwert von Folgen|konvergente]] Folge mit Limes $a$.
> Dann konvergiert auch *jede* Teilfolge von $(a_n)_{n\ge 1}$ gegen $a$.

Insbesondere kann die Konvergent *widerlegt* werden, in dem eine nicht konvergente Teilfolge angegeben wird.


## Mit Monotonie und Beschränktheit
>[!def] Monotonie und Beschränktheit erzwingen Konvergenz
> Jede monotone, beschränkte [[Reelle Zahlen und Schranken|reelle]] Folge $(a_n)_{n\ge 1}$ ist konvergent.
> Sei $W$ die Wertemenge von $(a_n)_{n\ge 1}$, so gilt:
> $$
> \lim_{ n \to \infty } a_{n}= \begin{cases}
> \text{sup }W &,(a_n)_{n\ge 1}\text{ ist monoton wachsend} \\
> \text{inf }W &,(a_n)_{n\ge 1}\text{ ist monoton fallend}
> \end{cases}
> $$
> 

Anders gesagt aber gleichbdeutend:
>[!def] Monotonie und einseitige Beschränktheit
> - Eine nach oben beschränkte und monoton wachsende Folge ist konvergent gegen ihr Supremum.
> - Eine nach unten beschränkte und monoton fallende Folge ist konvergent gegen ihr Infimum.

(Bei monoton wachsenden Folgen ist die Beschränktheit nach unten durch den Startwert sowieso gegeben; Bei monoton fallenden Folgen analog die Beschränkung nach oben durch den Startwert.)


## Cauchy-Kriterium
>[!def] Cauchy-Folgen
> Eine reelle Folge $(a_n)_{n\ge 1}$ heißt **Cauchy-Folge**, wenn es zu jedem $\varepsilon>0$ ein (von $\varepsilon$ abhängiges $N\in \mathbb{N}_{0}$ gibt, so dass:
> $$
> \forall_{m,n\ge N}:\left| a_{m}-a_{n} \right| <\varepsilon 
> $$

D.h. : 
- Wenn sich ab einem $N$ *alle Kombinationen* der restlichen Folgenglieder um weniger als $\varepsilon$ von einander unterscheiden, dann ist die Folge konvergent.
- Man benötigt keinen Grenzwert-Kandidaten

#### Beispiel-Beweis:
