---
tags:
  - PROGRA
status: rot
---
---
## Vokabular
- **Anweisung**: Übergang von einem Programmzustand zum nächsten
- **Programmzustand**: Daten im Speicher + Befehlszähler(position im Programm)
- **Kontrollfluss**: Reihenfolge, in der die Operationen des Programms abgearbeitet werden.
- **Datenfluss**: Übergabe der Daten von einer Operation an eine andere Operation.


---

# ``if``-Anweisung

```java
if (<BoolescherAusdruck>) {
	doSomething();
	doSomethingDifferent();
} else {
	doAnotherThing();
}
```


Dabei für die booleschen Ausdrücke wichtig:
- ``&&`` = oder
- `||` = und

## Ternärer Operator
Für kleine Entscheidungen welcher Wert zugewiesen werden soll, gibt es auch eine inline-Schreibweise:

``` java
int max = (a<b)? a : b;

```
gelesen:
``` java
int max = <BoolescherAusdruck> ? <WertWennWar> : <WertWenNFalsch> ;

```

Hier dürfen aber explizit nur einzelne Ausdrücke verwendet werden - keine ganzen Blöcke

---
# ``switch``-Anweisung und Ausdruck
Für größere Fallunterscheidung zwischen vielen Fällen, die vom Wert eines Ausdrucks abhängt. - kann sowohl als Anweisung verwendet werden.

## Anweisung
```java
int i = 3;

switch (i) {
	case 0,1,2,3,4 -> IO.printlin("i ist kleiner als 5");
	case 5 -> {
		IO.println("Das ist die Zahl");
		IO.println("Die Zahl ist gleich 5");
	}
	default -> IO.println ("i ist groesser als 5");
}
```

## Ausdruck

```java

int = 3;

String ausgabe = switch(i) {
	case 0,1,2,3,4 -> {
		doSomething();
		yield "die Zahl "+i+" ist kleiner als 5";
	}
	case 5 -> "die Zahl ist genau 5";
	default -> "die Zahl ist groesser als 5"

}

```
Will man beim switch-*Ausdruck* Codeblöcke ausführen, muss trotzdem ein Wert zurückgegeben werden. Dieser wird hinter ``yield`` geschrieben.

---
# ``while`` Schleife

```java
boolean notDone = true;  
String eingabe;  
while (notDone) {  
  
    IO.println("moin");  
  
    eingabe = IO.readln("weiter? :" );  
    if (eingabe.equals("stop")) {  
        notDone = false;  
    }  
  
}
```

Je nach Bedingung kann es passieren, das der Schleifenrumpf nie ausgeführt wird, 
z.b.
```java
while (false) {
	IO.println("moin");
}
```

# ``do`` Schleifen
Hier wird der Schleifenrumpf immer mindestens einmal ausgeführt. - die Bedingung wird sozusagen nach dem Durchlaufen des Rumpfes und überprüft - beim ersten mal also nicht.

```java
do {
	something();
	x = 10;

} while (Bedingung);

```

# ``for``-Schleifen
Am besten für Zählschleifen geeignet.

interessant: die Initialisierung kann enthalten : 
	eine Variablendeklaration
	ODER
	Beliebig viele Zuweisungen.

```java

for (int i = 1;i<=100;i++) {
	IO.println(i*i);
}
```

auch gültig:
```java
int x,y;  
  
for (x=4,y=10 ; x<20 && y<100 ; x++ , y*=2) {  
    IO.println(x+y);  
}

//Ausagabe:
//14
//25
//46
//87
```

---
# Sprunganweisungen

``break`` bricht die gesamte Schleife ab und springt ans Ende

``continue`` überspringt den Rest des momentanen Schleifendurchlaufs und macht mit dem nächsten Durchlauf weiter.

Welche verschachtelte Schleife ist gemeint?
- ``break`` und ``continue`` beziehen sich immer auf die Schleifeneben auf der sie selbst stehen
- mit labels kann man schleifen benennen und gezielt bestimmte Ebenen ansteuern:
  ![[Kontrollstrukturen in Java 2025-10-28 10.53.53.excalidraw]]
