---
"date:": 2025-10-17
tags:
  - PROGRA
status: rot
Ab Folie: 24
Bis Folie: 27
---
---

# Methoden bei verschiedenen Datentypen
aka. Polymorphismus
```
2 + 3 -> 5
"halo" + "lo" -> "hallo"
"hal" + 2 -> "hal2"

interessanter:
"hal" + 2 + 3 -> "hal23"

"hal" + (2+3) -> "hal5"

2+3+"hal" -> "5hal"

```

Möglich ist also:
```
IO.println("Das Resultat ist" + (x+y) );
```
# jshell
Read-Evaluate-Print Loop
(schön im terminal, sollte bei java meist dabei sein. unter KDE nicht)
Damit kann man schön mal testen, was bei einem Ausdruck rauskommt.

Praktischer Befehl: Man kann sich die Datentypen anzeigen lassen:
`/set feedback verbose`
(will man wieder zurück dann `/set feedback normal`)


# Bedingter Ausdruck

In einer Zeile - je nach Wahrheitswert eines bools - eine Variable verschieden zuweisen:
`a = x >= 0 ? x : -x`
d.h.
`variablenName = BoolscherAusdruck ? WertWennWahr : WertWennFalsch`

z.B. :
```
jshell> /set feedback verbose  
|  Feedback mode: verbose  
  
jshell> 1 + 3  
$3 ==> 4  
|  created scratch variable $3 : int
```

# Styleguide:
Mit Kleinbuchstaben anfangen:
- Variablen
- Methoden
Mit Großbuchstaben beginnen:
- Dateien
- Klassen


# Infix-Operatoren
stehen *zwischen* zwei Ausdrücken

`+ - * ^` usw 

# Präfix-Operatoren
stehen *vor* einem Ausdruck
`+ - ` 
z.b. `int n = -2;`


---

