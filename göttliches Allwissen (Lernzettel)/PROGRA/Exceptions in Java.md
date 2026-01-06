---
tags:
  - PROGRA
status: rot
---
---

Exceptions treten auf wenn *zur Laufzeit* semantische Restriktionen nicht erfüllt werden.

# Klassifizierung
![[Pasted image 20260106161036.png]]

**Error**: Fehler, von dem sich das Programm normalerweise erholen kann. Müssen nicht gefangen werden.

**Exceptions**: Schwerwiegender - werden sie nicht gefangen stürzen das Programm ab.
- *RuntimeExceptions*: sehr oft auftretende Exceptions - müssen *nicht* gefangen werden. Führen trotzdem zum Programmabsturz falls man sie nicht fängt.
- Alle anderen Exceptions (die keine U-Klassen von Exception, aber nicht von RuntimeException sind), müssen gefangen werden.
   Sie heißen "*checked exceptions*".  Kann eine checked exception entstehen und wird nicht gefangen, beschwert sich schon der Compiler.

# Syntax: ``try - catch - finally``

Im ``try`` steht normaler Code, bei dem eine Exception auftreten kann.

Im ``catch`` stehen verschiedene *Patterns* die versuchen auftretende Fehler zu fangen.
	Die einzelnen Patterns werden von oben nach unten abgearbeitet und die erste passende verwendet. Sie *müssen* (wie bei ``switch`` ) von speziell->allgemein sortiert sein basierende auf den Unter->Oberklassen der Exception-Klassen
	.
Der `finally` Block wird anschließend *immer* ausgeführt.
	Egal ob Fehler aufgetreten oder nicht; Egal ob Fehler gefangen oder nicht.
