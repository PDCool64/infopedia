---
"date:": 2025-10-16
tags:
  - PROGRA
status: rot
Ab Folie: 33
Bis Folie: 37
---
---

# EBNF : Kurzschreibweise für Kontextfreie Grammatiken

Aus $A\to Y$ wird $A=y$


Man kann Alternativen ausdrücken:
aus:
  $A\to y_{1}$
  $A\to y_{2}$
  ...
  $A\to y_{n}$

wird:
$A=(y_{1}\mid y_{2} \mid \dots \mid y_{n})$
wobei $\mid$ als "oder gelesen wird"


Mann kann optionale Dinge schreiben: etwas in eckigen klammern *kann* kommen, muss aber nicht:
 Aus 
 $A\to xz$
 $A\to xyz$
 
 wird:
$A=x[y]z$ 

Mann kann schreiben, dass etwas beliebig oft kommen kann:
Aus 
$A\to xA$ 
$A\to y$ 
wird
$A=\{ x \}y$


### Beispiel: Hund Katze EBNF

Satz = `Sub Präd Obj`
Subj =`Art Attr Subst`
Artikel = `[("der"|"die"|"das)]`
Attribut = `{Adjektiv}`
Adjektiv = `"kleine"|"bissige"|"große"`
Subst = `"Hund"|"Katze"`
Präd = `"jagt"`
Obj = `Art Attr Subst`


(Auch bei EBNF kommt man nicht immer mit einer Zeile pro Nichtterminal aus (Keine Ahnung ob dies nur auf Lesbarkeit oder auf Notwendigkeit gemeint war))

# Syntaxdiagramme
-  für jedes Nichtterminal ein Syntaxdiagramm
- Die Pfeile geben an, welche Wörter aus dem Nichtterminal hergeleitet werden können
- Syntaxdiagramme können auch rekursiv sein, d.h. ein Nichtterminal kann in seinem eigenen Syntaxdiagramm auftreten:
- ![[Pasted image 20251016150548.png]]




