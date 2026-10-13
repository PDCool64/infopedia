TARGET DECK: FOSAP::Reguläre Sprachen

Formale Definition **DFA**: #flashcard
Ein **deterministischer, endlicher Automat** (DFA) ist ein 5-Tupel
$M=(Q,\Sigma,\delta,q_0,F)$ mit
- $\Sigma$, dem endlichen nichtleeren Eingabealphabet
- $Q$, der endlichen Menge der Zustände
- $\delta: Q\times\Sigma \to Q$, der Zustandsübergangsfunktion
- $q_0$, dem Anfangszustand sowie
- $F\subseteq Q$, der Menge der Endzustände (F auf Englisch für Final-states)
<!--ID: 1786894783673-->


Definiere die (erweiterte) Zustandsübergangsfunktion eines **NFA:** #flashcard
- $\delta:Q\times\Sigma\to{2}^{Q}=\mathcal{P}(Q)$ 
- $\hat{\delta}(q,\varepsilon)=\{ q \}$
- $\hat{\delta}(q,wa)=\{ p \mid \exists r\in\hat{\delta}(q,w)\;,\;p\in\delta(r,a)\}$
<!--ID: 1786894783677-->


Definiere die (erweiterte) Zustandsübergangsfunktion eines **$\varepsilon$-NFA**: #flashcard
$\delta(q,\varepsilon)=\varepsilon\text{-Hülle}(q)$
$\hat{\delta}(q,wa)=\varepsilon\text{-Hülle}(P)\text{ mit }P:=\{ p\in Q \mid \exists r\in \hat{\delta}(q,w) \land p\in \delta(r,a) \}$
Also
1. mit $\hat{\delta}(q,w)$ zu einem Knoten $r$
2. von dort mit $q=\delta(r,a)$ einen Schritt weiter
3. von $q$ noch beliebige $\varepsilon$-Transitionen
<!--ID: 1786894783681-->


Definiere die $\varepsilon\text{-Hülle}$ eines Zustands #flashcard
$\varepsilon\text{-Hülle}(q):=$ Menge aller Zustände die man von $q$ aus nur mit $\varepsilon$-Transitionen erreichen kann
(auch mehrere Transitionen hintereinander)
<!--ID: 1786894783685-->


Was gilt immer bezüglich einem Zustand und seiner eigenen $\varepsilon\text{-Hülle}$? #flashcard
$q\in\varepsilon\text{-Hülle}(q)$
<!--ID: 1786894783689-->


Definiere die **Myhill-Nerode-Relation** #flashcard
$u\equiv_{L}v \iff \forall{w\in\Sigma^{*}}:uw\in L \leftrightarrow vw\in L$
<!--ID: 1786894783693-->


Definiere den Satz von **Myhill-Nerode** #flashcard
$L\text{ regulär}\iff\text{index}(\equiv_{L})<\infty$
<!--ID: 1786894783697-->

Definiere den **Myhill-Nerode-Automaten** bzw. diesen minimalen DFA #flashcard
$M=(Q,\Sigma,\delta,\left[ \varepsilon \right]_{\equiv_{L}},F)$
- $Q=\{ \left[ w \right]_{\equiv_{L}}\mid w\in \Sigma^{*} \}$
- $\delta:Q\times\Sigma\to Q \;,\;(\left[ w \right]_{\equiv_{L}},a)\mapsto \left[ wa \right]_{\equiv_{L}}$
- $F=\{ \left[ w \right]_{\equiv_{L}}\mid w\in L \}$
<!--ID: 1786984714399-->


Welche Eigenschaften muss ein **Homomorphismus zwischen zwei DFA** erfüllen? #flashcard
$h:Q\to Q'$ ist Homomorphismus gdw.:
1. $h(q_{0})=q_{0}'$
2. $h(q)\in F' \iff q\in F$ (**beide Richtungen:** Endzustände und auch NUR Endzustände werden auf Endzustände abgebildet)
3. $h(\delta(q,a))=\delta'(h(q),a)$ 
<!--ID: 1786894783701-->


Definiere die $L_{ij}^{k}$-Rekursionsgleichung: #flashcard
$$
L_{ij}^{0}=\begin{cases}
\{ a\in\Sigma \mid \delta(q_{i},a)=q_{j}&,i\neq j \\
\{ a\in \Sigma \mid \delta(q_{i},a)=q_{i} \}\cup \{  \varepsilon \}&,i=j
\end{cases}
$$
$$L_{ij}^{k}=L_{ij}^{k-1}\cup L_{ik}^{k-1}(L_{kk}^{k-1})^{*}L_{kj}^{k-1}$$
Beachte:
1. Die Zustände sind 1-indiziert
2. $L_{ij}^{k}$ darf nur die Zustände $\{ q_{1},\dots,q_{k} \}$ verwenden 
3. $L_{ij}^{0}$ darf gar keine Zwischenstopps verwenden
<!--ID: 1786894783705-->


Wann ist eine reguläre Sprache **präfixabgeschlossen**? #flashcard
Wenn jeder Präfix jedes Wortes aus $L$ selbst wieder in $L$ ist:
$\forall_{w\in L}\forall_{p \sqsubseteq w}:p\in L$
<!--ID: 1786894783708-->


Definiere das **Pumping-Lemma** #flashcard
Sei $L$ reguläre Sprache, dann existiert $n\in \mathbb{N}$ sodass sich jedes $w\in L$ mit $\left| w \right|\ge n$ schreiben lässt als $w=xyz$ mit:
1. $\left| xy \right|\le n$
2. $0 <\left| y \right|$
3. $xy^{i}z\in L\;\forall_{i\ge 0}$
<!--ID: 1786894783712-->



Wie Lautet das **Schema** um mit dem Pumpinglemma zu widerlegen, dass $L$ regulär ist? #flashcard
Angenommen $L$ sei regulär, dann würde nach PL ein $n\in \mathbb{N}$ existieren sodass sich jedes $w\in L$ mit $\left| w \right|\ge n$ schreiben lässt als $w=xyz$ mit:
1. $\left| xy \right|\le n$
2. $0 <\left| y \right|$
3. $xy^{i}z\in L\;\forall_{i\ge 0}$
Betrachte für **beliebiges** $n\in \mathbb{N}$ das Wort $w=\text{\color{red}Clever gewählt}$ mit $\left| w \right|\ge n\;,\;w\in L$.
Wegen 1. und 2. folgt, dass **jede** Zerlegung $w=xyz$ die Struktur $\color{red}\dots$  hat.
Für $k=\color{red}\text{Clever gewählt}$ betrachte dann aber $xy^{\color{red}k}z=\dots \not\in L$
Dies ist ein Widerspruch zur Annahme $L$ regulär.
<!--ID: 1786894783716-->


