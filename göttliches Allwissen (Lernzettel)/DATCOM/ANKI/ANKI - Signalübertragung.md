TARGET DECK: DATCOM::Bitübertragung

Welche Typen an kabelgebundenen Leitern gibt es? #flashcard
- elektrische Leiter
- Wellenleiter (für Licht)
<!--ID: 1793544355247-->



Welche Kategorien drathloser Kommunikation gibt es? #flashcard
- gerichtet
- ungerichtet
<!--ID: 1793544355255-->


Welche zwei Übertragungsverfahren gibt es bzgl. der Umsetzung in Signale? #flashcard
- Basisbandübetragung
- Modulation
<!--ID: 1793544355268-->


Definiere Basisbandübetragung #flashcard
- Direkte Weitergabe des Eingabesignals
- Umformung digital $\to$ digital
<!--ID: 1793544355311-->


Definiere Modulation #flashcard
Aufprägung des Eingabesignals auf harmonische Trägerschwingungen.
<!--ID: 1793544355315-->


Was macht eine 4B/5B Kodierung ? #flashcard
verhindere lange Läufe von mehr als drei 0en, indem 4 bit Wörter durch gut gewählt 5bit Wörter kodiert werden
<!--ID: 1793544355321-->


Wie arbeitet ein **RZ = Return to Zero** Code? #flashcard
Es wird nur alle zwei Taktschritte ein Bit übertragen; Effizienz = 50%
Erster Taktschritt = Daten(+-1); Zweiter Taktschritt = Immer 0
$\to$ Wertsprünge besser zu erkenne als Absolutwerte
$\to$ Selbsttaktung
![[Pasted image 20261101153249.png]]
<!--ID: 1793544355327-->


Wie arbeitet ein Differentialer Code? #flashcard
Bei jeder 1 wechselt die Darstellung von 0 und 1.
Bzw. jede 1 hat genau die andere Darstellung im Vergleich zur vorigen 1.
<!--ID: 1793544355333-->


Wie arbeitet der Manchester-Code? #flashcard
Es wird nur alle zwei Taktschritte ein Bit übertragen; Effizienz = 50%
1 = Wechsel $1\to{0}$
0 = Wechsel $0\to{1}$
<!--ID: 1793544355340-->



Welche drei Typen der Modulation gibt es? #flashcard
- Amplitudenmodulation
- Frequenzmodulation
- Phasenmodulation
<!--ID: 1793544355347-->


Was besagt das Abtasttheorem von Nyquist/Shannon u.A.? #flashcard
Ein bandbreitenbeschränktes Signal mit höchster Frequenz $B$ kann durch Abtasten mit einer Frequenz von $2 \cdot B$ oder mehr eindeutig bestimmt werden.
<!--ID: 1793544355359-->


Was besagt die Nyquist-Formel? #flashcard
**Störungsfreier Kanal** mit eingeschränkter Bandbreite:
- $B$ = Bandbreite in $\text{Hz}$
- $n$ = Anzahl diskreter Signalstufen (**endlich!**)
$$\text{Max. Datenrate [Bit/s]}=2\cdot B\cdot \log_{2}(n)$$
<!--ID: 1793544355363-->


Was besagt die Shannon-Formel? #flashcard

Bandbreitenbeschränkter Kanal mit **zufälligem Rauschen**
- $B=$ Bandbreite in $\text{Hz}$
- $S=$ Empfangsleistung des Nutzsignals
- $N$ = Empfangsleistung des Rauschens
 $$\text{Max. Datenrate [Bit/s]}=B\cdot \log_{2}(1+S/N)$$
<!--ID: 1793544355368-->


Wie schätzt man in der Praxis oft die erreichbare Datenrate? #flashcard
Als Minimum der Shannon-Formel sowie der Nyquist-Formel.
<!--ID: 1793544355374-->
