---
tags:
  - PROGRA
status: rot
---
---

# Allgemeines zu Methodenaufruf und Parameterübergabe:

>[!def] formale vs. aktuelle Parameter
> **Formale Parameter:** Die in der Methodendeklaration mit `typ name , typ name , ... `deklarierten Argumente die die Methode annimmt:
> 
> **Aktuelle Parameter:** Das was man beim Methodenaufruf an Werten/Ausdrücken an die Methode übergibt.

![[Call-by-value vs. call-by-reference 2025-11-14 17.49.31.excalidraw|600]]


## Methodenaufruf
- Aktueller Parameter wird ausgewertet (man kann auch Ausdrücke mit Rechnungen in die Klammern schreiben)

- **Parameterübergabe: Werte der aktuellen Parameter werden in die formellen Parameter kopiert.**

- Ausführung des Methodenrumpfs
- Beendigung der Methode bei `return` 
- Ergebnis wird an die Aufrufende Stelle zurück geliefert.

## Parameterübergabe
Verschiedene Arten in der Informatik
- call by value
- call by reference
- call by name (vor allem bei funktionalen Sprachen)


# Call by Value
- Es wird der bloße Wert des aktuellen Parameters in den formellen Parameter kopiert.
- *Änderung des formalen Parameters der Methode bewirkt **keine** Änderung des aktuellen Parameters*

# Call by Reference
- Formaler Parameter der Methode wird ein Verweis/Referenz/Zeiger auf den aktuellen Parameter. Beide Variablen werden wirklich "verknüpft"
- *Jede Änderung des formalen Parameters bewirkt eine Veränderung des aktuellen Parameters.*

---
# In Java
Java verwendet immer [[#Call by Value]] - auch wenn sich dieses sehr oft ähnlich wie Call-by-Reference verhält.

- Bei Primitiven Datentypen verhält sich call by value ganz wie erwartet: Bei ihnen wird auf dem Stack/Lauftzeitkeller direkt ihr Wert gespeichert. Beim Kopieren dieses in den formalen Parameter entsteht also eine komplett unabhängige Kopie des Wertes.

- Bei nicht primitiven Datentypen (Arrays, Objekte, usw.) verhält sich Java's call by value grob wie call by Reference. Dies liegt daran, dass bei Nichtprimitiven Datentypen auf dem Stack bloß ein Verweis auf das eigentliche Objekt auf dem Heap liegt. Diese wird call-by-value artig in den Formalen Parameter kopiert und beide Variablen zeigen nun auf ein und das selbe Objekt: Seiteneffekte sind möglich. Trotzdem ist es kein *echtes* call by-value: überschreibt man z.B. den formalen Parameter durch ``new`` mit einen neuen Objekt, wird nur den im formalen Parameter gespeicherte Verweis überschrieben und das eigentliche Objekt bleibt unberührt.

> Java kopiert immer den Wert der für den aktuellen Parameter auf dem Stack liegt in den aktuellen Parameter - Wenn auf dem Stack aber nur ein Verweis und kein direkter Wert liegt, fühlt es sich ähnlich wie call by reference an.