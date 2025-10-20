
## **Ausnahmefälle**
$$
\begin{align*}
0^a &= 0 \quad \text{für} \quad a > 0, \\
a^0 &= 1 \quad \text{für} \quad a \neq 0, \\
0^0 &= 1 \quad \text{(Konvention in vielen mathematischen Kontexten, z. B. Kombinatorik oder Polynomdefinitionen)}.
\end{align*}
$$
**Hinweis zu $0^0$:**
In der **Analysis** wird $0^0$ oft als **unbestimmte Form** betrachtet (ähnlich wie $\frac{0}{0}$), da der Grenzwert $\lim_{(x,y) \to (0,0)} x^y$ **nicht existiert**. Die Festlegung $0^0 = 1$ ist eine **pragmatische Konvention** für bestimmte Anwendungen.

---
## **Gültigkeitsbedingungen**
Die Potenzgesetze gelten in folgenden Fällen:
1. Für **nicht-negative ganzzahlige Exponenten** ($m,n \in \mathbb{N}_0$) und **beliebige reelle Basen** ($a,b \in \mathbb{R}$).
2. Für **rationale Exponenten** ($m,n \in \mathbb{Q}$) und **positive reelle Basen** ($a,b \in \mathbb{R}_{>0}$).

---
## Grundgesetze
$$
\begin{align*}
a^n \cdot a^m &= a^{n+m} \\ \\
\frac{a^n}{a^m} &= a^{n-m} \quad \text{(nur definiert für } a \neq 0\text{)}, \\\\
(a^n)^m &= a^{n \cdot m} \\ \\
a^n \cdot b^n &= (a \cdot b)^n
\end{align*}
$$
**Wichtig:**
Für $a = 0$ ist $\frac{a^n}{a^m}$ **immer undefiniert** (außer im trivialen Fall $n = m = 0$, der konventionsabhängig ist).

---
## Gebrochene Exponenten und Wurzeln
Für $m \in \mathbb{Z}$, $n \in \mathbb{N}$, und $a \in \mathbb{R}_{\geq 0}$ (bzw. $a \in \mathbb{R}$ mit $n$ ungerade):
$$
\begin{align*}
a^{\frac{m}{n}} &= \sqrt[n]{a^m} = (\sqrt[n]{a})^m \\ \\
\sqrt[n]{a} &= a^{\frac{1}{n}}
\end{align*}
$$
**Achtung:**
Für $a < 0$ und gerades $n$ ist $\sqrt[n]{a}$ **nicht reell**.

---
## Kehrwert von Brüchen
$$
\left(\frac{a}{b}\right)^{-k} = \left(\frac{b}{a}\right)^k \quad \text{für} \quad a,b \neq 0.
$$

---
