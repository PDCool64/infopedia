---
"date:": 2025-10-13
tags:
  - TI
status: gelb
---
m---


# 1.1 Natürliche Zahlen

Stellenwertsystem: Der Wert den eine Ziffer beiträgt hängt davon ab, wo sie in einer Zahl steht:

$$
2025_{10}=2\cdot{1}0^{3} + 0\cdot 10^{2} + 2\cdot 10^{1} + 5\cdot 10^{0}
$$

Basieren auf einem *endlichen Alphabet*:
z.B. im Dezimalsystem. $\sum_{10}=\{ 0,1,2,3,4,5,6,7,8,9 \}$
allgemein: $\sum_{b}=\{ 0,1,\dots,b-1 \}$, wobei $b$ genannt wird.


*b-adische Zahlen* mit *endlicher Wortmenge*: $n:\sum_{n}^{b}$
mit $b=\text{Wortänge}$  ; $n=\text{Basis}$

zb. : $00456 \in \sum_{10}^{5}$ weil die Zahl fünf stellen hat und Ziffern aus $1,2,\dots,9$ enthält.

### Häufige Basen
Dual-/Binärsystem: $\sum_{2}=\{ 0,1 \}$
Oktalsystem: $\sum_{8}=\{ 0,1,2,3,4,5,6,7 \}$
Hexadezimal: $\sum_{16}=\{ 0,1,2,3,4,5,6,7,8,9,A,B,C,D,E,F\}$

### Warum Binär:
 (Der ENIAC -einer der ersten Rechner- hat beispielsweise direkt im Dezimalsystem gearbeitet.)

Will man die kodierten Zahlen durch *ein einziges* Kabel übertragen, was für die Weiterverarbeitung nicht zu umgehen ist, *müssen Zahlen in Spannungen kodiert werden.*

 Je mehr unterschiedliche Ziffern man als Basis nehmen will, desto schwieriger wird es die Spannungen aus einander zu halten:
![[V01 - Zahlendarstellung 2025-10-13 15.34.32.excalidraw|600]]


>[!def] Darstellbarkeit in Zahlensystemen mit verschiedenen Basen
>Sei $b\in N$ mit $b>1$. Dann ist *jede* natürliche Zahl$z$ mit $0\le z \le b^{n}-1$ (und $n\in \mathbb{N}$) *eindeutig* als Wort der Länge $n$ über $\sum_{b}^{n}$ darstellbar durch:
>
>$$ z=\sum_{i=0}^{n-1}z_{i}b^{i}$$
> 
> mit $z_{i}\in \sum_{b}=\{ 0,1,\dots ,b-1 \}$ für $i=0,1,\dots ,n-1$

Abkürzungen:
- MSB: Most Significant Bit : der Bit mit der höchsten Potenz
- LSB : Least Significant Bit: der Bit der niedrigsten Potenz

Mit $n$ bits lässt sich maximal die Zahl $2^{n}-1$ darstellen.


# Binär -> Dezimal
trivial durch aufsummieren der Zweierpotenzen

# Dezimal -> Binär
Langsam: Immer gucken, was die Größte Zweierpotenz ist, die noch in den Rest reinpasst.

Besser. wiederholtes Dividieren durch 2 :
![[Pasted image 20251013154626.png]]

## Horner-Schema
Wie rechnet man Zahlen zwischen verschiedenen Zahlensystemen um?

Ausklammern von den $b$ rekursiv.

$w_{n}$ sind das, was im Schritt vorher als Ergebnis der Division rauskommt.

Die Reste kann man dann genau wie bei den Binärzahlen von unten nach oben ablesen um den Wert in der neuen Basis zu haben.

Am besten sieht man es am Beispiel von Folie 10:
![[Pasted image 20251013155443.png]]

# Addition im Binärsystem
### Vorwissen: $\text{mod}$-Operation ("modulo") 
$a\text{ mod }b$ ist der Rest der Divivsion von $a$ durch $b$

> Warum ist Modulo Wichtig? Weil wir im Computer/Speicher nie unendlich viel Platz haben. Stattdessen haben wir eine begrenzte Anzahl an Bits/Ziffern.

Wenn die Ergebnisse das Intervall verlassen, sagt uns die $\text{mod}$-Operation, was dann als Ergebnis abgespeichert werden soll.

## Addition selbst:

```
 0011
+0010
-----
 0101
```

Nun gibt es aber ein Problem, wenn das Ergebnis nicht mehr in die anzahl an bits reinpasst:

```
 1111
+0010
-----
10001
```
Der bit  für $2^{4}$ passt nichtmehr in die gegebenen 4 bit - das Ergebnis modulo 16 ist 1

Häufiger enstehen Überläufe durch Division (vgl. 1/3= 0.33333....)

# Multiplikation
(Schriftliche Multiplikation im Dezimalsystem nochmal anschauen)
s.h. PXL Foto

Im Dezimalsystem
```
  23*42
  -----
  46
 920
 ---
 966 
```

Im Binärsystem:
```
          1101*1011
          ---------
          1101
         11010
        000000
       1101.... 
          
```

