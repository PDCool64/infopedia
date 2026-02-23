TARGET DECK: AFI::Folgen
FILE TAGS: folgen

Definition der Konvergenz von Folgen? #flashcard
$a$ ist der Grenzwert der Folge $(a_{n})_{n\in \mathbb{N}}$, wenn
$$
\begin{align}
 \forall \epsilon > 0: \exists n_{0} \in \mathbb{N} : \forall n \geq n_{0}: |a_{n} - a| < \epsilon
\end{align}
$$
<!--ID: 1771751281806-->




Grenzwertsatz für zwei konvergente Folgen $(a_{n})_{n \in \mathbb{N}}, (b_{n})_{n \in \mathbb{N}}$ , was gilt dann für  $\lim_{ n \to \infty }(a_{n}+b_{n})_{n\in \mathbb{N}}$? #flashcard
$$
\lim_{ n \to \infty } (a_{n} + b_{n})_{n \in \mathbb{N}} =   a + b
$$
<!--ID: 1771751281808-->




Grenzwertsatz für zwei konvergente Folgen $(a_{n})_{n \in \mathbb{N}}, (b_{n})_{n \in \mathbb{N}}$ , was gilt dann für $\lim_{ n \to \infty } (a_{n} \cdot b_{n})_{n \in \mathbb{N}}$? #flashcard
$$
\lim_{ n \to \infty } (a_{n} \cdot b_{n})_{n \in \mathbb{N}} = a \cdot b
$$
<!--ID: 1771751281811-->




Wann sind die Grenzwertsätze anwendbar? #flashcard
Wenn beide Folgen konvergent sind
<!--ID: 1771751281814-->




Definition des Sandwich Lemmas? #flashcard
Die Folge $(a_{n})_{n\in \mathbb{N}}$ ist gegen $A$ konvergent, falls es Folgen $(b_{n})_{n\in \mathbb{N}},(c_{n})_{n\in \mathbb{N}}$ gibt mit $\lim_{ n \to \infty }b_{n}=\lim_{ n \to \infty }c_{n}=A$ und ab einem $N\in \mathbb{N}$ gilt, dass
$$
a_{n}\le b_{n} \le c_{n} \;\;,\;\forall\; {n\ge N}
$$
<!--ID: 1771751281816-->



Welche Eigenschaften muss $(a_{n})_{n \in \mathbb{N}}$ erfüllen, damit das Monotoniekriterium anwendbar ist? #flashcard
$(a_{n})_{n \in \mathbb{N}}$ muss beschränkt und monoton sein.
<!--ID: 1771751281819-->


Wie ist eine Cauchy-Folge definiert? #flashcard
Eine reelle Folge $(a_n)_{n\ge 1}$ heißt Cauchy-Folge, wenn es zu jedem $\varepsilon>0$ ein $N\in \mathbb{N}_{0}$ gibt, so dass
$$
\forall_{m,n\ge N}:\left| a_{m}-a_{n} \right| <\varepsilon
$$
<!--ID: 1771863587983-->



Eine Folge ist genau dann {{c1::konvergent}} wenn sie eine Cauchy-Folge ist.
<!--ID: 1771863587988-->





Die gegen den Grenzwert $g$ konvergente Folge $a_{n}$ sei rekursiv definiert mit der *stetigen* Funktion $f$ als:$$
a_{n+1}=f(a_{n})
$$ Wie bestimmt man den Wert von $g$? #flashcard
$$g=\lim_{ n \to \infty }a_{n+1}=\lim_{ n \to \infty } f(a_{n})\overset{f \text{ stetig}}=f(\lim_{ n \to \infty } a_{n})=f(g)$$
bzw. letztendlich:
$$
g=f(g)
$$
(Verwendet, dass alle Teilfolgen - insb. $a_{n+1}$ - den gleichen Grenzwert haben)
<!--ID: 1771863587986-->


