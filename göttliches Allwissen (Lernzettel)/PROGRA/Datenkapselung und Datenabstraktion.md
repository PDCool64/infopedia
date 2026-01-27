---
tags:
  - PROGRA
status: rot
---
---

Dies ist ein Verfahren, um bessere Software mit [[OOP Basics in Java|Objektorientierten Verfahren]] zu schreiben.

Datenkapselung als Entwurfsprinzip besagt, dass man zuerst die Schnittstelle entwirft sowie definiert und erst dann die Implementierung.

---
# Grundsätze

>[!def] Datenkapselung
> Schreiben und Lesen von Objektattributen sollte nicht außerhalb der eigenen Klasse erfolgen, sondern *nur* durch bestimmte Methoden, die in der eigenen Klasse festgelegt werden: So genannten **Selektoren**. bzw. `set`-Methoden und `get`-Methoden.

Man verwendet also [[OOP Basics in Java#``public`` vs. ``private`` vs. ``protected``|Zugriffsmodifikatoren]] , insbesondere ``private``, um den Zugriff auf Attribute von außen zu verhindern. 

# Vorteile
- Der Entwickler der Klasse kann selbst entschieden, wie auf Daten zugegriffen wird und wie diese verändert werden dürfen
	- Daten filtern/beschränken: z.B. keine negativen Werte erlauben.
	
- **Die genaue Implementierung ist gekapselt:** Solange die nach außen als *Schnittstellen* fungierenden Selektoren weiterhin das gleiche Verhalten aufweisen, kann die tatsächliche Implementierung ohne Probleme verändert werden: Man muss sich keine Sorgen machen, dass ein Anwender direkt ein Klasseninternes Attribut verwendet hat, das es in einer neuen Implementierung gar nicht mehr gibt.
  
  $\to$ Änderungsfreundlichkeit und Modularität: **Änderungen sind nur auf die eigene Klasse beschränkt**.

---
Daraus resultiert:
# Datenabstraktion und Geheimnissprinzip
>[!def] Datenabstraktion
> Nach außen ist nur eine abstrakte Sicht auf die Klasse auf die Klasse verfügbar. Die interne Implementierung ist für andere Klassen verborgen.

Sowie das Geheimissprinzip (Client-Server Prinzip)
- Anbieter publiziert Schnittstellendokumentation der öffentlich zugänglichen Komponenten ($\hat{=}$ abstrakter Datentyp)
- Kunden interessiert nur die Schnittstelle, aber nicht wie genau die Implementierung intern arbeitet
## Vorteile
- **Verständlichkeit**: (niemand kann/will/muss die Implementierung aller Dependencies kennen, solange sich diese an ihre Schnittstellendokumentation halten)
- Änderbarkeit
- Modularisierung

# Schnittstellendokumentation
Damit die Prinzipien der Datenkapselung, der Datenabstraktion und des Geheimnissprinzips funktionieren, muss eine klare **Schnittstellendokumentation** festgelegt werden.

Diese bestimmt:
- Die **Eingaben**, die eine Methode annimmt. Insbesondere ihre Datentypen als auch ihre inhaltliche Bedeutung sowie erlaubte Werte. 
- Die **Ausgaben**, die eine Methode zurückgibt. Insbesondere ihre Datentypen, aber auch unter welchen Umständen die Methode welche Ausgabe zurückgibt: Was tut diese Methode eigentlich.


## In Java
> Java erzeugt automatisch html-Seiten für die Schnittstellendokumentation von Klassen.

mit `javadoc -d Mein/Ziel/directory Rechteck.java`

(geht auch mit `*.java` für alle Dateien im Ordner)

So ist z.B. auch die Dokumentation on java selbst geschrieben.

Kommentare hinter `/**` , die direkt über Klassen/Methodendeklarationen stehen, werden automatisch erkannt und in den docs eingebettet. Dabei werden einzelne tags mit @ erkannt. z.b. @author (manche werden automatisch beachtet, andere muss man explizit auswählen, wie `javadoc -author` usw.)

Der erste Satz dieses Kommentars wird direkt in die Summary geschrieben, der Rest nur in die Detailübersicht.

wichtiger ist dabei z.B. `@return` mit der man zu jeder öffentlichen, nicht void-Methode angibt was die Methode wann ausgibt.

`@param x` sollte für jeden Eingabeparameter `x` verwendet werden, um die einzelnen Parameter zu beschreiben.