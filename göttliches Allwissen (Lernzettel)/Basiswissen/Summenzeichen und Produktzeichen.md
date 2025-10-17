>[!def] Summen- und Produktzeichen
>Sei $I$ eine endliche Menge.
>  ( $i$ heißt **Index** und $I$ **Indexmenge**)
>  Dann bezeichnet
>  - $\sum_{i\in I}$ die **Summe** der Zahlen $a_{i}$ mit $i\in I$
>  - $\prod_{i\in I}$ das **Produkt** der Zahlen $a_{i}$ mit $i\in I$
>

## Schreibweisen:
Ist die Indexmenge $I$ aus [[Zahlenräume#Natürliche Zahlen $ mathbb{N}$|Natürliche Zahlen]] wie $I=\{ 1,2,3,\dots,n \}$ gegeben, kann auch geschrieben werden:$$
\sum_{i\in I}=\sum_{i=1}^{n}
$$ sowie:
$$
\prod_{i\in I}=\prod_{i=1}^{n}
$$

## Indexverschiebung
Die Indexe in einer Summe sind lediglich *Laufvariablen* - sie können recht frei gewählt, verschoben und umbenannt werden.

Bsp: Sei $A=\{ a_{1},\dots,a_{n} \}$ eine Menge, dann ist egal wie die Indexe geschrieben werden:

$$
\sum_{i=1}^{n}a_{i}=\sum_{i=2}^{n+1}a_{i-1}=\sum_{i=-4}^{n-4}a_{i+5}=\sum_{i=0 }^{n-1}a_{n-i}=\sum_{\text{karlheinz}=2}^{2\cdot n}a_{\text{karlheinz}\,:\,2}
$$
Indexverschiebungen sind sehr nützlich, weil man damit Summen so aneinander anpassen kann, dass [[Summengesetze]] angewendet werden können.
### Merke dabei:
Wird der Index $i$ um $v$ verschoben, ändert ändert dieser sich *in der Summe* genau in die andere Richtung als *am Summenzeichen*.
$$\sum_{i=s}^{n}a_{i}=\sum_{i=s{\color{green}{+}}v}^{n{\color{green}{+}}v}a_{i{\color{red}{-}}v}$$
Nur dann heben sich beide Änderungen auf so, dass 
- das erste Element $i=s+v \to a_{(s+v)-v}=a_{s}$
- das letzte Element $i=n+v\to a_{(n+v)-v}=a_{n}$
gleich mit der Ausgangssumme bleiben.