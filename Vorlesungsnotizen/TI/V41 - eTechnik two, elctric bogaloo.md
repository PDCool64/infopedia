---
date: 2025-11-03
tags:
  - TI
status: rot
Vorlesungsfolien:
Skriptfolien:
---


---

# Kirchhoffsche Regeln
- Strom- bzw. Kantenregel
	- "Die Ladung wird erhalten - Alle Elektronen die hineinfließen kommen wieder heraus. In einem "kleinen" Knoten können keine Elektronen gespeichert, geschweige denn vernichtet oder erzeugt werden."

- Spannungs- bzw. Knotenregel
	- Mann kann die Maschen ziemlich beliebig wählen - es sind aber nicht alle Wahlen sinnvoll
	- Richtung ist wichtig
		- Spannungen, die mit der Maschenrichtung liegen bekommen ein positives Vorzeichen
		- Solche, die gegen die Maschenrichtung liegen bekommen ein negatives Vorzeichen
		- Bei Spannungspol zeichnet man per Konvention die Spannung vom Plus zum Minuspol.
	- Die Maschenregel drückt die Erhaltung von Energie aus: Wenn man in einem Kreis läuft muss man an einem Punkt mit gleich viel potentieller Energie rauskommen, sonst hätte man ein perpetum-mobile

> Die beiden kirchhoffschen Regeln zusammen mit dem Ohmschen Gesetz genügen, um einfache Schaltkreise aus Widerständen, Spannungsquellen und Verzweigungen zu analysieren.


---
# Reihen- und Parallelschaltung von Widerständen
Der Widerstand einer Serienschaltung von Widerstanden hat als Gesamtwiderstand die Summe der Widerstände der einzelnen Widerstände.

Bei einer Parallelschaltung von Widerständen ist der Widerstand
die Summe der Kehrwerte der Widerstände. (oder so. Nochmal doppelcheck)

1k$\Omega$ und 1k$\Omega$ in Parallel ergeben $\frac{1}{2}$ k$\Omega$ 

---
# Netzwerkanalyse: Vorbereitung
man hat k-1 Knotengleichungen, weil man aus den restlichen Gleichungen die Ergebnisse der letzten Herleiten kann: Wie da welche Ströme rein und raus fließen kennt man aus den anderen Gleichungen schon.

Man abstrahiert beim Zählen der Zweige zuerst einmal die Widerstände, Spannungsquellen weg und kümmert sich nur um die Topologie.

S.h. Folie 39: Wenn man eine der Knotengleichung als Produkt einer Konstante mit einer anderen Knotengleichung schreiben kann, bietet diese für das LGS keinerlei neue Informationen. Mann kann eine der beiden einfach weglassen.

Die Maschen dürfen sich überlappen, nur nicht identisch sein.
Jeder Zweig muss in mindestens einer Masche enthalten sein.

---
# Zweigstromanalyse
LGS in dem die Ströme die Unbekannten sind und idR. die Quellspannungen als bekannt angenommen werden.

---
# Maschenstromanalyse
LGS in der die Maschenströme die Unbekannten sind.

Man muss somit mit einer Gleichung weniger Rechnen - aber am Ende wieder von den Maschenströmen auf die Zweigströme schließen. (Bei der Zweigstromanalyse hatte man noch on top die Knotenregel.) Der Vorteil ist also gering.

1. Drücke alle Zweiströme durch Maschenströme aus.


---
# Knotenspannungsanalyse
Ersetze die Spannungsquellen durch Stromquellen - wähle dabei die Stromstärke der Stromquellen so, dass an der Schnittstelle an der die "neue" Stromquelle eingesetzt wurde wieder die gleichen Bedingungen herrschen wie mit der Spannungsquelle.


