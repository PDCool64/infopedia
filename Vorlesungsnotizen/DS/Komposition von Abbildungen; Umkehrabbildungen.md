---
tags:
  - DS
status: rot
---
---

>[!def] Komposition zweier Abbildungen
> Ist $f:A\to B$ eine Abbildung und $g:B\,'\to C$ eine weitere Abbildung mit der Eigenschaft $f(A)\subseteq B\,'$ , so nennt man $$
> f \circ g:A\to C,\;x\mapsto(f\circ g)(x):=f(g(x))
> $$ die **Verkettung** oder **Komposition** oder **Hintereinanderausführung** von $f$ und $g$.

> In DS kommen fast ausschließlich Abbildungen mit $B=B\,'$ vor.

# Assoziativität der Komposition

>[!def] Assoziativität der Komposition
> Für $f:M\to N\;,\;g:N\to L\;,\;h:L\to K$ gilt:
> $$
> h\circ(g\circ f) = (h\circ g) \circ f
> $$

> Die Komposition ist *nicht* kommutativ! $f\circ g \neq g\circ f$ 

## Komposition mit der Identität
>[!def] Komposition mit der Identität
>Für alle Abbildungen $f:M\to N$ gilt
> $$
> f\circ \text{id}_{M} = f = id_{N}\circ f
> $$


---
# Umkehrabbildungen
>[!def] Umkehrabbildungen
> 
> Es seien $f:M\to N$ und $g:N\to M$ [[Abbildungen]].
> 
> >[!def] Linksseitige Umkehrabbildung
> > $g$ ist **linksseitige Umkehrabbildung von $f$**, falls gilt
> >   $$
> > g \circ f = \text{id}_{M}
> > $$
>
> >[!def] Rechtsseitige Umkehrabbildung
> $g$ ist **rechtsseitige Umkehrabbildung von $f$**, falls gilt $$
> > f\circ g = \text{id}_{M}
> > $$
> 
> >[!def] Umkehrabbildung bzw. Inverses
> $g$ ist **Umkehrabbildung** von $f$ , man sagt auch **invers**, falls gilt $$
> > g\circ f = \text{id}_{M}\quad\text{und} \quad f\circ g=\text{id}_{N}
> > $$ also wenn $g$ und $f$ rechts- und linksseitige Umkehrabbildungen von einander sind.
> > ---
> > Die Umkehrabbildung ist, falls existent, eindeutig bestimmt. 
> > Sie wird mit $f^{-1}$ bezeichnet:
> > $$f^{-1} \circ f = \text{id}_{M}\quad\text{und}\quad f\circ f^{-1}=\text{id}_{N}$$ 
> > 
> > 


## Existenz von Umkehrabbildungen und [[Abbildungen#Injektiv, Surjektiv, Bijektiv|Surjektivität, Injektivität, Bijektivität]]

>[!def] Umkehrabbildungen und Surjektivität, Injektivität sowie Bijektivität
> Es gilt:
> - $f$ hat *links*seitige Umkehrabbildung $\iff$ $f$ ist [[Abbildungen#Injektiv, Surjektiv, Bijektiv|Injektiv]].
>   
>   Wäre $f$ nicht injektiv, dann könnte eine *danach* ausgeführte (also links stehende) die Elemente nicht mehr aus einander halten und korrekt umkehren.
> > Merke: in l*i*nksinvertierbar ist ein $i$ genauso wie in *i*njektiv.
>  $\;$
> - $f$ hat *rechts*seitige Umkehrabbildung $\iff$ $f$ ist [[Abbildungen#Injektiv, Surjektiv, Bijektiv|surjektiv]]
>   
>   Wäre $f$ nicht surjektiv, dann könnte man es nicht *nach* einer anderen (also rechts stehenden) Funktion ausführen, und wieder alle Elemente erhalten.
>  $\;$
> - $f$ besitzt Umkehrabbildung $\iff$ $f$ ist [[Abbildungen#Injektiv, Surjektiv, Bijektiv|Bijektiv]]

## Exemplarischer Beweis für Injektivität:
$f:M\to N$

$\implies$ : Existiere eine linksseitige Umkehrabbildung
Sei $g:N\to M$ eine linksseitige Umkehrabbildung von $f$, d.h. $g\circ f=\text{id}_{M}$ d.h. $g(f(x))=x\;\forall _{x\in M}$
Seien $x_{1},x_{2}\in M$ mit $f(x_{1})=f(x_{2})$ Dann gilt $x_{1}=\text{id}_{M}(x_{1})=(g\circ f)(x_{1})=g(f(x_{1}))=g(f(x_{2}))=(g\circ f)(x_{2})=\text{id}_{M}(x_{2})=x_{2}$
also ist $f$ injektiv.

$\impliedby$ : Sei $f$ injektiv
Definiere $$g:N\to M\;,\;y\to \begin{cases}
 x &,\text{wenn }y\in \text{Bild}(f),f(x)=y \\
m &,\text{wenn } y \not\in\text{Bild}(f)
\end{cases}$$
für ein beliebiges $m\in M$. Dann ist $g$ eine linksseitige Umkehrabbildung.

> Man müsste eig. auch $g$ auf das Bild von $f$ einschränken können, um sich die Fallunterscheidung zu sparen. Z.b. so:
> 
>$g:f(N)\to M\;,\;y\mapsto x\text{ mit }y=f(x)$
>Weil $f$ injektiv ist, gibt es für jedes $y$ höchstens ein $x$.
>Da der Definitionsbereich von $g$ auf das Bild von $f$ eingeschränkt ist, existiert dann genau ein $x$.

---
# Komposition injektiver, surjektiver und bijektiver Abbildungen

>[!def] Eigenschaften von Kompositionen
> - Die Komposition surjektiver Abbildungen ist surjektiv
> - Die Komposition injektiver Abbildungen ist injektiv
> - Die Komposition bijektiver Abbildungen ist bijektiv
> 

## Umkehrabbildung der Komposition zweier Bijektionen

>[!def] Umkehrabbildung bei Komposition von Bijektionen
> Sind $g\;,\;f$ [[Abbildungen#Injektiv, Surjektiv, Bijektiv|bijektive]] Abbildungen, dann gilt für die Umkehrabbildung ihrer Komposition:$$(g \circ f)^{-1} =f^{-1}\circ g^{-1}$$
> 
> Beachte die vertausche Reihenfolge:
> > (Socken Anziehen -> Schuhe Anziehen)$^{-1}$ 
> > = Schuhe ausziehen -> Socken ausziehen


---

# Mehrfache Komposition mit sich selbst
### Allgemeiner Fall
Wir definieren als Kurzschreibweise: $n\in \mathbb{N}$
$$
f^{n}:= \underbrace{ f\circ \dots \circ f }_{ n\text{-mal} } \;,\;f^{0}=\text{id}_{M}
$$
Es gelten dabei die bekannten Rechenregeln wie bei Potenzen: $a,b\in \mathbb{N}$
$f^{a+b}=f^{a}\circ f^{b}$ 
$f^{a\cdot b}=(f^{a})^{b}$ 

### Für Bijektionen
Ist $f$ [[Abbildungen#Injektiv, Surjektiv, Bijektiv|bijektiv]], definieren wir ebenfalls: $n\in \mathbb{N}$
$f^{-n}=(f^{-1})^{n}$

Für Bijektionen gelten die beiden obigen Potenzgesetze auch für $a,b\in \mathbb{Z}$.
