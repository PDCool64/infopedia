---
"date:": 2025-10-13
tags:
  - PROGRA
status: gelb
Ab Folie: 0
Bis Folie: 33
---
# Begriffe der Informatik
## Algorithmus
"Idee der Lösungsbeschreibung" (abstrakt; übertragbar)
### Eigenschaften:
- **Endlich**: (nicht von der Laufzeit, sondern von der Länge in der sich der Algorithmus selbst formulieren lässt) 
  
- **Effektiv:** Für eine Maschine ausführbar (=Umsetzbar)
  
- **Deterministisch:** der Algorithmus legt eindeutig fest, welche Elementaroperation als nächstes ausgeführt wird.
  
- **Determiniertheit:** Zu jeder Eingabe gibt es genau eine Ausgabe.
  
- **Terminierung**: Der Algorithmus hält immer nach endlich vielen Schritten an.

Die Eigenschaften *Determinismus, Determiniertheit, Terminierung* werden nicht immer verlangt.

>[!def] Deterministisch vs. Determinierheit
> Deterministisch $\neq$ Determiniertheit
> 
> Es gibt z.B. Determinierte Algorithmen, die nicht deterministisch sind
> 

## Eigenschaften von *"guten"* Algorithmen

- **Allgemeinheit**: Ein Algorithmus sollte nicht nur ein einziges Problem Lösen, sondern gleich eine ganze Problemklasse. (Niemand braucht einen Algorithmus der nur 3+8=11; nicht aber 2+4=6 rechnen kann)
  
- **Änderbarkeit**: Ein Algorithmus sollte leicht modifizierbar sein

- **Effizienz**: Der Ressourcenverbrauch, insbesondere die Anzahl der Rechenschritte sollte möglichst gering sein.
  
- **Robustheit**: Ein Algorithmus sollte selbst bei ungültigen Eingaben ?(habe mitschrift verkackt)deterministisch? arbeiten und ggfs. den benutzer warnen


## Programm
"Formulierung des Algorithmus in einer Programmiersprache" 



# Grundlagen von Programmiersprachen

## Syntax
Definition aller *zulässigen Wörter / Programme*, die in einer Sprache formuliert werden können

Beispiele:
- Nach jeder öffnenden Klammer muss auch eine schließende Klammer kommen

## Semenatik:
- *Bedeutung* der zulässigen Wörter / Programme
- Syntaktisch falsche Wörter/Programme haben keine Semantik


### Beispiel
z.B. : Die Sprache aller natürlichen Zahlen außer $0$.
**Syntax**: Jede Zahl ist eine Folge von Ziffern $\{ 0,1,2,\dots,9 \}$, wobei die erste Ziffer $\neq 0$.

**Semantik**:
Wert einer Zahl aus mehreren Ziffern ist der Wert der letzten Ziffern plus der 10-fache Wert der Zahl links davon. Der Wert einer Zahl ist die Ziffer selbst

#### Test:
Syntax:
$367$ ist syntaktisch Korrekt

Semantik:
$$
\begin{align}
&\text{wert(367)} \\
=&\text{wert}(7)+10(\text{wert(36)}) \\
=&7 + 10(wert(6)+10(\text{wert(3)})) \\
=&7+10(6+10\cdot 3) \\
=&367
\end{align}
$$
Hingegen ist $007$ nicht syntaktisch korrekt.

# Eigenschaften

Die Programmiersprache bildet die Schnittstelle zwischen Mensch und Rechner

Beide haben unterschiedliche Anforderungen:

Mensch:
- Erlernbarkeit
- Lesbarkeit
- Ausdrucksstärke

Rechner:
- einfaches Übersetzen in Maschinensprache
- Generierung von Effizienten Codes
- (Kann eigentlich nur sein limitiertes instruction set)

## Gruppen von Programmiersprachen

### Imperativen Sprachen:
kommt von "Imperativ" d.h. Anweisung
Folge von nacheinander ausgeführten Anweisungen

#### Prozedurale Sprachen
- Variablen, Zuweisungen, Kontrollstrukturen (Schleifen usw.)

####  Objektorientierte Sprachen
- Objekte und Klassen
- ADT und Vererbung
### Deklarative Sprachen

#### Funktionale Sprachen#
- *KEINE* Seiteneffekte
- Rekursion (keine Schleifen)
#### Logische Sprachen
- Regeln zur Definition von Relationen.
  
### Sprachen die wir verwenden werden
- Imperative Programmierung (Java)
- Objektorientierte Programmierung (Java)
- Funktionale Programmierung (Haskell)
- Logische Programmierung (Prolog)

# Alphabet und formale Sprache

## Alphabet
*nichtleere, endliche* Menge von Zeichen ("Buchstaben", Symbole)

- das lateinische Alphabet $\{ a,b,c,d\dots,z \}$
- `ASCII` (American Code of Information Interchange)
- $A_{1}=\{ 0,1 \}$
- $A_{2}=\{ (,),+,-,*, \setminus,\alpha\}$


## Wörter
*endliche Folge* von Buchstaben, die auch *leer* sein kann ($\epsilon$ als leeres Wort).
 $A^{*}$ ist die Menge aller Wörter über dem Alphabet $A$ (inkl. dem leeren Wort)

## Formale Sprache
Sei $A$ ein Alphabet. 
Eine (formale) Sprache (über A) ist eine beliebige Teilmenge von $A^{*}$ 


# Kontextfreie Grammatik
Eine kontextfreie Grammatik ist ein 4-Tuple
$G=(N,T,P,S)$

- $N$ ist eine endliche Menge an **Nichtterminalen**
- $T$ ist eine endliche Menge an **Terminalen** 
  
- $N \cap T = \emptyset$ (Ein Symbol kann nicht gleichzeitig Terminal und Nichtterminal seien.)
- (Schreibweise für unten: $N \cup T=V$)
  
- $P$ ist eine endliche Menge an **Produktionsregeln**: $X\to Y$
  mit
   $X \in V$ (links steht genau ein Nichtterminal)
   $Y \in V^{*}$ (recht kann jede Kombination aus Terminalen und Nichtterminalen Stehen)

- $S$ als Startysmbol

(einzige Einschränkung: In $Y$ muss mindestens ein Nichtterminal vorkommen.)

Die meisten Programmiersprachen die wir kennen sind kontextfrei.

(Haben wir noch nicht explizit gemacht: Kontextfreie Grammatiken sind gleichbedeutend mit Kellerautomaten)



## Sprache einer Grammatik
Die Sprache $L(G)$ einer Grammatik $G$ :
$$
L(G)=\{ w \mid w\in T^{*} \mid S \implies  \dots \implies w\}
$$
d.h. alle Terminalwörter die aus dem Startsymbol mit Hilfe der Produktionsregeln $P$ ableitbar sind.

Zwei Grammatiken sind äquivalent, wenn sie die gleiche Sprache erzeugen.
(Es ist oft möglich, mehrer Grammatiken zur gleichen Sprache zu bilden)


Eine Sprache ist kontextfrei, wenn sie von einer Kontextfreien Grammatik erzeugt werden kann.
(s.h. Beispiel auf Folie12) - Auch wenn die erste Grammatik auf die man gerade kommt nicht kontextfrei ist (sondern "höher"/mächtiger ist), kann eine Sprache sein, falls eine kontextfreie Grammatik existiert die die Sprache erzeugt.)

