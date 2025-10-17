>[!wip]
> Diese Notiz ist noch nicht auf dem rigoroseren Stand der DS Vorlesung: z.B. fehlen Terme, die Unterscheidung zwischen Subjunktion und Implikation usw. Es wird auf das [[Skript Diskrete Strukturen.pdf]] verwiesen.


---


>[!def] Aussage:
>Eine (mathematische) Aussage ist eine sprachlich oder symbolisch formulierte Behauptung, der auf eindeutiger Weise ein Wahrheitswert, nämlich *wahr (W)* oder *falsch (F)* zugeordnet werden kann.

Dabei zu beachten:
- Damit einer Aussage ein *eindeutiger* Wahrheitswert zugewiesen werden kann, muss klar sein, in welchem System/Kontext gearbeitet wird, d.h. mit welchen Axiomen die Aussage bewertet wird: $a^{2}+b^{2}=c^{2}$ ist *alleine* keine Aussage, weil nicht klar ist, was $a,b,c$ überhaupt seien sollen. Erst durch den Kontext "$a,b$ sind die Längen der Katheten und $c$ die Länge der Hypothenuse in einem rechtwinkligen Dreieck." wird es zu einer Aussage.
   
- Aussagen sollten *allgemeingültig* sein d.h. von jedermann logisch nachvollziehbar sein.
  
- Ob bewiesen ist, dass eine Aussage wahr/falsch ist, ändert nichts daran, dass es sich um eine Aussage handelt.

# Wahrheitstafeln
weisen für sämtlichen Kombinationen der Wahrheitswerte der Variablen neue Wahrheitswerte aus.
# Zusammensetzung von Aussagen durch Operatoren

Logische Operatoren verknüpfen gegebene Aussagen basierend ihrer jeweiligen Wahrheitstafel zu einer neuen Aussage.

>[!def] Negation / Verneinung
>Die Negation einer Aussage $\mathcal{A}$ wird beschrieben mit $\neg \mathcal{A}$. 
>
> | $\mathcal{A}$ | $\neg \mathcal{A}$ |
> | --- | -------- |
> | 0   | 1        |
> | 1   | 0        |
> 
>---
Die Negation wird vor allen anderen Operatoren ausgeführt (vgl. Punkt-vor-Strich)  ^2f2183
>
>---
> Bei der Negation von Aussagen, die mehrere Objekte betreffen, muss *sehr genau* aufgepasst werden: Mehr dazu bei [[Quantoren#Verneinung von Quantoren|Verneinung von Quantoren]].





>[!def] Konjunktion
>Die Konjunktion (logisches **Und**) zweier Aussagen $\mathcal{A}$ und $\mathcal{B}$ wird beschrieben mit $A \wedge B$
>
>
>|$\mathcal{A}$     |$\mathcal{B}$     | $\mathcal{A\wedge B}$
>| --- | --- | --- |
>|  0   |0   | 0|
>|  0   |1   | 0|
>|  1   |0   | 0|
>| 1  | 1   | 1|

>[!def] Disjunktion
>Die Disjunktion (logisches **Oder**, *nicht aber XOR*) zweier Aussagen $A$ und $B$ wird beschrieben mit $A \vee B$
>
>|$\mathcal{A}$     |$\mathcal{B}$     | $\mathcal{A\vee B}$
>| --- | --- | --- |
>|  0   |0   | 0|
>|  0   |1   | 1|
>|  1   |0   | 1|
>| 1  | 1   | 1|

## Zusammengesetzte Aussagen

**Klammern sind wichtig** - Aussagenlogik ist nicht immer [[Einfache Rechengesetze#Assoziativgesetz|assoziativ]].

z.B. : 
$$
\begin{align}
W \vee(W\wedge F) &\neq (W\vee W)\wedge F \\
W\vee F &\neq W \wedge F \\
W  &\neq F
\end{align}
$$
### Konstruieren neuer Aussagen
Mann kann somit aus gegebenen Aussagen und den [[#Logische Operatoren|Logischen Operatoren]] neue Aussagen konstruieren.

Das "Entweder-Oder" (XOR) lässt sich z.B. so herleiten:

gewünschte Wahrheitstafel:

| A   | B   | XOR(A,B) |
| --- | --- | -------- |
| W   | W   | F        |
| W   | F   | W        |
| F   | W   | W        |
| F   | F   | F        |

Zusammengesetze Aussage, welche dazu führt:
$(A\vee B)\wedge \neg(A \wedge B)$

| A   | B   | $A \vee B$ | $\neg(A\wedge B)$ | $(A \vee B) \wedge \neg (A \vee B)$ |
| --- | --- | ---------- | ----------------- | ----------------------------------- |
| W   | W   | W          | F                 | F                                   |
| W   | F   | W          | W                 | W                                   |
| F   | W   | W          | W                 | W                                   |
| F   | F   | F          | W                 | F                                   |

### Tautologie und Widerspruch
>[!def] Tautologie
>Eine Aussage, die für alle Wahrheitswerte der Grundannahmen wahr ist, heißt **Tautologie**.

 $A \vee \neg A$ ist eine Tautologie


>[!def] Widerspruch
>Eine Aussage, die für alle Wahrheitswerte der Grundannahmen falsch ist, heißt **Widerspruch**

$A \wedge \neg A$ ist ein Widerspruch.

Es folgt:
	Sei $A$ eine Tautologie, dann ist $\neg A$ ein Widerspruch.
	Sei $B$ ein Widerspruch, dann ist $\neg B$ eine Tautologie.

# Implikation

Die **Implikation** bildet den sprachlich oft als "*Wenn, ... , dann ...*" beschriebenen Zusammenhang ab.


>[!def] Implikation
>Sind $A$ und $B$ zwei Aussagen, dann können wir eine weitere zusammengesetzte Aussage mit Hilfe der **Folgerung (Implikation)** erzeugen:
>$$A \implies B$$
>
>Dies entspricht sprachlich:
>- "Aus $A$ folgt $B$"
>- "$A$ impliziert $B$"
>- "Wenn $A$ gilt, dann gilt auch $B$"
>  
>  Die [[#Wahrheitstafeln|Wahrheitstafel]] der Implikation ist:
>
> | $A$ | $B$ | $A\implies B$ |
> | --- | --- | --- |
> |  W   | W    | W  |
> |  W   | F    | F  |
> |  F   | W    | W  |
> |  F   | F    | W  |

#### Frage: 
*Warum führt A="F" dazu, dass die Implikation Wahr ist?* 

#### Erklärungsansätze:

1.  *Man kann die Implikation lesen wie einen **Konjunktiv**:*

> „Wenn A wahr wäre, dann wäre B wahr.“

- **Fall A = W, B = F** → Versprechen gebrochen → Falsch.
    
- **Fall A = F** → „Wenn A wahr wäre…“ ist ein hypothetisches Szenario, das nie eintritt.  
    Deshalb: egal, was B ist, die Aussage **wird nicht verletzt** → Implikation gilt.

2. *Eine Implikation ist formal ein **Versprechen**:*

> „Wenn A eintritt, dann sorge ich dafür, dass B eintritt.“

- A = W, B = W → alles erfüllt → wahr
    
- A = W, B = F → Versprechen gebrochen → falsch
    
- A = F → Das Versprechen wird gar nicht getestet → man kann nichts gegen das Versprechen sagen → wahr
    
>[!satz] Intuitiv:
> **Ein Versprechen ist nicht gebrochen, wenn die Bedingung nie eintritt.**

