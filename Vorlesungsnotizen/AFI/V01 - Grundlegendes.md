---
"date:": 2025-10-14
tags:
  - AFI
status: gelb
---
---
Konzentrierte Darstellung "wichtiger" math. Aussagen:
- Lemma (kleine Hilfsaussagen für Sätze)
- Proposition
- Satz/Theorem

---

# [[Zahlenräume|Zahlenbereiche]]

- $\mathbb{N}=\{ 1,2,3,4,5,\dots \}$
- $\mathbb{N}_{0}=\{ 0,1,2,3,4 ,\dots\}$
$\to$ Natürliche Zahlen hier -*solange nicht explizit anders*- immer OHNE NULL

Die reellen Zahlen : Wie man dies Kontinuum erzeugt/definiert machen wir bald


# Rechenoperationen

Man hat keine Zahlen - sondern sehr komische Abstrakte Objekte die ich aber auch verrechnen will 
Wie definiere ich die Rechengesetze dann so, dass sie auch allgemein funktionieren.

## Summe / Addition:
Es gibt eine Addition
	für die das Kommutativ- und das Assoziativgesetz gilt
	- $a+b=b+a$
	- $a+(b+c)=(a+b)+c$
	Es gibt ein neutrales Element der Addition::
	- $a+0=a$    (Muss man bei Matrizen usw. ebenso können)

## Subtraktion
Die Subtraktion $a,b$ gegeben ist die Lösung der Gleichung: $a+x=b$ 
$x=b-a$ als Subtraktion

Funktioniert in $\mathbb{Z},\mathbb{Q},\mathbb{R}$ nicht aber in $\mathbb{N}$ ode $\mathbb{N}_{0}$ 
weil $77+x=43$ in $\mathbb{N}_{0}$ keine Lösung hat

## Multiplikation
Wie gehabt: Kommutativ, Assoziativ

Neutrales Element $1\cdot a=a$
Nullelement $0\cdot a=0$ (Das Neutrale Element der Addition ist das Nullelement der Multiplikation (Allgemeinheit??))


# Division
$a\neq 0$ und  $b$ erfüllen die Gleichung $a\cdot x=b$ , so nennen wir $x= \frac{b}{a}$ Division.

Funktioniert in $\mathbb{Q}$ und $\mathbb{R}$ - in $\mathbb{N}$ und $\mathbb{Q}$ nicht-

Die Lösung von $ax=1$ ist $a^{-1}$ oder $\frac{1}{a}$

Man darf kürzen: $ab=ac \implies b=c$

# Distributivgesetz
Verbindet Addition und Multiplikation

$a\cdot(b+c)=a\cdot b+a\cdot c$

# Aus diesen Basics herleitbar:

(Es geht darum, das man alles formell aus diesen Basics herleiten kann - als ob man alle intuitiven Rechenregeln aus der Grundschule vergessen hätte. Man muss einfach nur die gegebenen Regeln clever hintereinander anwenden)

Distributivgesetz andersherum lässt sich z.b. herleiten, indem man zuerst das Kommutativgesetz der Multiplikation anwendet.
$(a+b)\cdot c=c\cdot(a+b)=ca+cb$

$(a-b)$

... ...

## Beispiel 1.1 - eine Herleitung

$\forall_{a,b,c,d\in \mathbb{R}}\mid b\neq 0 \mid d \neq 0$:

$$
\begin{align}
\frac{a}{b}+\frac{c}{d} &= \frac{ad+ab}{bd}  &|\text{Zu zeigen } \\ \\

bd\left( \frac{a}{b}+\frac{c}{d} \right) &= bd \frac{a}{b}+bd \frac{c}{d} \\
 \\
 \\
&=da+bc \\
&=ad+cb
\end{align}
$$
d.h.
$\frac{a}{b}+\frac{c}{d}$ Löst $bd-x=ad$
---

# Anordnung

Für zwei beliebige Zahlen $a,b$ gilt eine der drei folgenden Aussagen:
- $a<b$
- $a=b$
- $a>b$

Schreibweise: $a\leq b\implies a<b \vee a=b$

## Verträglichkeit mit der Addition
$a<b\implies a+c<b+c$

## Verträglichkeit mit der Subtraktion
$a<b\implies a-c<b-c$

## Verträglichkeit mit der Multiplikation mit *positiven* Zahlen
$a,b$ beliebig und $c>0$:

$a<b\implies a\cdot c<b\cdot c$
### Bei *negativen Zahlen*
$a,b$ beliebig und $c<0$:

$a<b\implies a\cdot c>b\cdot c$

# Hieraus herleitbar:

$$
\begin{align}
\frac{77}{86} &< \frac{78}{87} &|\cdot86 \text{ (Verträglichkeit mit Mult.)} \\ \\
77\cdot 87 &< 78\cdot 86 &|\cdot87 \text{ (Verträglichkeit mit Mult.)} \\ \\ 
\dots
\end{align}
$$


# [[Aussagenlogik#Implikation]]
Haben wir gemacht

schönes Beispiel:
$x=3 \implies x^{2}=9$ 
aber 
$x=3 \cancel{ \impliedby } x^{2}=9$
### kleines Lemma zur Übung:
Seien $A$ und $B$ Aussagen, dann gilt sog. *logische Umkehrung*

$(A\implies B)\iff(\neg B\implies \neg A)$
Zeigt man einfach mit ner Wahrheitstabelle

# Äquivalenz:
Die beiden Aussagen haben en gleichen Wert:

| A   | B   | $A\iff B$ |
| --- | --- | --------- |
| 0   | 0   | 1         |
| 1   | 0   | 0         |
| 0   | 1   | 0         |
| 1   | 1   | 1         |

daraus kann man (wie genau?) herleiten, dass die gegenseitige Implikation damit gleichbedeutend ist. 