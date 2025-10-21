---
date: 2025-10-21
tags:
  - TI
status: rot
Vorlesungsfolien: "[[Kapitel 02 - Boolesche Funktionen.pdf#page=47]]"
Skriptfolien:
---
---
# Studentische Initiative: "enactus"

Studentischer Startupverein. Wollen Nachhaltige, gesellschaftlich verträgliche Startups machen.

Sind in 36 Ländern unterwegs, haben Firmen als Partner

viele soziale Events

---

# Kofaktoren

Eigentlich geht es nur darum, dass man eine der Eingaben auf einen festen Wert 0/1 setzt.
Bsp:
	$f(x_{1},x_{0})=x_{1}\wedge x_{0}$
	
	$f(x_{1}/ 1)=1\wedge x_{0}=x_{0}$
	$f(x_{1}/ 0)=0\wedge x_{0}=0$

## Baumdarstellung
Wenn man die nicht bis zu blättern durchzieht, kann man sich dabei diesen tollen theoretischen Hintergrund geben:
Binärer Entscheidungsbaum, bei dem man sich jeweils entscheidet ob man die momentane Eingabe variablen auf 1 oder 0 festsetzt. Man bekommt für jede Option dann eine neue Boolesche Funktion in der dieser Kofaktor gewählt wurde.

Zieht man es durch, bis man *alle* Variablen durch knoten / Ebenen im Baum festgesetzt hat, dann kommen als Blätter boolesche Funktionen raus, die immer die gleiche Ausgabe geben d.h. unten stehen auf Folie [[Kapitel 02 - Boolesche Funktionen.pdf#page=48]] nur noch 0 / 1.

## OBDD
anstatt aus einer Booleschen Funktion nach dem obigen schema [[#Baumdarstellung]] einem Baum zu machen, kann man oben auch irgendeinen DAG hinmalen und hat dadurch eine neue boolesche Funktion definiert.


### Beispiel:
![[Pasted image 20251021190114.png|200]]

Kodiert die Funktion:

| x2  | x1  | x0  | f   |
| --- | --- | --- | --- |
| 1   | _   | 1   | 1   |
| 0   | 1   | 1   | 1   |
bzw. 
$f=x_{2}x_{0}+ \overline{x_{2}}x_{1}x_{0}$

als DNF:
$f:\bar{x_{2}}x_{1}x_{0}+x_{2}x_{1}x_{0}+x_{2}\bar{x_{1}}x_{0}$

als KNF:

| x2  | x1  | x0  | f   |
| --- | --- | --- | --- |
| 1   | _   | 0   | 0   |
| 0   | 1   | 0   | 0   |
| 0   | 0   | __  | 0   |
$f=()()()$

### Beispiel: Schwellenwertfunktion
Die Funktion besagt, ob mindestens zwei der Eingaben gleich 1 sein.
In einer Tabelle / DNF / KNF wäre dies recht mühselig/lang.

### Beispiel: Ungerade-Paritäts-Funktion
ist eine gerade oder eine ungerade Anzahl an eingaben 1 ?


> in einem OBDD sollte man jede Variable nur einmal abfragen. 
> In welcher Reihenfolge man die Variablen abfragt (d.h. welche "Variablenordnung") man wählt ist wichtig, aber es *gibt keinen effizienten Algorithmus eine optimale Variablenordnung zu finden* (s.h. [[Kapitel 02 - Boolesche Funktionen.pdf#page=53]])

---

# Gray-Code

- Generieungsverfahren zur *robusten* Übertragung (glaube, es geht hier in Richtung Parität) - Die Werte hier werden aber *parallel* übertragen. Es gibt mehrere Kabel oder in der Realität mehrere Adern in einem Kabel.


![[V24 - Kofaktoren 2025-10-21 19.13.02.excalidraw]]

Wichtige Eigenschaft:
	Die Darstellung zweier benachbarten Zahlen unterscheidet sich nur um $1$Bit

Wenn ichs verstanden habe, wird dadurch die Auswirkung eines Flip-Fehlers vom Außmaß reduziert, weil ähnlich große Zahlen immer ähnliche Binärdarstellung haben.
Bei normalem Binär wäre dies nicht so:
7 = 0111
8 = 1000

# Karnaug-Diagramme
> Ausgesprochen "Karnooh"

Ist eigentlich nur eine Tabelle, bei der die Werte der Eingangsvariablen auf den Achsen aufgetragen sind,
während die Werte in der Tabelle die aus der Kombination von Zeile und Spalte entstehende Wert der booleschen Funktion ist.
![[Pasted image 20251021192438.png]]

sind später für die Vereinfachung von DNF/KNF sehr chillig


Bei mehr als Zwei Variablen, gliedert man die Variablen zu 2bit zusammen und nimmt diese als Indizes für die Spalten/Reihen: 
![[Pasted image 20251021192454.png]]
> MAN MACHT DIE REIHENFOLGE DIESER 2BIT PAARE ABER IRGENDWIE NACH GRAY-CODE

s.h. bei der [[V30 - Vereinfachung Boolescher Funktionen]] und auch PXL foto
# TL:DR

Darstellung von Booleschen Funktionen
- KNF
- DNF
- DAGs
- OBDDs
- Karnaug-Diagramme

Gray-Code:Generierungsverfahren zur robusten Übertragung.
(hat auch was mit GrayCode zutun)


