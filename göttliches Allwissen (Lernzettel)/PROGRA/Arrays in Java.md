---
tags:
  - PROGRA
status: rot
---
---

Arrays sind in Java [[Wert vs. Referenzvariablen & Call-By-Value vs. Call-By-Reference#Zuweisung von Referenzvariablen|Referenzvariablen]], also muss bei Zuweisungen auf Seiteneffekte geachtet werden. Ebenfalls sollte man arrays niemals mit `` == `` vergleichen.

Man achte auf [[Call-by-value vs. call-by-reference]].

---

# Syntax

## Deklaration

Stellt eine Speicherzelle x bereit, der aber noch ein Zeiger ins Leere "null" steht:
```java
int [] x; 
```

Erst mit ``new`` wird auf dem [[Wert vs. Referenzvariablen & Call-By-Value vs. Call-By-Reference|Heap]] ein neuer Speicherbereich für die Einträge des Arrays erzeugt: (Hier von der Länge 10)
```java
int [] x;
x = new int[10];
```

Meist schreibt man beides direkt zusammen:
```java
int[] x = new int[10];
```

## Kurzschreibweisen für die Wertzuweisung
anstatt langwierig zu schreiben:
```java
int[] x = new int[3];
x[0]=1;
x[1]=2;
x[2]=3;
```
Geht auch einfach:
```java
int[] x = {1,2,3};
```

Dies ist auch mehrdimensional möglich:
```java
int[][] x = { {14,2} , {5,0} , {6,7}};
```


## Mehrdimensionale Arrays

### TL:DR


### Was genau passiert:

Stellt eine Speicherzelle x bereit, der aber noch ein Zeiger ins Leere "null" steht:
```java
int [][] x;
```
![[Arrays in Java 2025-11-06 13.07.46.excalidraw]]



Mit ``new`` wird in auf dem Heap ein Speicherbereich erstellt: Dieser enthält hier aber keine Elemente, sondern nur Verweise auf die verschachtelten Arrays. Noch zeigen diese aber selbst ins leere:
```java
x = new [3][];
```
![[Arrays in Java 2025-11-06 13.09.43.excalidraw]]

Auch diese Arrays können dann (theoretisch auch einzeln und mit verschiedenen Längen) initialisiert werden:
```java
x[0] = new int[2];
x[2] = new int[3];
```

![[Arrays in Java 2025-11-06 13.12.02.excalidraw]]

Werte kann man entweder einzeln zuweisen oder mit ``{}`` auch alle auf einmal:
```java
x[0][0] = 1;
x[0][1] = 2;

x[2][2] = 10;
```
![[Arrays in Java 2025-11-06 13.22.12.excalidraw]]



