---
tags:
status: rot
---
---
# Schranken
>[!def] Obere und untere Schranken
> Sei $K$ ein [[Körper#Angeordneter Körper|angeordneter Körper]]  und $M\subseteq K$.
> Dann heißt $M$ **nach oben beschränkt**,  falls ein $C\in K$ existiert, so dass $x\le C \;\forall_{x\in M}$
> 
> $M$ heißt **nach unten beschränkt**, wenn ein $c\in K$ existiert so, dass $x\ge c\;\forall_{x\in K}$.
> 
> $M$ heißt **beschränkt**, wenn $M$ nach unten und nach oben beschränkt ist.
> bzw. wenn $R>0$ existiert, so dass $\left| x \right|\leq R\forall_{x\in M}$

^a16b1c

- Die Schranken müssen selbst nicht in $M$ liegen, sondern nur im Körper $K$.
# Supremum, Infimum
>[!def] Supremum und Infimum
> Sei $K$ ein [[Körper#Angeordneter Körper|angeordneter Körper]]
> $M\subseteq K$. Ein $C\in K$ heißt **Supremum** oder **kleinste obere Schranke**, wenn
> - $C$ ist obere Schranke von $M$, d.h $x\le C\;\forall _x\in M$
> - Ist $C'$ eine (andere) obere Schranke von $M$, so gilt $C\le C'$
> 
>  Umgekehrt heißt $c\in K$ **Infimum**, bzw. **größte untere Schranke**, wenn es eine untere Schranke ist und gilt: 
> - $c$ ist untere Schranke von $M$, d.h $x\ge c\;\forall _x\in M$
> - Ist $c'$ eine (andere) untere Schranke von $M$, so gilt $c\ge c'$
>
> ---
> Es gibt nicht für jede Menge obere/untere Schranken.
> 
> ---
> Existiert ein Supremum (bzw. ein Infimum) einer Menge $M$, so ist es *eindeutig* bestimmt. (Denn seien $C$ und $C'$ Suprema, dann folgt aus ihrer jeweiligen Definition $C\le C' \land C' \le C\implies C=C'$)
> 
> ---
> Falls die Menge $M$ ein Supremum $s$ besitzt, so besitzt $-M:=\{ x\in K \mid -x\in M \}$ ein Infimum und zwar $-s$

^370e3d

- Häufiges Beispiel ist die Menge $\{ x\in \mathbb{Q} \mid x\ge 0 \land x^{2}<2 \}$ , welche *kein* Supremum in $\mathbb{Q}$ hat, weil $\sqrt{ 2 }$ eine [[Zahlenräume#^4c01ae|irrationale Zahl]] ist. 


>[!def] Maximum und Infimum
> Existiert ein $C\in M$ mit $C=\text{sup } M$, so heißt $C$ das **Maximum** von $M$.
>  $C=\text{max }M$
> 
>Liegt also das Supremum- die kleinste obere Schranke- selbst in der Menge $M$, dann nennt man es auch Maximum.
>
> ---
> Existiert ein $c\in M$ mit $c=\text{inf }M$, so heißt $c$ das **Minimum** von $M$.
> $c=\text{min }M$.
> 
> Liegt also das Infimum -die größte untere Schranke- selbst in der Menge $M$, dann nennt man es auch Minimum.
> 


---
# In den [[Zahlenräume#Rationale Zahlen $ mathbb{Q}$|Rationalen Zahlen]] hat nicht jedes Intervall ein Supremum:

Am Beispiel $M=\{ x\in \mathbb{Q} \mid x\ge 0 \land x^{2}<2 \}$ kann dies einfach gezeigt werden, weil $\sqrt{  2}$ keine rationale Zahl ist.

### Beweisprinzip: 
Wir wissen durch [Euklids Beweis](https://de.wikipedia.org/wiki/Beweis_der_Irrationalit%C3%A4t_der_Wurzel_aus_2_bei_Euklid), dass $\sqrt{ 2 }$ irrational, insbesondere also $\sqrt{ 2 }\not\in \mathbb{Q}$ ist. 

Dann zeigen wir, dass kein Supremum $s$ existieren kann, das ungleich $\sqrt{ 2 }$ ist.
Dafür führen wir sowohl $s^{2}<2$ als auch $s^{2}>2$ zum Widerspruch.

Wenn gezeigt ist, das ein theoretisches Supremum $s$ genau $\sqrt{ 2 }$ seien muss, ist klar, dass kein Supremum in $\mathbb{Q}$ existiert.

### Annahme: $s^{2}<2$
Wir zeigen, dass $s$ keine obere Schranke von $M$ ist, indem wir ein $(s+h_{0})\in M$ bzw. $(s+h)^{2}<2$ konstruieren, dass *größer* als $s$ ist.

Für $0<h<1$ beachte man $0<h^{2}<h$. Damit lässt sich konstruieren:
$$(s+h)^{2}=s^{2}+2sh+h^{2}\le s^{2}+2sh+h=s^{2}+3sh$$
Somit lässt sich $(s+h)^{2}\leq s^{2}+3sh$ nach oben abschätzen.
Damit gilt sicher, dass wenn $s^{2}+3sh<2$ auch $(s+h)^{2}<2$.

Diese Bedingung lässt sich umformen:
$$
\begin{align}
s^{2}+3sh &<2 \\
3sh&<2-s^{2} \\
h &< \frac{2-s^{2}}{3s}
\end{align}
$$
Dabei existieren offensichtlich $h_{0}$ welche diese Bedingung erfüllen: Z.B. $h_{0}$ gewählt als die Hälfte des rechten Terms (der immer positiv ist)
$$
\begin{align}
h_{0} &< \frac{2-s^{2}}{3s}\\ \\
\frac{2-s^{2}}{6s} &< \frac{2-s^{2}}{3s}
\end{align}
$$
Damit gilt sicher, dass auch $(s+h_{0})^{2}<2$ bzw. $(s+h_{0})\in M$ sind.
Insbesondere gilt durch $0<h<1$ auch, dass $s<s+h_{0}$ , womit $s$ keine obere Schranke seien kann.
Die Aussage $s^{2}<2$ wurde somit zum Widerspruch geführt.

### Annahme: $s^{2}>2$
Wir zeigen, dass eine andere obere Schranke $r$ gibt, die $r<s$ erfüllt, womit $s$ nicht die kleinste obere Schranke seien kann.

Für $0<h$ lässt sich konstruieren:
$$
(s-h)^{2}=s^{2}-2sh+h^{2}\geq s-2sh
$$
Somit lässt sich $(s-h)^{2}$ nach unten abschätzen durch $s-2sh$.
Damit gilt sicher, dass wenn $s-2sh>2$ auch $(s-h)^{2} >2$.

Diese Bedingung lässt sich umformen:
$$
\begin{align}
s^{2}-2hs &>2 \\
-2hs&>2-s^{2} \\ \\

h &<  -\frac{2-s^{2}}{2s}
\end{align}
$$
Dabei existieren offensichtlich $h_{0}$ welche diese Bedingung erfüllen: Z.B. $h_{0}$ gewählt als genau die Hälfte des rechten Terms (der immer positiv ist):
$$
\begin{align}
h_{0} &< - \frac{2-s^{2}}{2s} \\
\frac{2-s^{2}}{4s} &< - \frac{2-s^{2}}{2s}
\end{align}
$$
Damit gilt sicher auch, dass $(s-h_{0})^{2}>2$, womit $r=s-h_{0}$ eine gültige obere Schranke von $M$ in $\mathbb{Q}$ ist.
Insbesondere gilt durch $h<0$ auch, dass $s>s-h_{0}$, womit $s$ nicht die kleinste obere Schranke gewesen ist.
Die Aussage $s^{2}>2$ wurde somit zum Widerspruch geführt.

### Beweisschluss
Aus $\neg(s^{2}<2)\land \neg(s^{2}>2)$ folgt $s^{2}=2\iff s=\sqrt{ 2 }$.

Mit [Euklids Beweis](https://de.wikipedia.org/wiki/Beweis_der_Irrationalit%C3%A4t_der_Wurzel_aus_2_bei_Euklid) wissen wir, dass $\sqrt{ 2 }$ irrational, insbesondere also $\sqrt{ 2 }\not\in \mathbb{Q}$ ist. 

Es existiert also kein Supremum $s\in \mathbb{Q}$ von $M$.

---
# Reelle Zahlen

>[!def] Reelle Zahlen
> $\mathbb{R}$ ist ein **vollständiger**, [[Körper#Angeordneter Körper|angeordneter Körper]]; d.h. Jede [[#^a16b1c|nach oben beschränkte]], nicht-leere Teilmenge von $\mathbb{R}$ besitzt ein Supremum.
> 
> ---
> 
> D.h. : Jede nicht-leere Teilmenge von $\mathbb{R}$ die eine obere Schranke $\in \mathbb{R}$ hat, hat auch eine *kleinste* obere Schranke $\in \mathbb{R}$.
> 
> Somit fangen wir in $\mathbb{R}$ alle Fälle wie $\sqrt{ 2 }$ usw. ein, die in den rationalen Zahlen noch gefehlt haben.
> 
> ---
> Es folgt nach dem [[#^370e3d|Satz]] : "*Falls die Menge $M$ ein Supremum $s$ besitzt, so besitzt $-M:=\{ x\in K \mid -x\in M \}$ ein Infimum und zwar $-s$*" ebenfalls, dass jede nach unten beschränkten Teilmenge von $\mathbb{R}$ ein Infimum besitzt.


- Aus mathematischer Sicht lässt die Charakterisierung eigentlich alle Fragen offen. Weder die Frage nach Existenz noch die nach Eindeutigkeit wird beantwortet. In der Tat gibt es einen solchen Körper und er ist im Wesentlichen (mathematisch: „bis auf Isomorphie“) eindeutig bestimmt. Bewiesen soll dies hier aber nicht werden


Mit dieser Definition kann man folgern:
- [[Natürliche und rationale Zahlen als Teilmenge der Reellen Zahlen]]
- 