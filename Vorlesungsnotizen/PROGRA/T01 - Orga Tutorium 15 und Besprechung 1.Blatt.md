---
date: 2025-10-22
tags:
status: rot
Vorlesungsfolien: "[[Blatt01-Übung.pdf]]"
Skriptfolien:
---
---
# Orga: Tutorium 15

Erreichbarkeit Tutor 15
- luna@fsmpi.rwth-aachen.de
- am besten über Moodle

Jeder muss zwei Hausaufgaben aufgaben vorstellen:
- Jedes Tutorium kommen 6 Personen dran
- Jeder wird 2x vorstellen können
- *Man meldet sich selbst* um eine Aufgabe vorzustellen - Wenn man also ein bisschen die Initiative ergreift, kann man sich aussuchen welche Aufgabe man vorstellen will.

- Es *kann* passieren, dass die Ausgaben-Vorstellungs-Regel weggfällt, weil die Fachschaft die dadurch entstehende Anwesenheitspflicht am anfechten ist.


> Die Mitschriften des Tutors werden auf "Scibo" (oder so ähnlich) hochgeladen

---
# A1 : Überblickswissen

a) 
- Javacode(.java) zu Java bytecode(.class)  (Compiler dafür heißt JavaC)
- Java Virtual Machine führt bytecode aus

> Fun-fact: Es gibt den Just-in-Time Compiler (JIT), der ein Teil der JVM ist, der dafür sorgt, dass häufig ausgeführte Programmteile hochperformanter ausgeführt werden.
  
  
b)
- variable mit beliebigem Wert
- 'x' ist der Wert irgendeiner Variable, welche den char wert 'x' hat
- "x" ist der Wert irgendeiner Variable, welche den string wert "x" hat

c)
MSB=1 -> negativ
MSB=0 -> positiv

# A2 : Syntax und Semantik

## a) 
s(x) = successor(x) d.h. s(0)=1

i) nicht syntaktisch korrekt, weil sich kein plus(X;Y;Z) mit drei "Argumenten" erzeugen lässt.

ii)
Semantik = 3

iii)
![[T01 - 2025-10-22 12.53.19.excalidraw]]


## b)
Jedem Syntaktisch korrektem Ausdruck lässt sich genau eine Semantik zuordnen => Behauptung ist richtig.

## c)
Falsch: Ein Programm ist semantisch korrekt, wenn es das tut, wofür es entwickelt wurde. Ist es syntaktisch schon nicht korrekt, kann es seinen Zweck nicht erfüllen: (Ein Java-Programm kann seinen Zweck nicht erfüllen, wenn es beim compilieren schon einen Fehler wirft)


> Kommt in einem Ausdruck ein Symbol vor, das nicht zu den Nichtterminalen der Sprache gehört, dann ist dies ein Syntaxfehler.
# A4 :  Formale Sprachen und Grammatiken:

a)
![[T01 - 2025-10-22 13.07.59.excalidraw]]

b)
![[T01 - 2025-10-22 13.20.03.excalidraw]]


c)
![[T01 - 2025-10-22 13.24.20.excalidraw]]


# A6 : Zweierkomplement
a) Bilde das Zweierkomplement

b)

erstes print:
`int zahl ` ist im Speicher `10000000....000`

addiert man `1` erhält man
``1000....00001`

Was durch interpretation mit dem Zweierkomplement
2147483647 ergibt.

zweites print:
`int zahl ` ist im Speicher `10000000....000`

die `-1` wird im Speicher durch $111111111111111111\dots$
repräsentiert

Das erzeugt einen addiert man beide ensteht ein Overflow, und die größte Darstellbare Zahl entsteht:
Die 1 im MSB von `1000...` sowie die 1 im MSB von `1111....` ergeben "0 Übertrag 1" , der Übertrag fällt links weg und `0111111....` entsteht.

c)

2
-9
-5
13
-16

