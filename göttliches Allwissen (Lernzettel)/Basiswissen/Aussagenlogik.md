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
>Die **Negation** einer Aussage $\mathcal{A}$ wird beschrieben mit $\neg \mathcal{A}$. 
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
>Die **Konjunktion** (*Und*-Verknüpfung) zweier Aussagen $A$ und $B$ wird beschrieben mit $A \wedge B$
>
>
>|$A$     |$B$     | $A\wedge B$
>| --- | --- | --- |
>|  0   |0   | 0|
>|  0   |1   | 0|
>|  1   |0   | 0|
>| 1  | 1   | 1|

>[!def] Disjunktion
>Die **Disjunktion** (*Oder*-Verknüpfung) zweier Aussagen $A$ und $B$ wird beschrieben mit $A \vee B$
>
>|$A$     |$B$     | $A\vee V$
>| --- | --- | --- |
>|  0   |0   | 0|
>|  0   |1   | 1|
>|  1   |0   | 1|
>| 1  | 1   | 1|
> ---
> Die Disjunktion ist das *inklusive* Oder. D.h. auch beide Aussagen können war sein. Dies steht im Gegensatz zum *exklusiven* Oder, welches $\text{xor}$ geschrieben wird und nur dann wahr ist, wenn *genau eine* der beiden Aussagen wahr ist.


>[!def] Subjunktion
> Die **Subjunktion** (*wenn-dann*-Vernknüpfung) zweier Aussagen $A$ und $B$ wird beschrieben mit $A\to B$ 
> 
> | $A$ | $B$ | $A\to B$ |
> | --- | --- | -------- |
> | 0   | 0   | 1        |
> | 0   | 1   | 1        |
> | 1   | 0   | 0        |
> | 1   | 1   | 1        |
> Die Subjunktion ist nur genau dann falsch, wenn $A$ wahr und $B$ falsch sind.
> 
> ---
> 
> Anders als $A\vee B$ oder $A\wedge B$ ist die Subjunktion *nicht* symmetrisch.

>[!def] Bijunktion
> Die Bijunktion (*genau-dann*-Verknüpfung) zweier Aussagen $A$ und $B$ wird beschrieben mit $A\leftrightarrow B$ 
> 
> | $A$ | $B$ | $A\leftrightarrow B$ |
> | --- | --- | -------- |
> | 0   | 0   | 1        |
> | 0   | 1   | 0       |
> | 1   | 0   | 0        |
> | 1   | 1   | 1        |
> Die Bijunktion ist nur genau dann wahr, wenn $A$ und $B$ die gleichen Wahrheitswerte haben. d.h. wenn beide wahr sind oder wenn beide falsch sind.
> 


# Logische Terme

>[!def]
> Ein **logischer Term** ist ein Ausdruck bestehend aus Variablen $A,B,\dots$ und den Konstanten $w,f$ bzw. $0,1$ , die *verknüpft sind* mit den [[#Zusammensetzung von Aussagen durch Operatoren|Symbolen]] $\neg\;,\,\vee\;,\;\wedge\;,\;\text{xor}\;,\;\to\;,\; \leftrightarrow$ sowie Klammern.
> 
> Terme sind aus dem Alphabet der Aussagenlogik zusammengesetzte Worte.
> 
> Durch rekursives anwenden der folgenden Muster kann man aus beliebigen schon existierenden Wörtern $F$ und $G$ neue Wörter nach den Folgenden Regeln bilden:
> - $\neg(F)$
> - $(F)\vee(G)$
> - $(F)\wedge(G)$
> - $(F)\to(G)$
> - $(F)\leftrightarrow(G)$
> 
> durch rekursives Anwenden dieser Regeln kann man beliebige neue Terme bilden.
> 
> ---
> 
> Durch Belegung der Variablen mit Wahrheitswerten bekommt de Term selbst einen Wahrheitswert.

## Regeln bei zusammengesetzten Aussagen

1. **Klammern sind wichtig** - Aussagenlogik ist oft nicht [[Einfache Rechengesetze#Assoziativgesetz|assoziativ]].
   z.B. : 
$$
\begin{align}
w \vee(w\wedge f) &\;\cancel{ \iff }\; (w\vee w)\wedge f \\
w\vee f&\;\cancel{ \iff }\; w \wedge f \\
w  &\;\cancel{ \iff }\; f
\end{align}
$$
2. Die [[#^2f2183|Negation]] wird vor allen anderen Verknüpfungen ausgeführt.
   (Dies ist eine Konvention, um sich das Schreiben von unnötig vielen Klammern zu sparen)

# Implikation und Äquivalenz
>[!def] Implikation
> Die **Implikation** $A\implies B$ drückt aus, dass die Aussage $(A\to B)$ den Wahrheitswert $w$ hat. 
> 
> Man sagt dann:
> - "Aus $A$ folgt $B$"
> - "$A$ impliziert $B$"
> - "Wenn $A$, dann $B$"
> - "$A$ ist [[Notwendige vs hinreichende Bedingung#Hinreichende Bedingung|hinreichend]] für $B$"


Die 


# Tautologie und Widerspruch
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

