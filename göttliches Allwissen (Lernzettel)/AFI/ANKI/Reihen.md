TARGET DECK: AFI::Reihen
FILE TAGS: reihen


Wenn $\sum_{k=1}^{\infty}a_{k}$ konvergiert, dann ist $a_{k}$ {{c1::eine Nullfolge}}
<!--ID: 1771751281765-->




Ist $a_{k}$ eine Nullfolge, so {{c1::folgt nicht unbedingt}}, dass $\sum_{k=1}^{\infty}a_{k}$ konvergiert.
<!--ID: 1771751281767-->



Die harmonische Reihe $\sum_{k = 1}^{\infty} \frac{1}{k}$ {{c1::konvergiert nicht}}
<!--ID: 1771751281770-->




Die geometrische Reihe $\sum_{k=1}^{\infty} q^{k}, |q|^{k}\leq 1$ {{c1::konvergiert gegen $\frac{1}{1-q}$}}
<!--ID: 1771751281772-->




$\sum_{k=1}^{\infty} a_{k}, \sum_{k=1}^{\infty}b_{k}$ konvergent, $\alpha, \beta \in \mathbb{R}$ #flashcard
$\implies \sum_{k=1}^{\infty}\alpha a_{k} + \beta b_{k}$ konvergent, $\sum_{k=1}^{\infty}\alpha a_{K} + \beta b_{k} = \alpha \sum_{k=1}^{\infty}a_{k} + \beta \sum_{k=1}^{\infty} b_{k}$
<!--ID: 1771751281752-->




Definition des Leibnitzkriteriums? #flashcard

$$
\begin{align}
 &\text{Sei } a_{k} \text{ eine monoton fallende Nullfolge dann gilt für} \sum_{k=1}^{\infty} (-1)^{k} \cdot a_{k}:  \\
 & \text{ Die Reihe konvergiert} \\
  & \forall n \in \mathbb{N} : \rvert\sum_{k=n}^{\infty} (-1)^{k} a_{k}\lvert \leq a_{n}
\end{align}
$$
<!--ID: 1771751281754-->




Was ist absolute Konvergenz? #flashcard

$\sum_{k=1}^{\infty} a_{k}$ ist absolut konvergent, wenn $\sum_{k=1}^{\infty} |a_{k}|$ konvergent ist.
<!--ID: 1771751281757-->




Definition des Majorantenkriteriums? #flashcard
Sei $\sum_{k=1}^{\infty} c_{k}$ eine konvergente Reihe und $\exists N \in \mathbb{N}\forall k \geq N : |a_{k}| \leq c_{k}$, dann ist $\sum_{k=1}^{\infty} a_{k}$ absolut konvergent
<!--ID: 1771751281760-->




Definition des Minoratenkriteriums? #flashcard
Sei $\sum_{k=1}^{\infty} d_{k}$ eine divergierende Reihe und $\exists N \in \mathbb{N} \forall k \geq N: 0 <? d_{k} \leq |a_{k}|$, dann konvergiert $\sum_{k=1}^{\infty} a_{k}$ nicht absolut
<!--ID: 1771751281762-->




Das Quotientenkriterium besagt, dass wenn $\lim_{ k \to \infty } |\frac{a_{k + 1}}{a_{k}}|$ existiert und er {{c1::kleiner}} als 1 ist, dann divergiert die Reihe $\sum_{k=1}^{\infty} a_{k}$
<!--ID: 1771751281775-->





Das Quotientenkriterium besagt, dass wenn $\lim_{ k \to \infty } |\frac{a_{k + 1}}{a_{k}}|$ existiert und er {{c1::größer}} als 1 ist, dann konvergiert die Reihe $\sum_{k=1}^{\infty} a_{k}$ absolut
<!--ID: 1771751281777-->





Das Quotientenkriterium besagt, dass wenn $\lim_{ k \to \infty } |\frac{a_{k + 1}}{a_{k}}|$ existiert und er {{c1::gleich}} als 1 ist, dann kann keine Aussage über die Konvergenz der Reihe $\sum_{k=1}^{\infty} a_{k}$  gemacht werden.
<!--ID: 1771751281780-->




Nach dem Quotientenkriterium konvergiert $\sum_{k=1}^{\infty} a_{k}$ absolut wenn {{c1:: $\exists N \in \mathbb{N} \forall k \geq N: a_{k} \neq 0$}} und {{c2:: $\exists C < 1 \forall k \geq N: | \frac{a_{k + 1}}{a_{k}} | \leq C$}}
<!--ID: 1771751281782-->




Nach dem Quotientenkriterium divergiert $\sum_{k=1}^{\infty} a_{k}$, wenn {{c1:: $\exists N \in \mathbb{N} \forall k \geq N: a_{k} \neq 0$}} und {{c2:: $\forall k \geq N: | \frac{a_{k + 1}}{a_{k}} | \geq 1$}}
<!--ID: 1771751281785-->




