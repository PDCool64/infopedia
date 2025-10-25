---
tags:
status: rot
---
---

>[!def] Kontextfreie Grammatik
>Eine **Kontextfreie Grammatik** ist ein $4$-Tupel $(N,T,P,S)$ mit folgenden Definitionen
> - $N$ ist eine endliche, nichtleere Menge von *Nichtterminalen*.
>   (meist Großbuchstaben als Variablennamen)
>   
> - $T$ ist eine endliche, nichtleere Menge von *Terminalen* mit $N\cap T=\emptyset$
>   (meist Kleinbuchstaben als Zeichen)
>   
> - $P\subseteq N\times(N\cup T)^{*}$ ist eine endliche, nichtleere Menge von *Produktionsregeln*, welche jeweils genau ein *Nichtterminal* abbilden auf eine beliebige Kombination von *Terminalen und/oder Nichtterminalen*. Eine Produktionsregel $X\to Y$ erlaubt es das Nichtterminal $X$ durch das Teilwort $Y$ ersetzen darf.
>   
> - $S\in N$ ist das Startsymbol, von dem alle Wörter der Sprache nach den *Produktionsregeln* hergeleitet werden.

## Bemerkungen
- Bei den Produktionsregeln ist als einziges entscheidend, das *links nur genau ein Nichtterminal steht*. Rechts hingegen darf beliebig kombiniert werden. Steht $a\in T$  stellvertretend für beliebige und auch verschieden Terminale und $B\in N$ stellvertretend für beliebige und auch verschiedene Nichtterminale, dann sind z.B. solche und ähnliche Produktionsregeln erlaubt:
	- $B\to a$
	- $B\to aB$
	- $B\to Baaa$
	- $B\to BaB$
	- $B\to aBBaBa$
	- $B\to BBBBa$
	- $B\to \epsilon$    (Das leere Wort ist erlaubt)
	- ...
	An der Definition wird dies Ebenfalls ersichtlich: $P\subseteq N\times(N\cup T)^{*}$
	- "$N\times$" besagt das die erste Hälfte der Tupel (d.h. das, von dem aus abgebildet wird) nur aus einzelnen Nichterminalen besteht
	- "$\times(N\cup T)^{*}$" enthält in der Klammer ein Alphabet aus allen Terminalen und Nichtterminalen. der Stern " $^{*}$  " um ein Alphabet bezeichnet die Menge *aller* möglichen Wörter über diesem Alphabet - es ist also jede beliebige Kombination von Terminalen und Nichtterminalen möglich.

## Beispiel: Klammergrammatik:

Die Grammatik von korrekten Klammern (d.h. gleich viele öffnende wie schließende Klammern sowie, dass jeder Präfix eines Worts nie mehr schließende als öffnende Klammern enthalten darf.)
Lässt sich beispielsweise so schreiben:
$G=(N,T,P,S)$ 

$N=\{ K \}$
$T=\{ \;(\;,\;)\; \}$
$S=K$

$P=\{$
- $K\to\epsilon$
- $K\to(K)K$
$\quad\}$

---
# Sprache einer Grammatik

>[!def] Sprache einer Grammatik
> Die **Sprache $L(G)$ einer Grammatik** $G$ (dies muss nicht spezifisch eine kontextfreie Grammatik sein) ist 
$$L(G)=\{ w\mid w\in T^{*} \;,\;\underbrace{ S\implies\dots\implies w }_{ \text{mit } P } \}$$
>
> ---
> Zwei Grammatiken sind *äquivalent*, wenn sie die gleiche Sprache erzeugen.



---

# EBNF - Extended Backus-Naur-Form
Eine kürzere/kompaktere Schreibweise für Kontextfreie Grammatiken. (Gleichmächtig)
Nichtterminale werden hier in Anführungszeichen geschrieben.

