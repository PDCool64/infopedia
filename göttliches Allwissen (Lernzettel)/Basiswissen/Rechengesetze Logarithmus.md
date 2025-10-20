Für die Herleitung: Funktionalgleichung der jeweiligen Exponentialfunktion:
$a^{x+y}=a^{x}\cdot a^{y}$

---
$$
\log_{a}(u\cdot v)=\log_{a}(u)\;+\;\log_{a}(v)
$$
$$
\log_{a}\left( \frac{u}{v} \right)=\log_{a}(u) \;-\log_{a}(v)
$$
---
$$
\log_{a}(u^v)=v \cdot \log_{a}(u)
$$
$$
\log_a{\sqrt[n]{u}}=\frac{1}{n}\cdot \log_{a}{u}
$$
---
$$
\log_{b}(r)=\frac{\log_{a}(r)}{\log_{a}(b)}
$$
Dies ist besonders praktisch, wenn ein Taschenrechner bsp. nur 2 oder 10 als Basis für Logarithmen berechnen kann.


---

# Beweise / Herleitungen

---
Satz:
$$
\log_{a}(u^{v})=v\cdot \log_{a}(u)
$$
Beweis:
$$\begin{array}{rllll}
u&=&a^{\log_{a}(u)} &|^{v} \\
u^{v} &=&(a^{\log_{a}(u)})^{v} \\
u^{v} &=&a^{\log_{a}(u)\cdot v} &|\log_{a}(\dots) \\
\log_{a}(u^{v}) &=&\log_{a}(a^{\log_{a}(u)\cdot v}) \\
\log_{a}(u^{v}) &=&\log_{a}(u)\cdot v
\end{array}
$$

---
Satz:
$$
\log_{a}(u\cdot v)=\log_{a}(u)\;+\;\log_{a}(v)
$$
Beweis:
$$
\begin{align}
&\log_{a}(u\cdot v)\;=\;\underbrace{ \log_{a}(u) }_{ x:= }+\underbrace{ \log_{a}(v) }_{ y:= } \\

&\quad\quad\;\,\text{Dann ist }a^x =u \,\quad\ a^{y}=v \\
 \\
 \\
&\implies \underbrace{ a^{x} \cdot a^{y} }_{ u\cdot v }=a^{x+y} \\ 

&\implies \log_{a}(u\cdot v)=x+y=\log_{a}(u)+\log_{a}(v)
\end{align}
$$

---
Satz
$$
\log_{b}(r)=\frac{\log_{a}(r)}{\log_{a}(b)}
$$

Beweis:
$$
\begin{align}
\log_{a}(y) \cdot \log_{c}(a) &= \log_{c}(a^{\log_{a}(y)}) \\
&=\log_{c}(y) \\
 \\
\implies \log_{a}(y)&= \frac{\log_{c}(y)}{\log_{c}(a)}
\end{align}
$$---
