>[!wip]
> Diese Notiz ist noch nicht auf dem rigoroseren Stand der DS Vorlesung: z.B. fehlen Terme, die Unterscheidung zwischen Subjunktion und Implikation usw. Es wird auf das [[Skript Diskrete Strukturen.pdf]] verwiesen.


---


>[!def] Aussage:
>Eine (mathematische) Aussage ist eine sprachlich oder symbolisch formulierte Behauptung, der auf eindeutiger Weise ein Wahrheitswert, nämlich *wahr (W)* oder *falsch (F)* zugeordnet werden kann.

^8f29c5

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
> ---
> Das man aus einer Falschen Aussage alles folgern kann ist nicht ganz intuitiv.
> Erklärungsansatz: 

^7a467a

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

^075f1b

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
> Durch rekursives Anwenden dieser Regeln kann man beliebige neue Terme bilden.
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
> Die **Implikation** ist $A\implies B$ drückt aus, dass die Aussage $(A\to B)$ den Wahrheitswert $w$ hat. 
> 
> Man sagt dann:
> - "Aus $A$ folgt $B$"
> - "$A$ impliziert $B$"
> - "Wenn $A$, dann $B$"
> - "$A$ ist [[Notwendige vs hinreichende Bedingung#Hinreichende Bedingung|hinreichend]] für $B$"

>[!def] Genau dann, wenn
> 
> "$A$ Genau dann. wenn $B$", geschrieben durch $A\iff B$ drückt aus, dass die Aussage $(A\leftrightarrow B)$ den Wahrheitswert $w$ hat.
> 
> Man sagt dann:
> - "$A$, genau dann, wenn $B$"
> - "$A$ dann und nur dann, wenn $B$"
> - "$A$ ist [[Notwendige vs hinreichende Bedingung#Äquivalente Bedingung|notwendig und hinreichend]] für $B$"


>[!def] Wertverlaufsgleich / Logisch Äquivalent
> Zwei Logische Terme $S$ und $T$, definiert auf derselben Variablenmenge, heißen **logisch äquivalent** oder **wertverlaufsgleich**, geschrieben $S\equiv T$, wenn $S$ und $T$ denselben Wahrheitswert haben für jede Belegung der Variablen.

## Unterscheidung: Subjunktion vs. Implikation bzw. Bijunktion vs. Äquivalenz
>[!wip]
> 
> Hier ist man auf dünnen Eis unterwegs - Wirklich rigoros haben wir dass hier alles nicht gemacht und die Erklärungen vom Fragestunden-Dude waren auch ein bisschen komisch.
> 
> Für die Zwecke der DS Vorlesung ist die genaue Unterscheidung angeblich bald schon nichtmehr wirklich wichtig.


Die [[#^7a467a|Subjunktion]] $A\to B$ ist einfach logischer Operator, genau wie $\vee,\wedge$ und Co. : Er verknüpft zwei Aussagen basierend auf seiner Wahrheitstafel zu einer neuen Aussage. 
![[Aussagenlogik 2025-10-18 12.26.09.excalidraw]]

Die [[#^4f7e2e|Implikation]] hingegen ist kein logischer Operator, sondern eine Schreibweise um auf "Metabene" über Aussagen zu reden. 
![[Aussagenlogik 2025-10-18 12.29.28.excalidraw]]


Ebenso für Bijunktion und "Genau dann, wenn" :

Die [[#^075f1b|Bijunktion]] $A\leftrightarrow B$ ist einfach logischer Operator, genau wie $\vee,\wedge$ und Co. : Er verknüpft zwei Aussagen basierend auf seiner Wahrheitstafel zu einer neuen Aussage. 
![[Aussagenlogik 2025-10-18 12.34.51.excalidraw]]

"Genau dann, wenn" $\iff$ hingegen ist kein logischer Operator, sondern eine Schreibweise um auf "Metabene" über Aussagen zu reden. 
![[Aussagenlogik 2025-10-18 12.36.12.excalidraw]]

### TL:DR
- Wenn man aus zwei Aussagen mit einem logischen Operator zu einer neuen Aussage verknüpfen so, schreibt man $\leftrightarrow$
- Wenn man auf "Metaebene" sagen will, dass aus einer Aussage eine andere folgt (z. B für einen Beweis), dann schreibt man $\implies$.

>[!wip]
> Ob es einen Unterschied zwischen $\equiv$ und $\iff$ gibt kann uns angeblich recht bald egal sein - wir werden wohl bald fast nur noch $\iff$ sehen.

# Tautologie und Widerspruch
>[!def] Tautologie
>Ein Logischer Term $T$ heißt **Tautologie**, wenn $T\equiv w$, d.h. wenn der Term für alle Belegungen der Variablen immer wahr ist.

Bsp:
 $A \vee \neg A$ ist eine Tautologie

>[!def] Widerspruch
>Eine Aussage, die für alle Wahrheitswerte der Grundannahmen falsch ist, heißt **Widerspruch**

$A \wedge \neg A$ ist ein Widerspruch.

Es folgt:
	Sei $A$ eine Tautologie, dann ist $\neg A$ ein Widerspruch.
	Sei $B$ ein Widerspruch, dann ist $\neg B$ eine Tautologie.


# Frage: Warum kann man aus einer Falschen Aussage alles folgern ?

Gegeben sie die Implikation $A\implies B$ 

Die Wahrheitstafel der zugrundeliegenden Subjunktion ist:

| $A$ | $B$ | $A\to B$ |
| --- | --- | -------- |
| 0   | 0   | 1        |
| 0   | 1   | 1        |
| 1   | 0   | 0        |
| 1   | 1   | 1        |

### *Warum führt  $A=f$ dazu, dass die Implikation Wahr ist?* 

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


# Aussageformen

>[!def] Aussageform
> Eine **Aussageform** ist ein sprachlicher Ausdruck, der Variablen enthält, und der für jede Belegung aller vorkommenden Belegung mit *konkreten Objekten* zu einer [[#^8f29c5|Aussage]] wird.
> 
> ---
> (Da es konkrete Objekte seien müssen sorgt in der Regel dafür, dass man die Auswahl der Objekte mit denen die Variablen belegt werden können einschränkt / explizit definiert. Häufig sind z.B. einzelne [[Zahlenräume]])
> 
> ---
> Eine Aussageform selbst ist *keine* Aussage. Dies liegt daran, dass die Aussageform keinen eindeutigen Wahrheitswert hat, da dieser von der Belegung der Variablen abhängt.
> 
> Die Zusammensetzung von Aussageformen mit den [[#Zusammensetzung von Aussagen durch Operatoren|Operatoren]] erzeugt wieder eine Aussageform.

## Bsp. 1:
"Wenn $x>0$, dann ist $x$ ein Quadrat" ist eine Aussageform. Erst wenn Variable $x$ konkret mit einer reellen Zahl belegt wird, erhalten wir eine Aussage(Eines eindeutigen Wahrheitswertes)

