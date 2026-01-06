---
tags:
  - TI
status: rot
TARGET DECK: TI
---
---

Ein Überblick über verschiedene Darstellungsformen von [[Schaltfunktionen und Boolesche Funktionen#Boolesche Funktionen|Booleschen Funktionen]]

---

# 1.0 Wahrheitstafeln

Jede boolesche Funktion kann als Warheitstafel geschrieben werden, die für alle Kombinationen der Eingaben eine Ausgabe ausweißt.

z.B. :

| $x_{1}$ | $x_{0}$ | $f(x_{1},x_{0})$ |
| ------- | ------- | ---------------- |
| 0       | 0       | 0                |
| 0       | 1       | 1                |
| 1       | 0       | 1                |
| 1       | 1       | 0                |
wobei es sich hier um die Wahrheitstafel von $\text{xor}$ handelt.

# 1.1 Liste "*einschlägiger Indizes*"

^bbd58f
Woraus besteht die Liste der einschlägigen Indizes #flashcard 
Man nummeriert die Zeilen einer Wahrheitstabelle durch.
Dann speichert man nur noch die Indizes der Spalten welche $1$ als Ausgabe liefern.
<!--ID: 1767096642081-->


![[Darstellung boolescher Funktionen 2025-10-23 13.00.00.excalidraw]]

Basierende darauf, wie im Binärsystem gezählt wird, sind die Zeilenindizes eigentlich nur die ins Dezimalsystem übertragenen Bitmuster, welche als Ausgabe $1$ liefern:

$(3)_{10}=(011)_{2}$
$(5)_{10}=(101)_{2}$
$(7)_{10}=(111)_{2}$

Das Konvertieren aus einer Liste einschlägiger Indizes zu einer Wahrheitstabelle ist somit ebenfalls trivial.

# 1.2 Binärvektorliste und Ternärverktorliste
(heute eher veraltet)

Wofür steht der `_` in einer Binärvektorliste? #flashcard 
Verwendet wird die Schreibweise mit einem Unterstrich `_` , welcher "Do Not Care" bedeutet - der Eingabebit an dieser Stelle kann also einen beliebigen Wert haben.
<!--ID: 1767098461350-->


Man nimmt sich eine Tabelle der [[#1.1 Liste "*einschlägiger Indizes*"|Einschlägigen Zeilen]] und streicht dan redundante Informationen:
![[Darstellung boolescher Funktionen 2025-10-23 13.08.10.excalidraw]]
Es entsteht also die Form `1_1 , _11` welche beide Eingabeoptionen zeigt, bei denen die Boolesche Funktion $1$ ausgibt:
- die erste und die Letze Eingabe sind $1$
- die letzten beiden Eingabe sind $1$

---
# 3.[[DNF und KNF - Disjunktive und Konjunktive Normalform]]


---
# 4. DAG - Directed Acyclic Graph

DAG = Directed Acylic Graph
- Directed = Gerichtet
- Acyclic = Keine Zyklen (man kann nicht im Kreis laufen sondern kommt nach endlich vielen Schritten an)
 - Graph = Graph aus Knoten und Kanten

Für den Moment ist die Einschränkung auf nicht-zyklische Graphen sehr sinnvoll - die Flimmerschaltung ist aber ein Beispiel, bei dem es schon Sinn machen kann:

## Beispiel: Logikgatter -> DAG

![[Darstellung boolescher Funktionen 2025-10-29 09.31.34.excalidraw|600]]

## Warum DAGs die Fehlersuche leicht machen:



---

# 5. OBDD - Ordered Binary Decision Diagram
Darstellung als Entscheidungsbaum:
- durchgezogene Linie: Variable ist 1
- gestrichelte Linie: Variable ist 0
![[Pasted image 20251030095225.png]]

## Variablenordnung
- Man darf auf jedem Pfad eine Variable nur einmal (auch keinmal erlaubt) abfragen, womit automatisch die Festlegung auf eine bestimmte Reihenfolge der Variablen notwendig wird.
- Die Variablenordnung kann beliebig gewählt werden, je nach Variablenordnung kann der kleinstmögliche OBDD aber eine sehr unterschiedliche Größe haben.
  
z.b. Kleinster OBDD mit dieser Variablenordnung:
![[Pasted image 20251030110626.png]]

Wählt man einfach eine Variablenordnung nach absteigenden Index ist plötzlich dies der kleinste OBDD:
![[Pasted image 20251030110704.png]]
## Herleitung über Kofaktoren
Setzt man in einer Booleschen Funktion eine Eingabevariable auf einen festen Wert, so erhält man eine neue boolesche Funktion mit einer Variable weniger.
Bsp:
	$f(x_{1},x_{0})=x_{1}\wedge x_{0}$
	
	$f(x_{1}/ 1)=1\wedge x_{0}=x_{0}$
	$f(x_{1}/ 0)=0\wedge x_{0}=0$
	
Macht man dies rekursiv erhält man einen OBDD - jeder Knoten ist die Festlegung einer Variable auf 1 (durchgezogener Ast) oder 0 (gestrichelter Ast) und der Folgeknoten dann die Folgeknoten die Kofaktoren mit der jeweiligen Variable als Fest 1 oder 0.

Zieht man dies bis zum Ende durch hat man konstante boolesche Funktionen ohne Variablen, die den Blättern gleichkommen.
