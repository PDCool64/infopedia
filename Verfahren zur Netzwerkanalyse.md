---
tags:
  - TI
status: rot
---
---

Grundlage sind die [[Grundliegende Gesetze der Elektrotechnik|Grundlegenden Gesetzte der Elektrotechnik]] : [[Grundliegende Gesetze der Elektrotechnik#Ohm'sches Gesetz|Ohm'sches Gesetz]] sowie die [[Grundliegende Gesetze der Elektrotechnik#Kirchhoff'schen Regeln|Kirchhoff'schen Regeln]]

Hier werden Verfahren thematisiert, die es erlauben einfache, lineare Schaltungen die nur aus Widerständen, Strom/Spannungsquellen und Knoten bestehen zu untersuchen.

Beispiele für die Anwendung dieser Verfahren gibt es zum Beispiel in dieser Globalübung:
[[Beispiele_Netzwerkanalyse.pdf]]

---
# Vorbereitung

1. **Untersuche die Topologie des Netzwerks**
	-  Zähle die Anzahl an Knoten $k$ (*nur* topologische Knoten. Für die Übersichtlichkeit sind oft deutlich mehr "Punkte" eingezeichnet, die aber mit andern kurzgeschlossen sind)
	-  Zähle die Anzahl an Zweigen $z$
	-  Berechne die Anzahl an notwendigen [[Grundliegende Gesetze der Elektrotechnik#^4f95a2|Maschen]] $m=z-(k-1)$

2. Zeichne die Spannungen und Zweigströme in das Schaltdiagramm ein.
    Am besten wählt man Richtung von Strom/Spannung an jedem Bauteil in die selbe Richtung.

3. **Stelle die Knotengleichungen auf** : [[Grundliegende Gesetze der Elektrotechnik#^88c4a5|Knotenregel]]
   Stelle für alle (bis auf einen Knoten) Gleichungen der Form $0=I_{1}+\dots+I_{n}$ auf.

4. **Lege $m$-viele Maschen fest**
	- Jede Masche muss einen Zweig erhalten, der in keiner anderen Maschen enthalten ist. (Somit stellt man sicher, dass alle Zweige/Variablen abgedeckt sind)

5. **Aufstellen der Maschengleichungen** : [[Grundliegende Gesetze der Elektrotechnik#^4f95a2|Maschenregel]]
	- Stelle für alle Maschen die Maschengleichungen der Form $0=U_{1}+\dots+U_{2}$ auf.
	- Sortiere dabei die Quellspannungen

6. **Anwenden des [[Grundliegende Gesetze der Elektrotechnik#Ohm'sches Gesetz|Ohm'schen Gesetzes]] auf die Teilspannungen in den Maschengleichungen**
	- Ersetze jede Spannung $U_i$ durch $U_{i}=R_{i}\cdot I_{i}$ 
	- Bei Bauteilen auf dem gleichen Zweig -also mit gleichem Strom- kann man auch direkt ausklammern: $0=R_{1}I_{1}+\dots+(R_{2}+R_{3})\cdot I_{2}+\dots$


---
# Zweigstromanalyse
**Gegeben:** Quellspannungen
**Gesucht**: Zweigströme

Eigentlich ist man hier nach den Vorbereitungsschritten schon fertig.

1. Schreibe die Knotengleichungen zusammen mit den Maschengleichungen in ein LGS
2. Klammere überall die Zweigströme (ggfs. mit Faktor 0) aus,
3. Schreibe als Matrix-Vektor Produkt

Z.B.:
LGS:
![[Pasted image 20251115204249.png]]
Als Matrix-Vektor Produkt:
![[Pasted image 20251115204334.png]]

---
# Maschenstromanalyse
**Gegeben**: Quellspannungen
**Gesucht**: Maschenströme bzw. auch Zweigströme

Stelle genau wie in der [[#Zweigstromanalyse]] die Maschengleichungen auf.
**Hier kann man sich die *Knoten*gleichungen sparen**

Dann:
1. Beschreibe alle Zweigströme als Kombination von Maschenströmen![[Pasted image 20251115204710.png]]
2. Setzte die neuen Definitionen der Ströme in die Maschengleichungen ein.
3. Klammere die Maschenströme aus und schreibe das LGS als Matrix-Vektor-Produkt


Z.B.:
![[Pasted image 20251115205100.png]]


---
# Knotenspannungsanalyse
