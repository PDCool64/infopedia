---
tags:
  - DS
status: rot
---
---

Geordnetes Paar und Tupel sind von der Funktion her für uns das Gleiche - Die Tupel-Definition ist einfach eine sehr praktische Schreibweise und eine Definitionsvariante mit vielen nützlichen Eigenschaften. Meist verwendet man den Ausdruck "geordnetes Paar" wenn es darum geht wie man diese Dinge schön axiomatisch aus Mengen konstruiert.

Man kann zeigen, das beide Ansätze equivalent/gleichmächtig sind.

Ein geordnetes Paar, was identisch zu einem 2-Tupel ist, kann man definieren als Objekt $(x,y)$ wobei zwei verschieden $(x_{1},y_{1})$ und $(x_{2},y_{2})$ genau dann gleich sind, wenn $x_{1}=x_{2}\land y_{1}=y_{2}$ .

Man kann Geordnete Paare/Tupel auch direkt aus Mengen konstruieren, ohne dafür Abbildungen zu benötigen: $(x,y)$ lässt sich konstruieren als $\{ x,\{ x,y \} \}$ wobei die Verschachtelungslevel die Reihenfolge angeben. Ebenso ist dies für beliebige Größen möglich: $(x,y,z)$ kann konstruiert werden als $\{ (x,y),\{ (x,y),z \} \}=\{ \{ x,\{ x,y \} \} ,\{ \{ x,\{ x,y \} \},z \}\}$.

Der [Wikipedia Artikel zu Tupeln](https://de.wikipedia.org/wiki/Tupel#:~:text=Darstellung%5BBearbeiten,echte%20Klasse%20handelt.) fasst die beiden Ansätze ganz schön zusammen. Er verwendet aber noch einen anderen, ebenso gleichmächtigen, Ansatz wie man die Mengen "indiziert" d.h. die Reihenfolge festlegt.

---
>[!def] Tupel
> Es sei $M$ eine Menge und $n\in \mathbb{N}$. Ein $n$-**Tupel** über $M$ ist eine [[Abbildungen|Abbildung]]$$t:\underline{n}\to M$$Wie bei [[Folgen (Alt)]] schreiben wir das Tupel als $(x_{1},\dots,x_{n})$ oder $(x_{i})_{i\in \underline{n}}$ .
> Dabei sind die einzelnen Elemente definiert als:$$x_{i}:=t(i)\text{ für }i\in \underline{n}$$
> Wir setzen $M^{n}:=M^{\underline{n}}=\text{Abb}(\underline{n},M)$ 

Das $5$-Tupel $(1,-3,0,0,27)$ über $\mathbb{Z}$ ist z.B. die Abbildung $f:\underline{5}\to \mathbb{Z}$ mit 
$t(1)=1\;,\;t(2)=-3\;,\;t(3)=t(4)=0\;,\;t(5)=27$


## Bemerkungen
- die Mengen $\underline{n}:=\{ 1,2,3,\dots,n \}$ sind "Anfangsstücke" der [[Zahlenräume#Natürliche Zahlen $ mathbb{N}$|Natürlichen Zahlen]].


---
# Verbindung zum [[Mengen#Kartesisches Produkt|Kartesischen Produkt]] 


