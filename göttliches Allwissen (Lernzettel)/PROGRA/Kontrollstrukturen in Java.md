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