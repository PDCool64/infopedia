---
"date:": 2025-10-15
tags:
  - DS
status: gelb
Ab Folie: 17
Bis Folie: 20
---

# Äquivalenz und Tautologie

Seien $S$ und $T$ logische Terme, definiert auf derselben Variablenmenge:
- $S$ und $T$ heißen logisch äquivalent, geschrieben $S\equiv T$, wenn $S$ und $T$ denselben Wahrheitswert haben für jede Belebung der Variablen.
- $T$ heißt **Tautologie**, wenn $T\equiv 1$


# Bedeutsame Tautologien
Modus Ponens:
$(A\wedge(A\to B))\to B$

Tertium non datur
$A\vee \neg A$

de Morgansche Gesetze

Wichtig:
Kontraposition:
$(A\to B) \leftrightarrow(\neg B\to \neg A)$
(sieht man mal wieder an der Wahrheitstafel)

---
# Aussageformen
Eine Aussageform selbst ist keine Aussage.
Erst nachdem man für die Variablen etwas sinnvolles einsetzt erhält man eine Aussage.

"Wenn $x>0$, dann ist $x$ ein Quadrat"
ist noch keine Aussage - erst wenn man für $x$  z.b.  eine reelle Zahl ein, erhält man eine sinvolle Aussage. (Hier war weird, dude hat behauptet, dass es für -4 keine Aussage wäre oder so war komisch)

Interessant ist, wenn ich hier einen Dackel als $x$ reinschmeißen würde - hat er so aber mit "sinvoll" eingesetzten Werten für Variablen aber nicht konkret besprochen.


Das Dritte Beispiel ist hier besser:
![[Pasted image 20251015170056.png]]


# Konventionen

Neben den Basics ist interessant neben $:=$ auch:
	$A:\!\iff B$ bedeutet: Die Aussage $A$ wird durch die Aussage B definiert. (A hat per Definition den gleichen Wahrheitswert wie $B$)

"*Ein*" bedeutet stets *mindestens ein* - es ist von *genau ein* zu unterscheiden


>[!def] Heureka: Was bedeutet paarweise Verschieden
> paarweise verschieden := "Keine Zwei sind gleich"
> "normal" verschieden := "Nicht alle sind gleich"
> 
