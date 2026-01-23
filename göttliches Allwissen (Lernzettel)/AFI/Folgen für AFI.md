---
tags:
  - AFI
status: rot
---
---

Diese Notiz richtet sich nach dem AFI Skript.
Für DS-spezifische Inhalte gibt es [[Folgen für DS]].
Vorkursinhalte die noch nicht übertragen sind, gibt es noch in [[Folgen (Alt)]]

>[!def] Folge
>Eine ([[Reelle Zahlen und Schranken|reelle]]) Folge ist eine [[Abbildungen|Abbildung]] $\mathbb{N}\to \mathbb{R}$.
>
> ---
>Statt $\mathbb{N}\to \mathbb{R}\;,\;n\mapsto a_{n}$ schreibt man auch $(a_{n})_{n\ge 1}$
>
>Man nennt die Wertemenge dieser Abbildung $W:=\{ a_{n}\mid n\in \mathbb{N} \}$ . Gilt $W\subseteq M$, so spricht man von einer Folge in $M$.

## Leichte Verallgemeinerung
Anstatt $1$ als ersten Index zu verwenden, ist auch ein beliebiges $n_{0}\in \mathbb{Z}$ möglich, also$$ \mathbb{Z}_{\ge n_{0}}\to \mathbb{R}\;,\;n\mapsto a_{n}$$
Man kann also sowohl bei größeren positiven Zahlen $2,3,200$ usw. anfangen, insbesondere aber auch bei negativen Zahlen wie $-20,-4,-1,0$.
Dies ändert nichts an der [[Abzählbarkeit]] der Indexmenge, denn die Indexmenge wird legendlich verschoben.

( Z.B. ist $\mathbb{N}\to \mathbb{R}\;,\;n\mapsto(n-5)^{2}$ praktisch das gleiche wie $\mathbb{Z}_{\ge 5}\to \mathbb{R}\;,\;n\mapsto n^{2}$, nur dass die Indexe für die jeweils identischen Folgenglieder nun um 5 von einander verschoben sind.)
# Gleichheit von Folgen
Zwei Folgen sind genau dann gleich, wenn ale Folgenglieder gleich sind.


# Arithmetische und geometrische Folgen
## Arithmetische Folge:
Bei einer arithmetischen Folge ist die Differenz zwischen aufeinanderfolgenden Folgengliedern konstant: 
$$a_{n+1}-a_{n}=\text{const}$$
Rekursiv schreibt man sie als:
$a_{n+1}=a_{n}+\text{const}$ ; $a_{n_{0}}=x$
Explizit schreibt man sie als:
$a_{n}=a_{n_{0}}+\text{const}\cdot (n-n_{0})$

## Geometrische Folge:
Bei einer geometrischen Folge ist der Quotient zwischen aufeinanderfolgenden Folgengliedern konstant.
$$
\frac{a_{n+1}}{a_{n}}=\text{const}
$$
Rekursiv schreibt man sie als:
$a_{n+1}=a_{n}\cdot const$ ; $a_{n_{0}}=x$
Explizit schreibt man sie als:
$a_{n}=a_{n_{0}}\cdot\text{const}^{n-n_{0}}$

---
# Monotonie von Folgen

>[!def] Monotonie von Folgen
> >[!def] (einfache) Monotonie
> > Eine Folge $(a_{n})_{n\in \mathbb{N}}$ heißt **monoton wachsend**, wenn $a_{n+1}\ge a_{n}$ für alle $n\in \mathbb{N}$ gilt.
> > Eine Folge heißt **monoton fallend**, wenn $a_{n+1}\le a_{n}$ für alle $n\in \mathbb{N}$ gilt.
> 
> 
> >[!def] Strenge Monotonie
> > Eine Folge $(a_{n})_{n\in \mathbb{N}}$ heißt **streng monoton wachsend**, wenn $a_{n+1} > a_{n}$ für alle $n\in \mathbb{N}$ gilt. 
> > Eine Folge $(a_{n})_{n\in \mathbb{N}}$ heißt **streng monoton fallend**, wenn $a_{n+1} < a_{n}$ für alle $n\in \mathbb{N}$ gilt. 


