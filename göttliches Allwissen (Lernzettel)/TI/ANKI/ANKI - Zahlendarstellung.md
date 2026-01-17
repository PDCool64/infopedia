TARGET DECK: TI

Wie bestimmt man das Zweierkomplement einer Binärzahl #flashcard
1. invertiere alle Bits
2. addiere +1
<!--ID: 1768576162442-->

Welchen Bereich kann man in $n$ Bit im Zweierkomplement darstellen #flashcard
$-2^{n-1}\le x \le 2^{n-1}-1$
<!--ID: 1768578251949-->


Warum kann man im Zweierkomplement eine Zahl mehr als im Einerkomplement darstellen  #flashcard
Es gibt keine doppelte Darstellung für die $0$
<!--ID: 1768578251953-->



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
Wann ist eine IEEE754-Zahl normalisiert? #flashcard
Wenn der Exponent weder ``00..00`` oder ``11...111`` ist
<!--ID: 1768578251956-->


Wann ist eine IEEE754-Zahl denormalisiert
und was ist dann für die Mantisse wichtig #flashcard
- denormalisiert wenn der Exponent  ``00..000`` ist
- *keine* implizite " $1,$ " vor der Mantisse
<!--ID: 1768578251958-->



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
1: ``01``
2: ``11``
3: `10`
<!--ID: 1768577354416-->


Wie rechnet man eine Binärzahl $x$ in den Gray-Code um #flashcard
$$g=x \oplus(x\gg 1)$$
<!--ID: 1768578251961-->
