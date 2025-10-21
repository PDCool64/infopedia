---
date: 2025-10-20
tags:
  - TI
status: rot
Vorlesungsfolien: "[[Kapitel 02 - Boolesche Funktionen.pdf]]"
Skriptfolien:
---
---

Für Mittwoch sollte man mal das Übungsblatt durchrechnen. Ist technically nicht pflicht - sonst macht die Vorstellung der Lösungen in der Globalübung wenig Sinn.

---

$f:B^{n}\to B$ heißt "n-Stellig", wenn sie genau $n$ Bools annimmt 

---

Wie viele verschiedene n-Stellige Boolesche Funktionen gibt es?

für n=1 gibt es z.b. nur diese vier Booleschen Funktionen:
![[Pasted image 20251020145131.png]]

für n=2 gibt es schon 16 boolesche Funktionen:
![[Pasted image 20251020145230.png]]
![[Pasted image 20251020145451.png]]

>[!def]
> 
> Es gibt $2^{2^{n}}$ n-stellige boolsche Funktionen

Anstatt sich bei langen Wahrheitstabellen von großes n-stellige Boolsche Funktionen alle Ausgaben zu speichern, 
kann man auch einfach eine Liste der sog. "Einschlägigen Indizes speichern" das sind alle Indexe für die Kombinationen, welche 1en ergeben:

![[V23 - Boolsche Funktionen genauer 2025-10-20 15.00.02.excalidraw]]


 
Als Binärvektorliste (heute eher veraltet). Die "Do Not Care" schreibweisen als _ sind/bleiben aber wichtig

man macht ne tabelle aus den einschlägigen Zeilen und schtreicht dann redundatne infos mit _ 

d.h. die obige Tabelle wäre:
`1_1`
`_11` 

# Darstellung Boolescher Funktionen

## DNF und KNF

> Reminder $+=\vee$ und $\cdot=\wedge$

>[!def] Literal
> 
> Ein Literal ist enteweder eine boolsche Variable oder eine Verneinte Variable d.h. entweder
> $x$ oder $\bar{x}$


# DNF

>[!def]
> 
> Minterm - eine Anzahl von Literalen verknüpft mit UND


Will man die Tabelle einer n-stelligen boolschen Funktion mit Mintermen darstellen,
dann entspricht jede Zeile der Tabelle genau einem Minterm aus n-Literalen

Jede Boolsche Funktion ist eindeutig darstellbar als Summe der Mintermme ihrer einschlägigen Indizes

d.h. die verODERUNG der Minterme

wurde hier viel komplizierter erklärt als es eigentlich ist. Funktioniert auch intuitiv.
Einfacher:
- Jeder Minterme stellt genau einer der einschlägigen Zeilen dar, dh. genau eine der Fälle, in denen die Boolesche Funktion war sein soll. VerODERT man aller dieser erlaubten Kombinationen die zu 1 führen sollen, spiegelt man die Boolsche Form exakt wieder.

>[!def]
> 
> Alle n-stelligen Booleschen Funktionen lassen sich mit den 2-stelligen Funktionen UND und ODER und der 1-stelligen Funktion NICHT darstellen, weil jede Boolesche Funktion als eine KNF (welche nur aus UND, ODER, NICHT)besteht) darstellbar ist..
> 
> Man sagt: Das System $(\wedge,\vee,\neg)$ ist "funktional vollständig"

> Auch das System $(\vee,\neg)$  oder auch das Sytem aus $(\wedge,\neg)$ sind alleine schon funktional vollständig, weil man mit der de-Morganschen regel das jeweils fehlende Symbol herleiten kann: 

> Auch das System NAND ist funktional vollständig

Wie zeigt man sowas: 
	Man nimmt sich ein System von dem man weiß, dass es funktional vollständig ist.
	Schafft man es, alle Operatoren dieses bekannten Systems mit dem zu testenden System herleiten, dann ist das zu testende System ebenfalls funktional vollständig.
	Beim Beweisen geht man aber von der Richtung meist andersherum vor und versucht das bekannte system auf das zu testende zu redzuieren s.h. [[Kapitel 02 - Boolesche Funktionen.pdf#page=25]]

Dann gemacht, dass $(\to,1)$  nicht funktional vollständig sind.
Macht man, indem man für alle Kombinationen zeigt, dass sie $\neg$ nicht darstellen können.
Frage: Muss man zeigen, dass es einen Operator gibt, den man nicht herleiten kann, oder das man keinen darstellen kann, oder dass man nicht alle darstellen kann.




# KNF
>[!def] Maxterm
> 
> Eine Anzahl an Literalen, die alle durch ODER verknüpft sind

Jeder Maxterm ist genau für seinen Index falsch
Jeder Minterm ist genau für seinen Index wahr

$Max_{i}=\overline{min_{i}}$

>[!def]
> 
> Jede Boolsche Funktion ist eindeutig darstellbar als VERUNDUNG ihrer NICHT-einschlägigen Indizes



> Wann verwendet man was: Hat man mehr einschlägige Indizes, ist die DNF kürzer. Hat man mehr *nicht*-einschlägige Indizes ist die KNF kürzer.


---

# Boolsche Funktionen als Schaltungen



Warum auch immer nutzen wir eine cursed Darstellung aus der DIN-Norm für die Logikgatter
Schreibweisen s.h.h. [[Kapitel 02 - Boolesche Funktionen.pdf#page=30]]

![[Pasted image 20251020153849.png]]

Kann dargestellt werden durch:
![[V23 - Boolsche Funktionen genauer 2025-10-20 15.39.01.excalidraw]]

# Als DAG:

DAG = Directed Acyclic Graph
- Directed =  Gerichted
- Acyclic = Keine Zyklen (man kann nicht im Kreis rennen; Man kann nicht endlos lang im Graph rumlaufen sondern landet immer an einem Ende)
- Graph = ein Graph aus der Graphentheorie halt

Haben dann mal am beispiel der Flimmerschaltung gezeigt, warum die Einschränkung auf nicht zyklische Graphen für den Moment sehr sinnvoll ist.


## Warum DAGs: Fehlersuchen leicht gemacht
- Hat man eine Boolsche Funktion in hardware realisiert und hat einen Fehler, (z.B. Kabel gerissen) helfen DAGs diese zu finden.

Die Liste der Funktionen auf Folie 41 besagt der Index, welcher Draht gerissen ist.

Rechenregel: $xyz+x \bar{y}z=xz$

Wir kennen dann also das Verhalten für jeden der möglichen Fehler.
Dann testet man und sieht, welches der Verhalten auftritt.

 Doof ist leider, dass es verschiedene Fehler geben kann, die das gleiche Verhalten hervorrufen
 Innerhalb einer solchen "Fehlerklasse" muss man dann wirklich die Drähte selbst inspizieren.

## Noch schöner mit XOR: 
Tabelle zeigt ein XOR zwischen Fehlerklasse und erwartetem verhalten:
D.h. wenn in der Tabelle eine 1 steht, dann weiß man dass die Fehlerklasse bei dieser Eingabekombination sich von der erwarteten Ausgabe unterscheiden würde.



![[Pasted image 20251020155655.png]]

Mann kann damit sehr schön testen und schnell herausfinden, in welcher Fehlerklasse man ist.

