---
date: 2025-10-30
tags:
  - PROGRA
status: rot
Vorlesungsfolien: "[[II15_Arrays.pdf]]"
Skriptfolien:
---
---

Kurzschreibweise für Array-Initialisierung:
`int [] x = {14,2,5};`
erzeugt ein array der Länge 3 (man muss die Länge nicht selbst eingeben -  java macht das automatisch)

geht auch mehrdimensional:
`int [][] x = {{14,2},{5,0},{6,7}}`


## Gleicheit von Arrays.
```java
int [] x = {14,2,5};
int [] y = {14,2,5};
int [] z = x;

x==y // false
x==z //true
```

Es wird nur direkt verglichen, ob im Stack das gleich Steht - dort liegen aber nur verweise auf zwei getrennte Arrays und `false`kommt raus.

> ` == ` vergleicht nur die Referenzen, nicht die Inhalte von Objekten.
> (Bei Primitiven Datentypen ist dies ok - da werden die Werte ja direkt im Stack gespeichert)
> 
> Für Klassen (wie u.A. Strings) implementiert man meist eine .equals(methode)


## String->Array
```java
char [] wort = MeinString.toCharArray();
```

# `main`-Methode mit Argumenten
- man hat entweder kein Argument oder
- ein Argument von Typ `String []`

> Wenn es beide gibt, wird die `main`-Methode mit `String [] args` verwendet.

Man kann dann auch perfekt aus der Konsole die Argumente an sein Java-Programm geben. Man erhält dann in seiner Java-Datei einfach ein array an Strings, das man schön als Argumente verwenden kann.

---

# Sortieralgorithmen
Haben eine selection-sort-Implementierung gemacht.


---
# foreach-Schleife

Durchläuft alle Elemente einer Sammlung.

```java
int [] a = {2,3,3,4,5}
for (int x : a) {
	IO.print(x);
}
```

Man schreibt also:
`for (<datentyp> <VariablenName> : <array>) {x}`

foreach-schleifen sind nur gut, um die Werte in einem Array auszulesen - nicht aber zum schreiben - denn das obige `x` wird einfach eine Kopie des jeweiligen Arrayeintrags. Ändert man dann `x` wird nur die Kopie nicht aber das Array geändert.

---

# Unbenannte Variablen
- Programmierer sollte deutlich machen, wenn eine Variable absichtlich nie wieder verwendet wird.

in java verwendet man dafür den Unterstrich: `_` 
Auf unbenannte Variablen kann nicht zugegriffen werden.
Mehrfache Vorkommen gelten als verschiedene Variablen.