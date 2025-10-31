---
date: 2025-10-31
tags:
  - AFI
status: rot
Vorlesungsfolien:
Skriptfolien:
---
---

>[!def] Obere und untere Schranken
> Sei $K$ ein angeordneter Körper und $M\subseteq K$.
> Dann heißt $M$ **nach oben beschränkt**,  falls ein $C\in K$ existiert, so dass $x\le C \forall_{x\in M}$
> 
> $M$ heißt **nach unten beschränkt**, wenn ein $c\in K$ existiert so, dass $x\ge c\forall_{x\in K}$.
> 
> $M$ heißt beschränkt, wenn $M$ nach unten und nach oben beschränkt ist.
> bzw. wenn $R>0$ exisitiert, so dass $\left| x \right|\leq R\forall_{x\in M}$

- Die Schranken müssen selbst nicht in $M$ liegen, sondern nur im Körper $K$.
  
## Beispiele:
$\mathbb{N}$ ist nach unten beschränkt. z.B. mit $c=1$ oder $c=\frac{1}{2}$

$M\subseteq Q\text{ endlich}$, so ist $M$ beschränkt.

$M=\{ x\in \mathbb{Q} \mid x^{2}<2\}$ ist beschränkt.

$\left\{  x\mid \exists_{m\in \mathbb{N}}:x=\frac{1}{m}  \right\}$ ist z.B. von oben durch $1$ und von unten durch $0$ beschränkt.
- $1$ ist das Maximum
- $0$ ist (nur) das Infimum-nicht aber das Minimum


>[!def] Supremum und Infimum
> Sei $K$ ein angeordneter Körper.
> $M\subseteq K$. Ein $C\in K$ heißt **Supremum** oder **kleinste obere Schranke**, wenn
> - $C$ ist obere Schranke von $M$, d.h $x\le C,\forall _x\in C$
> - Ist $C'$ eine obere Schranke von $M$, so gilt $C\le C'$
> 
>  Umgekehrt heißt $c\in K$ **Infimum**, bzw. **größte untere Schranke**, wenn es eine untere Schranke ist und gilt $c'\le c$ .
> 
> $C=\text{sup }M$
> $c=\text{inf }M$
> 
> Es gibt nicht für jede Menge obere/untere Schranken.


Existiert ein $C\in M$ mit $C=\text{sup } M$, so heißt $C$ das **Maximum** von $M$. $C=\text{max }M$
Existiert ein $c\in M$ mit $C=\text{inf }M$, so heißt $C$ das **Minimum** von $M$.
$C=\text{min }M$

Interessant / Wichtig.
$\{ x\in \mathbb{Q}\mid x\ge 0 \land x^{2}<2 \}$ ist eine Teilmenge von $\mathbb{Q}$  und hat kein Supremum in $\mathbb{Q}$.


> Fallunterscheidung für $s^{2}<2$ vs $s^{2}>2$ :
> Lsg.: Wir wollen zeigen, das kein *Supremum in $\mathbb{Q}$* existiert. Wir wissen schon/können zeigen, dass $\sqrt{ 2 }\not\in \mathbb{Q}$ .
> 
> Also versuchen wir zu zeigen, dass für ein Supremum $c^{2}=2$ gelten muss. (damit $c=\sqrt{ 2 }$)
> Dies machen wir, indem wir $c^{2}<2$ und $c^{2}>2$ jeweils zum Widerspruch führen.


(GIBT HIER EINEN FEHLER IM SKRIPT SH: PXL Foto)

---

# Reelle Zahlen
Charakterisierung
$\mathbb{R}$ ist ein vollständiger, angeordneter Körper, d.h. jeder nach oben beschränke, nicht-leere Teilmenge von $\mathbb{R}$ besitzt ein Supremum.
> D.h. die kleinste Obere Schranke liegt immer wieder in $\mathbb{R}$
> So "Probleme", wie dass $\sqrt{ 2 }$ nicht in $\mathbb{Q}$ liegt hat man nicht - jede obere Schranke einer Teilmenge von $\mathbb{R}$ liegt immer in $\mathbb{R}$

Es lässt sich daraus herleiten, dass es mit dem Infimum genauso funktioniert.


> Noch Offen: Existiert so ein Körper $\mathbb{R}$, ist er Eindeutig?
> Haben wir nicht bewiesen, ist aber beides so (Eindeutigkeit bis auf Isomorphie) gültig.


## Beispiel:
Die Menge $\tilde{M}:=\{ x\in \mathbb{R}\mid x \geq 0 \land x^{2}<2 \}$ besitzt in $\mathbb{R}$ ein Supremum und mit Bsp. von oben gilt $C=2^{2}$ was tatsächlich in $\mathbb{R}$ liegt.

---

## Satz von Archimedes:
Die Menge $\mathbb{N}$ ist in $\mathbb{R}$ nicht nach oben beschränkt.

Beweis:
- Wegen $1\in \mathbb{N}$ gilt $N\neq \emptyset$
- Widerspruch:
  Angenommen $\mathbb{N}$ ist nach oben beschränkt. $\mathbb{R}$ vollständig $\implies$ $\exists C:C=\text{sup }\mathbb{N}$ mit $C\in \mathbb{R}$. 
  
  Dann ist $C-1$ keine obere Schranke von $\mathbb{N}$
  $\implies$ es gibt ein $a\in \mathbb{N}$ mit $a>C-1$ 
  
  d.h. $C-1<a\leq C\implies C<a+1$ aber 
  $a+1\in \mathbb{N}\implies C$  keine obere Schranke.
  
  > Wir haben bewiesen "$\infty \not\in \mathbb{R}$" (oder so)
  
---
rationale Zahlen liegen "dicht" in $\mathbb{R}$.
Zu allen $a,b\in\mathbb{R}$ mit $a<b$ existiert ein $q\in \mathbb{Q}$ mit der Eigenschaft
$a<q<b$
(Mann kann zwischen jede paar an reellen Zahlen noch einen Bruch quetschen)

Man verschiebt zuerst  zu $0$ (müssen aber Fallunterscheidung nach   und $a\le 0$) Den zweiten Fall kann man aber auf den ersten reduzieren.
1. Fall: $0< \frac{1}{n}<b-a$
2. Fall: $0<a+r<b+r$

Verwenden den Satz des Archimedes für eine der Verschiebungen.

> Wir suchen den kleinsten Bruch, der gerade noch größer als $a$ ist und können dann auch folgern, dass dieser kleiner $b$ ist.

> das es auch kleiner $b$ ist zeigt man mit Widerspruch.

---
in $\mathbb{Q}$ gibt es also Lücken wie $\sqrt{2 }$ (oder die Wurzeln aus Primzahlen per se)
In $\mathbb{R}$ können wir Wurzel aber sauber definieren, weil wir nie aus $\mathbb{R}$ raus-fallen.



---
> Nächste Frage: Was ist dann der unterschied zwischen $\mathbb{Q}$ und $\mathbb{R}$ - das ist die Frage für nächste Woche.

