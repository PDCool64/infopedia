---
date: 2025-11-03
tags:
  - PROGRA
status: rot
Vorlesungsfolien: "[[II22_Methoden.pdf]]"
Skriptfolien:
---
---
Programme sind jetzt abfolgen von Klassendeklarationen

Bei Methodendeklarationen gibt man den Typ an, den die Methode zurück gibt. Inbesondere sind auch selbst geschriebene Klassen erlaubt. 
Methoden können jetzt Eingabeargumente haben.

wenn es keine Eigenschaft von einem Objekt seien soll, d.h. nicht von einer Objektinstanz abhängt, schreibt man `static`

Jede Datei darf höchstens eine `public` Klasse enthalten und die Datei muss genau so heißen wie die Klasse.

Seit Java 25 neu: Compact Source File
- Compact Source File = Datei ohne Klassendeklaration
- Dadurch wird implizit auch eine Klasse deklariert, nur man muss sie nicht hinschreiben.
- Name der Klasse wird automatisch generiert, man kann sie aber nicht wirklich aufrufen
- Man Kann keine neuen Objekte dieser Klasse erzeugen
- Datei muss dann eine `main`-Methode enthalten.

`java Dateiname` führt die `main` Methode der public-Klasse der Datei aus.

man sollte eigentlich immer `static` vor `main` schreiben, weil es fast nie von einem Objekt abhängt. Wenn man kein `static` schreibt, erzeugt java automatisch eine Instanz der Klasse und ruft `main` für diese Instanz auf. Ist aber wieder ein autogeneriertes Objekt das man nicht selbst verwenden kann.



---
# Realisierung im Speicher
Variablen von Klassendatentypen enthalten als Wert nur eine Adresse für eine Stelle im Heap (Referenz).

Alles zum Thema Seiteneffekte, Garbage Collector etc. ist wie bei Arrays.

> Bluejay soll eine für Anfänger ganz nette Entwicklungsumgebung sein.(Matthias sagt aber, es sei der Größte Schwachsinn `┻━┻︵ \(°□°)/ ︵ ┻━┻` ) Hat auch so ein paar nette Features wie eine eingebaute j-shell Äquivalent und auf für OOP eine "Workbench" in der man einzelne Objekte zur Laufzeit anschauen/untersuchen kann.


---

# Methodenaufrufe und Parameterübergabe.


Methode = Unterprogramm, d.h. parametrisierter Anweisungsblock mit Namen. Er kann über seinen Namen aufgerufen werden. Hinterher wird der Code an der Aufrufenden Stelle fortgesetzt.

>[!def] formale vs. aktuelle Parameter
> formale parameter: Die in der Methodendeklaration mit `typ name , typ name , ... `deklarierten Argumente die die Methode annimmt:
> 
> aktuelle Parameter: Das was man beim Methodenaufruf an Werten/Ausdrücken an die Methode übergibt.
> 

![[V51 - Was machen eigentlich Java-Klassen 2025-11-03 19.09.05.excalidraw]]

## Methodenaufruf
- Aktueller Parameter wird ausgewertet (mann kann auch Ausdrücke mit Rechnungen in die Klammern schreiben)
- Parameterübergabe: Werte der aktuellen Parameter werden in die formellen Parameter kopiert.
- Ausführung des Methodenrumpfs
- Beendigung der Methode bei `return` 
- Ergebnis wird an die Aufrufende Stelle zurückgeliefert.

## Parameterübergabe
Verschiedene Arten in der Informatik
- call by value
- call by reference
- call by name (vor allem bei funktionalen Sprachen)

### Call by value
wird bei Primitiven Datentypen verwendet.
- aktueller Parameter (im Methodenaufruf) wird ausgewertet
- Wert des aktuellen Parameters wird in den formalen Parameter der Methode kopiert. - wir rufen die Methode also direkt mit dem Wert des aktuellen Parameters.
- Änderung des formalen Parameters der Methode bewirkt *keine* Änderung des aktuellen Parameters.

