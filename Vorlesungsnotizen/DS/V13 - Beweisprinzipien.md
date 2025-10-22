---
date: 2025-10-22
tags:
  - DS
status: rot
Vorlesungsfolien:
Skriptfolien: "[[Skript Diskrete Strukturen.pdf]]"
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
# Kontraposition
Zeige die Implikation $A\implies B$

## Methode:
Zeige stattdessen: $\neg B\implies \neg A$
Was auf der Tautologie $(A\to B)\iff(\neg B\to \neg A)$ beruht.

## Beispiel:

Für alle $z\in \mathbb{Z}$ gilt : $\underbrace{ z^{2}\text{ gerade} }_{ =:A }$ $\implies$ $\underbrace{ z\text{ gerade} }_{ =:B }$

Beweis dies durch Kontraposition: zeige $\neg B\implies \neg A$ 
$\neg B:$ z ist nicht gerade, d.h. z ist ungerade
$\neg A$ : z ist nicht gerade, d.h. z ist ungerade

Die Behauptung $z\text{ ungerade}\implies z^{2}\text{ ungerade}$ wurde im [[#Direkter Beweis|vorherigen Beispiel]] bewiesen.
q.e.d.

---
# Beweis der Äquivalenz
Zeige die Äquivalenz $(A\iff B)$

## Methode
Zeige die Implikation in beide Richtungen:
$(A\iff B)\iff\big((A\implies B)\wedge(B\implies A)\big)$

## Beispiel.
Für jede ganze Zahl $z$ gilt:
Genau dann ist $\underbrace{ z^{2}\text{ gerade} }_{ =:A }$ gerade, wenn $\underbrace{ z\text{ gerade} }_{ =:B }$ ist.

Beweis "$\implies$" : Die Implikation wurde im [[#Kontraposition|voherigen Beispiel]] gezeigt

Beweis "$\impliedby$" : 
	Sei $z\in \mathbb{Z}$ gerade. Also gibt es ein $k\in \mathbb{Z}$ mit $z=2k$. Dann gilt:
	$z^{2}=(2k)^{2}=4k^{2}=2(\underbrace{ 2k^{2} }_{ \in \mathbb{Z} })$ 
	Weil $2k^{2}$ das Produkt ganzer Zahlen ist und damit eine Ganze Zahl ist.

---
# Widerspruchsbeweis
Zeige: $A$ ist wahr

## Methode
Zeige stattdessen: $\neg A\implies(B\wedge \neg B)$ für eine passende Aussage $B$.

## Warum funktioniert das:
- $B\wedge \neg B$ ist falsch
- Aus $\neg A \implies(B\wedge \neg B)$ folgt (per Definition)
- Aus der Definition von $\to$ folgt: $\neg A$ ist falsch. (Hier ist der wichtige Punkt!)
- Damit ist $A$ wahr.


wichtiger Punkt:
Wende dies an auf:
$X:=\neg A$
und $Y:=(B\wedge \neg B)$


Wir haben die Subjunktion gezeigt, sind also in einem der Fälle, in dem rechts eine 1 steht: (Die Implikation wurde als wahr erkannt) s.h. "<"

Da  $Y:=(B\wedge \neg B)$ immer falsch ist, sind wir definitiv im Fall "<<<"

| X   | Y   | $X\to Y$ |     |     |
| --- | --- | -------- | --- | --- |
| 0   | 0   | 1        | <   | <<< |
| 0   | 1   | 1        | <   |     |
| 1   | 0   | 0        |     |     |
| 1   | 1   | 1        | <   |     |
Es folgt also, dass $X=\neg A$ falsch ist, bzw, dass $A$ selbst wahr ist.

(Vgl. PXL Foto, er hat das echt schön aufgemalt)


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

# Vollständige Induktion

> Inder Klausur sollten wir immer "Induktionsanfang", "Induktionsvoraussetzung" und "Induktionsschritt"  schreiben.

Hier kann man *Aussageformen* beweisen, welche von einer natürlichen Zahl abhängen.

Ich verweise einfach mal auf [[Vollständige Induktion]]

Neu/wichtig, ist nochmal die präzise Aussage, über welche Variable die Induktion läuft:
> Sei $A(n)\;,\;n\in \mathbb{N}_{0}$ eine [[Aussagenlogik|Aussage]], die von einer [[Zahlenräume#Natürliche Zahlen $ mathbb{N}$|natürlichen Zahl]] $n$ abhängt. Um zu beweisen, dass die Aussage für alle $n\geq n_{0}$ richtig ist, genügt es, zu beweisen:
>1. $A(n)$ ist wahr für $n=n_{0}$ (**Induktionsanfang**)
>2. $A(n)\implies A(n+1)\;,\;n\geq n_{0}$ (**Induktionsschritt**)
>   
 $\to$ Dann spricht man von einer *vollständigen Induktion **über $n$*** .

## Warum funktioniert das (Ergänzungen)

Das ganze beruht auf der folgenden Eigenschaft von $\mathbb{N}$: (mit viel Zeit mehr nachlesen unter "Peano-Axiome")
	Für jede Teilmenge $A\subseteq \mathbb{N}$ gilt: Ist $1\in A$ und ist für jedes $n\in A$ auch $n+1\in A$, dann ist $A=\mathbb{N}$
	
Damit kann man dann schön zeigen, dass es für *alle* natürlichen Zahlen gilt.

## Beispiel:
Wir haben ***NOCHMAL*** die Gaußsche Summenformel bewiesen.

## Varianten der vollständigen Induktion
- Man kann anstatt bei $1$ auch bei einem anderen $n_{0}$ Anfangen.
- Andere Induktionsvoraussetzung: Man nimmt nicht nur an dass $A(n)$ gilt, sondern auch dass $A(1)\wedge \dots\wedge A(n)$ , wenn man die vorherigen Bedingungen ebenfalls in seinem Beweis für $A(n+1)$ braucht/benutzen will.
- Man kann die Beweise auch aufteilen, z.B. für gerade/ungerade Zahlen jeweils mit $1$ und $2$ als Induktionsanfang und Induktionsschritten à la $A(n)\implies A(n+2)$. Kann man auch mit beliebigen Aufteilungen machen.
