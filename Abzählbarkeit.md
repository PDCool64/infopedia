---
tags:
  - AFI
  - DS
status: rot
---
---
>[!def] Abzählbarkeit
> Definition:
> >[!def] von $\mathbb{N}$ surjektiv.
> Eine Menge $M$ heißt abzählbar, wenn $M=\emptyset$ oder wenn eine [[Abbildungen#Injektiv, Surjektiv, Bijektiv|surjektive]] Abbildung $f:\mathbb{N}\to M$ existiert.
> 
> Ableitbar:
> >[!def] nach $\mathbb{N}$ injektiv.
> Eine Menge $M\neq \emptyset$ ist genau dann abzählbar, wenn eine [[Abbildungen#Injektiv, Surjektiv, Bijektiv|injektive]] Abbildung $g:M\to \mathbb{N}$ existiert.
> ($\emptyset$ ist abzählbar, der Beweis für diese Richtung funktioniert aber sonst nicht)
> 
> 
 Eine abzählbare Menge, die nicht endlich ist, heißt abzählbar unendlich. 
> Eine nicht abzählbare Menge nennt man **überabzahlbar**.


Intuitiv Menge ist somit Abzählbar wenn
- die natürlichen Zahlen ausreichen um mit ihnen alle Elemente zu treffen
- die Menge klein genug ist, damit man keine natürliche Zahl doppelt treffen muss.

Es gibt kein "unterabzählbar" - Man kann keine Unendlichkeit kleiner als $\mathbb{N}$ konstruieren.

Jede endliche Menge ist abzählbar.
## Verwandt: [[Mengen#Mächtigkeit einer Menge|Mächtigkeit von Mengen]]
findet man sogar eine [[Abbildungen#Injektiv, Surjektiv, Bijektiv|bijektive]] Abbildung zwischen einer Menge und $\mathbb{N}$, dann ist diese nicht nur abzählbar sondern auch gleichmächtig zu $\mathbb{N}$.

---

# Wichtige Abzählbare Mengen

## Die Ganzen Zahlen $\mathbb{Z}$ sind abzählbar

Idee:

| $\mathbb{N}$ | $\mathbb{Z}$ |
| ------------ | -----------: |
| 1            |            0 |
| 2            |           -1 |
| 3            |            1 |
| 4            |           -2 |
| 5            |            2 |
| 6            |           -3 |
| 7            |            3 |
| 8            |           -4 |
| 9            |            4 |
als Abbildung:
$$
f:\mathbb{N}\to \mathbb{Z}\;,\;n\mapsto \begin{cases}
-\frac{n}{2} &,n\text{ gerade} \\
\frac{n-1}{2} &,n \text{ ungerade}
\end{cases}
$$
Diese Abbildung ist sogar *bijektiv*, womit nicht nur gezeigt ist, dass $\mathbb{Z}$ abzählbar ist, sondern auch gleichmächtig wie $\mathbb{N}$.


# Cantor'sches Diagonalargument: das kartesische Produkt $\mathbb{N}\times \mathbb{N}$ ist abzählbar

## Formal:
![[Pasted image 20251116145442.png]]


## Verständniss: Warum funktioniert das:
### Graphisch
![[Pasted image 20251116122406.png|400]]

Das Durchlaufen alle Elemente $(m,n)\in \mathbb{N}\times \mathbb{N}$ wird gut deutlich: Man kann eine bijektive Abbildung aufstellen, womit $\mathbb{N}\times \mathbb{N}$ abzählbar ist.
### Die explizite Abbildung

#### Hinrichtung: $\mathbb{N}\times \mathbb{N}\to \mathbb{N}$
Alle Tupel $(j,k)$ auf einer $m$-ten Diagonale haben die gleiche Summe $j+k$ ihrer Komponenten. Wir verschieben die Indizierung der Diagonalen aber um $-2$, damit das Tupel $(1,1)$ die $0$-te Diagonale bildet.
$$
m=j+k-2
$$
**Wir bilden die Tupel einer Diagonalen zusammen auf ein Intervall der natürlichen Zahlen ab.** 

Jede Diagonale hat ein Element mehr als die Vorherige. - den "Block" der natürlichen Zahlen, auf den sie abgebildet werden soll, muss also eins größer als der Vorherige Block sein.

Wo kann der $m$-te Block anfangen: Genau bei der Summe der Länge aller vorherigen Blöcke. Also bei:$$\sum_{i=0}^{m}i=\frac{m(m+1)}{2}$$
Also bilden wir jedes der Tupel $(j,k)$ die in der $j+k-2$-ten Diagonale liegen ab auf:
- Den Start des Intervalls auf $\mathbb{N}$ dieser diagonale: $\frac{m(m+1)}{2}$ mit $m=j+k-2$
- Addiert mit der Position des jeweiligen Elements in der Diagonale: $j$ 
  (man könnte anstatt $j$ auch $k$ wählen, dann wäre die Sortierung innerhalb der einzelnen Diagonalen umgekehrt)

Also:$$n(j,k) =\frac{(j+k-2)(j+k-2)}{2}+j$$
> Es gibt also eine injektive Abbildung, die jedem Tupel $(j,k)\in \mathbb{N}\times \mathbb{N}$ genau eine natürliche Zahl $n$ zuordnet.


>[!wip]
> Die beiden graphischen Beispiele hier stellen eine vertausche Sortierung da, die aber ebenso verwendet werden könnte.

Achtung: *WARUM AUCH IMMER* hat man uns ins Skript ein Diagramm gepackt, in dem Die Diagonalen gespiegelt gewählt worden sind. In dem Diagramm hier wird innerhalb der einzelnen Diagonalen nach steigender zweiter Komponente sortiert, während die Formeln im Skript nach steigender erster Komponente sortiert.)
![[Abzählbarkeit 2025-11-16 13.04.05.excalidraw|800]]

![[Abzählbarkeit 2025-11-16 12.28.03.excalidraw|600]]


#### Rückrichtung: $\mathbb{N}\to \mathbb{N}\times \mathbb{N}$
Wir Teilen die natürlichen Zahlen in Blöcke ein, die jeweils einer Diagonale im Kartesischen Produkt entsprechen. Da jede Diagonale ein Element mehr als die vorherige hat, müssen auch die Blöcke jeweils ein Element größer werden.

Die Grenzen der Blöcke werden somit als die Ergebnisse der Gauß'schen Summenformel gewählt:
> Zu jedem $n\in \mathbb{N}$ gibt es *genau eine* Kombination $(m,l)$ mit $m\in \mathbb{N}_{0}$ und $1\le l \le m+1$, so 
> dass
> $n= \frac{m(m+1)}{2}+l$

Nun ist die Idee, $m$ als Index der Diagonale aufzufassen, die wir mit diesem Block abdecken wollen und $l$ als Position innerhalb der Diagonale. 
Wir versuchen nun die $m+1$ vielen Tupel $(j,k)$ die auf dieser Diagonale liegen zu treffen:

Von $n$ subtrahieren wir also den Beginn des Blocks, um die Position relativ zum Blockanfang zu bestimmen : $l=n- \frac{m(m+1)}{2}$.

Indem man jede dieser relativen Positionen einfach als ersten Index des Tupels wählt, 
erhält man mit $j=l= \frac{m(m+1)}{2}$ schon eine gültige erste Komponente des Tupels,
die alle notwendigen ersten Komponenten der Diagonale abdeckt.

Da die Summe der beiden Komponenten für jedes Element der Diagonale gleich ist,
wählen wir für die jede erste Komponente $j=k= \frac{m(m+1)}{2}$ die Zweite Komponente so, dass ihre Summe konstant ist. Da $j=l$ für die einzelnen Elemente der Diagonale wächst, muss $k$ ebenso sinken: $k=m\!+\!1-l$ .
Damit durch $1 \le l \le m+1$ auch hier aber alle notwendigen zweiten Komponenten $k$ der Diagonale mit $1\le k \le m+1$ getroffen werden, muss $k$ um $+1$ verschoben werden. (Sonst würde $k$ von $0\le k \le m$) liegen.

Also wählt man als Zweite Komponente:

$$
k=m+2-l
$$

Insgesamt also:
$$\varphi(n)=\varphi\left(  \frac{m(m+1)}{2} +l\right)=(l,m+2-l)$$

> Es gibt eine Abbildung, die jeder natürlichen Zahl genau ein Tupel aus $\mathbb{N}\times \mathbb{N}$ zuordnet.


# Eine Abzählbare Vereinigung $\cup$ abzählbarer Mengen ist abzählbar


>[!def] Vereinigung $\cup$ abzählbar vieler abzählbarer Mengen 
> Eine abzählbare Vereinigung $\cup$ abzählbarer Mengen ist abzählbar.


Sei M= \bigcup_{n=1}^{\infty}M_{n} jedes $M_{n}$ abzählbar und ohne Einschränkung $M_{n}\neq \emptyset$.

Da jedes $M_{n}$ abzählbar ist, existiert auch für jedes $n\in \mathbb{N}$ eine *surjektive* Funktion, die $M_{n}$ abzählt:
$$
f_{n}:\mathbb{N}\to M_{n}
$$

Die Abbildung $\varphi$ aus dem [[#Cantor'sches Diagonalargument das kartesische Produkt $ mathbb{N} times mathbb{N}$ ist abzählbar|Cantor'schen Diagonalargumet]] liefert mit Definitionsberreich $\mathbb{N}$ als Werteberreich alle Kombinationen $\mathbb{N}\times \mathbb{N}$ . Will man dabei die Kombinationen nicht als Tupel sondern einzeln haben, kann man definieren: $\varphi(n)=(\varphi_{1}(n),\varphi_{2}(n))$
(Informatisch geschrieben von der Idee her: $\varphi_{1}(n):=\varphi(n)[\,0\,]$ und $\varphi_{1}(n):=\varphi(n)[\,1\,]$)

Ziel ist es nun, eine surjektive Abbildung zu konstruieren, die ganz $M$ abzählt
$$g:\mathbb{N}\to M$$
dies ist möglich, in dem man die durch $\varphi(n)$ erzeugten Paare benutzt, um gleichzeitig den gesamten Definitionsberreich jeder Funktion $f_{n}$ durch zu iterieren, als auch simultan alle verschiedenen Funktionen $f_{1}\;,\;f_{2}\;,\;\dots \;,\;f_{n}$ abzudecken:
$$
g:\mathbb{N}\to M \;,\; g(l)= f_{\varphi_{1}(n)}\big(\,\varphi_{2}(n)\;\big)
$$

Mit dieser Konstruktion ist $g$ surjektiv.


# Die Rationalen Zahlen $\mathbb{Q}$ sind abzählbar

Mehre anschauliche Optionen:
Jeder rationale Zahl ist auch nur eine Kombination aus zwei natürlichen Zahlen, also ist
$\mathbb{Q} \approx \mathbb{N}\times \mathbb{N}$. 
Wobei durch kürzen nicht alle Kombinationen durchnummeriert werden müssen, weil sie $\mathbb{Q}$ nicht um "neue" Zahlen erweitern. 

Graphisch: ([Wikipedia](https://de.wikipedia.org/wiki/Cantors_erstes_Diagonalargument))
![[Abzählbarkeit 2025-11-16 15.18.13.excalidraw|600]]

Man zählt genau wie beim Kreuzprodukt, überspringt aber nicht vollständig gekürzte Brüche.

---
# Das [[Mengen#Kartesisches Produkt|Kartesische Produkt]] endliche vieler abzählbarer Mengen ist abzählbar

>[!def] Abzählbarkeit des kartesischen Produkts
> Sind $M_{1}$ und $M_{2}$ abzählbar, so ist auch $M_{1}\times M_{2}$ abzählbar
>
> ---
> Ist $M$ abzählbar, und $n\in \mathbb{N}$, so ist auch $M^{n}=\underbrace{ M\times\dots \times M }_{ n-mal }$ abzählbar

## Beweis.
Aus $a)$ ergibt sich wegen $M^{(n+1)}=M^{n}\times M$ mit offensichtlicher Induktion.

a) selbst lässt sich zeigen: Das kartesische Produkt ist die [[#Eine Abzählbare Vereinigung $ cup$ abzählbarer Mengen ist abzählbar|Vereinigung]] $\cup$ abzählbar vieler Zweitupel.

---

# Die [[Mengen#Potenzmenge|Potenzmenge]] ist *nicht* abzählbar

>[!def] Potenzmenge ist überabzählbar
> Die Potenzmenge $\text{Pot}(\mathbb{N})$ ist überabzählbar.

