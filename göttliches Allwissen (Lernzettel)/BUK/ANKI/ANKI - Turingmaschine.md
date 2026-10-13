TARGET DECK: BUK::Turingmaschine

Definition: **Turingmaschine** #flashcard
$T=(Q,\Sigma,\Gamma,B,q_{0},\overline{q},\delta)$ mit
- $Q$ als endliche Zustandsmenge
- $\Sigma$ als endliches Eingabealphabet
- $\Gamma \supset \Sigma$ als endliches Bandalphabet
- $B\in\Gamma\setminus\Sigma$ das Leerzeichen (Blank, $\square$)
- $q_{0}\in Q$ als Anfangszustand
- $\overline{q}\in Q$ als Endzustand
- $\delta:(Q\setminus\{ \overline{q} \})\times\Gamma \to Q\times \Gamma \times \{ R,L,N \}$
  als Zustandsübergangsfunktion

Wann stoppt eine Turingmaschine? #flashcard
Genau dann, wenn sie den Endzustand $\overline{q}$ erreicht.
Eine TM kann _nicht_ blockieren; die Zustandsübergangsfunktion ist vollständig definiert.

Wie ist das Ausgabewort $y\in\Sigma^{*}$ einer TM definiert? #flashcard
Vom Band ablesen:
- von inkl. der momentanen Kopfposition
- endet unmittelbar vor dem ersten Symbol aus $\Gamma\setminus\Sigma$ 

Welche Ausgabewörter einer TM werden bei einen **Entscheidungsproblem** als Ja bzw. Nein interpretiert? #flashcard
- Ja = Ausgabewort beginnt mit $1$
- Nein = Ausgabewort beginnt nicht mit $1$

Wann wird das Ausgabewort einer TM als undefiniert bezeichnet? #flashcard
Wenn die TM bei der Berechnung mit einer Eingabe nicht terminiert.
Wir schreiben für "undefiniert" das Symbol $\perp$ .

Definiere den Speicherbedarf einer TM. #flashcard
Die Anzahl von Bandzellen, die während der Berechnung **besucht** werden.

Wie kodiert die **Konfiguration** einer TM die Informationen? #flashcard
Eine Konfiguration ist ein String $\alpha q\beta \;,\;q\in Q\;,\;\alpha,\beta\in\Gamma^{*}$.
- Auf dem Band steht $\alpha\beta$ eingerahmt von Blanks
- der Zustand ist $q$
- Der Kopf steht über dem ersten Zeichen von $\beta$
Ein Ableitungsschritt wird durch $\vdash$ geschrieben.

