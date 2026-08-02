TARGET DECK: DSAL::Bäume
# 2-3-4-Bäume

In einem 2-3-4-Baum hat ein "n-Knoten" {{c1::n}} ausgehende Kanten und enthält selbst {{c1::n-1}} Schlüssel.
<!--ID: 1785414493069-->


Was gilt für die Länge der Pfade in die Blätter eines 2-3-4-Baums? #flashcard
Alle Pfade zu Blättern sind **genau gleich lang**
<!--ID: 1785414492990-->


2-3-4-Baum **Einfügen**: Wo die darf Baumhöhe verändert werden? #flashcard
Nur in der Wurzel darf durch Spalten die Baumhöhe gesteigert werden.
<!--ID: 1785414492997-->


2-3-4-Baum **Einfügen**: Was wird beim Herabsteigen zum gesuchten Wert mit bestimmten Knoten gemacht? #flashcard
Aus jedem vollen Knoten (4-Knoten) wird der mittlere Wert in den Elternknoten raufgeschoben.
<!--ID: 1785414493002-->


2-3-4-Baum **Löschen**: gefundener Zielknoten ist **Blatt**. Verfahren? #flashcard
Der Wert kann einfach gelöscht werden, da vorher garantiert wurde, dass das Blatt **nicht minimal ist**.
<!--ID: 1785414493007-->


2-3-4-Baum **Löschen**: gefundener Zielknoten ist **innerer Knoten**. Verfahren? #flashcard
Sind direktes Linkes und Rechtes Kind BEIDE minimal?
- ja: **verschmelze** gesuchten Wert mit direkten Kindern zu 4-Knoten. Versuche dort Löschen erneut durch rekursiven Aufruf.
- nein: Bestimme **numerischen Vorgänger/Nachfolger** im Teilbaum, ersetze durch dessen Wert.
  Lösche diesen rekursiv.
<!--ID: 1785414493012-->

2-3-4-Baum **Löschen**: Nächster Knoten für Abstieg ist minimal. Verfahren? #flashcard
Mache ihn nichtminimal:
Sind ALLE **direkten** Geschwister des Abstiegsknotens minimal?
- ja: **Verschmelze**
	1. Abstiegsknoten
	2. präferiert sein LINKES Geschwisterkind
	3. dazwischenliegenden Wert aus dem Elternknoten
- nein: **Verschiebe** Schlüssel aus nichtminimalem Geschwister in Abstiegsknoten. (präferiere LINKES Geschwisterkind)
Steige dann in den -jetzt nichtminimalen- Knoten herab.
<!--ID: 1785426628092-->



2-3-4-Baum **Löschen**: Beim Abstieg in nächsten Knoten. Verfahren #flashcard 
Ist der Nachfolger für den Abstieg minimal?
- ja: Mache ihn minimal
- nein: Steige einfach rekursiv ab
<!--ID: 1785414493017-->



# Rot-Schwarz-Bäume

Welche Eigenschaften muss ein **Rot-Schwarz-Baum** erfüllen? #flashcard
1. (Jeder Knoten ist entweder Rot oder Schwarz)
2. Die Wurzel ist schwarz
3. Ein roter Knoten hat nur schwarze Kinder
4. Für jeden Knoten enthalten alle Pfade von ihm ausgehend zu einem externen Knoten die gleiche Anzahl schwarzer Knoten
5. externer Knoten = nicht existierende **schwarze** Kinder
<!--ID: 1785414493023-->


Wie wandelt man einen **2-3-4-Baum** in einen **Rot-Schwarz-Baum** um? #flashcard 
- Jeden 4-Knoten in einen schwarzen Knoten mit zwei roten Kindern spalten.
- Jeden 3-Knoten (beliebig) in einen schwarzen Knoten mit einem roten Kind spalten.
![[Pasted image 20260730134330.png]]
<!--ID: 1785414493028-->



Wie wandelt man einen **Rot-Schwarz-Baum** in einen **2-3-4-Baum** um? #flashcard
- Verbinde schwarze Knoten ihren **roten Kindern** zu einem Knoten
- (Analog: schreibe Rote Knoten neben ihre schwarzen Väter)
<!--ID: 1785414493036-->


Welche Schwarzhöhe hat die Wurzel eines einelementigen **Rot-Schwarz-Baums**? #flashcard
1
<!--ID: 1785414493042-->


Definiere die Schwarzhöhe $bh(x)$ eines Knotens $x$. #flashcard
$bh(x)$ ist die Anzahl schwarzer Knoten bis zu einem externen Blatt, **$x$ ausgenommen**.
<!--ID: 1785414493047-->



Wie viele **innere Knoten** kann ein RBT $t$ mit Schwarzhöhe $bh(t)$ höchstens und mindestens haben? #flashcard
- Mindestens: $2^{bh(t)}-1$
- Höchstens: $4^{bh(t)}-1$
<!--ID: 1785414493052-->


Wie hoch kann ein RBT mit $n$ inneren Knoten höchstens sein? #flashcard
$2\cdot \log_{2}(n+1)$
<!--ID: 1785414493058-->


Was gilt für das Verhältnis von Schwarzhöhe $bh(t)$ und Gesamthöhe $h$ eines RBT $t$? #flashcard
$bh(t)\leq h \leq2\cdot bh(t)$
<!--ID: 1785414493063-->

Zeichnen von Rot Schwarz Bäumen: Welche Form für welche Knotenfarbe? #flashcard
- Rot = Kreis (Rot=Rund)
- Schwarz = Quadrat
<!--ID: 1785415369973-->
