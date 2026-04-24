---
tags:
  - DSAL
status: rot
---
---
# Die Klassen:

| Klasse           | in Worten:<br>Funktionen, die ... <br>als $f$ wachsen | als Limes<br>$g\in X(f)\iff$                                                                                         | Quantoren:                                                                                                                               |
| ---------------- | ----------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| $\omega(f)$      | *echt schneller*                                      | $\lim_{ n \to \infty } \frac{g(n)}{f(n)}=\infty$                                                                     | $\color{red}{\forall_{c>0}}\color{white}\exists_{n_{0}}\forall_{n\ge n_{0}}$:<br>$c\cdot f(n)<g(n)$                                      |
| $\Omega(f)$      | *schneller oder gleich*                               | $0<\lim \text{inf}_{ n \to \infty } \frac{g(n)}{f(n)}$                                                               | $\color{red}{\exists_{c>0}}\color{white}\exists_{n_{0}}\forall_{n\ge n_{0}}$:<br>$c\cdot f(n)\le g(n)$                                   |
| $\Theta(f)$      | *genauso schnell*                                     | $0<\lim \text{inf}_{ n \to \infty } \frac{g(n)}{f(n)}\le \lim \text{sup}_{ n \to \infty } \frac{g(n)}{f(n)}< \infty$ | $\color{red}{\exists_{c_{1},c_{2}>0}}\color{white}\exists_{n_{0}}\forall_{n\ge n_{0}}$:<br>$c_{0}\cdot f(n)\le g(n) \le c_{1}\cdot f(n)$ |
| $\mathcal{O}(f)$ | *langsamer oder gleich*                               | $\lim \text{sup}_{ n \to \infty } \frac{g(n)}{f(n)}<\infty$                                                          | $\color{red}{\exists_{c>0}}\color{white}\exists_{n_{0}}\forall_{n\ge n_{0}}$:<br>$g(n)\le c\cdot f(n)$                                   |
| $o(f)$           | *echt langsamer*                                      | $\lim_{ n \to \infty } \frac{g(n)}{f(n)}=0$                                                                          | $\color{red}{\forall_{c>0}}\color{white}\exists_{n_{0}}\forall_{n\ge n_{0}}$:<br>$g(n)<c\cdot f(n)$                                      |

> Beachte dabei zur Vereinfachung:
> Bei den meisten "netten" Funktionen kann man sich die $\lim\text{inf}_{ n \to \infty }$ vs. $\lim\text{sup}_{ n \to \infty }$  Unterscheidung sparen:
> 
> Falls $\lim_{ n \to \infty } \frac{g(n)}{f(n)}$ existiert, dann gilt:$$
\lim\text{inf}_{ n \to \infty }  \frac{g(n)}{f(n)}=
\lim          _{ n \to \infty }  \frac{g(n)}{f(n)}=
\lim\text{sup}_{ n \to \infty }  \frac{g(n)}{f(n)}
$$
## Bildung der Klassen aus einander
Es gilt:
$$\mathcal{O}(f) = o(f)\cup\Theta(f)$$
sowie:
$$
\Omega(f) = \omega(f) \cup \Theta(f)
$$
## Eigenschaften als [[göttliches Allwissen (Lernzettel)/DS/Relationen|Relationen]]
### Transitivität von $\omega \;,\;\Omega,\Theta \;,\;\mathcal O \;,\;o$
Das Enthalten-sein von $f$ in der Klasse von $g$ ist bei allen dieser Klassen *transitiv*.
Es gilt zum Beispiel:
$$
f\in \Omega(g) \;\land\; g\in\Omega(h) \implies f\in \Omega(h)
$$
### Reflexivität von $\mathcal{O}\;,\;\Omega \;,\;\Theta$
$$
f\in \mathcal{O}(f) \;,\;f\in \Omega(f) \;,\;f\in \Theta(f)
$$
> Beachte aber, dass $f \not\in o(f)\;,\;f \not\in \omega(f)$

### Symmetrie von $\Theta$
$$
f\in\Theta(g) \iff g\in\Theta(f)
$$
> Somit ist $\Theta$ eine [[göttliches Allwissen (Lernzettel)/DS/Relationen|Äquivalenzrelation]]

