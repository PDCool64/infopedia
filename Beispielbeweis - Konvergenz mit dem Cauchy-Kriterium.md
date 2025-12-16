Das Cauchy-Kriterium besagt:

![[Kriterien für Folgen#Cauchy-Kriterium]]

---
Wir wollen mit dem Cauchy-Kriterium zeigen, dass $\frac{1}{n}$ konvergent ist:
$$
\forall_{\varepsilon>0}\exists_{N\in \mathbb{N}_{0}}\forall_{n,m\ge N}:\left| a_{n}-a_{m} \right| <\varepsilon
$$
Einsetzen, Umformen und Abschätzen ergibt:
$$
\begin{align}
&& \left| \frac{1}{n}-\frac{1}{m} \right| =\left| \frac{1}{n}+\left( -\frac{1}{m} \right)  \right| \overset{1.\Delta-UG.}\leq \left| \frac{1}{n} \right| +\left| -\frac{1}{m} \right| =\frac{1}{n} +\frac{1}{m}
\end{align}
$$
Man wähle $N>\frac{2}{\varepsilon}$ und erhält mit $n,m\ge N$:
$$\left| a_{n}-a_{m} \right| = \left| \frac{1}{n}-\frac{1}{m} \right|<\dots< \frac{1}{n} +\frac{1}{m}\le \frac{1}{N}+\frac{1}{N}=\frac{2}{N}<\frac{2}{\frac{2}{\varepsilon}}=\varepsilon$$
Womit die Konvergenz gezeigt ist - auch ohne schon $0$ als Grenzwert gekannt zu haben.
(Es ist hiermit *nicht* bewiesen, dass $0$ der Grenzwert ist, lediglich dass ein solcher existiert.)