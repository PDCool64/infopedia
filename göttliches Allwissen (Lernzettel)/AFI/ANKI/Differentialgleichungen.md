TARGET DECK: AFI::Differentialgleichungen
FILE TAGS: differentialgleichungen

Nenne die Schritte und Bedingungen für das Lösungsverfahren einer separierbaren, gewöhnlichen Differenzialgleichung. gegeben durch
$$
y'(x)=f(x)\cdot g(y(x))\;,\;y(x_{0})=y_{0}
$$
mit den Definitionsbereichen $f:I\to \mathbb{R}\;,\;g:J\to \mathbb{R}$
 #flashcard
1. Überprüfe $g(y_{0})\neq 0$
2. Bestimme $F(x)=\int_{x_{0}}^{x} f(t)dt$   (bzw. mit $F(x_{0})=0$)
3. Bestimme $H(y)=\int_{y_{0}}^{y} \frac{1}{g(s)}\;\text{d}s$   (bzw. mit $H(y_{0})=0$)
	1. Definitionsbereich von $H$: Sodass $y_{0}$ enthalten und wohldefiniert.
	   (Größtes Teilintervall von $J$, welches $y_{0}$ enthält und auf dem $g$ keine Nullstelle hat)
4. Löse $H(\varphi(x))=F(x)$ nach der Lösung $\varphi$ auf
<!--ID: 1772378141815-->



Wenn beim Lösen des Anfangswertproblems
$$
y'(x)=f(x)\cdot g(y(x))\;,\;y(x_{0})=y_{0}
$$
mit den Definitionsbereichen $f:I\to \mathbb{R}\;,\;g:J\to \mathbb{R}$
$g(y_{0})=0$ gilt, dann ist eine Lösung gegeben durch? #flashcard
$\varphi:I\to \mathbb{R}\;,\;\varphi(x)=y_{0}$
<!--ID: 1772378141819-->

