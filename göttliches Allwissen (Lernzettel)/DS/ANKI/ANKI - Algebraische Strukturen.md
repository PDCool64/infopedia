TARGET DECK: DS

# Gruppen und Monoide

Welche zwei Komponenten definieren eine algebraische Struktur #flashcard
- Eine Menge
- Eine oder mehrere Verknüpfungen
<!--ID: 1769077654497-->


Was unterscheidet eine Gruppe von einem Monoid #flashcard
Jedes Element ist invertierbar
<!--ID: 1769077654500-->


Kann ein Monoid mehrere neutrale Elemente haben  #flashcard
Nein
<!--ID: 1769077654502-->

Definiere eine Untergruppe $U$ der Grupp $G$ #flashcard
Eine Menge $U\subseteq G$ ist Untergruppe, wenn für alle $x,y\in U$ gilt
- $x\cdot y\in U$ 
- $x^{-1}\in U$
Also muss eine Untergruppe *abgeschlossen* bzgl. Verknüpfung und Inversenbildung sein.


# Ringe

Welche Anforderung muss die Addition "$+$"  auf einem Ring $R$ erfüllen #flashcard
$(R,+)$ muss *abelsche Gruppe* sein
<!--ID: 1769077654505-->


Welche Anforderung muss die Multiplikation " $\cdot$ "  auf einem Ring $R$ erfüllen #flashcard
$(R,\cdot)$ muss *Monoid* sein
<!--ID: 1769077654507-->


Wann heißt ein Ring kommutativ #flashcard
Wenn die *Multiplikation* ebenfalls kommutativ ist
<!--ID: 1769077654510-->


Können in einem Ring das neutrale Element von $\cdot$ und von $+$ gleich sein  #flashcard
Ja
(betrachte den einelementigen Ring)
<!--ID: 1769077654512-->


# Körper

Definiere einen Körper #flashcard
Ein *kommutativer* Ring heißt Körper, wenn
- Jedes Element bis auf $0$ ist auch bei der Multiplikation invertierbar
  also $K^{\times}=K \setminus\{ 0 \}$
- $1\neq 0$ muss gelten
<!--ID: 1769077654515-->

Ist die Multiplikation in einem Körper immer kommutativ #flashcard
Ja

# Nullteiler und Einheiten

Welche Eigenschaft muss ein Ring erfüllen, damit der Begriff "Nullteiler" überhaupt definiert ist. #flashcard
Nullteiler betrachten wir nur auf *kommutativen* Ringen.

Definiere einen Nullteiler #flashcard
$a\in R$ ist Nullteiler des *kommutativen* Rings $R$,
wenn ein $b\in R \setminus\{ 0 \}$ existiert, sodass
$$
a\cdot b = 0
$$

Wann ist ein Ring *nullteilerfrei* #flashcard
Wenn er keine Nullteiler außer $0$ enthält

Definiere einen Integritätsbereich #flashcard
Kommutativer Ring mit
- $1\neq 0$
- nullteilerfrei

Kann ein Element eines kommutativen Rings sowohl Nullteiler als auch Einheit sein #flashcard
Nein

Welche wichtige algebraische Struktur ist ein Spezialfall des Integritätsbereichs #flashcard
Körper


Definiere eine Einheit in einem Monoid #flashcard
$a$ ist Einheit, wenn es ein $b$ gibt, so dass
$a\cdot b=1=b\cdot a$

Wie viele Lösungen kann die Gleichung $x\cdot a =b$ in einer *Gruppe* haben #flashcard 
Es existiert immer *genau* eine eindeutige Lösung.

Was ist die Einheitengruppe $G^{\times}$ einer Gruppe $G$ #flashcard
In einer Gruppe gilt per Definition $G^{\times}=G$

