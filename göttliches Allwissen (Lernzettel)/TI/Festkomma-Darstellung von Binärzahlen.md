---
tags:
  - TI
  - PROGRA
status: grün
---
---
>[!wip]
> Wir haben nur die Festkomma-Darstellung *positiver* Zahlen gemacht. Man kann da aber auch einen Vorzeichenbit draufwerfen oder irgendwas mit dem Zweierkomplement machen. Wurde aber nicht behandelt.


>[!def] Festkomma-Darstellung
>In der **Festkomma-Darstellung** werden Kommazahlen im Binärsystem mit einer *festen* Anzahl an Stellen vor und nachdem Komma gespeichert.
>
>---
>
>Die Stellen ***vor*** dem Komma werden ganz normal wie bei natürlichen Zahlen behandelt.
>Sei vor dem Komma ein $n$-Bit Wort $(z_{n-1},\dots,z_{0})$) dann ist die Zahl vor dem Komma: $$z=\sum_{i=0}^{n-1}z_{i}\cdot {2}^{i}$$
>
>Die Stellen ***nach*** dem Komma werden hingegen nicht als Potenten  $2^{i}$ interpretiert sondern als$\frac{1}{2^{n}}$ bzw. $2^{-i}$. Sei hinter dem Komma ein $n$-Bit Wort $(z_{1},\dots,z_{n})$:
>$$z=\sum_{i=1}^{n}z_{i}\cdot 2^{-i}$$
>
>Fügt man beides Zusammen, steht die Bitfolge $(z_{n-1},\dots,x_{1},x_{0},x_{-1},\dots,x_{-m})$ , bei der das Komma *zwischen $x_{0}$ und $x_{1}$ liegt*, die folgende Zahl dar: $$z=\sum_{i=-m}^{n-1}x_{i}2^{i}$$
>
>---
>Die Anzahl an Bits für den Ganzzahligen Teil und die für den Komma-Teil müssen nicht immer übereinstimmen.

## Anschaulich:
![[Festkomma-Darstellung von Binärzahlen 2025-10-19 13.46.24.excalidraw|600]]

``0110.1101`` ist also: $4+2+\frac{1}{2}+\frac{1}{4}+\frac{1}{16}=6\text{,}8125$

# Umrechnung Dezimalzahl $\to$ Festkommazahl:

Was ist $47.6875$ als Festkomma-Zahl in $6$ Bit vor dem Komma und $4$ Bit nach dem Komma ?

1. Konvertiere den Teil vor dem Komma ganz normal nach dem [[Horner Schema]]:
![[Festkomma-Darstellung von Binärzahlen 2025-10-19 14.21.52.excalidraw]]

2. Konvertiere den Teil nach dem Komma mit einem *abgewandelten* Horner Schema, bei dem nicht durch $2$ geteilt wird, sondern mit $2$ *multipliziert* wird.
   ![[Festkomma-Darstellung von Binärzahlen 2025-10-19 14.04.25.excalidraw]]
3. Schreibe beide Teile zusammen auf: $47.6875=101111.1011$ 


# Rechnen mit Festkomma-Zahlen

Das schöne an Festkomma-Zahlen ist, dass man einfach so rechnen kann als ob das Komma gar nicht da wäre - man darf nur nicht vergessen es am ende wieder an der gleichen Stelle aufzuschreiben.

$(3.5)_{10}+(2.75)_{10}=(6.25)_{10}$

Umrechnen: (Hier mit willkürlichen $4$Bit vor und $3$Bit nach dem Komma)
$(3.5)_{10}\;\,=0011.100$
$(2.75)_{10}=0010.110$

Addition wie immer:
```
  0011.100
 +0010.110
   111
 ---------
  0110.010
```
Was geklappt hat, weil: 
$(0110.010)_{2}=4+2+\frac{1}{4}=6.25$
