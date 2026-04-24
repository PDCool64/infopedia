---
tags:
  - FOSAP
status: rot
---
---

# Reguläre Ausdrücke

>[!def] Reguläre Ausdrücke
>> [!def] Syntax von regulären Ausdrücken
>> Es sei $\Sigma$ ein Alphabet
>> 
>> Atomare Bestandteile:
>> - $\emptyset$ ist ein regulärer Ausdruck
>> - $\varepsilon$ ist ein regulärer Ausdruck
>> - $a$ ist ein regulärer Ausdruck, falls $a\in\Sigma$
>>
>> Induktive Erweiterung:
>> - $rs$ ist ein regulärer Ausdruck, falls $r$ und $s$ reguläre Ausdrücke sind.
>> - $r+s$ ist ein regulärer Ausdruck, falls $r$ und $s$ reguläre Ausdrücke sind.
>> - $r*$ ist ein regulärer Ausdruck, falls $r$ ein regulärer Ausdrücke ist.
>
> Dies beschreibt erstmal nur, was syntaktisch überhaupt ein korrekter regulärer Ausdruck ist.
> Den Zusammenhang zur *Sprache*, welche der reguläre Ausdruck erzeugt entsteht erst mit der folgenden Definition:
> 
>>[!def] Semantik von regulären Ausdrücken
>> Wir ordnen jedem regulären Ausdruck $r$ mit der Abbildung $L$ seine Sprache $L(r)$ zu.
>> 
>> Basisfälle:
>> - $L(\emptyset)=\emptyset$ 
>> 	  (Man unterscheidet in der Praxis nicht zwischen dem atomaren regulären Ausdruck $\emptyset$ und der leeren Menge/Sprache $\emptyset$)
>> - $L(\varepsilon)=\{ \varepsilon \}$  
>> 	  (Dem regulären Ausdruck $\varepsilon$ wird die Sprache, welche nur das leere Wort $\varepsilon$ enthält zugeordnet)
>> - $L(\alpha)=\{ \alpha \}$ 
>> 	  (der reguläre Ausdruck $\alpha$ für ein $\alpha\in\Sigma$ wird die Sprache welche nur genau dieses Symbol enthält zugeordnet)
>> 
>> Induktive Fälle: Definiert über die [[Alphabete, Wörter, Sprachen#Operationen auf Sprachen|Operationen auf Sprachen]]
>> - $L(rs):=L(r)L(s)=\{ uv\mid u\in L(r),v\in L(s) \}$
>> - $L(r+s):=L(r)\cup L(s)$
>> - $L(r^*):=(L(r))^*=\bigcup_{n\ge 0}(L(r))^{n}$ 

## Eigenschaften der Abbildung $L(r)$
- $L$ ist nicht surjektiv:
	  $\{  0^{n}1^{n}\mid n\in \mathbb{N}\}$ kann z.B. nicht durch reguläre Ausdrücke erzeugt werden
- $L$ ist nicht injektiv:
	 z.B. gilt: $L(r)=L(r)\cup \underbrace{ L(\emptyset) }_{ :=\emptyset } =L(r+\emptyset)$ 

# Reguläre Sprachen
>[!def] reguläre Sprache
> Eine Sprache $A\subseteq\Sigma^{*}$ ist **regulär**, falls es einen regulären Ausdruck $r$ über $\Sigma$ gibt mit $A=L(r)$.

## Abzählbarkeit von Sprachen

Sprachen allgemein:
- **Die Menge aller Sprachen über einem endlichen Alphabet ist überabzählbar**, denn:
  Eine Sprache ist definiert als beliebige Teilmenge, also als: $L\subseteq\Sigma^{*}$.
  Die Menge aller Teilmengen aka die [[Abzählbarkeit#Die Mengen Potenzmenge Potenzmenge ist *nicht* abzählbar|Potenzmenge ist aber überabzählbar]].
*Reguläre* Sprachen:
- Jede reguläre Sprache wird von mindestens einem regulären Ausdruck erzeugt.
- Die Menge der syntaktisch korrekten regulären Ausdrücke ist *abzählbar*:
	- Sortiere die regulären Ausdrücke aufsteigend nach Länge
	- Sortiere die Ausdrücke gleicher Länge alphabetisch/lexikographisch[^1]
- Somit ist die **Menge der regulären Sprachen über einem endlichen Alphabet abzählbar.**

Somit sind "die Meisten" Sprachen keine regulären Sprachen. 
(vgl. reelle vs. rationale Zahlen)

[^1]: Nach dem Gleichen Schema folgt auch, dass die Menge $\Sigma^{*}$ der Wörter aus einem endlichen Alphabet $\Sigma$ abzählbar unendlich ist: Nach Länge + lexikographisch sortieren.