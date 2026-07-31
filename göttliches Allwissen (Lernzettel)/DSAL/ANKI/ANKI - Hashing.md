TARGET DECK: DSAL::Hashing

Bei der **direkten Adressierung** werden hat die Tabelle {{c1::genauso viele}} Einträge wie es mögliche Schlüssel gibt.
<!--ID: 1785487282482-->

Konsequenz: {{c1::nicht realisierbare Tabellengröße}}
<!--ID: 1785487282486-->


Wie berechnet man die Wahrscheinlichkeit für **keine** Kollision nach $n$ Einfügevorgängen in eine $m$-elementige Tabelle? #flashcard
$$
\prod_{i=0}^{n-1} \frac{m-1}{m}
$$
(Geburtstagsparadoxon)
<!--ID: 1785487282434-->


Average-Case-Laufzeit von Hashing durch **Verkettung**: Suche nach Element #flashcard
Für $n=\text{Anzahl eingefügter Werte}$
Und $m=\text{Größe der Hashtabelle}$
$$\mathcal{O}(\alpha):=\mathcal{O}\left( \frac{n}{m} \right)$$
(Füllgrad)
<!--ID: 1785487282439-->


Vier Eigenschaften einer guten Hashfunktion: #flashcard
1. einfach zu berechnen
2. surjektiv auf die Menge $\{ 0,\dots ,m-1 \}$
3. möglichst gleichverteilte Hashwerte liefern
4. ähnliche Schlüssel breit auf die Hashtabelle verteilen
<!--ID: 1785487282442-->



Formel: Hashing mit **Divisionsmethode** #flashcard
$m=\text{Größe der Hashtabelle}$
$h(k)=k\text{ mod }m$
<!--ID: 1785487282446-->



Was ist bei Hashing mit der Divisionsmethode zu beachten? #flashcard
Die Wahl der Größe $m$ ist kritisch, z.b. bei $m$ Zweierpotenz nur die letzten Bits überhaupt einen Einfluss hätten: Bei echten Daten mit Mustern katastrophal.
$\to$ Primzahlen weit weg von Zweierpotenzen sind gut
<!--ID: 1785487282450-->



Formel: Hashing mit **Multiplikationsmethode** #flashcard
$m=\text{Größe der Hashtabelle}$
$0<c<1$ empfohlen $c \approx \frac{\sqrt{ 5 }-1}{2}\approx 0,618$
$$
h(k)= \lfloor m \cdot (k\cdot c\text{ mod }1) \rfloor 
$$
<!--ID: 1785487282453-->


Formel: universelle Standardklasse an Hashfunktionen: #flashcard
$$h_{a,b}(k)=((ak+b)\text{mod p})\text{mod } m$$
- $p$ Primzahl mit $p>m$ und $p>\text{größter Schlüssel}$
- $a,b$ einmalig bei Programmstart gewählt
	- $1\le a<p$ 
	- $0\le b < p$
(Beachte die Mindestgröße von $p$ sowie $a \not\equiv_{p}0$ damit innerer Teil Bijektion -> schön mischt)
<!--ID: 1785487282457-->



Wie funktioniert **offene Adressierung** bei Hashing? #flashcard
- Werte direkt in Hashtabelle gespeichert
- Falls Stelle belegt, mit **Sondieren** weiterspringen
- Löschen schwierig, nur mit "DELETED" marken die Platz nie freigeben
<!--ID: 1785487282461-->


Was bedeutet **Clustering** bei Hashing mit offener Adressierung? #flashcard
Lange Folgen belegter Slots die dazu tendiert immer länger zu werden.
- entsteht durch schlechtes Sondieren
- macht alles langsamer
<!--ID: 1785487282464-->


Formel & con: **Lineares Sondieren** #flashcard
$$
h(k,i)=(h'(k)+i)\text{ mod }m
$$
con:
- erste Sondierung bestimmt gesamte Sequenz
- **Clustering**
<!--ID: 1785487282468-->


Formel: **Quadratisches Sondieren** #flashcard
$$
h(k.i)=(h'(k)+c_{1}\cdot i +c_{2} \cdot i ^{2})\text{ mod }m
$$
<!--ID: 1785487282472-->



pro/con: **Quadratisches Sondieren** #flashcard
pro:
- lineares Clustering wird vermieden
con:
- erste Sondierung bestimmt gesamte Sequenz:
  $h(k,0)=h(k',0)\implies \forall_{i}: h(k,i)=h(k',i)$
  $\to$ "sekundäres Clustering"
<!--ID: 1785487282475-->



Formel: **doppeltes Hashing** #flashcard
$$
h(k,i)=(h_{1}(k)+i \cdot h_{2}(k))\text{ mod }m
$$
pro/con: **doppeltes Hashing** #flashcard
pro:
- erste Sondierung bestimmt **nicht** gesamte Sequenz+
- Verteilt gut auf gesamte Tabelle, kaum Clustering
<!--ID: 1785487282479-->


