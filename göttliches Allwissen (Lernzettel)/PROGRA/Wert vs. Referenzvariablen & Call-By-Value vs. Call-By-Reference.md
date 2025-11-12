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