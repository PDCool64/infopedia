TARGET DECK: LA::Lineare Codes

Welche Dimension hat die **Generatormatrix A**? #flashcard
$A\in K^{n\times k}$ mit $k<n$ 
Spalten linear unabhängig bzw. $\text{Rg}\,A=k$
<!--ID: 1786205085621-->


Welche Dimension hat die **Kontrollmatrix B**? #flashcard
$B\in K^{(n-k)\times n}$
<!--ID: 1786205085637-->


Welche Länge hat ein Nachrichtenwort? #flashcard
$k$
<!--ID: 1786205085644-->


Welche Länge hat ein Codewort? #flashcard
$n$
<!--ID: 1786205085652-->


Welche Länge hat ein Syndrom? #flashcard
$n-k$
<!--ID: 1786205085666-->


Welche Länge hat ein Anführer eines Syndroms? #flashcard
$n$
<!--ID: 1786205085688-->


Wie viele Nachrichten bzw. Codewörter kann ein Code $C$ übermitteln?
$2^{k}=\left| C \right|$

Wie beschreibt die Generatormatrix $A$ einen Code $C$? #flashcard
$C=SR(A)$
$k=dim(C)=\text{Rg}\,A$
<!--ID: 1786205085693-->


Wie beschreibt die Kontrollmatrix $B$ einen Code $C$? #flashcard
$C=\mathbb{L}(B,0)$
$v\in C \iff Bv=0$
<!--ID: 1786205085702-->


Wie kommt man von einem empfangenen Wort $x$ und dem Anführer seines Syndroms $e$ auf das nächstgelegene Codewort $c$? #flashcard
$c=x-e$
<!--ID: 1786205085713-->


Wie bestimmt man den Minimalabstand $d(C)$ eines Codes? #flashcard
$d(C)$ ist das minimale Hamming-Gewicht unter allen Codewörtern aus $C$.
Es entspricht der Größe einer minimalen linear abhängigen Teilmenge an Spalten der Kontrollmatrix $B$.
<!--ID: 1786205085729-->


Wie viele Fehler können in einem linearen Code **erkannt** werden? #flashcard
Bis zu inklusive $d(C)-1$ Fehler können erkannt werden.
<!--ID: 1786205085736-->


Wie viele Fehler können in einem linearen Code **korrigiert** werden? #flashcard
Bis zu inklusive $\left\lfloor  \frac{d(C)-1}{2}  \right\rfloor$ Fehler können korrigiert werden.
<!--ID: 1786205085745-->


Was besagt die **Singleton-Schranke**? #flashcard
$d(C)\le n-k+1$
<!--ID: 1786205085757-->

