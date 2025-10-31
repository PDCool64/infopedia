---
date: 2025-10-27
tags:
  - TI
status: rot
Vorlesungsfolien: "[[II15_Arrays.pdf]]"
Skriptfolien:
---
---

## Mehrdimensionale Arrays
```java
MyArray = new int [2] [2];

int wert = MyArray[1][1];
```

## Summe der Werte in einem array
```java

Zahlen = new int [10];

int sum=0;
for (int i=0;i<Zahlen.lenght,i++)
	sum+=Zahlen[i]

```

# Wert- und Referenzvariablen
`int x;`
Bei Primitiven Datentypen steht an der Stelle x direkt der Wert der Variable


`int [] x;`
Bei anderen Datentypen wird eine Speicherzelle bereitgestellt.
In `x` wird später eine Speicheradresse stehen, an der die Array-Einträge zu finden sind. Im Moment ist `x` der "Zeiger ins Leere", in Java durch `null` gekennzeichnet.

### Zwei Speicherbereiche
- Stack / Kellerspeicher (das, was wir bisher gesehen haben.) Hier steht der Wert der Variablen. Bei primitiven steht hier direkt der Wert. Bei nicht-primitiven nur Verweise auf Adressen im Heap
- Heap / Haufenspeicher für Werte von Objekten wie z.B. Arrays

`new` erzeugt neuen Speicherbereich auf dem Heap für die Einträge des Arrays.
(Abhängig von der Länge die man erzeugen will; plus ein paar Metadaten wie die Länge des arrays) 

![[V40 - Arrays 2025-10-27 19.42.42.excalidraw]]



# Konsequenzen / TL:DR
 In Java hängt es am Datentyp, ob Werte oder Verweise in den Variablen gespeichert werden.
 
In Java gibt es kein explizites Verwalten von Pointern.

Programmierer muss sich nicht selbst um die Speicherverwaltung kümmern.

Vorteil von Arrays: Wahlfreier Zugriff: Man kann sofort aus Anfangsadresse, gewünschten index sowie Länge der einzelnen Einträge ausrechnen, an welcher Stelle das gewünschte Element liegt. Man kann somit auf alle Elemente gleich schnell zugreifen.

Die Größe von arrays ist fest. Man kann es danach nicht mehr verlängern.


# Speicherverwaltung von Mehrdimensionalen Arrays:

```java

int [][] x;
x = new int[3][];
x = new int[3][];
x[0] = new int[2];
x[0][0] = 18;
x[1] = new int[1];
x[1][0] = 42;
```

Bei Mehrdimensionalen Arrays werden im oberen Array nur noch verweise auf weitere arrays auf dem heap. (die Verschiedenen sub-arrays müssen nicht gleich lang sein - sind sie meistens aber)

> d.h. `int [][][]` bedeutet "irgendwas, bei dem nach drei verweisen ein `int`" rauskommt. (Keine Ahnung, ob dies *wirklich* so ist?)


# Lengt eines Arrays
`MyArray.length` ist ein Attribut von der Objekte der Klasse


# Seiteneffekte
Speicher-Realisierung / Umsetzung im Speicher ist wichtig für Programmierung wegen *Seiteneffekten*:

## Zuweisung von Wertvariablen
bei 
```java
int x =2;
int y = x;

y = 8;

-> x bleibt unverändert
```

bei einem array wird auch der Wert im Stack überschrieben - dort liegt aber nur ein Verweis auf den Speicher - am ende liegt also an beiden Stellen ein Verweis auf ein und das selbe array. 

> "Verweise vs. Kopien"

![[Pasted image 20251027195514.png]]![[Pasted image 20251027195525.png]]

