---
tags:
status: rot
---
---

>[!def] Binärsystem
> Das Binärsystem ist ein Zahlsystem zur [[Basen von natürlichen Zahlen#Basen|Basis]] 2.
> Es hat als [[Basen von natürlichen Zahlen#^61e78e|Alphabet]] $0$ und $1$.
> --
> Die Abkürzung `bit` steht für **BI**nary Digi**T** und bezeichnet eine einzelne Ziffer aus den Binärsystem.


---
*Die Folgenden Abschnitte beinhalten nur Informationen zur Darstellung positiver, natürlicher Zahlen im Binärsystem*. Für fähigere Kodierungen wird verwiesen auf:
- [[Negative Binärzahlen durch Komplement]]
- [[Festkomma-Darstellung von Binärzahlen]]
- [[Gleitkomma-Darstellung von Binärzahlen]]

----

## Beispiel: Wert einer Zahl
$z=(1011)_{2}$
$$z=\sum_{i=0}^{3}2^{i}\cdot z_{i}=2^{0}\!\cdot\!1 +2^{1} \!\cdot\! 1 + 2^{2}\!\cdot\! 0 + 2^{3} \! \cdot\! 1=1+2+0+8=11$$
# Größte darstellbare Zahl mit $n$-Bits

$$
z_{max}=\sum_{i=0}^{n-1}2^{i}=2^{n}-1
$$

Bsp. : $3$-stellige Binärzahl: $(111)_{2}=2^{0}+2^{1}+2^{2}=1+2+4=7=2^{3}-1$

# Umrechnung Dezimal- zu Binärsystem
Wie bei allen Zahlsystemen ist diese Umrechnung mit den [[Basen von natürlichen Zahlen#Horner-Schema|Horner Schema]] möglich.


Mit der Basis $2$ kann man es sich aber noch einfacher machen, und die Binärdarstellung wie folgt ermitteln:

![[Binärsystem 2025-10-14 11.49.31.excalidraw]]

--- 

# Rechenoperationen im Binärsystem

Allgemeine Einschränkung: In Rechner steht nicht beliebig viel Speicher zur Verfügung und der für einzelne Variablen reservierte Speicher hat eine feste Länge. Es entstehen ggfs. Überläufe die mit $\text{mod}$ beseitigt werden.

## Addition 
Bit für Bit mit Übertrag:
![[Binärsystem 2025-10-14 21.08.37.excalidraw|100]]

(Für die Überträge vergleiche man mit der Wahrheitstafel eines [Volladdierers](https://de.wikipedia.org/wiki/Volladdierer):

| $A$ | $B$ | $\text{Carry}_{in}$ | Result | $\text{Carry}_{out}$ |
| --- | --- | ------------------- | ------ | -------------------- |
| 0   | 0   | 0                   | 0      | 0                    |
| 0   | 0   | 1                   | 1      | 0                    |
| 0   | 1   | 0                   | 1      | 0                    |
| 0   | 1   | 1                   | 0      | 1                    |
| 1   | 0   | 0                   | 1      | 0                    |
| 1   | 0   | 1                   | 0      | 1                    |
| 1   | 1   | 0                   | 0      | 1                    |
| 1   | 1   | 1                   | 1      | 1                    |
bzw. kurz:

| Anzahl an Einsen | Result | $\text{Carry}_{out}$ |
| ---------------- | ------ | -------------------- |
| 0                | 0      | 0                    |
| 1                | 1      | 0                    |
| 2                | 0      | 1                    |
| 3                | 1      | 1                    |
)

### Überläufe
Nun kann es aber zu einem **Überlauf** kommen, wenn das Ergebnis nicht mehr in die gegebenen $4$-Bit passt: Der Bit der "zu viel" ensteht wird ignoriert, was damit gleichbedeutend ist, dass das Ergebnis $\text{mod }2$ gerechnet wird.

![[Binärsystem 2025-10-14 21.14.50.excalidraw|100]]



# Multiplikation
Die Multiplikation funktioniert im Binärsystem genauso wie im Dezimalsystem, nur dass sie binär noch einfacher ist.

## "Auf dem Papier"

(Zur Erinnerung: Schriftliche Multiplikation im Dezimalsystem)
![[Binärsystem 2025-10-14 21.23.02.excalidraw|150]]

Zu Grunde liegt für einzelne Bits die folgende Multplikationstabelle:
$0\cdot 0=0$
$0\cdot1=0$
$1 \cdot 0 = 0$
$1 \cdot 1 = 1$

![[Binärsystem 2025-10-14 21.27.50.excalidraw|200]]

Man sieht schön: Es wird eigentlich nur um eins nach links verschoben und dann -wenn der bit 1 beträgt- addiert.

## Als Formel:
Sei $x$ der Multiplikand und $y=(y_{n-1},\dots,y_{0})$ der Multiplikator, dann ist $$
\begin{align}
x\cdot y&= x\!\cdot\! y_{0} \;+\; x\!\cdot\! y_{1}\!\cdot\! 2 \;+\; x\!\cdot\! y_{2}\!\cdot\! 2^{2} \;+\; \dots \;+\; x \!\cdot\! y_{n-1} \!\cdot\! 2^{n-1} \\
 \\
&=\sum_{i=0}^{n-1}x\cdot y_{i}\cdot2^{i}
\end{align}
$$
In der Praxis ist es sinnvoll, jeden Term der Form $x\cdot y_{i}\cdot 2^{i}$ sofort zur laufenden Summe zu addieren, sobald der generiert wurde.




