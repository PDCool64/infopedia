*Ziel: im [[Binärsystem]] nicht nur [[Zahlenräume#Natürliche Zahlen $ mathbb{N}|natürliche Zahlen$]], sondern auch negative Zahlen -d.h. die [[Zahlenräume#Ganze Zahlen $ mathbb{Z}$|Ganzen Zahlen]] darstellen können.*

---
# Naiver Ansatz

"Wir designieren einen Bit -z.B. am Anfang der Zahl-, welcher entscheidet ob das Vorzeichen $+$ oder $-$ ist"

Probleme bei diesem Ansatz:
- Zwei Darstellungen für $0$ möglich: $+0$ und $-0$
- Umsetzung in der Hardware: Eine *einzige* einfache Schaltung wie der [Volladdierer](https://de.wikipedia.org/wiki/Volladdierer) würde nicht ausreichen, um Zahlen addieren und subtrahieren zu können: Man würde ein weiteres "Subtrahierwerk" (mehr teure Hardware) benötigen und Außerdem je nach Vorzeichen beider Zahlen entscheiden müssen, welches Rechenwerk verwendet werden muss

---
# Negative Zahlen als Einer-Komplement

>[!def] Einer-Komplement
> 
> Um das **Einer-Komplement** einer Binärzahl zu bilden, vertauscht man jeden Bit:
> $$K_{1}(x):=(\overline{x_{n-1}},\dots,\overline{x_{0}})_{2}$$
> ---
> 
> z.B. : $K_{1}(1011)=0100$
> 
> ---
> Es handelt sich bei dieser Abbildung um ein *Komplement* d.h. die Funktion hebt sich selbst wieder auf:
> $$K_{1}(K_{1}(x))=x$$
> ---
> Der Name *Komplement* ergibt sich daher, das die Ziffern einer Zahl und ihres Komplements sich genau zu $1$en ergänzen. Es gilt somit für zwei Binärzahlen mit $n$ Bit:
> $$\begin{align} &2^{n}-1=z+K_{1}(z) \\\\ \iff &K_{1}(z)= (2^{n}-1)-z
\end{align}$$

Mit dem **Einer-Komplement** können ganze Zahlen wie folgt codiert werden:
- Der *Most Significant Bit (MSB)* entscheidet darüber, ob die Zahl als positiv oder als negativ zu interpretieren ist:
	- MSB=0 : Interpretation wie im vorzeichenlosen Fall
	- MSB=1 : Bilde das Einer-Komplement $K_{1}$ der Zahl und interpretiere dieses als negative Zahl

### Beispiel:
$(0111)_{2}$ : MSB=0 $\to$ Interpretation wie im Vorzeichenlosen Fall $\to$ $(7)_{10}$
$(1100)_{2}$ : MSB=1 $\to$ Bilde $-K_{1}(1100)=-(0011)_{2}=-(3)_{10}$

## Addition im Einerkomplement
### Funktionierendes Beispiel:
$(3)_{10}+(-6)_{10}=(-3)_{10}$

$$
\begin{flalign}
(3)_{10} &= (0011)_{2} &\\
-(6)_{10} &= K_{1}(0110)_{2}=(1001)_{2}
\end{flalign}
$$

```
 0011 (3)
+1001 (-6)
  11  (Überträge)
-----
 1100 
```

Interpretation des Ergebnisses:
$(1100)_{2}$ : MSB ist $1$ $\to$ Bilde $-K_{1}(1100)_{2}=-(0011)_{2}=-(3)_{10}$

### ABER: Dies Funktioniert nicht immer perfekt
Wird die Null durchschritten entsteht ein "Off-By-One-Error" :

$(-4)_{10}+(6)_{10}=(2)_{10}$

$$
\begin{flalign}
-(4)_{10} &= K_{1}(0100)_{2}=(1011)_{2}&\\
 (6)_{10} &= (0110)_{2}
\end{flalign}
$$
```
 1011 (-4)
+0110 ( 6)
1110  (Überträge)
-----
 0001 (falsches Zwischenergebnis)
```

Um diesen Fehler zu beheben, muss der am weitesten links stehende Übertrag ausgewertet werden ([Wikipedia](https://de.wikipedia.org/wiki/Einerkomplement#:~:text=Die%200001%20st%C3%BCnde%20f%C3%BCr%20%2B1%2C%20nicht%20f%C3%BCr%20%2B2.%20Damit%20ein%20korrektes%20Ergebnis%20erscheint%2C%20muss%20der%20am%20weitesten%20links%20stehende%20%C3%9Cbertrag%20ausgewertet%20werden%20(hier%201)%20und%20ggf.%20das%20Ergebnis%20um%201%20erh%C3%B6ht%20werden.%20Mit%20anderen%20Worten%20muss%20der%20%C3%9Cbertrag%20noch%20zum%20Zwischenergebnis%20hinzuaddiert%20werden%3A)) : Steht dort eine $1$, so muss auf das Zwischenergebnis $1$ addiert werden, um das richtige Ergebnis zu erhalten.

In anderen Worten: Der übertrag der ganz links entsteht mach einen "wrap around" und muss ganz rechts addiert werden.  Es gibt einen "End around Carry" - Dies kann in der Hardware eines [Volladdierers](https://de.wikipedia.org/wiki/Volladdierer)  einfach umgesetzt werden, indem der `Carry_OUT` des MSB mit dem `Carry_IN` des LSB verkabelt wird.

### Warum dieser Fehler?
![[Negative Binärzahlen durch Komplement 2025-10-18 21.03.30.excalidraw]]

Man sieht: Da es zwei mögliche Darstellungen für $0$, nämlich `-0` und `+0` gibt, wird ein Schritt zu wenig gegangen, wenn die $0$ durchquert wird.
