---
tags:
  - TI
  - DS
status: gelb
---

---
>[!def]  Boolesche Algebra
>Die **Boolesche Algebra**, benannt nach [George Boole](https://de.wikipedia.org/wiki/George_Boole) ist die auf [[Aussagenlogik]] beruhende Grundlage für Schaltungen, Prozessoren, Speicher und Co.

Wie die Aussagenlogik basiert die Boolesche Aussagenlogik auf zwei Werten
0/false und 1/true, welche durch Operatoren zu komplexeren Aussagen verknüpft werden.

# Grundlegende Verknüpfungen
(Wir werden im Thema [[#Funktionale Vollständigkeit]] sehen, dass nicht alle drei notwendig sind, um die gesamte Boolesche Algebra herzuleiten.)

## Die unäre Verknüpfung *nicht*:
> unär bedeutet, dass die Verknüpfung nur ein einziges Argument annimmt, d.h. aus *einer* Aussage eine neue macht.

| $a$ | $\neg a$ |
| --- | -------- |
| 0   | 1        |
| 1   | 0        |
## Die binären Verknüpfungen *oder* und *und*:
> "binär" bedeutet, dass diese Verknüpfungen jeweils *zwei* Aussagen zu einer neuen verknüpfen.

|     |     | *oder*    | *und*       |
| --- | --- | --------- | ----------- |
| $a$ | $b$ | $a\vee b$ | $a\wedge b$ |
| 0   | 0   | 0         | 0           |
| 0   | 1   | 1         | 0           |
| 1   | 0   | 1         | 0           |
| 1   | 1   | 1         | 1           |
#### Schreibweisen:
- $\text{ODER}$ = $\vee$ = $+$ = **Disjunktion**
- $\text{UND}$ = $\wedge$ = $\cdot$ = **Konjunktion**. Der Malpunkt wird, wie bei der Multiplikation von Zahlen, oft nicht geschrieben.


---
# Logische Gesetze

### Gesetze, die man viel zum Umformen braucht:
Kommutativgesetze:
$$
\begin{align}
a\vee b &= b\vee a \\
a\wedge b &= b \wedge a
\end{align}
$$
Assoziativgesetze:
$$
\begin{align} \\
(a\vee b)\vee c &= a\vee(b\vee c) \\

(a\wedge b)\wedge c &= a\wedge (b\wedge c)
\end{align}
$$
Distributivgesetze:
$$
\begin{align}
a\vee(b\wedge c) &= (a\vee b)\wedge(b \vee c) \\
a\wedge (b \vee c) &= (a \wedge b) \vee (a \wedge c)
\end{align}
$$
De Morgansche Gesetze:
$$
\begin{align}
\neg(a\vee b) &=\neg a \wedge \neg b \\
\neg(a\wedge b)&= \neg a\vee \neg b
\end{align}
$$
Absorptionsgesetze:
$$
\begin{align}
a\vee(a\wedge b) &= a \\
a \wedge (a\vee b) &=a
\end{align}
$$

### "obvious" Gesetze, den man aber für die Axiomatik braucht:
Idempotenzgesetze:
$$
\begin{align}
a \vee a &= a \\
a \wedge a &=a
\end{align}
$$
Neutralitätsgesetze:
$$
\begin{align}
a\vee 0 &= a \\
a \wedge 1 &=a
\end{align}
$$
Extremalgesetze:
$$
\begin{align}
a \vee 1 &= 1 \\
a \wedge 0 &= 0
\end{align}
$$
Komplementärgesetze:
$$
\begin{align}
a \vee \neg a &=1 \\
a \wedge \neg a &=0
\end{align}
$$
Dualitätsgesetze:
$$
\begin{align}
\neg 0 &=1 \\
\neg 1 &= 0
\end{align}
$$
Doppelnegationsgesetz (Involution):
$$
\neg(\neg a)=a
$$

