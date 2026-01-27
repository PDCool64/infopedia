TARGET DECK: DS

Eine Relation zwischen $M$ und $N$ ist Teilmenge welcher Menge? #flashcard
Die Relation $R \subseteq M \times N$

häufiges Symbol für Relationen? #flashcard
~

Ein besonderer Spezialfall von Relationen? #flashcard
Abbildungen

Für die Relation $R$ gilt $xRx$, was ist die Relation? #flashcard
Reflexiv

Für die Relation $R$ gilt $xRy \implies yRx$, was ist die Relation? #flashcard
Symmetrisch

Für die Relation $R$ gilt $xRy \land yRx \implies x = y$, was ist die Relation? #flashcard
Antisymmetrisch

Für die Relation $R$ gilt $xRy \land yRz \implies xRz$, was ist die Relation? #flashcard
Transitiv

Für die Relation $R$ gilt $xRy \lor yRx$, was ist die Relation? #flashcard
Vollständig

Was gilt für eine reflexive Relation? #flashcard
$$
xRx
$$

Was gilt für eine symmetrische Relation? #flashcard
$$
xRy 0> yRx
$$

Was gilt für eine antisymmetrische Relation? #flashcard
$$
xRy \land yRx \implies x = y
$$

Was gilt für eine transitive Relation? #flashcard
$$
xRy \land yRz \implies xRz
$$

Was gilt für eine vollständige Relation? #flashcard
$$
xRy \lor yRx
$$

Was bedeutet die Vollständigkeit für eine Relation? #flashcard
Jedes beliebige Paar an Elementen ist bzgl der Relation vergleichbar. 

Eine Äquivalenzordnung ist? #flashcard
Reflexiv, symmetrisch und transitiv

Eine Präordnung ist? #flashcard
Reflexiv und transitiv

Eine Ordnung (oder auch partielle Ordnung) ist? #flashcard
Reflexiv, antisymmetrisch und transitiv

Eine totale Ordnung ist? #flashcard
Reflexiv, antisymmetrisch, transitiv und vollständig

Wie ist eine Äquivalenzklasse definiert?? #flashcard
 $$
 \left[ x \right] :=\left[ x \right] _{C}:=\{ y\in M \mid xCy\}= \{ y\in M \mid yCx \}
$$

Wie viele Elemente können sich Äquivalenzklassen teilen? #flashcard
Äquivalenzklassen sind entweder gleich oder disjunkt. Sie teilen sich keine Elemente

Sei $C$ eine beliebge Relation auf der Menge $M$, was bedeutet $M/C$? #flashcard
$$
M/C := {[x]_{C} | x \in M}
$$
$M/C$ bezeichnet die Menge aller Äquivalenzklassen auf der Menge $M$

Was macht die Quotientenabbildung? #flashcard
Quotientenabbildung
 Die **Quotientenabbildung** $\kappa$ ("Kappa") bildet jedes Element einer Menge $M$ auf seine Äquivalenzklasse unter der Äquivalenzrelation $C$ ab:
 $$
 \kappa : M\to M /C \;,\;x \mapsto \left[ x \right] _{C}
 $$

// Ab hier ist ein bisschen AI im Spiel - vielleicht ist das großer Schwachsinn, dann tut mir das leid, aber ich verspreche, das davor hab ich selber gemacht ;)

Was besagt der Hauptsatz über Äquivalenzrelationen? #flashcard  
Die Quotientenmenge einer Äquivalenzrelation ist eine Partition der Menge, und jede Partition entsteht so aus genau einer Äquivalenzrelation.

Die Äquivalenzklassen einer Äquivalenzrelation entsprechen was? #flashcard  
Genau den Teilen der zugehörigen Partition.

Zwischen welchen Mengen besteht eine Bijektion im Hauptsatz der Äquivalenzrelationen? #flashcard  
Zwischen der Menge aller Äquivalenzrelationen auf $M$ und der Menge aller Partitionen von $M$.

