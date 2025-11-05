---
tags:
status: rot
---
---
# Was ist Verifikation?
Es geht hier nicht mehr darum, dass eine Programm *syntaktisch* korrekt ist -das kann der Compiler für uns recht einfach machen. (s.h.[[Formale Sprachen und Grammatiken]])- sondern darum dass es *semantisch* d.h. inhaltlich und von der Funktion korrekt ist.

## Begriffe
- **Spezifikation** : Was soll ein Programm tun
	- in natürlicher Sprache
	- in graphischen Sprachen (UML, etc.)
	- in logischen Sprachen (Z, VDZ, etc.)
- **Testen**: Überprüfen des Verhaltens des Programms für endlich viele Eingaben
	- aber: keine 100%-tige Sicherheit: Man kann nicht alle Fälle durchprobieren
	
- **Verifikation**: *Mathematisch rigoroser Beweis der Korrektheit*
	- **Terminierung**: Hält das Programm immer an?
	- **Partielle Korrektheit**: Falls das Programm anhält, erfüllt es die Spezifikation
	- **Totale Korrektheit:** Sowohl Terminierung als auch partielle Korrektheit.
	
> Warum der Aufwand:
> - Sicherheitskritische Anwendungen wie Autopilot eines Flugzeugs, Steuersoftware im Atomkraftwerk, Arbeit mit sensiblen Daten.
>  Schön zu lesen: [Liste an Softwarebugs (mit größeren Konsequenzen)](614GBN@rwth-aachen.de)

---
# Hoare-Kalkül
> Benannt nach Tony Hoare

Ein Mathematisch rigoroses Verfahren um mit absoluter Sicherheit sowohl Partielle Korrektheit als auch Terminierung zu beweisen.
## Syntax
Das **Hoare-Tripel**$$
<\varphi> P <\psi>
$$besagt: Wenn vor der Ausführung des *Programms* $P$ die Vorbedingung $\varphi$ gilt, dann gilt danach $\psi$ . Jede dieser in $<>$ stehenden [[Aussagenlogik|Aussagen]] wird **Zusicherung** genannt.

## Regeln:
Das Hoare-Kalkül ist *streng syntaktisch* - jede einzelne Zeile muss unbedingt einer der Regeln des Hoare-Kalküls entsprechen. Für eine kleine Teilmenge von Java-Programmen -solchen die nur aus Zuweisungen, ``if``, ``if-else`` und ``while`` bestehen- reichen die folgenden 7 Regeln.

Jede Regel wird mit einem Strich geschrieben, der bedeutet: Wenn die Bedingungen über dem Strich gelten, dann gelten auch die Bedingungen unter dem Strich.
### Zuweisungsregel
$$
\frac{}{{\color{red}{<\varphi[x/t ]>}}\;\text{ x=t; }{\color{red}{<\varphi>}}}
$$
- ``x`` ist eine Variable
- `t` ist ein Ausdruck (ohne Seiteneffekte)
- ${\color{red}{<\varphi[x/t ]>}}$ ist ${\color{red}{<\varphi>}}$ , nur das jedes Vorkommen von ``x`` durch ``t`` ersetzt wird.

Am besten geht man bei der Zuweisungsregel von unten nach oben vor: Man nimmt die Nachbedingung und erstellt dann die Vorbedingung, indem man alle Vorkommen von  ``x`` durch ``t`` ersetzt.

Beispiele:
1. 
$$
\begin{array}{l}
{\color{red}{<5=5>} }\\ 
\text{x=5;} \\
{\color{red}{<x=5>}}
\end{array}
$$
2. 
$$
\begin{array}{l}
{\color{red}{<res=2(i-1)>} }\\ 
\text{i=i-1;} \\
{\color{red}{<res=2i>}}
\end{array}
$$
## Konsequenzregel 1 (Stärke Vorbedingung)
$$
\frac{
{\color{red}{<\varphi>}}
\text{ P }
{\color{red}{<\psi>}}\quad{\color{red}{\alpha}}\implies{\color{red}{\varphi}}
}{
{\color{red}{<\alpha>}}\;\text{ P }{\color{red}{<\psi>}}
}
$$
Wenn $\alpha\implies \varphi$, dann kann man auch die stärke Vorbedingung $\alpha$ verwenden, weil diese notwendigerweise alles impliziert was $\varphi$ impliziert hat.

> Praktisch bedeutet dies: Stehen zwei Zusicherungen direkt über einander, muss die obere die untere Implizieren. Denn genau dann könnte man die obere Zeile auch als Vorbedingung des folgenden Hoare-Tripels verwenden.

