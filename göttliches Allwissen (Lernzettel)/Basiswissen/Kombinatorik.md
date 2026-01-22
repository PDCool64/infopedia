---
tags:
  - DS
status: rot
---
---
> Falls die doch solche Aufgaben in die Klausur packen

$n$ = Anzahl der Kugeln
$k$ = Wie oft gezogen wird

### Größe der Ergebnismenge $|S|$ bzw. $|\Omega|$ :

|                                       | Mit Zurücklegen                              | Ohne Zurücklegen                           |
| ------------------------------------- | -------------------------------------------- | ------------------------------------------ |
| **Mit Beachtung<br>Der Reihenfolge**  | $$n^k$$                                      | $$\frac{n!}{(n-k)!}$$                      |
| **Ohne Beachtung<br>Der Reihenfolge** | $$\frac{(n+k-1)!}{(n-1)!}=\binom{n+k-1}{k}$$ | $$\frac{n!}{(n-k)!\cdot k!}=\binom{n}{k}$$ |

^78a8a9


### Beispiele:

|                                       | Mit Zurücklegen                                                                                              | Ohne Zurücklegen                                                                                                                                                                                        |
| ------------------------------------- | ------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Mit Beachtung<br>Der Reihenfolge**  | Wie viele Kombinationen hat ein dreistelliges Zahlenschloss mit 9 Ziffern                                    | Wie viele Podiumsanordnungen gibt es in einem Lauf mit 10 Läufern?                                                                                                                                      |
| **Ohne Beachtung<br>Der Reihenfolge** | Im Baumarkt gibt es 3 Blumensorten.<br>Ich kaufe mir 5 Blumen. Wie viele Kombinationen habe ich zur Auswahl. | Ziehung der Lottozahlen:<br>Jede Zahl kann nur einmal vorkommen.<br>Die Zahlen werden **klein $\to$ groß** gelistet,<br>d.h. die Reihenfolge ist irrelevant.<br>[[Lottomodell\|Anwendung: Lottomodell]] |


