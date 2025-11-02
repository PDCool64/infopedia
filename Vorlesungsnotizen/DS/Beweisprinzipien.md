---
tags:
  - DS
  - AFI
status: rot
---
---

## Direkter Beweis
>[!def] Direkter Beweis
> 
> Eine Folge von Implikationen die eine direkte Kette von Aussage $A$ zu Aussage $B$ aufbauen.


Beispiel: 
$$
\forall_{z\in \mathbb{Z}}:\underbrace{ z \text{ ungerade } }_{ =:A } \implies \underbrace{ z^{2}\text{ ungerade} }_{ =:B }
$$
mit den Definitionen:
- gerade: $z=2k$ für ein $k\in \mathbb{Z}$
- ungerade: $z=2k+1$ für ein $k\in \mathbb{Z}$

Beweis:
Sei $z\in Z$ ungerade, dann gibt es ein $k\in \mathbb{Z}$ mit $z=2k+1$ 
Dann gilt also $z^{2}=(2k+1)^{2}=4k^{2}+4k+1=2(\underbrace{ 2k^{2}+2k }_{ \in \mathbb{Z} })+1$ 

 $(2k^{2}+2k)\in \mathbb{Z}$ (Die Ganzen Zahlen sind auf Addition und Multiplikation abgeschlossen)

---
# Beweis durch Kontraposition
Zeige die Implikation $A\implies B$

## Methode:
Zeige stattdessen: $\neg B\implies \neg A$
Was auf der [[Aussagenlogik#Tautologie und Widerspruch|Tautologie]] $(A\to B)\iff(\neg B\to \neg A)$ beruht.

## Beispiel:

Für alle $z\in \mathbb{Z}$ gilt : $\underbrace{ z^{2}\text{ gerade} }_{ =:A }$ $\implies$ $\underbrace{ z\text{ gerade} }_{ =:B }$

Beweis dies durch Kontraposition: zeige $\neg B\implies \neg A$ 
$\neg B:$ z ist nicht gerade, d.h. z ist ungerade
$\neg A$ : z ist nicht gerade, d.h. z ist ungerade

Die Behauptung $z\text{ ungerade}\implies z^{2}\text{ ungerade}$ wurde im [[#Direkter Beweis|vorherigen Beispiel]] bewiesen.
q.e.d.

--
# Widerspruchsbeweis
Zeige: $A$ ist wahr

## Methode
Zeige stattdessen: $\neg A\implies(B\wedge \neg B)$ für eine passende Aussage $B$.
D.h. führe $\neg A$ zu einem Widerspruch.
## Warum funktioniert das:
- $B\wedge \neg B$ ist falsch
- Aus $\neg A \implies(B\wedge \neg B)$ folgt per Definition der Implikation:
   $\neg A\to(B\wedge \neg B)$ ist eine wahre Aussage.
![[Beweisprinzipien 2025-11-02 15.55.53.excalidraw]]

## Beispiel: $\sqrt{ 2 } \not\in \mathbb{Q}$
Mit Widerspruchsbeweis:
$A=(\sqrt{ n }\not\in \mathbb{Q})$
$\neg A=(\sqrt{ 2 }\in \mathbb{Q})$

Also gibt es $m,n\in \mathbb{Z}$, so dass es $\sqrt{ 2 }=\frac{m}{n}$ wobei $n\neq 0$.

Wir können außerdem ohne Beschränkung der Allgemeinheit annehmen, dass $m,n$ keine gemeinsamen Teiler außer $1$ haben - d.h. das der Bruch vollständig gekürzt ist.
Insbesondere haben $m$ und $n$ nicht gen gemeinsamen Teiler $2$, bzw. sie sind nicht beide durch 2 teilbar.

$$
\begin{align}
\sqrt{ 2 }&=\frac{m}{n} &|^{2}  \\ \\

2 &= \left( \frac{m}{n} \right)^{2} \\
 \\
2 &= \frac{m^{2}}{n^{2}} &|\cdot n^{2} \\ \\

2n^{2} &=m^{2}
\end{align}
$$
Da $2n^{2}$ immer gerade ist, ist auch $m^{2}$ gerade.

Da $m^{2}$ gerade ist, ist auch $m$ gerade ([[#Beweis der Äquivalenz]]) d.h. es gibt ein $k\in \mathbb{Z}$ mit $m=2k$
Es folgt. $m^{2}=(2k^{2})=2n^{2}$
$\implies (2k)^{2}=4k^{2}=2n^{2}\implies 2k^{2}=n^{2}$ 
Da $n^{2}$ gerade, ist auch $n$ gerade ([[#Beweis der Äquivalenz]]) , d.h. es gibt $k'\in Z$ mit $n=2k'$

Es sind also $n$ und $m$ gerade, sie haben also den Gemeinsamen Teiler $2$ - Dies ist ein Widerspruch zur Annahme, das $m$ und $n$ nicht beide durch $2$ teilbar sind.

---
# Beweis der Äquivalenz
Zeige die Äquivalenz $(A\iff B)$

## Methode
Zeige die Implikation in beide Richtungen:
$(A\iff B)\iff\big((A\implies B)\wedge(B\implies A)\big)$

## Beispiel.
Für jede ganze Zahl $z$ gilt:
Genau dann ist $\underbrace{ z^{2}\text{ gerade} }_{ =:A }$ gerade, wenn $\underbrace{ z\text{ gerade} }_{ =:B }$ ist.

Beweis "$\implies$" : Die Implikation wurde im [[#Kontraposition|vorherigen Beispiel]] gezeigt

Beweis "$\impliedby$" : 
	Sei $z\in \mathbb{Z}$ gerade. Also gibt es ein $k\in \mathbb{Z}$ mit $z=2k$. Dann gilt:
	$z^{2}=(2k)^{2}=4k^{2}=2(\underbrace{ 2k^{2} }_{ \in \mathbb{Z} })$ 
	Weil $2k^{2}$ das Produkt ganzer Zahlen ist und damit eine Ganze Zahl ist.

---
# Beweis durch [[Vollständige Induktion]]
hat einen eigenen Lernzettel.