## Call by Reference
- Aktueller Parameter ist Variable (z.B. `s`)
- Formaler Parameter der Methode wird mit Verweis/Referenz/Zeiger auf den aktuellen Parameter
- Jede Änderung des formalen Parameters verändert ebenso den Wert des aktuellen Parameters. (Weil beide auf ein und die selbe Speicheradresse zeigen)
- In vielen Sprachen kann man sich selbst entscheiden, ob man call-by-value oder call-by-reference haben will. In Java geht dies nichts. Man kann aber eine Art call-by-reference in Java simulieren, nämlich bei Methoden deren Parameter keinen primitiven Datentyp haben. Denn hier wird mit "call by value" auch nur der "value" aus dem heap kopiert, bei dem es sich hier aber um einen Verweis/eine Referenz handelt.
  
  Da Objekte (und Arrays) als Referenzen gespeichert werden, bewirkt eine Änderung über den formalen Parameter der Methode eine Änderung, die auch über den aktuellen Parameter sichtbar ist. Es sieht ziemlich nach call by reference aus - ist es aber nicht das gleiche. z..b in diesem Beispiel:
![[Pasted image 20251103195246.png]]

Es wird nur die Adresse von s auch in r kopiert - die Objekte werden aber nicht wirklich mit einander "identifiziert". Wenn dem formalen Parameter r hier ein neues Objekt zugewiesen wird, hat dies keine Auswirkungen auf den aktuellen Parameter.

> Java kopiert immer den Wert des aktuellen Parameters in den formalen Parameter. Der Wert da da drin steht kann aber eine Referenz sein, was einer eingeschränkten Form von call-by-reference entspricht.

Informationen von der aufrufenden Stelle an die Methode solle man immer über Parameter übergeben - nicht etwa mit globalen Variablen oder so.

Negativbeispiel: Schlechter Stil, weil Datenfluss unklar.
```java
public static in x;

public static void f(...) {
	x=x+1
	}
public static void main() {
	x
	...
	f()
	...
	X
}
```

---
# Laufzeitkeller / Stack
Speicherverwaltung bei Blöcken von Anweisungen.
Jedem Block entspricht einem Speicherbereich (frame) auf dem Laufzeitkeller / runtime stack, in dem die Werte der Variablen des Blocks gespeichert sind.

Beim Eintritt in einen neuen Block wird der dazugehörige Speicherbereich oben(im Sinne der Wachstumsrichtung, auf den Folien wachsen die Teile nach unten) auf dem Laufzeitkeller angelegt (allocate).

Der zuletzt angelegte Speicherbereich wird als erstes wieder gelöscht, nämlich genau dann, wenn man aus dem Block wieder herausgeht. (Last-In-First-Out)

Variable ist zugreifbar in dem Block, in dem sie deklariert wurde und auch in den Unterblöcken.

In Java ist es *nicht* erlaubt, in Unterblöcken Variablen zu deklarieren, die in den oberen Blöcken schon existieren.

## Laufzeitkeller bei Methoden
- Gleiches Prinzip: Methodenaufruf ist auch ein Block
- Für jeden Methodenaufruf wir auf dem Laufzeitkeller ein neuer Speicherbereich angelegt. (u.A. für die formalen Parameter)
- Beim Aufruf der Methode kommt der neue Speicherbereich oben auf den Keller.
- Die Variablen in der Methoden dürfen aber genauso heißen, wie Variablen im aufrufenden Block.
- Aus der Methode kann man nicht auf die Variablen im aufrufenden Block zugreifen.




---

## Prozedur vs. Funktion
- Man nennt Methoden mit Rückgabetyp `void` oft Prozedur.
  Hier ist kein `return` notwendig. Stattdessen wird `return` einfach zum vorzeitigen Abbrechen verwendet.
- Man nennt Methoden mit Rückgabetypen meist Prozeduren.
  die haben dann immer ein `return` 

> Will man mehrere verschiedene Datentypen ausgeben, gibt es dafür später "Records" als kleine Wrapper-Klassen in denen man gemischte Typen verpacken kann. Bis dato muss man sich halt selbst eine Klasse schreiben, die als Verpackung dient.

### Warum Prozeduren
- Ausgaben (z.B. `IO.println()`)
- Seiteneffekte (z.B. Sortier-Methode)