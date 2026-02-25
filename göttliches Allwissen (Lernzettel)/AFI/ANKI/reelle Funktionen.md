TARGET DECK: AFI::Funktionen

Wann nennt man eine Funktion $f: \emptyset \neq D \subseteq \mathbb{R} \to \mathbb{R}$  monoton wachsend? #flashcard
$$
\begin{align}
x, y \in D, x \leq y \\
\implies f(x) \leq f(y)
\end{align}
$$
<!--ID: 1771686203260-->


Wann nennt man eine Funktion $f: \emptyset \neq D \subseteq \mathbb{R} \to \mathbb{R}$  monoton fallend? #flashcard
$$
\begin{align}
x, y \in D, x \leq y \\
\implies f(x) \geq f(y)
\end{align}
$$
<!--ID: 1771686203264-->


Wann nennt man eine Funktion $f: \emptyset \neq D \subseteq \mathbb{R} \to \mathbb{R}$  streng monoton wachsend? #flashcard
$$
\begin{align}
x, y \in D, x \leq y \\
\implies f(x) < f(y)
\end{align}
$$
<!--ID: 1771686203268-->


Wann nennt man eine Funktion $f: \emptyset \neq D \subseteq \mathbb{R} \to \mathbb{R}$  streng monoton wachsend? #flashcard
$$
\begin{align}
x, y \in D, x \leq y \\
\implies f(x) > f(y)
\end{align}
$$
<!--ID: 1771686253072-->

Definiere einen inneren Punkt einer Menge $M$ #flashcard
$x_{0}\in M$ ist innerer Punkt von $M$, wenn eine $\varepsilon$-Umgebung $U_{\varepsilon}$ um $x_{0}$ existiert, sodass
$$
U_{\varepsilon}(x_{0}) \subseteq M
$$
<!--ID: 1771931548978-->

Wann ist eine Menge $M\subseteq \mathbb{R}$ offen? #flashcard
$M$ ist offen, wenn alle Elemente von $M$ innere Punkte sind.
<!--ID: 1771936027511-->


Wann ist eine Menge $M\subseteq\mathbb{R}$ abgeschlossen? #flashcard
$M$ ist abgeschlossen, wenn $\mathbb{R}\setminus M$ offen ist.
<!--ID: 1771936027516-->


Definiere einen Häufungspunkt einer Menge $M$ #flashcard
$x_{0}$ ist Häufungspunkt von $M$, wenn für alle $\varepsilon>0$ der Schnitt von $U_{\varepsilon}(x_{0})\setminus\{ x_{0} \}$ mit $M$ nichtleer ist, also
$$
\left( U_{\varepsilon}(x_{0})\setminus\{ x_{0} \} \right) \cap M \neq \emptyset
$$
Ein Punkt, der kein Häufungspunkt ist, heißt isolierter Punkt.
<!--ID: 1771931548983-->

Innere Punkte vs. Häufungspunkte:
Jeder {{c1::innere Punkt}} ist auch ein {{c2::Häufungspunkt}}.
<!--ID: 1771940383907-->


Innere Punkte vs. Häufungspunkte:
Nicht Jeder {{c1::Häufungspunkt}} ist auch ein {{c2::innerer Punkt}}.
<!--ID: 1771940383910-->


Wie ist der Grenzwert einer Funktion gegen einen Punkt definiert? #flashcard
Für $f:D\to \mathbb{R}$ und $x_{0}$ Häufungspunkt ist $L$ der Funktionsgrenzwert, wenn $\forall_{\varepsilon>0}\exists_{\delta>0}$ sodass
$$
\forall_{x\in D}\text{ mit }0<\left| x-x_{0} \right|<\delta\text{ gilt :} \\
$$
$$ \left| f(x)-L \right| <\varepsilon$$
(Beachte: $x_{0}$ muss nicht in $D$ sein. Außerdem wird nur $0<\left| x-x_{0} \right|$ betrachtet)
<!--ID: 1771931548985-->

Was besagt der Satz vom Minimum und Maximum? #flashcard
Eine stetige Funktion nimmt auf einem *geschlossenen* Intervall ein Minimum und Maximum an.
<!--ID: 1771934169671-->


Was besagt der Zwischenwertsatz bezüglich Nullstellen? #flashcard
Sei $f:D\to \mathbb{R}$ stetig und $a,b\in D$ mit $a<b$ sowie $[a,b]\subseteq D$.
Gilt $f(a)<0\land f(b)>0$ (oder alternativ $f(a)>0 \land f(b)<0$), dann existiert ein
$c\in(a,b)$ mit $f(c)=0$.
<!--ID: 1771934169676-->


Was besagt der Zwischenwertsatz bezüglich dem Wertebereich? #flashcard
Sei $f:D\to \mathbb{R}$ stetig und $a,b\in D$ mit $a<b$ sowie $[a,b]\subseteq D$.
Dann gilt $f([a,b])=[\text{m},M]$ mit
$m=\text{min}\{ f(x) |x\in[a,b]\}$
$M=\text{max}\{ f(x) |x\in[a,b]\}$
<!--ID: 1771934169678-->


