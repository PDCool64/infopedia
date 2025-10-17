> [!def] Allquantor $\forall$
> Die Aussage $\forall_{x\in M}:A(x)$ ist genau dann wahr, wenn $A(x)$ für jedes $x\in M$ wahr ist.
> 
> gelesen : "Für alle Elemente $x$ in $M$ gilt $A(x)$."

>[!def] Existenzquantor $\exists$
>Die Aussage $\exists_{x\in M}:A(x)$ ist genau dann wahr, wenn es mindestens ein $x\in M$ gibt, für das $A(x)$ wahr ist.
>
>gelesen : "Es existiert mindestens ein $x$ in $M$, für das $A(x)$ gilt."
>
>"Es existiert *genau* ein" kann man schreiben als $\exists!$

## Verkettung von Quantoren:
Die Aussage
"Es gibt für jede natürliche Zahl mindestens eine Zahl, die größer als sie ist." lässt sich umschreiben zu:
$\forall_{x\in \mathbb{N}}\exists_{y\in \mathbb{N}} : y>x$

Bei solchen Verkettungen von Quantoren ist die *Reihenfolge* entscheidend:
$\exists_{x\in \mathbb{N}}\forall_{y\in \mathbb{N}}:y>x$ ist eine andere Aussage. (Die zufällig falsch ist weil $0\not>0$)
## Mit leeren Mengen zu beachten:
Ist $M=\emptyset$, dann ist die Aussage
- $\exists_{x\in M}:A(x)$ immer falsch
- $\forall_{x\in M}:A(x)$ immer wahr

## Verneinung von Quantoren
Aussagen mit Quantoren werden wie folgt negiert:
$$
\neg\big(\exists_{x\in M}:A(x)\big) \iff \forall_{x\in M}\neg\big(A(x)\big)
$$
$$
\neg(\forall_{x\in M}:A(x)) \iff \exists_{x\in M}:\neg \big(A(x)\big)
$$
z.b.
$\neg(\text{"Es existiert mindestens eine blaue Katze"})\iff\text{"Alle Katzen sind nicht blau"}$
$\neg(\text{"Alle Fische sind rot"})\iff\text{"Es existiert mindestens ein Fisch, der nicht rot ist"}$

