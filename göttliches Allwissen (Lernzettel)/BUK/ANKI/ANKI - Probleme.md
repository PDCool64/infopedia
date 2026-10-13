TARGET DECK: BUK::Probleme

Definition: **Problem** #flashcard
Ein Problem ist eine Relation über zwei Alphabeten.
$R\subseteq\Sigma^{*}\times\Sigma'^{*}$
$(x,y)\in R\iff y\text{ ist zulässige Ausgabe zur Eingabe }x$

Definition: **Problem als Funktion** #flashcard
Bedingung: es gibt zu jeder Eingabe ein eindeutige Ausgabe.
$f:\Sigma^{*}\to\Sigma'^{*}$ bildet Eingaben auf die gesuchten Ausgaben ab.

Definition: **Entscheidungsproblem als Funktion** #flashcard
$f:\Sigma^{*}\to \{ 0,1 \}$

Definition: **Sprache eines Entscheidungsproblem** #flashcard
$L=f^{-1}(\{ 1 \})\subseteq\Sigma^{*}$
Menge derjenigen Eingaben, die mit "Ja" beantwortet werden.
