TARGET DECK: FOSAP::Kontextfreie Sprachen

Definition: **Kontextfreie Grammatik** #flashcard
$G=(N,T,P,S)$
- $N$ nichtleere endliche Menge an **Nichtterminalen**
- $T$ nichtleere endliche Menge an **Terminalen**
- $N \cap T=\emptyset$
- $P$ nichtleere endliche Menge an **Produktionen**
  $A\to\alpha$ mit $A\in N\;,\;\alpha\in(N\cup T)^{*}$
- Das **Startsymbol** $S\in N$
<!--ID: 1786984714377-->


Definiere die **Ableitungsrelation** für kontextfreie Grammatiken #flashcard
$A\in N\;,\;\alpha,\beta\in(N\cup T)^{*}$ dann gilt:
$\alpha A\beta \Rightarrow_{G}\alpha\gamma\beta \;\iff\; (A\to\gamma)\in P$
<!--ID: 1786984714383-->


Definiere die Sprache einer kontextfreien Grammatik #flashcard
$G=(N,T,P,S)$
$L(G):=\{ w\in T^{*}\mid S \overset{*}\Rightarrow_{G}w \}$
<!--ID: 1786984714387-->


Wann ist eine kontextfreie Grammatik $G$ **eindeutig**? #flashcard
Wenn es für jedes Wort in $L(G)$ **genau eine Linksableitung** bzw. **genau einen Ableitungsbaum** gibt.
<!--ID: 1786984714391-->


Wann ist eine kontextfreie Sprache $L$ **eindeutig**? #flashcard
Wenn eine eindeutige kontextfreie Grammatik $G$ existiert mit $L=L(G)$.
<!--ID: 1786984714395-->