Was ist eine Partition einer Menge? #flashcard  
Eine Menge nichtleerer, paarweise disjunkter Teilmengen, deren Vereinigung die ganze Menge ergibt.

Was sind Fasern einer Abbildung $f:M\to N$? #flashcard  
Die Mengen $f^{-1}({y})$ aller Elemente aus $M$, die auf dasselbe $y\in N$ abgebildet werden.

Was bilden die nicht-leeren Fasern einer Abbildung? #flashcard  
Eine Partition der Definitionsmenge $M$.

Was ist die Bildgleichheit zu einer Abbildung $f:M\to N$? #flashcard

$x Rf x′  \iff   f(x)=f(x′)x\,R_f\,x' \iff f(x)=f(x')xRf​x′⟺f(x)=f(x′)$

Welche Art von Relation ist die Bildgleichheit $R_f$? #flashcard  
Eine Äquivalenzrelation.

Was ist die Quotientenabbildung zur Bildgleichheit? #flashcard

$κ:M→M/Rf,x↦[x]Rf\kappa:M\to M/R_f,\quad x\mapsto [x]_{R_f}κ:M→M/Rf​,x↦[x]Rf​​$

Was besagt der Homomorphiesatz für Mengen? #flashcard  
Zu jeder Abbildung $f:M\to N$ existiert eine wohldefinierte Abbildung $\hat f:M/R_f\to N$ mit $f=\hat f\circ\kappa$.

Wie ist die Abbildung $\hat f$ im Homomorphiesatz definiert? #flashcard

$f^([x]Rf)=f(x)\hat f([x]_{R_f}) = f(x)f^​([x]Rf​​)=f(x)$

Warum ist $\hat f$ wohldefiniert? #flashcard  
Weil alle Elemente einer Äquivalenzklasse unter $R_f$ denselben Funktionswert haben.

Welche Eigenschaften hat $\hat f$ im Homomorphiesatz? #flashcard  
$\hat f$ ist injektiv und erfüllt $\hat f(M/R_f)=f(M)$.

Was ist ein Abschluss einer Relation? #flashcard  
Die kleinste Obermenge einer Relation, die eine gewünschte Eigenschaft erfüllt.

Was bedeutet „minimal groß“ bei Abschlüssen? #flashcard  
Jede andere Relation mit der gewünschten Eigenschaft, die $R$ enthält, ist mindestens so groß.

Was ist der transitive Abschluss einer Relation? #flashcard  
Die kleinste transitive Relation, die die ursprüngliche Relation enthält.

Wann gilt $xSy$ im transitiven Abschluss? #flashcard  
Wenn es eine endliche Kette gibt:

$xRx0Rx1⋯RxnRyxRx_0Rx_1\cdots Rx_nRyxRx0​Rx1​⋯Rxn​Ry$

Was ist der reflexive Abschluss einer Relation? #flashcard  
Die kleinste reflexive Relation, die $R$ enthält.

Wie erhält man den reflexiven Abschluss explizit? #flashcard

$S=R∪{(x,x)∣x∈M}S = R \cup \{(x,x)\mid x\in M\}S=R∪{(x,x)∣x∈M}$

Wann gilt $xSy$ im reflexiven Abschluss? #flashcard

$xSy  ⟺  xRy∨x=yxSy \iff xRy \lor x=yxSy⟺xRy∨x=y$

Was ist der symmetrische Abschluss einer Relation? #flashcard  
Die kleinste symmetrische Relation, die $R$ enthält.

Wann gilt $xSy$ im symmetrischen Abschluss? #flashcard

$xSy  \iff  xRy∨yRxxSy \iff xRy \lor yRxxSy⟺xRy∨yRx$

Welche Abschlüsse sind immer eindeutig und existent? #flashcard  
Der reflexive, symmetrische und transitive Abschluss.

Warum kann Antisymmetrie nicht durch einen Abschluss erzwungen werden? #flashcard  
Weil Antisymmetrie das **Nicht-Existieren** bestimmter Paare verlangt.
