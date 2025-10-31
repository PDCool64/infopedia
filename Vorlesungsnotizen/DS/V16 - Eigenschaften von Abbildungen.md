---
date: 2025-10-29
tags:
  - DS
status: rot
Vorlesungsfolien:
Skriptfolien:
---
---
Infos: Präsenztest
- Dienstag 16:30 anstatt der Vorlesung im H01
- gibt Bonuspunkte für die Klausurzulassung - sowohl für den Online-Teil als auch für die Schriftlichen Teil. (6 Punkte pro test, insgesamt 18)
- unter den gleichen Bedingungen wie die Klausur
- (keine Ahnung ob wir Papier kriegen. Sollte mir aber sowieso mal einen neuen Block kaufen)
- man kann nichts verlieren

von Moodle:
- Der Präsenztest findet am Dienstag, den 04.11.2025, ab 16:30 im Hörsaal H01 statt
- Sie brauchen nur einen Kugelschreiber und ggf. Papier für Nebenrechnungen mitzubringen
- Merken Sie sich Ihre Matrikelnummer und Ihre Tutoriumsnummer.
- Relevant sind die Themen der Wochen 0-2, insbesondere also Aussagenlogik, Mengenlehre, Beweismethoden, v.a. vollständige Induktion
- Bitte nutzen Sie die Anmeldung über Moodle, damit wir Abschätzen können, wie viele Teilnehmende es geben wird. Diese wird bis zum 29.10. um 23:55 geöffnet sein

---

# Eigenschaften von Abbildungen
wenn man auf die Surjektivitätsdefinition die Formalität draufjagen würde:
$f:M\to N$ und $A\subseteq M$ 

$f(A):=\{ f(x)\mid x \in A\}$

könnte man schreiben als
$f(A):=\{ y\in A \mid \exists x\in A:y=f(x) \}$
wenn man dies macht, wäre mit der Abbildungsdefinition sehr formell:
$f(A):=\{ y\in n\mid \exists x\in A:(x,y)\in f \}$

Neue Definition:
>[!def] Fasern einer Abbildung
> $f:M\to N$
> $$f^{-1}(\{ y \})\text{ mit y}\in N$$
> nennen wir **Faser von $y$**. 
> Alle Fasern zusammen nennt man **Fasern von $f$**.
#### Bemerkungen:
- Die Faser eines $y\in N$ einer nicht surjektiven Funktion $f$ kann leer sein.
- Die nicht-leeren Fasern von $f$ bilden eine Partition von $M$.
	- Beweis: Die Fasern sind paarweise disjunkt: 
	  Seien $y_{1},y_{2}\in N$ mit $f^{-1}(\{ y_{1} \})\neq \emptyset$ und $f^{-1}(\{ y_{2} \})\neq \emptyset$.
	  Angenommen, $x\in f^{-1}(\{ y_{1} \})\cap f^{-1}(\{ y_{2} \})$. 
	  Dann gilt: $f(x)=y_{1}$ und $f(x)=y_{2}$. Es folgt $y_{1}=y_{2}$.
	  
	  Wir zeigen un, dass $\bigcup_{y\in N}f^{-1}(\{ y \})=M$ 
	  
	 Wir zeigen beide Inklusionen:
	 $\subseteq$ ist klar, weil die Fasern alle in $M$ liegen. Wenn man Teilmengen einer Menge vereinigt, erhält man immer wieder eine Teilmenge.
	 $\supseteq$: Sei $x\in M$. Dann gilt  $x\in f^{-1}(\{ f(x) \})$ . q.e.d

# Surjektiv, Injektiv, Bijektiv
- $f$ heißt surjektiv, falls $f(M)=N$ 
	- Äquivalent: Jede Faser von $f$ besitzt mindestens eine Element
- $f$ heißt injektiv, falls $\forall x,x'\in M:f(x)=f(x')\implies x=x'$
	- Äquivalent: Jede Fasern von $f$ besitzt höchstens ein Element 
- $f$ heißt bijektiv, falls $f$ surjektiv und injektiv ist. Mann nennt $f$ dann auch eine Bijektion. 
	- Äquivalent: Jede Faser von $f$ besitzt genau ein Element.

> Die Definition über die Größe der Fasern ist eigentlich echt nett.

---

# Einschränkung von Abbildungen.
>[!def] Einschränkung einer Abbildung
> Schreibweise genau wie in AFI:
> Es sei $f:M\to N$ eine Abbildung und $M'\subseteq M$, dann heißt
> $$f|_{M'}:M'\to N,x\mapsto f(x)$$
> die **Einschränkung von $f$ auf $M'$**.
>

Es existiert dabei immer $M'\subseteq M$, so dass $f|_{M'}$ injektiv und $f(M)=f|_{M'}(M')$ 
d.h. die Bilder sind gleich.
- z.B. man macht jede nichtleere Faser einelementig. Dabei wird immer noch jedes $y$ getroffen.


> Random Fun-Fact zum Kartesischen Produkt: Nach dem Auswahlaxiom ist das kartesische Produkt $\large\times_{i}M_{i}$ nicht leer, wenn alle $M_{i}$ nicht leer sind. (AFAIK ?nur? bei unendlich vielen Mengen.)

---
# Inklusion
$M$ Menge, $N\subseteq M$

Inklusion von $N$ in $M$:
$$
\iota=\iota^{N}:=(\text{id}_{M})|_{N}:N\to M
$$
ist einfach die Beschränkung der Identität auf die Teilmenge $N$
