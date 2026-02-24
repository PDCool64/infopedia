TARGET DECK: AFI::Differentialrechnung
FILE TAGS: differentialrechnung

Definiere die Ableitung einer Funktion in einem Punkt #flashcard
Für $f:D\to\mathbb{R}$ und $x_{0}$ als innerer Punkt von $D\subseteq \mathbb{R}$ nennt man $f$ differenzierbar in $x_{0}$, wenn der Funktionsgrenzwert
$$
\lim_{ h \to 0 }  \frac{f(x_{0}+h)-f(x_{0})}{h}
$$
existiert. Wenn dieser existiert, wird er mit $f'(x_{0})=\frac{\text{d}}{\text{d}x}f(x_{0})$ bezeichnet.
(Beachte, dass mit $x_{0}$ als innerem Punkt sowohl positive als auch negative $h$ berücksichtigt werden)
<!--ID: 1771940383893-->



Definierte rechtsseitige Differenzierbarkeit einer Funktion in einem Punkt $x_{0}$ #flashcard
Für $f:D\to\mathbb{R}$ und gebe es ein $\rho>0$, sodass $[x_{0},x_{0}+\rho)\subseteq D$. Falls
$$
\lim_{ h \,\downarrow\, 0 }  \frac{f(x_{0}+h)-f(x_{0})}{h}
$$
existiert, dann nennt man $f$ in $x_{0}$ rechtsseitig differenzierbar.
<!--ID: 1771949074621-->



Definiere, wann eine Funktion auf ihren Definitionsbereich $D$ differenzierbar ist #flashcard
Sei $f:D\to \mathbb{R}$ eine Funktion und $D\subseteq \mathbb{R}$ enthalte keine isolierten Punkte (also jeder Punkt sei Häufungspunkt).
$f$ heißt dann differenzierbar auf $D$, wenn $f$ in *jedem inneren Punkt* von $D$ differenzierbar ist, und in jedem Randpunkt, der zu $D$ gehört, einseitig differenzierbar ist.
<!--ID: 1771940383899-->



Wie lautet die Regel für die Ableitung der Umkehrfunktion? #flashcard
Sei $I\subseteq \mathbb{R}$ ein Intervall, $x_{0}\in I$ und $f:I\to \mathbb{R}$ differenzierbar und injektiv mit $f(x_{0})\neq 0$.
Dann ist die Umkehrfunktion $f^{-1}:W\to \mathbb{R}\;,\;W:=f(I)$ differenzierbar in $y_{0}=f(x_{0})$ mit
$$
(f^{-1})'(y_{0}) = \frac{1}{f'(x_{0})} = \frac{1}{f'(f^{-1}(y_{0}))}
$$
(Die Umkehrfunktion einer Tangente $mx+b$ hat die Steigung $\frac{1}{m}$)
<!--ID: 1771940383902-->