# Beschränktheit von Folgen
>[!def] Beschränktheit von Folgen
> Eine Folge $(a_{n})_{n\in \mathbb{N}}$ heißt **nach oben beschränkt**, wenn es ein $M_{1}\in \mathbb{R}$ gibt, so dass $a_{n} \le M$ für alle $n\in \mathbb{N}$.
> 
> Eine Folge $(a_{n})_{n\in \mathbb{N}}$ heißt **nach unten beschränkt**, wenn es ein $M_{2}\in \mathbb{R}$ gibt, so dass $a_{n}\ge M_{2}$ für alle $n\in \mathbb{N}$.
> 
> Eine nach oben *und* nach unten beschränkte Folge heißt kurz **beschränkt.**
> 
> ---
> 
> Feststellen von Beschränktheit:
> - Eine monoton wachsende Folge ist offensichtlich durch ihr erstes Element nach unten beschränkt.
>   Eine monoton fallende Folge ist offensichtlich durch ihr erstes Element nach oben beschränkt.
> - Eine Folge $(a_{n})_{n\in \mathbb{N}}$ ist *genau dann* beschränkt, wenn es ein $M\in \mathbb{R}$ gibt, so dass $\left| a_{n} \right|\le M$ für alle $n\in \mathbb{N}$.

---

# Grenzwert von Folgen

>[!def] Grenzwert einer Folge
> Eine [[Reelle Zahlen und Schranken|reelle]] Folge $(a_{n})_{n \ge 1}$ heißt **konvergent**, wenn ein $a\in \mathbb{R}$ existiert, so das zu jedem $\varepsilon>0$ ein $n_{0}(\varepsilon)\in \mathbb{N}$ existiert, so dass:$$\left| a_{n}-a \right| < \varepsilon \quad\text{für alle}\;n\ge n_{0}$$
> 
> was bedeutet:
> Für *jedes* $\varepsilon$ findet sich ein (großer) Index $n_{0}$ , ab dem alle weiteren Folgenglieder in der $\varepsilon$-Umgebung liegen.
>
> ---
> Man nennt $a$ **Limes** oder **Grenzwert** der Folge $(a_{n})_{n\ge 1}$ und schreibt 
> $$\lim_{ n \to \infty } a_{n}=a\quad \text{oder}\quad a_{n} \underset{n\to \infty}\longrightarrow a$$
> 
> Man sagt auch, dass $(a_{n})_{n\ge 1}$ gegen $a$ **konvergiert**.
> Eine Folge die nicht konvergent ist, heißt **divergent**.
> 
> Eine Folge mit Grenzwert $0$ heißt **Nullfolge**.
> 

- Mit $n_{0}(\varepsilon)$ ist gemeint, dass $n_{0}$ von $\varepsilon$ abhängen kann. Wird z.B. ein sehr kleines $\varepsilon$ eingefordert, muss man ggfs. ein sehr großes $n_{0}$ wählen, ab dem die Folge ausreichend nah an ihrem Grenzwert bleibt.
- Die Konvergenzbedingung besagt, dass *fast alle* Folgenglieder (d.h. alle bis auf endlich viele) in ger geforderten $\varepsilon$-Umgebung liegen.

Wenn man Quantoren mag ist auch diese kompakte Schreibweise gleichbedeutend:
> Eine Folgen reeller Zahlen $(a_{n})_{n\ge 1}$ konvergiert gegen $a$, falls gilt:$$
\forall_{\varepsilon>0}\exists_{n_{0}\in \mathbb{N}}\forall_{n\ge n_{0}}:\left| a_{n}-a \right| <\varepsilon$$
# Eindeutigkeit des Grenzwerts

