>[!def] Gleichung
> Um das Problem des Lösens einer Gleichung eindeutig zu formulieren, benötigen wir zwei Dinge:
> 1. Die [[Mengen|Menge]] $M$, genannt **Grundgesamtheit**. Alle Lösungen sollen Elemente dieser Menge $M$ sein. ("In welcher Menge suche ich überhaupt Lösungen", insbesondere wenn diese eingeschränkt werden soll/muss)
>    
> 2. Eine *Gleichung* $f(x)=0$, wobei $f:M\to \mathbb{K}$ eine [[Abbildungen|Abbildung]] in einen [[Körper]] $\mathbb{K}$ ist.
> 
> Die Lösungsmenge $\mathbb{L}$ dieser Gleichung sind nun diejenigen Elemente $x$ der Grundgesamtheit $M$, welche die Gleichung erfüllen, d.h.$$
> \mathbb{L}:=\{ x\in M \mid f(x)=0 \}
> $$

^731ce7

## Schreibweisen
- Ist $\mathbb{L}=\emptyset$ so ist die Gleichung *nicht* lösbar.
- Besteht $\mathbb{L}$ nur aus einem Element, so ist die Lösung der Gleichung *eindeutig*.

>[!def] Ungleichung
>Für Ungleichungen gehen wir analog vor:
> 1. Die [[Mengen|Menge]] $M$, genannt **Grundgesamtheit**. Alle Lösungen sollen Elemente dieser Menge $M$ sein. ("In welcher Menge suche ich überhaupt Lösungen", insbesondere wenn diese eingeschränkt werden soll/muss)
> 
> 2. Eine [[Abbildungen|Abbildung]] $f:M\to \mathbb{K}$, wobei $\mathbb{K}$ jetzt aber ein **[[Körper#Anordnung auf einem Körper|angeordneter]]** Körper sein muss.
> 
> 3. Es gibt nun zwei qualitativ verschiedene Ungleichungen, nämlich
>    - $f(x)>0$ und
> 	 - $f(x)\geq 0$
>
>  Die Lösungsmenge $\mathbb{L}$ der Ungleichung sind nun diejenigen Elemente der Grundgesamtheit $M$, welche die Gleichung erfüllen d.h. :
>  - $\mathbb{L}:=\{ x\in M \mid f(x)>0\}$ bzw.
>  - $\mathbb{L}:=\{ x\in M \mid f(x)\geq0\}$

^4dfb68

## Bemerkungen
- Die Lösungsmenge $\mathbb{L}$ hängt von $f$, aber auch von der Grundgesamtheit $M$ ab.
  Für $f(x)=3x+2$ folgt zum Beispiel:$$
\mathbb{L}:=\{ x\in M\mid 3x+2=0 \}= \begin{cases} \emptyset &,M=\mathbb{Z} \\
\left\{  -\frac{2}{2}  \right\} &,M=\mathbb{Q} \end{cases}
$$
- Da die [[Abbildungen]] in einen [[Körper]] hinein abbilden, können wir *scheinbar* allgemeinere/komplexere Gleichungen der Form $g(x)=k(x)$ immer auf die Form mit nur einer Abbildung $f(x)$ reduzieren:
  
  Wegen der Existenz des [[Körper#^315cce|inversen Elements der Addition]] und $g(x)\in \mathbb{K}$ gilt:$$
\begin{align} 
k(x)&=g(x) &|+(-g(x))\\
\underbrace{ k(x)+(-g(x)) }_{ f(x) }&=0 \\

\end{align}
$$ Dabei wird die Lösungsmenge nicht verändert.