>[!def] Körper
> Eine [[Mengen|Menge]] $\mathbb{K}$ bildet einen **Körper**, wenn zu je zwei Zahlen $x,y\in \mathbb{K}$
> - eine **Summe** $x+y\in \mathbb{K}$
> - und ein **Produkt** $x\cdot y\in \mathbb{K}$
>
>definiert sind, welche die folgenden Rechenregeln erfüllen:
>
> ---
> 
> Für die *Addition*:
> - (A.1) $x+y=y+x$                   (Kommutativgesetz)<br><br>
> - (A.2) $x+(y+z)=(x+y)+z$ (Assoziativgesetz) <br><br>
> - (A.3) Es gibt ein Element $0\in \mathbb{K}$ mit $\forall_{x\in \mathbb{K}}:0+x=x$ 
> 		("$0$" ist hier eher als Name/Bezeichnung und nicht als die $0\in \mathbb{R}$ zu lesen)
> 		 ->  **Nullelement** bzw. **neutrales Element der Addition**. <br><br>
>  - (A.4) Zu jedem Element $x\in \mathbb{K}$ gibt es ein Element $(-x)\in \mathbb{K}$ mit $x+(-x)=0$
> 		-> **Inverses Element der Addition** <span id="additiv-invers"></span>
> 
> ---
> 
> Für die *Multiplikation*:
> - (M.1) $x\cdot y=y\cdot x$               (Kommutativgesetz)<br><br>
> - (M.2) $x\cdot (y\cdot z)=(x\cdot y)\cdot z$ (Assoziativgesetz)<br><br>
> - (M.3) Es gibt ein Element $1\in \mathbb{K}\;,1\neq 0$ mit $\forall_{x\in \mathbb{K}}:1\cdot x=x$ 
> 		("$1$" ist hier eher als Name/Bezeichnung und nicht als die $1\in \mathbb{R}$ zu lesen)
> 		 ->  Einselement** bzw. **neutrales Element der Multiplikation**.<br><br>
> - (M.4) Zu jedem Element $x\in \mathbb{K}\;,x\neq 0$ gibt es ein Element $(x^{-1})\in \mathbb{K}$ mit $x\cdot (x^{-1})=1$
> 		-> **Inverses Element der Multiplikation**
> 
>---
>Die Multiplikation und die Addition sind im folgenden Sinne verträglich:
>- (A.M) $x\cdot(y+z)=(x\cdot y)+(x\cdot z)$   (Distributivgesetz)

^a3c120

## Bemerkungen:
- Sowohl das neutrale als auch das inverse Element der Addition sowie der Multiplikation sind jeweils *eindeutig*. (Es kann in einem Körper z.B. nicht zwei neutrale Elemente geben)
  
- $\mathbb{N}$ ist *kein* Körper, weil u.A. kein Inverses Element der Addition besteht. ($2+n\neq 0\;,\;n\in \mathbb{N}$)
  
- $\mathbb{Z}$ ist *kein* Körper, weil u.A. kein Inverses Element der Addition besteht. ($2\cdot z\neq 1\;,\;z\in \mathbb{Z}$
  
- in einem Körper ist ein Produkt genau dann Null, wenn einer der Faktoren Null ist:$$
a\cdot b=0\iff(a=0)\vee(b=0)
$$
## Anordnung auf einem Körper:
>[!def] Anordnung auf $\mathbb{R}$
>Ein [[Körper]] heißt **Angeordneter Körper**, wenn in ihm eine **Anordnung $\leq$ (kleiner gleich)** definiert ist, die den folgenden Regeln für alle $x,y,z\in \mathbb{K}$ gehorcht:
> 
> - (Q.1) *Trichotometrie:* Es gilt stets $x\leq y \;\vee\; y\le x$
> - (Q.2) *Reflexivität*: $x \le x$
> - (Q.3) *Asymmetrie*: $(x\le y \;\wedge\; y\le x)\implies x=y$
> - (Q.4) *Transitivität*:  $(x\le y \;\wedge\; y\le z) \implies x \le z$
> - (Q.5) *Monotonie der Addition*: $(x \le y)\implies x+z \le y+z$
> - (Q.6) *Monotonie der Multiplikation*: $(x \le y \;\wedge 0 \le z) \implies x\cdot z \le y\cdot z$

^315cce
Die [[Zahlenräume#Reelle Zahlen $ mathbb{R}$|Reellen Zahlen]] sind z.B. ein angeordneter Körper.
