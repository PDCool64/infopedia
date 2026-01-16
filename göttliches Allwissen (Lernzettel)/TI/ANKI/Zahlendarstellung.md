TARGET DECK: TI

Wie bestimmt man das Zweierkomplement einer Binärzahl #flashcard
1. invertiere alle Bits
2. addiere +1
<!--ID: 1768576162442-->


Floating-Point Zahlen:
Welche Bits sind für Vorzeichen, Mantisse und Exponent in einer 32bit IEEE754 Gleitkommazahl vorgesehen #flashcard
- 0 : Vorzeichen
- 1-8 : Exponent
- 9-31 : Mantisse
<!--ID: 1768576162446-->


Floating-Point Zahlen:
Für den Exponent seien 8Bit vorgesehen - um welches bias muss er verschoben werden #flashcard
$$\text{bias}=2^{k-1}-1=2^{7}-1=127$$
<!--ID: 1768576162448-->


Floating-Point Zahlen:
Sei $\hat{e}$ der gespeicherte Exponent - wie berechnet man aus ihm mit dem $\text{bias}$ den tatsächlichen Exponent $e$ für die Umrechnung? #flashcard
$$
\begin{align}
e&=\hat{e}-\text{bias} \\
\hat{e} &= e+\text{bias}
\end{align}
$$
> Merke:
> Das $\hat{e}$ mit Dach ist *visuell größer* als das $e$ ohne Dach.
<!--ID: 1768576162451-->



Floating-Point Zahlen:
Was muss bei der Mantisse in der normalisieren Darstellung beachtet werden? #flashcard
Es wird eine implizite " $1,$ " vor den Nachkommastellen angenommen, welche im Speicher nicht geschrieben wird.
$\to$ Beim konvertieren wieder einfügen.
<!--ID: 1768576162453-->

Wozu verwendet man den Gray-Code #flashcard
- KV-Diagramme zur Vereinfachung boolescher Funktionen
- Weniger schwere Fehler durch Bitflips bei der Datenübertragung
<!--ID: 1768577354407-->


Was ist die definierende Eigenschaft des Gray-Code #flashcard
Benachbarte Zahlen unterscheiden sich nur in einem Bit
<!--ID: 1768577354413-->


Wie lauten die Zahlen $0-4$ im Gray-Code #flashcard
0: ``00``
1: ``10``
2: ``11``
3: `10`
<!--ID: 1768577354416-->


Wie rechnet man eine Binärzahl in den Gray-Code um #flashcard
``( (x<<1) xor x ) >>1``
- Wende ``xor`` auf die Zahl und ihr um eins nach *Links* geshiftetes an
- Shifte zurück
<!--ID: 1768577354418-->