TARGET DECK: DSAL::Sortieren

Selectionsort sucht immer das ... des restlichen Teils. #flashcard
Minimum.
<!--ID: 1780572621385-->


Insertionsort bildet den sortierten Teil ... im Array. #flashcard
vorne
<!--ID: 1780572621389-->


Bei Mergesort mit ungerader Arraylänge wird die ... Hälfte eins größer als die ... Hälfte gewählt. #flashcard
Die linke Hälfte ist eins größer als die rechte Hälfte.
<!--ID: 1780572621392-->


Was ist beim Aufschreiben der Schritte von Mergesort wichtig? #flashcard
Wir verwenden keine Parallelisierung: Es findet immer nur ein Merge statt.
Reihenfolge ist der call-stack d.h. erst linke arrayhälfte komplett absteigen/auflösen bevor die rechte überhaupt bearbeitet wird.
<!--ID: 1780572621394-->


In welcher Arrayhälfte landen bei Quicksort Elemente, die genau gleich dem pivot sind? #flashcard
rechts
<!--ID: 1780572621397-->


Eigenschaften: _Selectionsort_ #flashcard
**W**: $n^{2}$
**A**: $n^{2}$
**Speicher**: $1$
**Stabil**: Nein (gibt aber Varianten)
<!--ID: 1780572621399-->


Eigenschaften: _Bubblesort_ #flashcard
**W**: $n^{2}$
**A**: $n^{2}$
**Speicher**: $1$
**Stabil**: Ja
<!--ID: 1780572621401-->


Eigenschaften: *Insertionsort* #flashcard
**W**: $n^{2}$
**A**: $n^{2}$
**Speicher**: $1$
**Stabil**: Ja
<!--ID: 1780572621404-->


Eigenschaften: *Mergesort* #flashcard
**W**: $n\log n$
**A**: $n\log n$
**Speicher**: $n$
**Stabil**: Ja
<!--ID: 1780572621407-->


Eigenschaften: *Quicksort* #flashcard
**W**: $n^{2}$
**A**: $n\log n$
**Speicher**: $\log n$
**Stabil**: Nein (gibt aber Varianten)
<!--ID: 1780572621409-->



Eigenschaften: *Countingsort* #flashcard
**Mit** $r=$ Anzahl möglicher Werte
**W**: $n+r$
**A**:  $n+r$
**Speicher**:  $n+r$
**Stabil**: Ja (in der Präfixsummen-Variante)
<!--ID: 1780572621411-->


Eigenschaften: *Radixsort* #flashcard
**W=A**: $d\cdot(n+k)$ 
	mit $d=$ Anzahl Schlüsselkomponenten
	und $k$ = mögliche Werte pro Schlüsselkomponente
**Speicher**: $n$
**Stabil**: Ja
<!--ID: 1780572621414-->


Eigenschaften: _Bucketsort_  #flashcard
Sei $b$ = Anzahl Buckets
**W**: Alles in einem Bucket: Laufzeit des verwendeten Subalgorithmus
(oft $n^{2}$ mit Insertionsort)
**A**: $n+b$
**Speicher**: $n$ oder ($n\cdot b$ bei stumpfen malloc(n) für jeden Bucket)
**Stabil**: Ja
<!--ID: 1780572621416-->