Beispiele:
1. $$
\begin{array}{l} \\
{\color{red}{<true>} }\\ 
{\color{red}{<5=5>} }\\ 
\text{x=5;} \\
{\color{red}{<x=5>}}
\end{array}
$$ weil $$
\frac{
{\color{red}{<5=5>}}
\text{ x=5; }
{\color{red}{<x=5>}}\quad{\color{red}{true}}\implies{\color{red}{5=5}}
}{
{\color{red}{<true>}}\;\text{ x=5; }{\color{red}{<x=5>}}
}
$$

2. $$
\begin{array}{l} \\
{\color{red}{<x<y>} }\\ 
{\color{red}{<x+1\le y>} }\\ 
\text{x=x+1;} \\
{\color{red}{<x\leq y>}}
\end{array}
$$
weil$$
\frac{
{\color{red}{<x+1 \le y>}}
\text{ x=x+1; }
{\color{red}{<x\le y>}}\quad{\color{red}{x<y}}\implies{\color{red}{x+1\leq{1}}}
}{
{\color{red}{<x<y>}}\;\text{ x=x+1; }{\color{red}{<x\leq y>}}
}
$$
(mit $x,y\in \mathbb{N}$)

### Konsequenzregel 2 (Schwächere Nachbedingung)
$$
\frac{
{\color{red}{<\varphi>}}
\text{ P }
{\color{red}{<\psi>}}\quad{\color{red}{\psi}}\implies{\color{red}{\beta}}
}{
{\color{red}{<\varphi>}}\;\text{ P }{\color{red}{<\beta>}}
}
$$
Wenn $\psi\implies\beta$, dann kann man auch die schwächere Nachbedingung $\beta$ verwenden. Denn: Wenn $\psi$ schon erfüllt war, dann ist $\beta$ es sicher auch.

> Praktisch bedeutet dies: Stehen zwei Zusicherungen direkt über einander, muss die obere die untere Implizieren. Denn genau dann könnte man die untere Zeile auch als Nachbedingung des vorherigen Hoare-Tripels verwenden.

Beispiele:
1. $$
\begin{array}{l} \\
{\color{red}{<true>} }\\ 
{\color{red}{<5=5>} }\\ 
\text{x=5;} \\
{\color{red}{<x=5>}} \\
{\color{red}{<x\ge5>}}
\end{array}
$$

### Sequenzregel
$$
\frac{
{\color{red}{<\varphi>}}
\text{ P }
{\color{red}{<\psi>}}\quad
{\color{red}{<\psi>}}
\text{ Q }
{\color{red}{<\beta>}}}
{
{\color{red}{<\varphi>}}\;\text{ P Q }{\color{red}{<\beta>}}
}
$$
Wenn die Nachbedingung von P gleich der Vorbedingung von Q ist, gilt dann ist auch P Q verifizierbar.

### Bedingungsregel 1 (if-Anweisung)
$$
\frac{
{\color{red}{<\varphi \land \text{B}>}}
\text{ P }
{\color{red}{<\psi>}}\quad
{\color{red}{\psi \land \neg B}}\implies{\color{red}{\psi}}}
{
{\color{red}{<\varphi>}}\;\text{ if (B) \{P\} }{\color{red}{<\psi>}}
}
$$
Damit $\psi$ nach einem if-Block gilt, muss $\psi$ sowohl gelten,
- nach dem das Programm $P$ ausgeführt wurde weil $B$ gilt.
- nach dem der if-Block nicht ausgeführt wurde weil $\neg B$ gilt.

> d.h. auf beiden möglichen Pfaden muss die gleiche Nachbedingung $\psi$ entstehen, um gültig zu sein.

### Bedingungsregel 2 (if-else-Anweisung)
$$
\frac{
{\color{red}{<\varphi \land \text{B}>}}
\text{ P }
{\color{red}{<\psi>}}\quad
{\color{red}{<\varphi \land \neg\text{B}>}}
\text{ Q }
{\color{red}{<\psi>}}}
{
{\color{red}{<\varphi>}}\;\text{ if (B) \{P\} else \{Q\} }{\color{red}{<\psi>}}
}
$$
Damit $\psi$ nach einem if-Block gilt, muss $\psi$ sowohl gelten,
- nach dem das Programm $P$ ausgeführt wurde weil $B$ gilt.
- nach dem das Programm $Q$ ausgeführt wurde weil $\neg B$ gilt.

> d.h. auf beiden möglichen Pfaden muss die gleiche Nachbedingung $\psi$ entstehen, um gültig zu sein.

## Schleifenregel
$$
\frac{
{\color{red}{<\varphi \land \text{B}>}}
\text{ P }
{\color{red}{<\varphi>}}}
{
{\color{red}{<\varphi>}}\;\text{ while (B) \{P\} }{\color{red}{<\varphi \land \neg \text{B}>}}
}
$$