>[!def] Eindeutigkeit des Grenzwerts
> Eine reelle Folge besitzt höchstens einen Grenzwert. 
> D.h. *wenn* ein Grenzwert existiert, dann ist dieser eindeutig bestimmt.

# Grenzwert und Beschränktheit.
>[!def] Grenzwert und Beschränktheit
> Eine konvergente Folge ist [[#Beschränktheit von Folgen|beschränkt]]. (nach Oben *und* nach Unten).

## Beweis:
Seien $a$ und $a'$ verschiedene Grenzwerte von $(a_{n})_{n\ge 1}$ und $\varepsilon>0$.
Man wählt $n_{0},n_{1}\in \mathbb{N}$ sodass $\left| a_{n}-a \right|< \frac{\varepsilon}{2} \;\forall{n\ge n_{0}}$ und $\left| a_{n}-a' \right|< \frac{\varepsilon}{2} \;\forall{n\ge n_{1}}$.

Sei $m=\text{max}\{ n_{0},n_{1} \}$. Dann gilt mit der [[Formelsammlung Abschätzungen#Dreiecksungleichung|Dreiecksungleichung]] :
$$
\left| a-a' \right| =\left| a-a_{m}+a_{m}-a' \right| \overset{\text{DUG}}{\le} \left| a-a_{m} \right| -\left| a_{m}-a' \right| < \frac{\varepsilon}{2}+ \frac{\varepsilon}{2}=\varepsilon 
$$
Also insbesondere:
$\left| a-a' \right|<\varepsilon$

Weil $\varepsilon$ beliebig ist, folgt $a=a'$.

---
# Limitenregeln /  Grenzwertsätze

>[!def] Limitenregeln
> Seien $c\in \mathbb{R}$ 
> und $(a_{n})_{n\ge 1}$ , $(b_{n})_{n\ge 1}$ [[#Grenzwert von Folgen|konvergente]] (reelle) Folgen mit 
> $\lim_{ n \to \infty }a_{n}=a$ und
> $\lim_{ n \to \infty }b_{n}=b$.
> 
> Dann gilt:
> 
> >[!def] Summe zweier konvergenter Folgen
> > $$
> > (a_{n}+b_{n})_{n\ge 1} \quad \text{konvergiert mit}\quad \lim_{ n \to (\infty) } (a_{n}+b_{n})=a+b 
> > $$
> 
> >[!def] Produkt konvergenter Folge mit konstantem Faktor
> > $$
> > (c\cdot a_{n})_{n\ge_{1}} \quad\text{konvergiert mit}\quad \lim_{ n \to   }(c\cdot a_{n})=c\cdot a
> > $$
> 
> >[!def] Produkt zweier konvergenter Folgen
> > $$
> > (a_{n}\cdot b_{n})_{n\ge 1} \quad \text{konvergiert mit} \quad \lim_{ n \to \infty } (a_{n}\cdot b_{n})=a\cdot b
> > $$
> 
> >[!def] Quotient zweier konvergenter Folgen.
> > Falls $b_{n}\neq 0 \;\forall _n\in \mathbb{N}$ und $b\neq 0$, dann:
> > $$
> >  \Big(\frac{a_{n}}{b_{n}}\Big)_{n\ge 1}\quad \text{konvergiert mit}\quad\lim_{ n \to \infty } \left( \frac{a_{n}}{b_{n}} \right) = \frac{a}{b}
> > $$
> 

---
# Teilfolgen

>[!def] Teilfolge
> Eine Folge $(a'_{k})_{k\geq 1}$ heißt **Teilfolge** einer [[Folgen für AFI|Folge]], wenn es eine [[Folgen für AFI#Monotonie von Folgen|streng monoton wachsende]] Folge $(n_{k})_{k\geq 1}\subseteq \mathbb{N}$ gibt mit $a'_{k}=a_{n_{k}}$ für alle $k\geq 1$.
