---
tags:
  - PROGRA
status: rot
---
---
Bekannt ist, dass [[Kontrollstrukturen in Java#``switch``-Anweisung und Ausdruck|switch]] über Werte von primitiven Datentypen sowie String anwendbar ist:

```java
void f(int x){
	switch (x){
		case 0,1  -> IO.println("Die Zahl ist 0 oder 1");
		case 13 -> {	
			IO.println("Unglück geschehe");
			IO.println("Komme die Verdammniss über dich");
			}
		default -> IO.println("eine andere Zahl halt");
	}
}
```

----
# Switch mit Type-Patterns
Möglich ist auch ``switch`` über beliebige Klassen-Datentypen zu verwenden. Die Unterscheidung wird jetzt danach gefällt, um welche *Unterklasse* es sich handelt.

> Hier ist meistens ein `default`-case Notwendig, damit eine Fallunterscheidung vollständig wird. Ausnahmen sind Enums und sealed-classes.

Neu dazu kommen:
- Neben ``default`` auch ein ``null``-case, da es sich um Objekte handelt.
- sog. "guared" case-labels: mit ``case <Pattern> when <boolean> {...};`` können weitere Anforderungen an die Eigenschaften eines Objekts gestellt werden

### Syntax:



