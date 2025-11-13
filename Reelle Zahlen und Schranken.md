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

Am Beispiel $\{ x\in \mathbb{Q} \mid x\ge 0 \land x^{2}<2 \}$ kann dies einfach gezeigt werden, weil $\sqrt{  2}$ keine rationale Zahl ist.

