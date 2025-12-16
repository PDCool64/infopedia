Das Cauchy-Kriterium besagt:

![[Kriterien für Folgen#Cauchy-Kriterium]]

---
Wir wollen mit dem Cauchy-Kriterium zeigen, dass $\frac{1}{n}$ konvergent ist:
$$
\forall_{\varepsilon>0}\exists_{N\in \mathbb{N}_{0}}\forall_{n,m\ge N}:\left| a_{n}-a_{m} \right| <\varepsilon
$$
Einsetzen, umformen und abschätzen ergibt:
$$
\begin{align}
&& \left| \frac{1}{n}-\frac{1}{m} \right| =\frac{\left| m-n \right| }{m\cdot n} = \frac{\left| m+(-n) \right| }{m\cdot n} \leq \frac{\left| m \right| +\left| n \right| }{m\cdot n}
\end{align}
$$
Man wähle $N=\frac{1}{\varepsilon}$ und erhält mit $n\ge N$:
$$\left| \frac{1}{n}-\frac{1}{m} \right|<\dots< \frac{1}{n}< \frac{1}{N}=\frac{1}{\frac{1}{\varepsilon}}=\varepsilon$$