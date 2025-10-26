
>[!def] Abbildung
> Seien $A, B$ nicht-leere [[Mengen]]. Eine **Abbildung** $f$ von $A$ nach $B$ ist eine Vorschrift, die jeden $x \in A$ *genau ein* $y \in B$ zuordnet.
> 
> Man nennt $x$ das *Argument* und
> $f(x):=y$ das *Bild von $x$ unter $f$*.
> 
> Man schreibt die Abbildung in der Form:
> $$f:A\to B,\;x\mapsto f(x)$$
> 
> Man nennt die Menge $A$ *Definitionsbereich* und
> die Menge $B$ *Zielbereich oder Ziel* der Abbildung.
> 
> ___
> 
> Die Menge $$G_{f}:=\{ (x,f(x))\mid x\in A \}\subseteq A\times B$$
> nennt man *Graph von $f$*.
>
>---
>Zei Abbildungen 
> $f: A \to B$ und  $g: U \to V$ heißen gleich,
>  wenn $A=U \land B=V$ und $f(x) = g(x) \forall x \in A$

### Beispiel
$f: \mathbb{R} \to \mathbb{R}, x \mapsto x^{2}$
$g: \mathbb{R} \to \mathbb{R}, x \mapsto (x+r)^{2}$

---

# Bild, Urbild und Wertebereich
>[!def] Bild, Urbild, Wertebereich
> 
> Seien $A.B$ nicht-leere Mengen und $f:A\to B$ eine Abbildung. 
> 
> ---
> Für $M\subseteq A$ heißt
> $$f(M):=\{ f(x) \mid x\in M\}$$ das **Bild von $M$ unter $f$**. Speziell nennt man $f(A)$ die **Wertemenge von $f$**.
> 
> ---
> Für $N\subseteq B$ heißt
> $$f^{-1}(N):=\{ x\in A \mid f(x)\in N \}$$ das **Urbild von $N$ unter $f$**.

## Bemerkung
- Es werden hier [[Mengen]] in die die Klammern der Funktion geschrieben, *nicht* einzelne Werte.
- Die Schreibweise $f^{-1}(N)$ darf keinesfalls mit der Umkehrabbildung verwechselt werden!
  Für jede Menge $N\subseteq B$ existiert sicher ein Urbild $f^{-1}(N)$, auch wenn dies $\emptyset$ ist.
  Die Umkehrabbildung (welche einzelne Elemente abbilden würde) existiert aber nur für bijektive Abbildungen und kann nicht allgemein angenommen werden.


---

# Restriktion des Definitionsbereichs
>[!def] Restriktion einer Abbildung
> 
> Ist $f:A\to B,\;x\mapsto f(x)$ eine Abbildung und $M$ eine nicht-leere Teilmenge des Definitionsbereichs $A$, so heißt die Abbildung $$
> f|_{M}:M\to B,\;x\mapsto(f|_{M})(x):=f(x)
> $$ die **Restriktion** oder **Einschränkung** von $f$ auf $M$. 

---


---
# Injektiv, Surjektiv, Bijektiv

>[!def] Surjektiv
>Das Bild schöpft den Zielbereich aus. Jeder Wert in Z wird getroffen.
>
>Bsp. $f: \mathbb{R} \mapsto \mathbb{R}, x \mapsto x^{2}$ ist *nicht surjektiv*, weil $f(\mathbb{R})=\mathbb{R}_{x\geq0}\subset \mathbb{R}$
>d.h. weil die negativen reelen Zahlen nicht getroffen werden.
>
>$\forall_{y\in Z} \exists_{x\in D} :f(x)=y \implies f$ ist surjektiv

^cf856f

> [!def] Injektiv
> Wenn jedes Element im Zielbereich höchstens einmal als Bild auftritt.
> $\forall_{z\in Z}$ gibt es *höchstens ein* $x\in D$ so, dass $f(x)=z$.
> 
> Entspricht:
> falls $f^{-1}(\{ z \})$ höchstens ein Element enthält, also entweder $f^{-1}(\{ z \})=\emptyset$ oder $f^{-1}(\{ z \})=\{ x \}$ für ein $x\in D$
> 
> Dies bedeutet, dass für alle Definitionswerte, die Funktionswerte unterschiedlich sind.
> 
> Bsp: Die Funktion $f: \mathbb{R}\mapsto \mathbb{R},x\mapsto e^x$ ist Injektiv.

^d80cf2


Bsp.
Für $f:\mathbb{R}\mapsto \mathbb{R},x\mapsto x^{2}$ gilt z.B. $f(2)=4=f(-2)$ und $-2\neq 2$, also ist $f$ nicht Injektiv.
Will man diese Funktion Injektiv machen, kann man sie umschreiben zu: $\overset{\sim}{f}:\mathbb{R}_{x\geq_{0}}\mapsto \mathbb{R},x\mapsto x^{2}$ macht es injektiv.


> [!def] Bijektiv
> Ist Die Funktion surjektiv und injektiv, ist sie bijektiv.
> 
> Klassische bijektive Funktionen sind Vertauschungen (Permutationen). 
> 
> Auch die Identische Abbildung ist bijektiv $id_{D}:D\mapsto D,x\mapsto x,D\neq \emptyset$
> Denn: surjektiv, weil für jedes $z\in D$ ist $id_{D}(z)=z$, also ist $id_{D}(D)=D$.
> Injektiv, weil. Wenn immer $id_{D}(x)=id_{D}(y)$ gilt, $x=y$
> 
> Auch $f:\mathbb{R}\mapsto \mathbb{R},x\mapsto x^3$ ist bijektiv.