TARGET DECK: DSAL::Algorithmen

Was bestimmt eine Problemklasse #flashcard
typisierte Ein- und Ausgabevariablen.
Vor- und Nachbedingungen.
<!--ID: 1780491948420-->

Neben der Korrektheit ist auch die ... eines Algorithmus wichtig. #flashcard
Terminierung aka. Vollständigkeit
<!--ID: 1780493121265-->


Was muss man wählen, um die Laufzeit eines Algorithmus analysieren zu können? #flashcard
Eine menge elementarer Operationen, die man dann zählt.
<!--ID: 1780493121268-->


Formel für die Average-Case Laufzeit eines Algorithmus #flashcard
Sei
$D_{n}$ die Menge möglicher Eingaben der Länge $n$,
$T(I)$ die Anzahl der elementaren Operationen für eine Eingabe $I$
$Pr(I)$ die Wahrscheinlichkeit, dass eine Eingabe eintritt.
$$
A(n):=\sum_{I\in D_{n}}T(I)\cdot Pr(I)
$$
<!--ID: 1780493121271-->



Definiere die Laufzeitklasse $\omega(f)$. #flashcard
$\omega(f)$ sind die Funktionen, welche _echt schneller_ als $f$ wachsen.
$g\in\omega(f)\iff$
$$
\lim_{ n \to \infty } \frac{g(n)}{f(n)}= \infty
$$
bzw.
$$\color{red}{\forall_{c>0}}\color{white}\exists_{n_{0}}\forall_{n\ge n_{0}}:c\cdot f(n)<g(n)$$
<!--ID: 1780493121273-->



Definiere die Laufzeitklasse $\Omega(f)$. #flashcard
$\Omega(f)$ sind die Funktionen, welche _schneller oder gleich_ $f$ wachsen.
$g\in \Omega(f)\iff$
$$
0< \text{lim inf}_{ n \to \infty } \frac{g(n)}{f(n)}
$$
bzw.
$$\color{red}{\exists_{c>0}}\color{white}\exists_{n_{0}}\forall_{n\ge n_{0}}:c\cdot f(n)\le g(n)$$
<!--ID: 1780493121276-->



Definiere die Laufzeitklasse $\mathcal{O}(f)$. #flashcard
$\mathcal{O}(f)$ sind die Funktionen, welche _langsamer oder gleich_ $f$ wachsen.
$g\in \mathcal{O}(f)\iff$
$$
 \text{lim sup}_{ n \to \infty } \frac{g(n)}{f(n)}< \infty
$$
bzw.
$$\color{red}{\exists_{c>0}}\color{white}\exists_{n_{0}}\forall_{n\ge n_{0}}:g(n)\le c\cdot f(n)$$
<!--ID: 1780493121279-->



Definiere die Laufzeitklasse $\Theta(f)$. #flashcard
$\Theta(f)$ sind die Funktionen, welche _genauso schnell_ wie $f$ wachsen.
$g\in \Theta(f)\iff$
$$
 0 < \text{lim inf}_{n\to \infty} \frac{g(n)}{f(n)}\le\text{lim sup}_{ n \to \infty } \frac{g(n)}{f(n)}< \infty
$$
bzw.
$$\color{red}{\exists_{c_{1},c_{2}>0}}\color{white}\exists_{n_{0}}\forall_{n\ge n_{0}}:c_{1}\cdot f(n)\le g(n) \le c_{2}\cdot f(n)$$
<!--ID: 1780493121281-->



Definiere die Laufzeitklasse $o(f)$. #flashcard
$o(f)$ sind die Funktionen, welche echt langsamer als $f$ wachsen.
$g\in o(f)\iff$
$$
\lim_{ n \to \infty } \frac{g(n)}{f(n)}=0
$$
bzw.
$$
\color{red}{\forall_{c>0}}\color{white}\exists_{n_{0}}\forall_{n\ge n_{0}}:g(n)<c\cdot f(n)$
$$
<!--ID: 1780493121284-->


Was besagt das Mastertheorem? #flashcard
Gegeben sei
$$
T(n)=a\cdot T\left( \frac{n}{b} \right)+f(n) \;,\;a\ge 1 \;,\;b >1
$$
Dann ist die Anzahl der Blätter im Rekursionsbaum:
$$
n^{E}\;,\;E:= \log_{b}a
$$
Fallunterscheidung:
- $f\in O(n^{E-\varepsilon})$ für ein $\varepsilon>0$  dann ist $T\in \Theta(n^{E})$
  (Blätter dominieren)
- $f\in\Theta(n^{E})$ dann ist $T\in\Theta(n^{E}\cdot \log n)$
- $f\in\Omega(n^{E+\varepsilon})$ für ein $\varepsilon>0$ sowie
  $a\cdot f\left( \frac{n}{b} \right)\le d\cdot f(n)$ für ein $d<1$ und $n$ hinreichend groß
  dann ist $T\in\Theta(f)$
<!--ID: 1780493957125-->

