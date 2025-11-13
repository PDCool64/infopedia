---
tags:
status: rot
---
---
# Schranken
>[!def] Obere und untere Schranken
> Sei $K$ ein angeordneter Körper und $M\subseteq K$.
> Dann heißt $M$ **nach oben beschränkt**,  falls ein $C\in K$ existiert, so dass $x\le C \;\forall_{x\in M}$
> 
> $M$ heißt **nach unten beschränkt**, wenn ein $c\in K$ existiert so, dass $x\ge c\;\forall_{x\in K}$.
> 
> $M$ heißt **beschränkt**, wenn $M$ nach unten und nach oben beschränkt ist.
> bzw. wenn $R>0$ existiert, so dass $\left| x \right|\leq R\forall_{x\in M}$

- Die Schranken müssen selbst nicht in $M$ liegen, sondern nur im Körper $K$.
# Supremum, Infimum
>[!def] Supremum und Infimum
> Sei $K$ ein angeordneter Körper.
> $M\subseteq K$. Ein $C\in K$ heißt **Supremum** oder **kleinste obere Schranke**, wenn
> - $C$ ist obere Schranke von $M$, d.h $x\le C\;\forall _x\in M$
> - Ist $C'$ eine obere Schranke von $M$, so gilt $C\le C'$
> 
>  Umgekehrt heißt $c\in K$ **Infimum**, bzw. **größte untere Schranke**, wenn es eine untere Schranke ist und gilt: 
> - $c$ ist untere Schranke von $M$, d.h $x\ge c\;\forall _x\in M$
> - Ist $c'$ eine (andere) untere Schranke von $M$, so gilt $c\ge c'$
> 
> 
> Es gibt nicht für jede Menge obere/untere Schranken.

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
Dabei existieren offensichtlich $h_{0}$ welche diese Bedingung erfüllen: Z.B. $h_{0}$ gewählt als die Hälfte des rechten Terms:
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





