---
tags:
  - PROGRA
status: rot
---
---

In Java gibt es zwei Speicherbereich: den **Stack** und den **Heap**

Jede Variable hat eine Speicherzelle auf dem **Stack**, was genau dort liegt hängt aber vom Datentyp ab
- [[Datentypen in Java|Primitive Datentypen]] speichern ihre *Werte* direkt auf dem Stack
- Alle anderen Datentypen speichern nur *Verweise/Referenzen/Speicheradressen* zu Stellen auf dem **Heap** an dem die eigentlichen Inhalte gespeichert werden.
  Dies sind z.B. Arrays und Objekte von Klassen.

> Wichtig: ` == ` vergleicht einfach die Werte auf dem Stack. Bei Primitiven Variablen funktioniert das auch vom Inhalt her - Bei nicht-primitiven wird hier nur verglichen, ob beide Variablen auf die gleiche Speicheradresse zeigen und *nicht* ob zwei verschiedene Objekte in ihren Eigenschaften übereinstimmen.

---
# Konsequenz: Seiteneffekte möglich

## Zuweisung von Wertvariablen:
```java
int x = 2;
int y = x;

y = 8;

IO.println(x); // -> x=2 und bleibt unverändert
```
$\to$ keine Seiteneffekte, Primitive Variablen bleiben unberührt.
## Zuweisung von Referenzvariablen
![[Pasted image 20251027195514.png]]![[Pasted image 20251027195525.png]]
Es wird nach dem Gleichen Schema einfach der Wert der bei x im Stack steht in die Speicherzelle von y kopiert. Da x aber ein array ist, liegt dort nur ein Verweis. y und x zeigen somit auf das gleiche Array.

 $\to$ Zuweisungen bei Referenzvariablen erstellen *keine* Kopien der Werte sondern duplizieren nur Verweise auf ein un den selben Datensatz im Speicher - Es entstehen also Seiteneffekte.

Ebenso muss auch bei Methodenaufrufen beachtet werden: Durch [[Call-by-value vs. call-by-reference]] können auch bei Methoden Seiteneffekte hervorgerufen werden.


---

# Blöcke / Abschnitte im Code und auf dem Stack
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