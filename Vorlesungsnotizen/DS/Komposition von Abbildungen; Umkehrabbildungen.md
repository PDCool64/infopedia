---
tags:
  - DS
status: rot
---
---

>[!def] Komposition zweier Abbildungen
> Ist $f:A\to B$ eine Abbildung und $g:B\,'\to C$ eine weitere Abbildung mit der Eigenschaft $f(A)\subseteq B\,'$ , so nennt man $$
> f \circ g:A\to C,\;x\mapsto(g\circ f)(x):=g(f(x))
> $$ die **Verkettung** oder **Komposition** oder **Hintereinanderausführung** von $f$ und $g$.

> In DS kommen fast ausschließlich Abbildungen mit $B=B\,'$ vor.

# Assoziativität der Komposition

>[!def] Assoziativität der Komposition
> Für $f:M\to N\;,\;g:N\to L\;,\;h:L\to K$ gilt:
> $$
> h\circ(g\circ f) = (h\circ g) \circ f
> $$



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
> - $g$ ist **linksseitige Umkehrabbildung von $f$**, falls gilt
>   $$
> g \circ f = \text{id}_{M}
> $$
> - $g$ ist **rechtsseitige Umkehrabbildung von $f$**, falls gilt $$
> f\circ g = \text{id}_{M}
> $$
> - $g$ ist **Umkehrabbildung** von $f$ , man sagt auch **invers**, falls gilt $$
> g\circ f = \text{id}_{M}\quad\text{und} \quad f\circ g=\text{id}_{N}
> $$ also wenn $g$ und $f$ rechts- und linksseitige Umkehrabbildungen von einander sind.


## Existenz von Umkehrabbildungen und [[Abbildungen#Injektiv, Surjektiv, Bijektiv|Surjektivität, Injektivität, Bijektivität]]

Es gilt:
- $f$ hat *links*seitige Umkehrabbildung $\iff$ $f$ ist injektiv.
  
  Wäre $f$ nicht injektiv, dann könnte eine *danach* ausgeführte (also links stehende) die Elemente nicht mehr aus einander halten und korrekt umkehren.
> merke: in l*i*nksinvertierbar ist ein $i$ genauso wie in *i*njektiv.

- $f$