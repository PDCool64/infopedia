# Basics
Ein **Nachrichtenwort** $\in \mathbb{F}_{2}^{k}$ wird kodiert als **Codewort** $\in \mathbb{F}_{2}^{n}$.

Es gilt immer $k<n$ d.h. wir fügen **Redundanz** ein.

Der sog. **Code**, also die Menge der Codewörter, ist ein Untervektorraum $C\le\mathbb{F}_{2}^{n}$ mit $dim(C)=k$, da die Nachrichtenwörter aus $\mathbb{F}_{2}^{k}$ injektiv auf Codewörter abgebildet werden. Der Code besitzt somit genau $2^{k}$ Codewörter: Genau die Anzahl der Nachrichtenwörter.

Es werden **nicht alle** möglichen Wörter aus $\mathbb{F}_{2}^{n}$ verwendet, damit Fehler erkannt werden können.

# Umsetzung
Umsetzung **Kodierung**:
	Multiplikation mit einer **Generatormatrix** $A\in \mathbb{F}_{2}^{n\times k}$.$$\varphi_{A} : \mathbb{F}_{2}^{k}\to \mathbb{F}_{2}^{n}\;,\;v\mapsto Av$$
	 Dabei gilt $SR(A)=C$ und $\text{Rg}\,A=k$ d.h. die Spalten von $A$ sind Basis von $C$.	


Umsetzung **Dekodierung**:
	Für ein Empfangswort $w\in \mathbb{F}_{2}^{n}$ wird ein $v\in \mathbb{F}_{2}^{k}$ gesucht, sodass
	$Av=w$ $\to$ inhomogenes LGS lösen.
	Da $\text{Kern}(A)=\{ 0 \}$ bzw. die Kodierung injektiv, gibt es genau eine eindeutige Lösung, falls $w\in C$.
	Falls $w\not\in C$ gibt es keine Lösung: $w$ ist durch einen Übertragungsfehler enstanden.
# Kontrollmatrix
Wir wollen einen einfachen schnellen Test um zu überprüfen, ob ein Fehler aufgetreten ist oder nicht.
Idee: Schreibe $C=\mathbb{L}(B,0)$.

Dann gilt:
$$
v\in C \iff Bv=0
$$
Bestimmung einer Kontrollmatrix:
	gegeben: $C=SR(A)$ 
	gesucht:  $B$ sodass $C=SR(A)=\mathbb{L}(B,0)$
	verwende: $SR(A)=\mathbb{L}(B,0)\iff \mathbb{L}(A^{T},0)=SR(B^{T})$
	also:
		1. Löse $\mathbb{L}(A^{T},0)$
		2. Schreibe eine Basis des Lösungsraumes **zeilenweise** auf, um $B$ zu erhalten.

Dimension von Kontrollmatrizen:
	$B$ soll mit den Codewörtern der Länge $n$ multipliziert werden, also hat $B$ genau $n$ Spalten bzw $B\in \mathbb{F}_{2}^{l\times n}$.
	Es soll gelten $C=\mathbb{L}(B,0)$ also folgt $k=dim(C)=\text{Defekt}(B)$.
	Mit dem Rangsatz gilt: $n=\text{Defekt}(B)+\text{Rg}\,(B)$ also $\text{Rg}\,(B)=n-k$
	Wähle die kleinste Zeilenanzahl um diesen Rang zu erreichen:$$
B\in \mathbb{F}_{2}^{(n-k)\times n}
$$
	Durch diese minimale Wahl der Zeilenanzahl sind die Zeilen von $B$ linear unabhängig, um mit $n-k$ Zeilen auch Rang $n-k$ zu erreichen.

# Syndromdekodierung
Wird $x\in \mathbb{F}_{2}^{n}$ empfangen, prüft man mit $K$ sein "Krankheitsbild", das sog. **Syndrom** $y\in\mathbb{F}_{2}^{n-k}$ :
$$
y=Bx
$$
Falls $y=0$ gilt, ist $x\in C$ und wir nehmen an, dass kein Fehler aufgetreten ist.


Andernfalls gilt $x\not\in C$ und suchen wir den **nächsten Nachbarn** von $x$ in $C$.

Definiere den **Anführer** $e\in \mathbb{F}_{2}^{n}$ des Syndroms $y$ :
	Ein Anführer $e\in \mathbb{F}_{2}^{n}$ eines Syndroms $y\in \mathbb{F}_{2}^{n-k}$ ist ein Wort mit minimalem Gewicht, welches dieses Syndrom hat.
	(Anführer für ein Syndrom ist nicht unbedingt eindeutig)

Trick:
1. Bestimme einen Anführer $e$ des Syndroms $y=Bx$
2. Definiere $c:=x-e$. Dann gilt für den Anführer: $e=x-c$ 
	1. Es gilt $c\in C$ da $Bc=B(x-e)=Bx-Be=y-y=0$
3. Nach Definition des Anführers $e$ ist $wt(e)=wt(x-c)$ minimal unter
4. Da $c\in C$ und $wt(x-c)$ minimal, ist $c$ der nächste Nachbar von $x$ in $C$

Hat man nun entweder festgestellt, dass das empfangene Wort schon Codewort war oder ggfs. mit Syndromdekodierung festgestellt, um welches Codewort es sich wahrscheinlich gehandelt hat, muss man nur noch das inhomogene $Av=c$ lösen, um die Nachricht $v$ zurückzugewinnen.

Diese Dekodierung ist korrekt, wenn $\left\lfloor  \frac{d(C)-1}{2}  \right\rfloor$ oder weniger Fehler aufgetreten sind.

> Warum lohnt sich Syndromdekodierung:
> Problemstellung: von einem beliebigen empfangenen Wort $x\in \mathbb{F}_{2}^{n}$ auf den nächsten Nachbarn in $C$ schließen.
> 
> Option A: Lookuptabelle für nächsten Nachbarn jedes **empfangbaren Wortes** $\in \mathbb{F}_{2}^{n}$:
>	Lookuptabelle $\mathbb{F}_{2}^{n}\to C$ hat $2^{n}$ Einträge
>	
>Option B: Syndromdekodierung: Bloß für jedes **Syndrom** $\in \mathbb{F}_{2}^{n-k}$ den Anführer speichern:
>	Lookuptabelle $\mathbb{F}_{2}^{n-k}\to \mathbb{F}_{2}^{n}$ hat nur $2^{n-k}$ Einträge
>	
>	$\to$ Viele Empfangswörter besitzen dasselbe Syndrom und werden daher durch denselben Anführer korrigiert.


