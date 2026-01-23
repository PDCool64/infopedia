---
tags:
  - TI
status: rot
---
---

Primär zur robusten Übertragung von Daten durch parallele Kabel gedacht (Timing unterschiede verändern der Wert im Gray-Code nur gering) gedacht, aber auch für KV-Diagramme sehr wichtig.

>[!def] Gray-Code
> Die Darstellung zweier benachbarter Zahlen im Gray-Code unterscheidet sich nur durch **1Bit** 
> 
> Generierung (eine Möglichkeit):
> - Zahl im Binärsystem darstellen: $x_{1}=(011)_{2}$
> - Links-Shift und 1Bit: $x_{2}=x\ll 1=(110)_{2}$
> - $\text{xor}$-Verknüpfung der beiden Vorherigen Schritte: $x_{3}=x_{1} \oplus x_{2}=(101)_{2}$
> - Rechts-Shift um 1Bit: $x_{4}=x_{3}\gg 1 = (10)_{2}$
>   
> Generierung (Bessere Möglichkeit):
>   $$g=x \oplus(x\gg 1)$$


![[Pasted image 20251030105705.png]]

![[Pasted image 20251030105713.png]]