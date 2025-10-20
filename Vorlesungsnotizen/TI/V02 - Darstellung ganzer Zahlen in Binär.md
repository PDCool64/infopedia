---
"date:": 2025-10-14
tags:
  - TI
status: rot
---
---

Naiver Ansatz: Wir designieren einen Bit, der entscheidet ob wir + oder - als Vorzeichen haben.

Probleme:
- Zwei Darstellungen für 0 möglich
- Umsetzung in der Hardware: Man bräuchte je nach Vorzeichen unterschiedliche Schaltungen für Addition und Subtraktion

Schöner wäre, wenn man ein Addierwerkt hat, und die codierung so aufgebaut ist, dass das Addierwerk damit für alle Vorzeichenkombinationen arbeiten kann.

Die Addition im Zweierkomplement funktioniert von der Hardware genauso wie die Addition von Zahlen ohne Vorzeichen

Grundlagen:
1. Einer-Komplement $K_{1}$ : Jede Ziffer umkehren
2. Zweier-Komplement $K_{2}$ : Einer-Komplement $+1\text{ mod }2^{n}$ 

Beachte: Wichtig.
	$K_{1}(K_{1}(x))=x$
	$K_{2}(K_{2}(x))= x$

## Anwendung dieser Tatsachen:

### Mit dem Einer-Komplement
Der MSB legt das Vorzeichen fest:
fängt mit 0 an -> alles normal
fängt mit 1 an -> bilde K1 und interpretiere dieses als negativ

funktioniert aber *nicht immer* für die Addition:


$-4+7=3$

```
 7= 0111
-4= K1(0100)= 1011

Addition:

 0111
 1011
 ---- 
10010
bzw mod
 0010
 
aber 7-4 != 2

(es gibt ab und zu off-by-one fehler; Man müsste in manchen bestimmten Fehlen 1 dazu addieren)
```


Beim Zweierkomplement funktioniert dies immer.
(Ist heute der Standard in fast allen Rechnern)



*Bei den Komplementen: Ist der Erste Bit eine 1, dann ist die Zahl als negativ zu Interpretieren, d.h. das Komplement muss gebildet werden*


## Darstellungsbereiche bei 4 bit in verschiedenen Systemen

(hier hat auch die Doppelte Möglichkeit die 0 im Einserkomplement zu speichern zum Vorschein)

Über die -8 -> 7 im Zweierkomplement kann man sich nochmal nen Moment Gedanken machen
-K2(1000)= -(0111+1) = -1000 ^= -8  (oder so)


An der Tabelle kann man sich mit Sprüngen schön sehen, warum manchmal im K1 der Fehler um 1 entsteht (s.h. PXL Foto)![[V02 - Darstellung ganzer Zahlen in Binär 2025-10-14 19.10.46.excalidraw]]

(hier fehlt noch ein bsl)



# BCD-Code

Ziffern werden einzeln mit 4 bits als vorzeichenlosen Binärzahl dargestellt.

(Der Ungenutze Platz wird bsp im Mobilfunk für Sonderzeichen wie * und Co. verwendet)
(Heute nutzt man das aber eigentlich nichtmehr)

Macht aber Die Addition schwieriger.
Korrektur: Bei den Überträgen wird 6 drauf addiert, wenn diese keine gültige BCD Zahl von 0-10 (binär) ist (s.h. PXL Foto)




