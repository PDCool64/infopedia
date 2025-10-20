---
date: 2025-10-20
tags:
  - PROGRA
status: rot
Vorlesungsfolien: "[[II13_Anweisungen_und_Kontrollstrukturen.pdf]]"
Skriptfolien:
---
---
---
# Vokabular

**Anweisung**: Definiert Übergang von einem Programmzustand zum nächsten

**Programmzustand**: 
- Daten im Speicher (Werte aller Variablen, ...)
- Wert des Befehlszählers

**Kontrollfluss:** Reihenfolge, in der die Operationen des Programms abgearbeitet werden.

**Datenfluss:** Übergabe der Daten einer Operation an eine andere Operation


# Zuweisung
`x=5;` Voraussetzung: Variable und Ausdruck müssen kompatible Typen haben.

## Kurzschreibweisen:


(hier ist noch etwas cursed. Muss nochmal auf Fehler überprüft werden)
`x=x+10` (`x+10` wird zu einem int)
`x+=10` (x bleibt in seinem Datentyp)

sind fast identisch. Ein kleiner Unterschied existiert aber:
`x+=10` bedeutet genau
`x=(int)x+10` 

d.h.
```java
byte a;
a=a+1; -> FEHLER
```
während:
```java
byte a;
a+=1; -> a=(byte)a+1
```


Man kann manche Aussagen auch als Ausdruck verwenden:
- `x++` hat als Ausdruck den "alten" Wert von x
- `++x` hat als Ausdruck den "neuen" Wert von $x$
d.h.
```java
x=4;
y=x++

-> y ist 4
-> x ist 5
```

während:
```java
x=4;
y=++x

-> y ist 5
-> x ist 5
```

$\to$ Deshalb: Man sollte `++x` und `x++` *NICHT* als Ausdrücke verwenden, sondern nur als Anweisungen.

Einzige Ausnahme dafür:
`x=y=5` ist fine zu schreiben.
Under the hood passiert:
``x=(y=5);``

# Bedingte Anweisung

## `if`-Anweisung

```java
if (Bedingung) {
	 Wenn-Anweisung
}
else {
	Else-Anweisung
}
```


Bei geschachtelten `if`-Anweisung: 
- else gehört zum innersten `if`
- {...} Block von Anweisungen und Variablendeklarationen
![[Pasted image 20251020185919.png]]


## `switch`-Anweisungen
für Größere Fallunterscheidungen zwischen vielen Fällen, die vom Wert eines Ausdrucks abhänge.


```java
switch (byte,short,int,char oder string-Ausdruck) {
	case Ausdruck_1 -> Anweisung_1
	case Ausdruck_2 -> Anweisung_2
	case Ausdruck_3A , Ausdruck_3B -> Anweisung_3 //Mehrere Ausdrücke mit Komma getrennt sind erlaubt
	...
	
	default -> Ausdruck_default //Kann auch Fehlen
}

```

z.B.
![[Pasted image 20251020190447.png]]

## `switch` in Ausdrücken
![[Pasted image 20251020190555.png]]

Problem: Will man nicht nur einen Ausdruck rausgeben, sondern vorher einen Block an Code ausführen. Aber: Es muss ja ein Wert rausgegeben werden, was Anweisungsblöcke normalerweise nicht tun.

 Lösung: In den Anweisungsblock schreibt man das schlüsselwort `yield` wobei das hinter dem `yield` ausgegeben wird.

Verwendet man `switch` als Ausdruck, *muss* die Fallunterscheidung vollständig sein, d.h. es muss für jede möglichen Wert der Entscheidenden Variable (oben im Bsp `i` ) definiert sein, was der Wert des Ausdrucks ist.
Oft als default verwenden

# Schleifen
Java hat 3 Arten von Schleifen `while`, `do` und `for`.
Alle drei Arten *sind gleich mächtig*, für unterschiedliche Probleme aber oft verschieden gut lesbar.

```java
while (Bedingung) {
	Schleifenrumpf
}
```

> Gefahr der Nichtterminierung, wenn die Bedingung immer erfüllt ist.

Beispielprogramm für Primzahltest:
![[Pasted image 20251020191642.png]]

> Was übelst cursed aussieht und schlechter Stil ist, dass man die Klammern { } hier weglassen kann, solange man nur einzelne Ausdrücke verwenden will. 

Haben nochmal den Mathe--Syntax für Abrunden gemacht: $\lfloor 1.3 \rfloor=1$ und $\lceil 1.3 \rceil=2$


# `do`-Schleife
Schleife, bei der Schleifenrumpf *auf jeden Fall* mindestens einmal ausgeführt wird. (Bei `while` kann der Rumpf auch garnicht ausgeführt werden, wenn die Bedingung vor dem ersten Durchlauf schon falsch ist.)
![[V21 - Anweisungen und Kontrollstrukturen 2025-10-20 19.28.13.excalidraw]]

![[Pasted image 20251020193131.png]]


# `for`-Schleife
```java
for (Initialisierung ; Bedingung ; Fortschreitung) {
	Schleifenrumpf
}
```
![[V21 - Anweisungen und Kontrollstrukturen 2025-10-20 19.39.10.excalidraw]]

Interessant:
Die Initialisierung kann enthalten:
- Eine Variablendeklaration
  ODER:
- Beliebig viele Zuweisungen
```java

for (int x,y=1; x*y < 100;x++,y+=2)
```
Oder:
```java
int x;
int y;

for (x=4,y=10;x<10;x--,y++)

```


> Guter Stil: `for` nur für Zählschleifen verwenden.


# Sprunganweisungen `break` und `continue`

(Es gibt technically auch noch die Sprunganweisung, die bis ganz ans ende des Programms springt:
`System.exit(n)` mit `n` als `int`.
Jede Zahl außer `0` zeigt hier an die Außenwelt einen Fehler an.
)

`break`: beendet die Aktuelle Schleife / Bricht sie ab 
	- bei geschachtelten wird obviously die innerste beendet
	- will man aber nicht die innerste, sondern eine der äußeren Schleifen beenden, geht das mit `labels`.
	  Man kann einzelne Schleifen ebenen mit Doppelpunkten benennen.

```java
aussen: while (...) {
	innen: while(...) {
	   break innen;
	   //vs.
	   break aussen;
	
	}

}
```
![[V21 - Anweisungen und Kontrollstrukturen 2025-10-20 19.57.23.excalidraw]]
	 
`continue` : springt ans Ende des aktuellen Schleifenrumpfs, d.h. gehe weiter zur nächsten Runde dieser Schleife.

