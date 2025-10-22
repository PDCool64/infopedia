---
date: 2025-10-22
tags:
  - TI
status: gelb
Vorlesungsfolien: "[[uebung01.pdf]]"
Skriptfolien:
---
---

Die *nicht*-Bonus e-Tests sind ebenfalls generiert - mann hat da also beliebig viele, randomisierte Übungsaufgaben für die Klausur.

---
# A1
a) 
Alles wie gehabt. $\sum_{i=0}^{n}z_{i}\cdot b^{i}$ um ins Zehnersystem zu kommen

Weil wir für das Horner Schema in den "komischen" gegebenen Basen dividieren könnten müsste (ich kann habe keine Ahnung, wie man in Basis 3 dividiert) ist es einfacher, vorher einmal in Basis 10 umzurechnen. In Basis 10 kann man dann gut dividieren und das Horner-Schema anwenden. Z.B: $(2012)_{3}=(59)_{10}=(111011)_{2}$

$(H 3 6 G)_{18}=(100240)_{10}=$

b)

## Schöner trick: Wenn die Basis des einen  eine Potenz der Basis des anderen ist

4 Ziffern im Binärsystem entsprechen einer Ziffer im Hexadezimalsystem.
Dann kann man einfach Viererblöcke aus Binärzahlen direkt in Hexadezimal umschreiben.
> Man sollte die Tabelle Binär<->Hexadezimal für die Klausur lernen. Dann geht das schnell


Binär -> Hexadezimal
![[G01 - Zahlendarstellung 2025-10-22 10.53.38.excalidraw]]
>[!def]
> 
> **Man Muss die Blöcke von Rechts nach Links bilden.** 
> Der block ganz links kann dann auch kleiner sein, funktioniert immer noch.

| 0   | 0000 |
| --- | ---- |
| 1   | 0001 |
| 2   | 0010 |
| 3   | 0011 |
| 4   | 0100 |
| 5   | 0101 |
| 6   | 0110 |
| 7   | 0111 |
| 8   | 1000 |
| 9   | 1001 |
| A   | 1010 |
| B   | 1011 |
| C   | 1100 |
| D   | 1101 |
| E   | 1110 |
| F   | 1111 |

Funktioniert z.b. für die Umrechnung zwischen Basis 5 und Basis 25

c) Multiplikation von Binärzahlen
wie immer.
wenn  man Zeit sparen will muss man die Zeilen mit $\cdot 0$ nicht mal aufschreiben.

# A2
$x=(17)_{10}=(00010001)_{2}$

$y=(-39)_{10}=K_{2}(00100111)+1=11011001$

$z=(119)_{10}=(01110111)_{2}$

- $x+x$ wie erwartet

- $y+y$: Die Übertragsbits bei der Addition, welche über die Anzahl an verfügbaren Bits hinausgeht werden einfach ignoriert. z.B. bei

- $x+z$:  17+119$ -> Überlauf -> $-120$

- $x-y=56$ wie erwartet

# A3

Welcher Zahlenbereich kann im Zweierkomplement mit 16Bit dargestellt werden:
$$
-2^{n-1} \leq x\leq 2^{n-1}-1
$$
d.h. $$
-32768 \leq x \leq 32767
$$
> In der Klausur würde man wahrscheinlich nur das Ergebnis als $-2^{15}\leq x\leq 2^{15}-1$ einfordern . Der Lerneffekt das noch auszurechnen ist eher gering. Aber immer auf die Aufgabenstellung achten.

# A4
Vorzeichenlos: 151
Einerkomplement: -104
Zweierkomplement: -105
# A5 Bit-Shifts:
![[Pasted image 20251022112003.png]]

Zur Unterscheidung:
- Logischer Shift: Mit Nullen
- Arithmetischer Shift: Von links entweder 0 under 1 reinschieben, so dass man im Komplement da Vorzeichen behält (oder so)

Warum das ganze:
- In der Hardware sind Bit-Shifts *sehr* effizient umsetzbar