1. Aus $A\to B$ wird $A=B$ als andere Schreibweise für die Abbildung bei einer Produktionsregel
2. Produktionsregeln die vom gleichen Nichtterminal ausgehen können mit "Oder" in einer Zeile geschrieben werden. 
	   Aus
		   $A\to y_{1}$
		   $A\to y_{2}$
		   $A\to y_{3}$ 
	   wird:
		   $A=(y_{1} \mid y_{2} \mid y_{3})$
3. Optionale Teile können in eckigen Klammern geschrieben werden.
      Aus
		   $A\to xz$
		   $A\to xyz$
	   wird:
		   $A=x[y]z$
4. Teile, die beliebig oft (inkl. 0) mal hintereinander gegangen werden können in geschweiften Klammern geschrieben werden.
	   Aus
		   $A\to xA$
		   $A\to y$
	   wird:
		   $A=\{ x \}y$


## Beispiel: Klammergrammatik als EBNF
Die [[#Beispiel Klammergrammatik|obige Klammergrammatik]] kann auch sehr kurz als EBNF geschrieben werden:
$K=\{ \;''(''\;K\;'')''\; \}$

---
# Syntaxdiagramme
Kontextfreie Grammatiken können ebenfalls als (ggfs. rekursive) Syntaxdiagramme angegeben werden.
- für *jedes* Nichtterminal ein Syntaxdiagramm
- Die Pfeile geben an

## Beispiel: Klammergrammatik als Syntaxdiagramm

```tikz
\begin{document}
\begin{tikzpicture}[scale=1.5, every node/.style={scale=1.2}, line width=1pt]
            \draw[->,very thick] (-3,0) -- (6,0);
            \node[font=\Large] at (-3,2) {K:};

            \begin{scope}[shift={(2,0)}]
                \draw[->,thick] (0,0)--(0,1)--(1,1);
                \draw[thick] (1,0.7) rectangle (2,1.3);
                \node at (1.5,1) {K};
                \draw[->,thick] (2,1)--(3,1)--(3,0);
            \end{scope}

            \begin{scope}[shift={(-2,0)}]
                \draw[->,thick] (0,0)--(0,1)--(1,1);
                \draw[thick,fill=white] (0.5,1) circle (0.25);
                \node at (0.5,1) {(};
                
                \draw[thick] (1,0.7) rectangle (2,1.3);
                \node at (1.5,1) {K};
                
                \draw[->,thick] (2,1)--(3,1)--(3,0);
                \draw[thick,fill=white] (2.5,1) circle (0.25);
                \node at (2.5,1) {)};
                
            \end{scope}

		\node at (0,-1) {};
            
        \end{tikzpicture}
\end{document}
```


---

>[!def] Kontextfreie Grammatik
>Eine **Kontextfreie Grammatik** ist ein $4$-Tupel $(N,T,P,S)$ mit folgenden Definitionen
> - $N$ ist eine endliche, nichtleere Menge von *Nichtterminalen*.
>   (meist Großbuchstaben als Variablennamen)
>   
> - $T$ ist eine endliche, nichtleere Menge von *Terminalen* mit $N\cap T=\emptyset$
>   (meist Kleinbuchstaben als Zeichen)
>   
> - $P\subseteq N\times(N\cup T)^{*}$ ist eine endliche, nichtleere Menge von *Produktionsregeln*, welche jeweils genau ein *Nichtterminal* abbilden auf eine beliebige Kombination von *Terminalen und/oder Nichtterminalen*. Eine Produktionsregel $X\to Y$ erlaubt es das Nichtterminal $X$ durch das Teilwort $Y$ ersetzen darf.
>   
> - $S\in N$ ist das Startsymbol, von dem alle Wörter der Sprache nach den *Produktionsregeln* hergeleitet werden.

## Bemerkungen
- Bei den Produktionsregeln ist als einziges entscheidend, das *links nur genau ein Nichtterminal steht*. Rechts hingegen darf beliebig kombiniert werden. Steht $a\in T$  stellvertretend für beliebige und auch verschieden Terminale und $B\in N$ stellvertretend für beliebige und auch verschiedene Nichtterminale, dann sind z.B. solche und ähnliche Produktionsregeln erlaubt:
	- $B\to a$
	- $B\to aB$
	- $B\to Baaa$
	- $B\to BaB$
	- $B\to aBBaBa$
	- $B\to BBBBa$
	- $B\to \epsilon$    (Das leere Wort ist erlaubt)
	- ...
	An der Definition wird dies Ebenfalls ersichtlich: $P\subseteq N\times(N\cup T)^{*}$
	- "$N\times$" besagt das die erste Hälfte der Tupel (d.h. das, von dem aus abgebildet wird) nur aus einzelnen Nichterminalen besteht
	- "$\times(N\cup T)^{*}$" enthält in der Klammer ein Alphabet aus allen Terminalen und Nichtterminalen. der Stern " $^{*}$  " um ein Alphabet bezeichnet die Menge *aller* möglichen Wörter über diesem Alphabet - es ist also jede beliebige Kombination von Terminalen und Nichtterminalen möglich.

## Beispiel: Klammergrammatik:

Die Grammatik von korrekten Klammern (d.h. gleich viele öffnende wie schließende Klammern sowie, dass jeder Präfix eines Worts nie mehr schließende als öffnende Klammern enthalten darf.)
Lässt sich beispielsweise so schreiben:
$G=(N,T,P,S)$ 

$N=\{ K \}$
$T=\{ \;(\;,\;)\; \}$
$S=K$

$P=\{$
- $K\to\epsilon$
- $K\to(K)K$
$\quad\}$

---
# Sprache einer Grammatik

>[!def] Sprache einer Grammatik
> Die **Sprache $L(G)$ einer Grammatik** $G$ (dies muss nicht spezifisch eine kontextfreie Grammatik sein) ist 
$$L(G)=\{ w\mid w\in T^{*} \;,\;\underbrace{ S\implies\dots\implies w }_{ \text{mit } P } \}$$
>
> ---
> Zwei Grammatiken sind *äquivalent*, wenn sie die gleiche Sprache erzeugen.



---

# EBNF - Extended Backus-Naur-Form
Eine kürzere/kompaktere Schreibweise für Kontextfreie Grammatiken. (Gleichmächtig)
Nichtterminale werden hier in Anführungszeichen geschrieben.

1. Aus $A\to B$ wird $A=B$ als andere Schreibweise für die Abbildung bei einer Produktionsregel
2. Produktionsregeln die vom gleichen Nichtterminal ausgehen können mit "Oder" in einer Zeile geschrieben werden. 
	   Aus
		   $A\to y_{1}$
		   $A\to y_{2}$
		   $A\to y_{3}$ 
	   wird:
		   $A=(y_{1} \mid y_{2} \mid y_{3})$
3. Optionale Teile können in eckigen Klammern geschrieben werden.
      Aus
		   $A\to xz$
		   $A\to xyz$
	   wird:
		   $A=x[y]z$
4. Teile, die beliebig oft (inkl. 0) mal hintereinander gegangen werden können in geschweiften Klammern geschrieben werden.
	   Aus
		   $A\to xA$
		   $A\to y$
	   wird:
		   $A=\{ x \}y$


## Beispiel: Klammergrammatik als EBNF
Die [[#Beispiel Klammergrammatik|obige Klammergrammatik]] kann auch sehr kurz als EBNF geschrieben werden:
$K=\{ \;''(''\;K\;'')''\; \}$

---
# Syntaxdiagramme
Kontextfreie Grammatiken können ebenfalls als (ggfs. rekursive) Syntaxdiagramme angegeben werden.
- für *jedes* Nichtterminal ein Syntaxdiagramm
- Die Pfeile geben an

## Beispiel: Klammergrammatik als Syntaxdiagramm

```tikz
\begin{document}
\begin{tikzpicture}[scale=1.5, every node/.style={scale=1.2}, line width=1pt]
            \draw[->,very thick] (-3,0) -- (6,0);
            \node[font=\Large] at (-3,2) {K:};

            \begin{scope}[shift={(2,0)}]
                \draw[->,thick] (0,0)--(0,1)--(1,1);
                \draw[thick] (1,0.7) rectangle (2,1.3);
                \node at (1.5,1) {K};
                \draw[->,thick] (2,1)--(3,1)--(3,0);
            \end{scope}

            \begin{scope}[shift={(-2,0)}]
                \draw[->,thick] (0,0)--(0,1)--(1,1);
                \draw[thick,fill=white] (0.5,1) circle (0.25);
                \node at (0.5,1) {(};
                
                \draw[thick] (1,0.7) rectangle (2,1.3);
                \node at (1.5,1) {K};
                
                \draw[->,thick] (2,1)--(3,1)--(3,0);
                \draw[thick,fill=white] (2.5,1) circle (0.25);
                \node at (2.5,1) {)};
                
            \end{scope}

		\node at (0,-1) {};
            
        \end{tikzpicture}
\end{document}
```


---

>[!def] Kontextfreie Grammatik
>Eine **Kontextfreie Grammatik** ist ein $4$-Tupel $(N,T,P,S)$ mit folgenden Definitionen
> - $N$ ist eine endliche, nichtleere Menge von *Nichtterminalen*.
>   (meist Großbuchstaben als Variablennamen)
>   
> - $T$ ist eine endliche, nichtleere Menge von *Terminalen* mit $N\cap T=\emptyset$
>   (meist Kleinbuchstaben als Zeichen)
>   
> - $P\subseteq N\times(N\cup T)^{*}$ ist eine endliche, nichtleere Menge von *Produktionsregeln*, welche jeweils genau ein *Nichtterminal* abbilden auf eine beliebige Kombination von *Terminalen und/oder Nichtterminalen*. Eine Produktionsregel $X\to Y$ erlaubt es das Nichtterminal $X$ durch das Teilwort $Y$ ersetzen darf.
>   
> - $S\in N$ ist das Startsymbol, von dem alle Wörter der Sprache nach den *Produktionsregeln* hergeleitet werden.

## Bemerkungen
- Bei den Produktionsregeln ist als einziges entscheidend, das *links nur genau ein Nichtterminal steht*. Rechts hingegen darf beliebig kombiniert werden. Steht $a\in T$  stellvertretend für beliebige und auch verschieden Terminale und $B\in N$ stellvertretend für beliebige und auch verschiedene Nichtterminale, dann sind z.B. solche und ähnliche Produktionsregeln erlaubt:
	- $B\to a$
	- $B\to aB$
	- $B\to Baaa$
	- $B\to BaB$
	- $B\to aBBaBa$
	- $B\to BBBBa$
	- $B\to \epsilon$    (Das leere Wort ist erlaubt)
	- ...
	An der Definition wird dies Ebenfalls ersichtlich: $P\subseteq N\times(N\cup T)^{*}$
	- "$N\times$" besagt das die erste Hälfte der Tupel (d.h. das, von dem aus abgebildet wird) nur aus einzelnen Nichterminalen besteht
	- "$\times(N\cup T)^{*}$" enthält in der Klammer ein Alphabet aus allen Terminalen und Nichtterminalen. der Stern " $^{*}$  " um ein Alphabet bezeichnet die Menge *aller* möglichen Wörter über diesem Alphabet - es ist also jede beliebige Kombination von Terminalen und Nichtterminalen möglich.

## Beispiel: Klammergrammatik:

Die Grammatik von korrekten Klammern (d.h. gleich viele öffnende wie schließende Klammern sowie, dass jeder Präfix eines Worts nie mehr schließende als öffnende Klammern enthalten darf.)
Lässt sich beispielsweise so schreiben:
$G=(N,T,P,S)$ 

$N=\{ K \}$
$T=\{ \;(\;,\;)\; \}$
$S=K$

$P=\{$
- $K\to\epsilon$
- $K\to(K)K$
$\quad\}$

---
# Sprache einer Grammatik

>[!def] Sprache einer Grammatik
> Die **Sprache $L(G)$ einer Grammatik** $G$ (dies muss nicht spezifisch eine kontextfreie Grammatik sein) ist 
$$L(G)=\{ w\mid w\in T^{*} \;,\;\underbrace{ S\implies\dots\implies w }_{ \text{mit } P } \}$$
>
> ---
> Zwei Grammatiken sind *äquivalent*, wenn sie die gleiche Sprache erzeugen.



---

# EBNF - Extended Backus-Naur-Form
Eine kürzere/kompaktere Schreibweise für Kontextfreie Grammatiken. (Gleichmächtig)
Nichtterminale werden hier in Anführungszeichen geschrieben.

1. Aus $A\to B$ wird $A=B$ als andere Schreibweise für die Abbildung bei einer Produktionsregel
2. Produktionsregeln die vom gleichen Nichtterminal ausgehen können mit "Oder" in einer Zeile geschrieben werden. 
	   Aus
		   $A\to y_{1}$
		   $A\to y_{2}$
		   $A\to y_{3}$ 
	   wird:
		   $A=(y_{1} \mid y_{2} \mid y_{3})$
3. Optionale Teile können in eckigen Klammern geschrieben werden.
      Aus
		   $A\to xz$
		   $A\to xyz$
	   wird:
		   $A=x[y]z$
4. Teile, die beliebig oft (inkl. 0) mal hintereinander gegangen werden können in geschweiften Klammern geschrieben werden.
	   Aus
		   $A\to xA$
		   $A\to y$
	   wird:
		   $A=\{ x \}y$


## Beispiel: Klammergrammatik als EBNF
Die [[#Beispiel Klammergrammatik|obige Klammergrammatik]] kann auch sehr kurz als EBNF geschrieben werden:
$K=\{ \;''(''\;K\;'')''\; \}$

---
# Syntaxdiagramme
Kontextfreie Grammatiken können ebenfalls als (ggfs. rekursive) Syntaxdiagramme angegeben werden.
- für *jedes* Nichtterminal ein Syntaxdiagramm
- Terminale stehen in Ovalen/Kreisen
- Nichtterminale stehen in Rechtecken
- Die Pfeile geben an, welche Wörter aus dem Nichtterminal hergeleitet werden können

## Beispiel: Klammergrammatik als Syntaxdiagramm

```tikz
\begin{document}
\begin{tikzpicture}[scale=1.5, every node/.style={scale=1.2}, line width=1pt]
            \draw[->,very thick] (-3,0) -- (6,0);
            \node[font=\Large] at (-3,2) {K:};

            \begin{scope}[shift={(2,0)}]
                \draw[->,very thick] (0,0)--(0,1)--(1,1);
                \draw[thick] (1,0.7) rectangle (2,1.3);
                \node at (1.5,1) {K};
                \draw[->,very thick] (2,1)--(3,1)--(3,0);
            \end{scope}

            \begin{scope}[shift={(-2,0)}]
                \draw[->,very thick] (0,0)--(0,1)--(1,1);
                \draw[thick,fill=white] (0.5,1) circle (0.25);
                \node at (0.5,1) {(};
                
                \draw[thick] (1,0.7) rectangle (2,1.3);
                \node at (1.5,1) {K};
                
                \draw[->,very thick] (2,1)--(3,1)--(3,0);
                \draw[thick,fill=white] (2.5,1) circle (0.25);
                \node at (2.5,1) {)};
                
            \end{scope}

		\node at (0,-1) {};
            
        \end{tikzpicture}
\end{document}
```




