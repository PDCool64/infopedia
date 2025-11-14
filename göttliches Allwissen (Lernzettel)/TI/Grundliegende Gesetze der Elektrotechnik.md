---
tags:
  - TI
status: rot
---
---

Das Ohm'sche Gesetz sowie die Kirchhoff'schen Regel reichen alleine aus, um alle Schaltkreise die nur aus Widerständen und Strom/Spannungsquellen sowie Verzweigungen zu analysieren.

---
# Ohm'sches Gesetz

> [!def] Ohm'sches Gesetz
> Der durch einen [[Physikalische Größen der Elektrotechnik#Widerstand|Widerstand]] $R$ fließende [[Physikalische Größen der Elektrotechnik#Elektrischer Strom|Strom]] $I$ wächst linear mit dem Wert der am Widerstand abfallenden [[Physikalische Größen der Elektrotechnik#Elektrische Spannung|Spannung]].
> 
>$$U=R\cdot I$$

(for fun:)
![[Pasted image 20251114193455.png|200]]


---
# Kirchhoff'schen Regeln

>[!def] Knotenregel
> Die Summe aller einen Knoten zufließenden Ströme ist gleich der Summe der von ihm abfließenden Ströme.
> 
> Somit ist die Summe aller Ströme an einem Knoten genau $0$
> $$0=I_{1}+I_{2}+\dots+I_{n}$$

- Diese Regel drückt aus, das die Ladung erhalten wird: Alle Elektronen die hineinfließen kommen auch wieder heraus.
- In einem Knoten können keine Elektronen gespeichert, geschweige denn vernichtet oder erzeugt werden.
![[Pasted image 20251114193120.png]]



>[!def] Maschenregel
> Die Summer aller in einer Masche abfallenden Spannungen ist gleich $0$.
> Dabei ist eine *Masche* ein beliebiger Zyklus im Stromkreis.
> 
> - Spannungen, die in Maschenrichtung abfallen, werden mit positivem Vorzeichen verrechnet
> - Spannungen, die *gegen* die Maschenrichtung abfallen, werden mit negativen Vorzeichen verrechnet.
> 
> - (Es ist Konvention, Maschen in die Richtung zu legen, in denen die Spannung der ggfs. enthaltenen Spannungsquelle abfällt)
>   

- Die Maschenregel drückt den Erhalt von Energie aus: Wenn man in einem Kreis/Zyklus läuft, muss man nach jedem Durchlauf wieder an einem Punkt mit genau gleich viel potentieller Energie (vgl. [[Physikalische Größen der Elektrotechnik#Elektrische Spannung|elektrische Spannung]]) herauskommen.

![[Pasted image 20251114193138.png]]

