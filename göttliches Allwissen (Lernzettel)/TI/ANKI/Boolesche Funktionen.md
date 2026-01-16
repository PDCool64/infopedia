TARGET DECK: TI

# Vereinfachung Boolescher Funktionen

Wie lauten die Resolutionsregeln #flashcard
$$
ab+\bar{a}b = a
$$
$$
(a+b)(\bar{a}+b)=a
$$
<!--ID: 1768579545590-->


Was ist ein Implikant $M$ einer booleschen Funktion $f$ #flashcard
Ein Term, so dass wenn er war ist, auch die boolesche Funktion wahr ist.
$$
M(x)=1 \implies f(x)=1
$$
für alle $x$.
<!--ID: 1768579545593-->


Was ist ein Primimplikant #flashcard
Ein Implikant, von dem keine echte Verkürzung noch Implikant ist.
<!--ID: 1768579545595-->


Was ist ein Kernimplikant  #flashcard
Ein Primimplikant, der in *jedem* Minimalpolynom vorkommt.
> z.B. Boxen, die man im KV Diagramm zeichnen *muss* um alle $1$en abdecken zu können.
<!--ID: 1768579545598-->



Was ist ein Minimalpolynom #flashcard
Eine Disjunktive (=$\text{ODER}$) Form, deren Länge nicht zu unterbieten ist
<!--ID: 1768579545600-->


Was sucht man bei der Vereinfachung von booleschen Funktionen letztendlich #flashcard
*Menge von Primimplikanten,* welche die Funktion vollständig abdecken
bzw. das *Minimalpolynom* welches diese bilden.
<!--ID: 1768579545603-->


Worauf basieren die Verfahren zur Vereinfachung boolescher Funktionen #flashcard
Resolutionsregel
<!--ID: 1768579545605-->


Nenne drei wichtige Verfahren zum Vereinfachung boolescher Funktionen #flashcard
- KV-Diagramme (Karnaugh-Veich)
- Quine-McCluskey-Verfahren
- OBDDs 
<!--ID: 1768579545607-->



# Funktionale Vollständigkeit

Wann ist eine Menge an logischen Operatoren sowie ggfs. Konstanten *funktional vollständig* #flashcard
Wenn sich mit ihnen jede boolesche Funktion darstellen lässt
<!--ID: 1768579545610-->


Nenne vier wichtige *funktional vollständige* Systeme #flashcard
- $\{ \neg,\land \}$
- $\{ \neg,\lor \}$
- $\{ \text{NAND} \}$
- $\{ \text{NOR} \}$
<!--ID: 1768579545612-->


Wie zeigt man, dass eine Menge an logischen Operatoren sowie ggfs. Konstanten *funktional vollständig* ist #flashcard
Konstruiere aus ihr die Operatoren eines bekannten funktional vollständigen Systems
<!--ID: 1768579545615-->



# Fehlerdiagnose
