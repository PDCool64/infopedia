---
"date:": 2025-10-16
tags:
  - PROGRA
status: rot
Ab Folie: 0
Bis Folie:
---
---
Java
- Objektorientierte Sprache
- Syntax zu C, C++ ähnlich
- Sammlung standardisierte Bibliotheken für häufige Programmieraufgaben
- wir arbeiten mit *Java 25* - kann einige coole neue Dinge *die wir auch verwenden werden*

## Syntax von Java
*Java Language Specification* (s.h. Oracle Website) besteht aus ewig vielen Grammatikregeln

```java
void main() {
	int x,y;
	y = -1+10202;
	x = 10
	IO.print("Das Resultat ist: ");
	IO.println(x+y);
}
```

> `IO.print();` ist ein schönes neues Java25 Feature.
## Variablendenklaration
`int x;` legt einen Speicherbereich für eine int-Zahl an.
Jeder Speicherbereich hat eine feste Größe, `int` z.B. 32bit.
`x` wird zu einem Verweis auf die Speicheradresse

`x=10` schreibt die Zahl 10 an die Speicheradresse.

Man kann beides auf einmal machen:
`int x = 10;`


Man kann mehrere Variablen des gleichen Typs auf einmal deklarieren, indem man sie mit einem Komma trennt:
`int x,y,z;`

was auch geht:
`int x=10,y,z=5;`

Jeder Datentyp hat einen Standardwert, bei `int` ist dies 0 (sollte man sich aber nicht drauf verlassen)


Seit Java10 kann Java den Typ mancher Variablen selbst inferieren:
`var x=10;`
manchmal ganz nützlich - *Für Anfänger empfiehlt es sich, `var` nicht zu verwenden*.

>[!def]
> Jede Variable *MUSS* vor ihrer Verwendung deklariert werden.



# Programmcode -> Ausführung
Im allgemeinen Fall: Folie 12

Für

