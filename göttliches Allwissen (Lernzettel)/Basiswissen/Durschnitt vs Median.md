
---
## Durschnitt

Der "Durschnitt" bezeichnet das **arithmetische Mittel**:

Der Quotient aus der Summe aller Werte und der Anzahl der Werte

$L = \underbrace{\{7,4,12,4,3,10,23\}}_{\substack{7 \;\text{Elemente}}}$

$$\text{Arithmetisches Mittel}=\frac{7+4+12+4+3+10+23}{7}=9$$
---
## Median

Der **Median** hingegen ist der Wert, welcher in einer **nach Größe sortierten** Liste in der Mitte steht.

$L=\{7,4,12,4,3,10,23\}$

$L_{\text{sortiert}}=\{3,4,4,7,10,12,23\}$
$$
\underbrace{\{3,4,4,}_{{3 \;\text{Elemente}}}    
\underbrace{7,}_{\quad\text{Median}} 
\underbrace{10,12,13\}}_{{\quad3 \;\text{Elemente}}}
$$

Da diese Liste eine **ungerade Länge** von $7$ hatte, gab es direkt einen eindeutigen Median.


Hat die Liste hingegen eine gerade Anzahl an Elementen,
ist der Median der **Durschnitt der beiden mittleren Elemente**:

$L=\{1,5,9,3,3,27,4,2\}$

$L_{\text{sortiert}}=\{1,2,3,3,4,5,9,24\}$

$$
\begin{align*}
\underbrace{\{1,2,3,}_{{3 \;\text{Elemente}}}    
\underbrace{3,4,}_{\quad\text{2 mittlere Elemente}} 
\underbrace{5,9,24\}}_{{\quad3 \;\text{Elemente}}} \\ \\
\to \text{Median}=\frac{3+4}{2}=\text{3,5}
\end{align*}
$$
---

Beide Verfahren haben Anwendungsfälle für die sie jeweils besser geeignet sind.

Bsp. :
	*Bill Gates kommt in einen Raum voller Normalverdiener.*
	Das [[#Durschnitt]] ergibt: In diesem Raum sind Millionäre.
	Der [[#Median]] ergibt: In diesem Raum sind Normalverdiener.

---
## Geometrisches Mittel
Die $n$-te Wurzel aus dem Produkt der $n$ betrachteten *positiven* Zahlen.

$L = \underbrace{\{7,4,12,4,3,10,23\}}_{\substack{7 \;\text{Elemente}}}$

$$
\text{geometrisches Mittel}=\sqrt[7]{7\cdot4\cdot12\cdot 4 \cdot 3 \cdot 10 \cdot 23} \approx 7,12
$$
