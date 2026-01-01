---
tags:
status: rot
---
---

# Implizite Datentypanpassung
Automatische Umwandlung vom speziellen zum allgemeinen Typ.
Passiert implizit/automatisch, wenn Werte des allgemeineren Datentyps benötigt werden.

Die Konversion findet *ausschließlich* entlang dieser Pfeile -und auch nur in Pfeilrichtung- statt.




![[Pasted image 20251017155137.png]]

Zu ``String`` wird *meistens* nicht automatisch konvertiert, wichtige Ausnahmen sind aber ``IO.println()`` und insbesondere ``+``.



>[!wip]
> 
> Literale - d.h. Ausdrücke die feststehend sind und keine Variablen enthalten wie z.b. ``102``- werden manchmal auch implizit *gegen* Pfeilrichtung verkleinert, wenn der Wert im Zieltyp darstellbar ist !
> z.b. ist `short x = 10` ok, obwohl `10` ein `int` Literal ist.
> Hingegen ist das hier nicht erlaubt:
> `int x = 10;`
> `short y = x;` $\to$ incompatible-types-Fehler.
> 
> Ebenfalls nicht ok ist aber auch:
> `short x = 40000` $\to$ Error: integer number to large
> 
> Möglich sind aber Dinge wie:
> `short x = 'a'` weil `char 'a'` implizit zu `int 97` wird und die "kleine" int dann implizit zu `short 97` werden kann.
## Beispiele:

#### Möglich:

| Code               | Ergebnis                                                                                                  |
| ------------------ | --------------------------------------------------------------------------------------------------------- |
| ``float x = 1``    | die ``int 1`` wird implizit zum ``float 1.0`` konvertiert                                                 |
| ``double x = 'a'`` | der ``char`` wird nach [ASCII-Tabelle](https://www.torsten-horn.de/techdocs/ascii.htm) zu ``double 97.0`` |
#### Fehler:

| Code                | Ergebnis                                                                       |
| ------------------- | ------------------------------------------------------------------------------ |
| ``int x = 10.0``    | der ``double`` wert ``10.0`` kann nicht implizit zu ``int`` konvertiert werden |
| ``String x = true`` | der ``bolean`` x wird nicht automatisch zu einem ``String`` konvertiert        |



---
# Explizite Datentypanpassung
Umwandlung von einem Typ zum anderen wir explizit *erzwungen*.
Geht auch von allgemeinen um speziellen Typ - es kann dabei aber häufig Information verloren gehen! (Nachkommastellen, führende Bits)

Explizite Datentypanpassung wird durchgeführt, indem man den gewünschten Datentyp in Klammern angibt.


| Code                       | Ausgabe        | Funktion                                                                                                                                                    |
| -------------------------- | -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ``int x = (int) 2.7``      | ``int 2``      | Die Nachkomastellen werden abgeschnitten.<br>Es wird NICHT gerundet                                                                                         |
| ``int x = (int) -3.9``     | ``int -3``     |                                                                                                                                                             |
| ``double x = (float)1/2``  | ``double 0.5`` | Das ``(float)`` wird zuerst angewendet, und dann die ``float 1`` durch die ``int 2`` dividiert, wobei ``float 0.5`` entsteht.                               |
| ``double x =(float)(1/2)`` | ``double 0.0`` | Es wird zuerst eine Division auf ``ìnt`` durchgeführt, die ``0`` ergibt und erst dann zu ``float`` konvertiert                                              |
| ``byte x = (byte) 130``    | `byte -126`    | die Führenden Bits werden einfach abgeschnitten.<br>Der Bit von $2^7=128$ der ``int 130`` steht plötzlich<br>ganz vorn und bestimmt als MSB das Vorzeichen. |
| ``int x = (int) 143L``     | ``int 143``    | Wäre eine als ``int`` nicht darstellbare Zahl gewählt worden, <br>wäre diese abgeschnitten worden.                                                          |
| ``char x = (char) 97.3``   | `char 'a'``    | der ``double 97.3`` wird über ``int`` und die  [ASCII-Tabelle](https://www.torsten-horn.de/techdocs/ascii.htm)zum `char` konvertiert.                       |
| ``char x = (char)('a'+1)`` | ``char 'b'``   | In der Klammer wird implizit der ``char 'a'`` zu `int 97`.<br>Die `int 98` wird wieder zum ``char 'b'``                                                     |


---

>[!def] Polymorphismus von Operationen
>Eine Operation (Methode, Funktion, ...) kann auf Argumente *verschiedender* Typen angewendet werden

Einfaches Beispiel in Java ist ``IO.print()``, welches verschiedenste Eingaben annimmt und für die Ausgabe alle zu Strings konvertiert.

Interessanter -und fehleranfälliger sind aber Rechenoperationen:

## Addition und Konkatenation: `+`


> Die hier weiter unten stehenden Regeln brechen die weiter oben stehenden Regeln. Aber auch nur so grob - habe die ganzen Hierarchien und Compiler-Shenanigans nicht bis ins Detail durchgetestet. Wenn's drauf ankommt lieber die [Java Language Specification](https://docs.oracle.com/javase/specs/jls/se25/html/index.html) durchforsten oder ne KI fragen.


1. Werden zwei Ausdrücke, deren Typ beide zu  ``byte,short,int`` gehören addiert, entsteht immer eine ``int`` als Ausgabe:
   ```java
   short a = 10;
   short b = 20;
   short x = a+b; -> FEHLER: Incompatible types:
                             possible lossy conversion from int to short
   ```
   2. Sobald ``long`` dabei ist, ist die Ausgabe wieder ``long``
         ```java
   long a = 10;
   byte b = 20;
   int x = a+b; -> FEHLER: Incompatible types:
                           possible lossy conversion from long to int
   ```
3. `char` kann zu ``int`` (und von da aus weiter) werden
   ```java
   char a = 'a';
   byte b = 20;
   int x = a+b; -> x=117
   ```
   4. Sobald ``float`` dabei ist, ist die Ausgabe wieder ``float``
```java
   int a = 10;
   float b = 20.4f;
   int x = a+b;  -> FEHLER: Incompatible types:
                           possible lossy conversion from float to int
   ```
5. Sobald ``double`` dabei ist, ist die Ausgabe wieder ``double``
```java
   int a = 10;
   double b = 20.4;
   float x = a+b;  -> FEHLER: Incompatible types:
                           possible lossy conversion from double to float
   ```
   6. Sobald ein ``String`` dabei ist, ist die Ausgabe wieder ein ``String``. Es werden die Zeichen von links nach rechts an einander gehängt:
```java
   String a = "hal"+"lo"    ->    "hallo"
   String a = "hal"+2       ->    "hal2"
   String a = "hal"+2+3     ->    "hall23"
   String a = "hal"+(2+3)   ->    "hal5"
   String a = "hal"+(2.0+3) ->    "hal5.0"
   String a = 2+3+"hal"     ->   "5hal"
   String a = 2.0+3+"hallo" -> "5.0hallo"
   ```
