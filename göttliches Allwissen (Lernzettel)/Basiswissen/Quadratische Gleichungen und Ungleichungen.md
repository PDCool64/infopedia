# Quadratische Gleichung

Gesucht werden die [[Zahlenräume#Reelle Zahlen $ mathbb{R}$|reellen]] Lösungen einer quadratischen [[Gleichungen und Ungleichungen|Gleichung]] der Form:
$$
ax^{2}+bx+c=0\quad,\quad a\neq {0} 
$$
Da $a\neq 0$ (sonst wäre es bloß eine lineare Gleichung), kann jede Gleichung dieser Form auch zu einer verschobenen *Normalparabel* umgeformt werden:
$$
\begin{align} \\
x^{2}+\;\;\;\;ax\;+\;\;b\;\;\; &=0 &|:a \\

x^{2}+\underbrace{ \frac{b}{a} }_{ p }x+\underbrace{ \frac{c}{a} }_{ q }&=0
\end{align}
$$

# Größe der Lösungsmenge.
Eine Quadratische Gleichung kann *keine, genau eine, oder zwei* [[Zahlenräume#Reelle Zahlen $ mathbb{R}$|reelle]] Lösungen haben.
Dies ist Abhängig von der Lage des [[Scheitelpunktsform der quadratischen Funktion|Scheitelpunkt]] der Parabel sowie ihrer Öffnungsrichtung.

Ablesen lässt sich die Größe der Lösungsmenge an der **Diskriminanten** der pq-Formel.
$$
x_{1,2}=-\frac{p}{2}\pm \sqrt{ \left( \frac{p}{2} \right)^{2}-q }
$$
Dabei ist die **Diskriminante** der Term unter der Wurzel:
$$
D=\left( \frac{p}{2} \right)^{2}-q
$$
Da die Quadratwurzel nur für nicht negative Zahlen definiert ist und $\sqrt{ 0 }=0$ folgt:
$$
\mathbb{L}= \begin{cases}
\emptyset &,D<0 \\
\Big\{  -\frac{p}{2}  \Big\} &,D=0 \\
\Big\{  -\frac{p}{2}-\sqrt{ D }\;;\;-\frac{p}{2}+\sqrt{ D }  \Big\} &,D>0
\end{cases}
$$
## Graphisch: Lage des Scheitelpunkts
Wird eine quadratische Gleichung der Form $x^{2}+px+q=0$ in die [[Scheitelpunktsform der quadratischen Funktion]] gebracht, erhält man folgenden Scheitelpunkt:
$$
\begin{align}
x^{2}+px+q&=0 &|\text{quadratische Ergänzung}\\ \\

x^{2}+px+\left( \frac{p}{2} \right)^{2}-\left( \frac{p}{2} \right)^{2}+q&=0  &|\text{1. binom. Formel rückwärts} \\ \\

\left( x+\frac{p}{2} \right)^{2}-\left( \frac{p}{2} \right)^{2}+q&=0 \\ \\

\Big( x-\underbrace{ \left(-\frac{p}{2}\right) }_{ x }\; \Big)^{2}\underbrace{ -\left( \frac{p}{2} \right)^{2}+q }_{ y=-D }&=0
\end{align}
$$
$$
\begin{align}
&\to S \left( \left( -\frac{p}{2} \right) \quad;\quad-\left( \frac{p}{2} \right)^{2}+q \right)  \\
&= S \left( -\frac{p}{2}\;;-D \right) 
\end{align}
$$
Interessant ist dabei die $y$-Komponente: Da die Normalparabel immer *nach oben geöffnet* ist, entscheidet sie darüber wie viele Nullstellen es gibt:

1. Der Scheitelpunkt liegt **über** der $x$-Achse:$$\begin{align}
&D<0 \\ 

&\implies \mathbb{L}= \left\{  \left( -\frac{p}{2} \right)  \right\}
\end{align}$$
```tikz
\begin{document}
\begin{tikzpicture}
  % Achsen
  \draw[->] (-1,0) -- (5,0) node[right] {$x$};
  \draw[->] (0,-1) -- (0,5) node[above] {$y$};
  \draw[dashed,lime] (0,1) -- (1,1);
  \draw[dashed,lime] (1,0) -- (1,1);

  \node[lime](G) at (-0.5,1) {$-D$};
  \node[lime](G) at (0.9,-0.4) {$-\frac{p}{2}$};

  \begin{scope}
    \clip (-1,-1) rectangle (5,5); % sichtbarer Bereich

    \draw[orange, thick, samples=400, domain=-5:5, smooth]
      plot (\x,{pow(\x-1,2)+1});
      

  \end{scope}
\end{tikzpicture}
\end{document}
``` 
2. Der Scheitelpunkt liegt **auf** der $x$-Achse:$$\begin{align}
&D=0 \\ 

&\implies \mathbb{L}= \left\{  \left( -\frac{p}{2} \right)  \right\}
\end{align}$$
```tikz
\begin{document}
\begin{tikzpicture}
  % Achsen
  \draw[->] (-1,0) -- (5,0) node[right] {$x$};
  \draw[->] (0,-1) -- (0,5) node[above] {$y$};
  
  \node[lime](G) at (1.9,-0.4) {$-\frac{p}{2}$};

  \begin{scope}
    \clip (-1,-1) rectangle (5,5); % sichtbarer Bereich

    \draw[orange, thick, samples=400, domain=-5:5, smooth]
      plot (\x,{pow(\x-2,2)});
      
      

  \end{scope}
  \fill[teal] (2,0) circle (3pt);
  
\end{tikzpicture}
\end{document}
``` 
3. Der Scheitelpunkt liegt **unter** der $x$-Achse:$$\begin{align}
&D>0 \\ 

&\implies \mathbb{L}= \left\{  \left( -\frac{p}{2} \right)-\sqrt{ D }\;;\;\left( -\frac{p}{2} \right)+\sqrt{ D }  \right\}
\end{align}$$
```tikz
\begin{document}
\begin{tikzpicture}
  % Achsen
  \draw[->] (-5,0) -- (5,0) node[right] {$x$};
  \draw[->] (0,-5) -- (0,5) node[above] {$y$};
  
   \draw[dashed,lime] (1,0) -- (1,-3);
   \draw[dashed,lime] (0,-3) -- (1,-3);

  \node[lime](G) at (0.9,-3.5) {$-\frac{p}{2}$};
  \node[lime](G) at (-0.5,-3) {$-D$};
  \begin{scope}
    \clip (-5,-5) rectangle (5,5); % sichtbarer Bereich

    \draw[orange, thick, samples=400, domain=-5:5, smooth]
      plot (\x,{pow(\x-1,2)-3});
      
      

  \end{scope}
  \fill[teal] (-0.732051,0) circle (3pt);
  \fill[teal] (2.73205,0) circle (3pt);
  
  
\end{tikzpicture}
\end{document}
``` 
# Lösungswege
## 1. Quadratische Ergänzung
   Bei der quadratischen Ergänzung zielt man darauf ab, die gegebene Gleichung zu dem *Ergebnis einer pq-Formel umzuformen*
   $$
\begin{array}{rll}
0&=\underbrace{ 4x^{2} }_{ a^{2} }\;\underbrace{ -12x }_{ -2ab }+5 &|+3^{2}-3^{2}\\
0&=\underbrace{ 4x^{2} }_{ a^{2} }\underbrace{ -12x }_{ -2ab }\;\underbrace{ +3^{2} }_{ +b^{2} }-3^{2}+5 \\
0&=\underbrace{ (2x-3)^{2} }_{ (a-b)^{2} }-3^{2}+5 \\
0&=(2x-3)^{2}-4 &|+4\\
4&=(2x-3)^{2}&|\sqrt{  \dots} \\
\pm2&=2x-3 &|+3|:2 \\
\frac{\pm 2+3}{2} &=x \\
 \\
\mathbb{L}&=\left\{  \frac{1}{2}; \frac{5}{2}  \right\}
\end{array}
$$
## 2. Mitternachtsformel
Eine alternative zur pq- Formel, bei der nicht zuerst der Faktor vor $x^{2}$ entfernt werden muss:
$$
\begin{align}
0=ax^{2}+bx+c \\
 \\
x_{1,2}=\frac{-b\pm \sqrt{ b^{2}-4ac }}{2a}
\end{align}
$$
Man kann zeigen, dass diese Formel gleichbedeutend mit der pq-Formel ist:

$$\begin{array}{rlll}
0&=&ax^{2}+bx+c&|:a\;,\;a\neq 0, \\
0&=&x^{2}+\underbrace{ \frac{b}{a} }_{ p }x+\underbrace{ \frac{c}{a} }_{ q }
\end{array}$$
Mit Einsetzen in die pq-Formel:
$$
\begin{align}
x_{1,2}&=-\frac{p}{2}\pm\sqrt{ \left(\frac{p}{2}\right)^{2}-q } \\ \\

&=-\frac{\frac{b}{a}}{2}\pm\sqrt{ \left(\frac{\frac{b}{a}}{2}\right)^{2}-\frac{c}{a} } \\  \\

&=-\frac{b}{2a}\pm \sqrt{ \left( \frac{b}{2a} \right)^{2}-\frac{c}{a} } \\ \\

&=-\frac{b}{2a}\pm \sqrt{  \frac{b^{2}}{4a^{2}} -\frac{c}{a} } \\
 \\
&=-\frac{b}{2a}\pm \sqrt{  \frac{b^{2}}{4a^{2}} -\frac{c\cdot 4a}{a\cdot 4a} } \\
 \\
&=-\frac{b}{2a}\pm \sqrt{  \frac{b^{2}-4ac}{4a^{2}}  } \\
 \\
&=-\frac{b}{2a}\pm \frac{\sqrt{ b^{2}-4ac }}{2a} \\
 \\
&=\frac{-b\pm \sqrt{ b^{2}-4ac }}{2a}
\end{align}
$$

## 3. pq-Formel
Formel um Quadratische Gleichungen der Form 
$$
0=x^{2}+px+q
$$
zu lösen. Auch wenn vor dem $x^{2}$ in der gegebenen Gleichung ein Faktor steht, welcher nicht Null ist, lässt sich dieser durch Division entfernen.
$$
x_{1,2}=-\frac{p}{2}\pm\sqrt{ \left(\frac{p}{2}\right)^{2}-q }
$$
## 4. Ablesen aus den Linearfaktoren
Ist die Gleichung schon als Produkt von Linearfaktoren gegeben, können die Nullstellen an diesen direkt abgelesen werden.

Denn: Ein Produkt ist genau dann null, wenn mindestens ein Faktor Null ist.
$$0=(x-3)(x+2)$$
$\implies(x-3)=0\;\;\vee\;\;(x+2)=0$
$\implies \mathbb{L}=\{ 3;-2 \}$

Ebenfalls gilt, dass eine schon bekannte (z.B. erratene) Nullstelle durch Polynomdivision als einer dieser Linearfaktoren aus dem Rest der Gleichung extrahiert werden kann. Dabei bleibt für das restliche Polynom genau die (ggfs. identische) andere Nullstelle übrig.

---

# Quadratische Ungleichung
Gesucht werden Gesucht werden die [[Zahlenräume#Reelle Zahlen $ mathbb{R}$|reellen]] Lösungen einer quadratischen [[Gleichungen und Ungleichungen#^4dfb68|Ungleichung]] der Form:$$
x^{2}+px+q \geq 0
$$
Durch Umformung erhält man als äquivalent:
$$
\begin{align}
\left( x+\frac{p}{2} \right)^{2}-D\geq 0
\end{align}
$$
Damit folgt für die Lösungsmenge:
$$
\mathbb{L}=\begin{cases}
\underbrace{ \left\{  x\in \mathbb{R} \mid x\leq -\frac{p}{2}-\sqrt{ D }  \right\} }_{ \text{bis linker Nullstelle} } \cap \underbrace{ \left\{  x\in \mathbb{R} \mid  x\geq -\frac{p}{2}-\sqrt{ D }  \right\} }_{ \text{ab rechter Nullstelle} } &,D>0\\
\mathbb{R} &,D \geq 0
\end{cases}
$$
```tikz
\begin{document}
\begin{tikzpicture}
  % Achsen
  \draw[->] (-5,0) -- (5,0) node[right] {$x$};
  \draw[->] (0,-5) -- (0,5) node[above] {$y$};
  
   \draw[thick,lime] (-5,0) -- (-0.732051,0);
   \draw[thick,lime] (2.73205,0) -- (5,0);

  \node[lime](G) at (-3,-0.5) {$ x\leq -\frac{p}{2}-\sqrt{ D }$};
  \node[lime](G) at (4.5,-0.5) {$ x\leq -\frac{p}{2}-\sqrt{ D }$};
  \begin{scope}
    \clip (-5,-5) rectangle (5,5); % sichtbarer Bereich

    \draw[orange, thick, samples=400, domain=-5:5, smooth]
      plot (\x,{pow(\x-1,2)-3});
      
      

  \end{scope}
  \fill[lime] (-0.732051,0) circle (3pt);
  \fill[lime] (2.73205,0) circle (3pt);
  
  
\end{tikzpicture}
\end{document}
``` 
```tikz
\begin{document}
\begin{tikzpicture}
  % Achsen
  \draw[->] (-5,0) -- (5,0) node[right] {$x$};
  \draw[->] (0,-1) -- (0,5) node[above] {$y$};
  \draw[thick,lime] (-5,0) -- (5,0);

 \node[lime] (G) at (0.9,-0.4) {$R$};

  \begin{scope}
    \clip (-1,-1) rectangle (5,5); % sichtbarer Bereich

    \draw[orange, thick, samples=400, domain=-5:5, smooth]
      plot (\x,{pow(\x-1,2)+1});
      

  \end{scope}
\end{tikzpicture}
\end{document}
``` 

Das Gegenstück zur Ungleichung 
$$
x^{2}+px+q\geq 0
$$
ist 
$$
x^{2}+px+q<0
$$
dabei ist die Lösungsmenge: $\mathbb{L}_{2}=\mathbb{R}\setminus\mathbb{L}$
```tikz
\begin{document}
\begin{tikzpicture}
  % Achsen
  \draw[->] (-5,0) -- (5,0) node[right] {$x$};
  \draw[->] (0,-5) -- (0,5) node[above] {$y$};
  
   \draw[thick,lime] (2.73205,0) -- (-0.732051,0);

  \node[lime](G) at (-3,-0.5) {$ x\in (\frac{p}{2}-\sqrt{ D };\frac{p}{2}+\sqrt{ D })$};
  
  \begin{scope}
    \clip (-5,-5) rectangle (5,5); % sichtbarer Bereich

    \draw[orange, thick, samples=400, domain=-5:5, smooth]
      plot (\x,{pow(\x-1,2)-3});q
      
      

  \end{scope}
  \fill[lime] (-0.732051,0) circle (3pt);
  \fill[lime] (2.73205,0) circle (3pt);
  
  \fill[white] (-0.732051,0) circle (2pt);
  \fill[white] (2.73205,0) circle (2pt);
  
  
  
\end{tikzpicture}
\end{document}
``` 

# Reduzierbarkeit auf den Standardfall
Es lassen sich *alle Varianten*, der Ungleichung auf den Fall 
$$
^^x^{2}+px+q \geq 0
$$
reduzieren oder zurückführen.
- Faktoren $a$ vor dem $x^{2}$ können durch Division entfernt werden
- Abbildungen mit $<$ oder $\leq$ können durch $\mathbb{R}\setminus \mathbb{L}$ bestimmt werden. *Aufpassen, ob Grenzen dabei sind oder nicht*.

$\to$
$\implies$

