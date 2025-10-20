---
"date:": 2025-10-17
tags:
  - PROGRA
status: rot
Ab Folie: 0
Bis Folie:
---
---

# Datentypen

## Primitve

## Konstruierte



# Ganze Zahlen (`byte`, `short`,`int`,`long`)

$\{ -2^{8n-1} ,\dots,2^{8n-1}-1\}$

wobei:

| `byte`  | 1   | $\{ -128;127 \}$ | 1 Byte |
| ------- | --- | ---------------- | ------ |
| `short` | 2   |                  | 2 Byte |
| `short` | 4   |                  | 4 Byte |
| `long`  | 8   |                  | 8 Byte |
Zahlen werden im *Zweier-Komplement* (s.h. TI Vorlesung) gespeichert:

|     | $2^{2}$ | $2^{1}$ | $2^{0}$ |
| --- | ------- | ------- | ------- |
| 3   | 0       | 1       | 1       |
| 2   | 0       | 1       | 0       |
| 1   | 0       | 0       | 1       |
| 0   | 0       | 0       | 0       |
| -1  | 1       | 1       | 1       |
| -2  | 1       | 0       | 1       |
| -3  | 1       | 0       | 0       |

Stelle die negative Zahl $-z$ dar als: $2^{n}-z$
z.B. $-4 \to 2^{3}-4=4=(100)_{2}$

d.h. : wie aus TI bekannt entscheidet der vorderste Bit über das Vorzeichen:
 $1\to \text{negativ}$
 $0 \to \text{positiv}$

Ebenfalls wie gehabt:
Um von $z$ zu $-z$ zu kommen : Invertiere die Ziffern und addiere $1$

Schön dabei z.b.
$-1+1=0\iff (111)_{2}+(1)_{2}=(0000)_{2}$


> Zur Lesbarkeit, kann man in `int` einfach Unterstriche verwenden (`.` ist im englischen System als Trennung für Kommazahlen gedacht)
> 
> `int 2_147_483_647;` ist beispielsweise die größte `int` $2^{31}-1$

## Überlauf
```java
int x = 2_147_483_647;
int y = 1;

int x+1  -> 0
```

in *jshell*:
```
jshell> 2_147_483_647 + 1  
$2 ==> -2147483648
```

Schlechter Stil: Ausnutzen von Überläufen für Programmiertricks sollte man nicht machen.

## Operationen auf den Ganzen zahlen

`+ - * ` wie gehabt

bei Division `/` : Ganzzahlige Division - alles hinter dem Komma wird einfach weggelassen.
Es wird *nicht* gerundet. : `2/3 -> 0`

`%` ist der Rest der Division

>[!def]
> Operationen auf `byte, short, int` erzeugen *immer* `int`
> ```
> byte a = 1;
> a = a + 1; -> FEHLER! (die Addition erzeugt ein int)
> ```

Werte vom Typ `long` lassen sich durch `L` erzeugen: `1L` ist die Zahl als `long`-Wert

# Gleitkomma-Zahlen
`float` und `double`

Standardmäßig wird alles mit einem Punkt zu einer `double`-Zahl.
Man kann mit `12.3f` aber float erzwingen.

Schreibweisen weil Faulheit:
`0.57 = .57`
`132.0 = 132.`

Schreibweisen mit Exponenten:
`1.2e-23` = $1.2\cdot 10^{-23}$


# Booleans

Datentyp mit Wert `true` oder `false`

Vordefinierte Operatoren mit dem Ergebnis vom Typ Boolean:

 ` == ` Gleichheit 
` != ` Ungleichheit

Größer/Kleiner wie gehabt

Operationen auf Werten vom Typ boolean:
`&&` ; und ; Konjunktion
`||` ; oder ; Disjunktion

`&&` und `||` werden von links nach rechts abgearbeitet.


# `char` - Datentyp für einzelne Zeichen
16 Bit Speicher benötigt
`'a'` `'A'` `1` usw, aber auch spezielle Zeichen wie den "newline": `'\n'
werden mit *einfachen* Anführungszeichen geschrieben


` == ` funktioniert zwischen chars wie gedacht.

`< > <= >=` wird nach der [Unicode](https://de.wikipedia.org/wiki/Unicode)-Nummer der Zeichen entschieden

Bsp. `a` hat als Nummer 97 `b` hat `98` 
d.h. ` 'a' < 'b' ` ergibt `true`

erlaubt Vergleich nach alphabetischer Sortierung
# `string` - Datentyp für Zeichenketten
Der Datenyp `string` ist zwar vordefiniert, *ist aber KEIN PRIMITIVER DATENTYP*.

Werden mit Doppelten Anführungszeichen geschrieben `"Hallo Welt!"`

# "Statisch getypte Sprache"
Java ist eine *statisch getypte Sprache* - d.h. jeder Ausdruck hat einen Typ und Operationen können nur auf Argumente des richtigen Typs angewendet werden.

Typkorrektheit wird *vor* der Laufzeit vom Compiler überprüft ("statisch") -> *Mann kann sich zur Laufzeit also jegliches Typ-Checking sparen.* 

(Zum Vergleich: Dynamisches-Type-Checking zur Laufzeit gibt es u.A. in Javascript oder Python)

# Typkonversion
Manchmal möchte man Werte von einem Typ in einen anderen Typ konvertieren:

`2 + 3.5` verknüpft Typen von `int` und `double`, was *eigentlich* nicht gehen sollte.
Damit es trotzdem klappt, wird vorher `2` in den entsprechenden `double` Wert `2.0` konvertiert.
-> Ergebnis ist dann `5.5` vom Typ double.

Bei welchen weiteren Datentypen funktioniert dies implizit und automatisch: (s.h. Folie 12)
![[Pasted image 20251017155137.png]]

>[!def] Implizite Datentypanpassung
>- vom speziellen in den allgemeinen Typ
>- passiert automatisch, wenn Werte des allgemeineren Datenyps benötigt werden
>- Konversion zu String passiert *nicht* automatisch, sondern nur in bestimmten Funktionen wie `IO.print` oder `+`.

z.B. cursed:
```java
int x = 'a'; -> x=97 weil unicode)
int y = 'a'+1; -> y=98
```

>[!def] Explizite Datentypanpassung (Type Cast)
> - Umwandlung von einem Typ zum anderen wird *explizit* erzwungen
> - Geht auch vom allgemeinen zum Speziellen Typ. (D.h. gegen die Pfeilrichtung)


```java
int x = (int) 2.7; -> x=2

int y = (int) 'a'; -> x=97

```

interessant:
```java
double x = (float)1/2; -> 0.5
weil das float sich nur auf die 1 , dann wird 1.0/2 = 1.0/2.0 = 0.4

aber:
double y = (float)(1/2); -> 0.0 weil (1/2)->int 0 und (float)0 = 0.0

```

```java
(char) ('a'+1) -> 'b'
```