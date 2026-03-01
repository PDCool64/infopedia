TARGET DECK: AFI::Differentialrechnung
FILE TAGS: differentialrechnung

Definiere die Ableitung einer Funktion in einem Punkt #flashcard
Für $f:D\to\mathbb{R}$ und $x_{0}$ als innerer Punkt von $D\subseteq \mathbb{R}$ nennt man $f$ differenzierbar in $x_{0}$, wenn der Funktionsgrenzwert
$$
\lim_{ h \to 0 }  \frac{f(x_{0}+h)-f(x_{0})}{h}
$$
existiert. 
(Beachte, dass mit $x_{0}$ als innerem Punkt sowohl positive als auch negative $h$ berücksichtigt werden)
<!--ID: 1771940383893-->



Definierte rechtsseitige Differenzierbarkeit einer Funktion in einem Punkt $x_{0}$ #flashcard
Sei $f:D\to\mathbb{R}$ und gebe es ein $\rho>0$, sodass $[x_{0},x_{0}+\rho)\subseteq D$. Falls
$$
\lim_{ h \,\downarrow\, 0 }  \frac{f(x_{0}+h)-f(x_{0})}{h}
$$
existiert, dann nennt man $f$ in $x_{0}$ rechtsseitig differenzierbar und schreibt $f'_{+}(x_{0})$ für den Grenzwert.
(Die $\rho$-Umgebung dient als einseitiger Ersatz dafür, dass $x_{0}$ kein innerer Punkt ist)
<!--ID: 1771949074621-->



Definiere, wann eine Funktion auf ihrem Definitionsbereich $D$ differenzierbar ist #flashcard
Sei $f:D\to \mathbb{R}$ eine Funktion und $D\subseteq \mathbb{R}$
Wenn
- $D$ keine isolierten Punkte enthält (jeder Punkt ist Häufungspunkt),
- $f$ in jedem inneren Punkt von $D$ differenzierbar ist,
- $f$ in jedem Randpunkt, der zu $D$ gehört, einseitig differenzierbar ist,
Dann heißt $f$ differenzierbar auf $D$.
<!--ID: 1771940383899-->



Wie lautet die Regel für die Ableitung der Umkehrfunktion? #flashcard
Sei $I\subseteq \mathbb{R}$ ein Intervall, $x_{0}\in I$ und $f:I\to \mathbb{R}$ 
Wenn
- $f$ differenzierbar und injektiv ist,
- $f'(x_{0})\neq{0}$ ist,
Dann ist die Umkehrfunktion $f^{-1}:W\to \mathbb{R}\;,\;W:=f(I)$ differenzierbar in $y_{0}=f(x_{0})$ mit
$$
(f^{-1})'(y_{0}) = \frac{1}{f'(x_{0})} = \frac{1}{f'(f^{-1}(y_{0}))}
$$
(Die Umkehrfunktion einer Tangente $mx+b$ hat die Steigung $\frac{1}{m}$)
<!--ID: 1771940383902-->





Was besagt der Satz von Michel Rolle? #flashcard
Seien $a,b\in \mathbb{R}\;,\;a<b\;,\;f[a,b]\to \mathbb{R}$ stetig und auf $(a,b)$ differenzierbar mit 
$f(a)=f(b)=0$. Dann folgt:
$$
\exists \,x_{0}\in(a,b):f'(x_{0})=0
$$
<!--ID: 1772011948655-->


Was besagt der Mittelwertsatz der Differentialrechnung? #flashcard
Seien $a,b\in \mathbb{R}\;,\;a<b\;,\;f:[a,b]\to \mathbb{R}$ stetig und auf $(a,b)$ differenzierbar.
Dann folgt:
$$
\exists\, x_{0}\in(a,b): f'(x_{0})= \frac{f(b)-f(a)}{b-a}
$$
<!--ID: 1772011948658-->


An einem inneren Punkt einer in $x_{0}$ differenzierbaren Funktion ist $f'(x_{0})=0$ {{c1::notwendig}}  für die Existenz eines lokalen Extremums.
<!--ID: 1772011948665-->


Wie lautet das Vorzeichenwechselkriterium für strikte lokale Extrema von Funktionen? #flashcard
Sei $x_{0}$ innerer Punkt und $\exists_{\delta>0}$ sodass $f$ differenzierbar auf $U_{\delta}(x_{0})\setminus\{ x_{0} \}$.
Hinreichend für strikte lokale *Minimalstelle*:
$$\forall\,x\in U_{\delta}(x_{0})\setminus\{ x_{0} \}: \begin{cases}
x<x_{0} \implies f'(x)<0\\
x>x_{0} \implies f'(x)>0
\end{cases}$$
Hinreichend für strikte lokale *Maximalstelle*:
$$\forall\,x\in U_{\delta}(x_{0})\setminus\{ x_{0} \}: \begin{cases}
x<x_{0} \implies f'(x)>0\\
x>x_{0} \implies f'(x)<0
\end{cases}$$
<!--ID: 1772011948660-->



Wie lautet das Kriterium mit zweiter Ableitung für strikte lokale Extrema von Funktionen? #flashcard
Sei $x_{0}$ innerer Punkt und $f$ zweimal *stetig* differenzierbar in einer Umgebung von $x_{0}$.
Hinreichend für strikte lokale *Minimalstelle*:
$$
f'(x_{0})=0 \land f''(x_{0})>0
$$
Hinreichend für strikte lokale *Maximalstelle*:
$$
f'(x_{0})=0 \land f''(x_{0})<0
$$
<!--ID: 1772011948663-->

Was besagt die Regel von L'Hospital? #flashcard
Für $a,b\in \mathbb{R}\;,\;a<b$ und $f,g:[a,b]\to \mathbb{R}$.
- Seien $f,g$ auf $[a,b]$ stetig und auf $(a,b)$ differenzierbar
- Gelte $g(a)=f(a)=0$
- Gelte $\forall_{x\in(a,b)}:g(x)\neq 0$
- Und Existiere der Grenzwert $$
\lim_{ x \downarrow a }  \frac{f'(x)}{g'(x)}=c
$$
Dann folgt $g(x)\neq(0)$ für alle $x\in(a,b)$ und
$$
\lim_{ x \downarrow a }  \frac{f(x)}{g(x)}=c
$$
<!--ID: 1772381486617-->


