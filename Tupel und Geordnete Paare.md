---
tags:
  - DS
status: rot
---
---

Geordnetes Paar und Tupel sind von der Funktion her für uns das Gleiche - Die Tupel-Definition ist einfach eine sehr praktische Schreibweise und eine Definitionsvariante mit vielen nützlichen Eigenschaften. Meist verwendet man den Ausdruck "geordnetes Paar" wenn es darum geht wie man diese Dinge schön axiomatisch aus Mengen konstruiert.

Man kann zeigen, das beide Ansätze equivalent/gleichmächtig sind.

Ein geordnetes Paar, was identisch zu einem 2-Tupel ist, kann man definieren als Objekt $(x,y)$ wobei zwei verschieden $(x_{1},y_{1})$ und $(x_{2},y_{2})$ genau dann gleich sind, wenn $x_{1}=x_{2}\land y_{1}=y_{2}$ .

Man kann Geordnete Paare/Tupel auch direkt aus Mengen konstruieren, ohne dafür Abbildungen zu benötigen: $(x,y)$ lässt sich konstruieren als $\{ x,\{ x,y \} \}$ wobei die Verschachtelungslevel die Reihenfolge angeben. Ebenso ist dies für beliebige Größen möglich: $(x,y,z)$ kann konstruiert werden als  $\{ (x,y),\{ (x,y),z \} \}=\{ \{ x,\{ x,y \} \} ,\{ \{ x,\{ x,y \} \},z \}\}$.






