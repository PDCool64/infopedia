$A\times(B\cap C)=(A\times B) \cap (A \times C)$
![[Blatt 10 2025-10-20 17.30.48.excalidraw]]


$$
\begin{array}{rll}        
&&A \times (B \cap C)                                &|\;\text{Definition des kartesischen Produkts}\\ 
&= &\{ (a,x) \mid a\in A \;,\;x\in(B \cap C)\}  &|\;\text{Definition der Schnittmenge} \\ &=& \{ (a,x) \mid a\in A\;,(x\in B)\wedge(x\in C) \}          &|\;\text{Bedingungen zusammenschreiben}  \\ 

&=& \{ (a,x) \mid (a\in A) \wedge (x\in B)\wedge(x\in C) \}    &
\end{array}
$$

$$
\begin{array}{rll}        
&&A \times (B \cap C)                                &|\;\text{Definition des kartesischen Produkts}\\ \\
&=&\{ (a,x) \mid a\in A \;,\;x\in(B \cap C)\}  &|\;\text{Definition der Schnittmenge} \\ \\ \\
&=& \{ (a,x) \mid a\in A\;,(x\in B)\wedge(x\in C) \}          &|\;\text{Aussonderungsbedingungen zusammenschreiben}  \\ \\

&=& \{ (a,x) \mid (a\in A) \wedge (x\in B)\wedge(x\in C) \}    &|\;\text{Mit Idempotenz ein redundantes }(a\in A) \text{ einfügen} \\ \\
 
&=& \{ (a,x)\mid(a\in A)\wedge(a\in A)\wedge(x\in B)\wedge(x\in C) \} &|\;\text{Kommutativgesetz der Aussagen} \\ \\

&=& \{ (a,x)\mid(a\in A)\wedge(x\in B)\wedge(a\in A)\wedge(x\in C) \} &|\;\text{Assoziativgesetz der Aussagen} \\ \\

&=& \{ (a,x)\mid(a\in A\wedge x\in B)\wedge(a\in A\wedge x\in C) \} &|\;\text{Definition der Schnittmenge} \\ \\
 
&=& \{ (a,x)\mid a\in A\wedge x\in B \} \cap \{ (a,x) \mid a\in A \wedge x\in C\} &|\;\text{Definition des kartesischen Produkts} \\\\ 

&=&(A\times B)\cap(A\times C)
\end{array}
$$



----


und:
$$
\begin{array}{rll}        
&&(A\times B) \cap(A \times C)                            &|\;\text{Definition des kartesischen Produkts}\\ 
&=& \{ (a,b)\mid a\in A , b\in B \} \cap \{ (a,c)\mid a\in A , c\in C \}   &|\;\text{Aussonderungsbedingungen durch Aussageformen umschreiben}  \\
&=& \{ (a,b)\mid(a\in A)\wedge (b\in B) \} \cap \{ (a,c)\mid (a\in A)\wedge (c\in C) \}\\
 \\

&&&|\;\text{Definition der Schnittmenge} \\ &=& \{ (a,x) \mid (a\in A\;\wedge(x\in B))\wedge(x\in C) \}          &|\;\text{Bedingungen zusammenschreiben}  \\ 

&=& \{ (a,x) \mid (a\in A) \wedge (x\in B)\wedge(x\in C) \}    &
\end{array}
$$

Eingabevariablen



# Letze Teilaufgabe:
![[Blatt01 2025-10-22 09.20.11.excalidraw]]


Zu zeigen ist die Implikation:
$x\in \big( (A\cup B)\setminus(A\cup C) \big)\implies x\in\big(A \cup(B\setminus C)\big)$

$$\begin{array}{rllll}
&x\in \big( (A\cup B)\setminus(A\cup C) \big) &|\;\text{Def. Komplement}\\
\implies& x\in(A\cup B)\wedge x \not\in (A \cup C) &|\; \text{Def. Vereinigungsmenge, De Morgansches} \\
\implies &(x\in A \vee x\in B)\wedge(x\not\in A \wedge x \not\in C) &|\;\text{Assoziativgesetz der Aussagen} \\
\implies& \big((x\in A\vee x\in B)\wedge x\not\in A)\wedge x \not\in C &|\;\text{Distributivgesetz der Aussagen} \\
\implies & \big((x\in A\wedge x \not\in A)\vee(x\in B\wedge x\not\in A)\big)\wedge x \not\in C &|\;\text{Komplementärgesetz, Neutralitätsgesetz } \\
\implies &(x\in B \wedge x \not\in A)\wedge x\not\in C &|\;\text{Def. Komplement} \\ 
\implies &   x\in(B\setminus C)       &|\;\text{Weil }\forall_{X,M,x}: x\in X\implies x\in X \cup M  \\

\implies&x\in(A\cup(B\setminus C))

\end{array}$$