Konvertierungstabelle:

| 0   | 0000 |
| --- | ---- |
| 1   | 0001 |
| 2   | 0010 |
| 3   | 0011 |
| 4   | 0100 |
| 5   | 0101 |
| 6   | 0110 |
| 7   | 0111 |
| 8   | 1000 |
| 9   | 1001 |
| A   | 1010 |
| B   | 1011 |
| C   | 1100 |
| D   | 1101 |
| E   | 1110 |
| F   | 1111 |
Also : $(2E)_{16}$ = 0010 1110 = $(46)_{10}$

und $(2E)\ll {2}=1011\;1000=(184)_{10}$ 

und $(2E)\gg {2}=0001\;0111=(23)_{10}$

Man sieht:
	$46\cdot 4 = 184$
	$46:2 = 23$

>[!def] Bitshifts sind Multiplikation / Division mit $2$
>$x\ll k =x\cdot 2^{k}$
>$x\gg k=x:2^{k}$

Aber: Macht man das auf begrenzt viel Speicher, kann ist dies nicht immer der fall, weil Daten am Rand runterfallen:

$(2E)_{16}=(00101110)_{2}$

$(2E)_{2}\gg 3=(0000\;0101)_{2}=5$

Genauer, fällt hier der "Kommateil" weg.
Die Letzen beiden Nullen währen bei unendlich viel Speicher zu $\frac{1}{2}$ und $\frac{1}{4}$ geworden:
$(0000\;0101 \;.\;11)_{2}=5.75$


# A6: Gleitkommazahlen

a)
$-10.625$
Vorkommastellen: $(10)_{2}=(1010)_{2}$
Nachkommastellen: $(0.625)_{10}=(0.101)_{10}$

also zusammen: $(1010.101)_{2}$ 


normalisiert: $(1.010101)_{2}\cdot 2^{3}$
d.h. $e=3$ und $\hat{3}=3+127=130=(10000010)_{2}$
und $\hat{m}=010101$

b)
$6\cdot 2^{-130}$

$s=\hat{s}=0$

$(110)_{2}\;.\;(2^{-130}_{10})$


normalisiert;
$(1.1)_{2}\cdot 2^{-128}$

Aber: Der Exponent $-128$ ist zu klein um ihn als normalisierte Zahl darzustellen: $\hat{e}=-128+127=-1$

Also: Denormalisierte Darstellung verwenden:

Lösung:
`0 00000000 011000....`

# A7: Fallstricke in der Programmierung

Was passiert:

Weil `lenght` eine unsigned int ist, (also nicht als negativ interpretiert wird)
ergibt das `lenght-1` im Schleifenkopf einen Unterlauf und `lenght-1` ergibt die Größte darstellbare `unsigned int` 
Das Programm würde also sehr oft durch die Schleife laufen und dabei Versuchen auf Array-Indizes zuzugreifen, die nicht existieren -> `segfault` weil das Programm versucht auf Speicher zuzugreifen, der ihm nicht gehört.

-> Fix: `i<lenght` anstatt `i<l=enght-1` verwenden.
-> Allgemein: solange man den nach oben größeren Zahlenbereich von `unsigned` nicht verwendet, sollte man einfach bei normalen, Vorzeichen behafteten Zahlen bleiben.

# A8

Implizit steht da:
`x=(a+b)+c`
`y=(b+c)+d`

Wenn man die neue Variable einführt, hat man bei x aber diese Reihenfolge der Additionen:
`x=a+(b+c)`

>[!def] Gleitkomma-Addition ist nicht wirklich kommutativ

Warum: Sind zwei Zahlen so weit auseinander, dann würden bei der Addition die Mantissen so weit auseinander landen, dass sie in die z.B. 23 Bit für die Mantisse nichtmehr gespeichert werden können.

d.h. Wenn man auf eine Zahl eine sehr viel Größere Zahl addiert, kann es passieren, dass die kleinere einfach bei den Mantissenbits weggerundet wird.


