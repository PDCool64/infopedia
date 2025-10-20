---
"date:": 2025-10-14
tags:
  - TI
status: rot
---
---

$\pm m\cdot b^{\pm e}$

Weil wir auf Rechner in Binär arbeiten nehmen wir als Basis 2

*WIR SPEICHERN; WIE WEIT WIR NACH VORNE/HINTEN GEHEN MÜSSEN UM DEN INTERESSANTEN TEIL ZU FINDEN, UND WIR SPEICHERN DEN INTERESSANTEN TEIL*

bei 32-Bit haben wir k=8 und n=23 -> "single precision"
Bei 64-Bit haben wir k=11 und n=52 -> "double precision"

(Ab und zu gibt es auch 128-Bit als "quadruple")


> Schreibweisen mit ê vs e bzw ^m und m : die mit Dach sind die, die wir in den Speicher haben - Die Varianten ohne Dach sind die, die in der Wissenschaftlichen Schreibweise / (?Dezimalform?) $s\cdot b^{e}$ finden.
> 


# Fallunterscheidung
## Normalisierte Darstellung
Für die Meisten Zahlen verwendet

Die bits in der Mantisse werden nur als die Nachkommastellen gelesen. Davor wird immer eine 1,XXX gehängt. Daraus resultiert aber, dass $1\leq m<2$ 


Dezimal -> Gleitkomma:
Erster Bit durch Vorzeichen
Teil vor dem Komma mit Horner
Teul nach dem Komma durch Neo-Horner

Dann normalisiert man, d.h. man schiebt so, dass die Mantisse passt (bzw?)  nur ein Bit vor dem komma steht

$m=1\text{,}\overset{\wedge}{m}$
$e=\overset{\wedge}{e}-127$  (Nochmal double check ob + oder -) 

## Denormalisierte Darstellung
Die Null lässt sich in der normalisierten Form NICHT darstellen.
Werden für Zahlen nah der Null, sowie die Null selbst verwendet.

Man muss als denormalisiert interpretieren, wenn der kodierte Exponent $\overset{\wedge}{e}$ *komplett* aus Nullen besteht.

Exponent wird als e=1-bias gewählt

Die Mantisse wird ohne führende 1, sondern mit 0 gewählt

Die Null kann hier aber mit Vorzeichen + oder - gespeichert werden.
Der Standard macht da ein paar komische Dinge - manchmal wird +0 und -0 gleich interpretiert, manchmal nicht

## Sonderfälle

### Überlauf/Unterlauf
Es ist kaum möglich, hier eine "sinvolle" /praktische Überlaufsoperation wie $\text{mod}$ zu definieren.
Stattdessen schreibt man dann $+\infty$ und $-\infty$ codiert durch eine Matisse aus nur 0; einen Exponenten nur aus 1 sowie das jeweils passenden Vorzeichen

### `NaN`
kommt "Scheiße" raus z.B. bei $+\infty+(-\infty)=$`NaN` oder $0/0=$`NaN`
Wichtig. Jede Operation die `NaN` als Eingabe kriegt, gibt auch wieder `NaN` raus z.b. `NaN`$\cdot2=$ `NaN`

`NaN` wird kodiert durch Mantisse die nicht nur aus 0000.... besteht sowie ein Exponent aus nur 11


# Entscheidungsbaum:
![[V04 - Gleitkomma-Darstellung 2025-10-15 11.01.44.excalidraw]]

(Muss man noch fertig machen)


> Das man mit dem Gleitkommasystem nicht alle reellen Zahlen darstellen kann ist keine besondere Eigenschaft.
> - Mit endlich vielen Nachkommastellen einer Dezimalzahl kann man 1/3 ebenso wenig aufschreiben. 


# Approximative Darstellung : Folgen

Es gibt bei 0.1+0.3 == 0.4 keine Garantie, dass true rauskommt:

Zwei gerundet kodierte Zahlen, die dann Addiert werden, und deren Ergebnis dann nochmal gerundet kodiert wird ist nicht unbedingt gleich mit dem Ergebnis, wenn man 0.4 direkt gerundet kodiert.

-> Mit Epsilon-Umgebung rechnen

# Rechnen mit Gleitkommazahlen
## Addition/Subtraktion
$$\begin{align}
5\cdot 2^{2}+3\cdot 2^{2} \\
= (5+3\cdot 2)\cdot 2^{2} \\
= ()

\end{align}$$
s..h PXL Foto

neuer Exponent ist der Größere der Beiden exponenten
Mantisse muss man als Summe berrechenn und ggfs. ein bsl verschieben

## Multiplikation
ist mega einfach


> Nach all solchen Rechenoperationen muss man ggfs. das Ergebniss nochmal normalisieren



## Runden
Die meisten reellen Zahlen sind nicht genau darstellbar -  es gibt aber viele Arten zu Runden

- Round to zero
	- Runde so, das der Betrag kleiner wird
- Round down
	- Runde so, dass der Wert kleiner wird
- Round up
	- Runde so, dass der Wert größer wird
- Round to nearest
	- Runde zur nächsten Zahl
		- sind die beiden möglichen Zahlen genau gleich weit von einander sind:
			- Tie to Even
			- Tie away from Zero


> Beim Tie wichtig: Würde mann immer in eine Richtung runden, würden sich die Rundungsfehler bei vielen Operationen Kumulieren. Rundet man mal auf und mal ab heben sie sich besser auf.

# Verteilung von Gleitkommazahlen

Bei dem Zahlenstrahl beispiel zu beachten: bias $=2^{k-1}-1=2^{3-1}-1=3$

Interessant: Die Denormalisierten Zahlen sind äquidistant von einander, während die normalisieren Zahlen mit wachsendem Betrag immer weiter von einander weg sind.




>[!def] Lektion fürs Leben
>Fließkommazahlen mit Vorsicht genießen - die Operationen verhalten sich nicht immer wie erwartet.
> 
