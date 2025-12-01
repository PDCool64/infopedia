---
tags:
  - DS
status: rot
---
---

>[!def] Algebraische Strukturen
> Algebraische Strukturen sind Mengen mit "Struktur" in Form von Verknüpfungen.
> >[!def] Verknüpfung
> > Eine **Verknüpfung** auf einer [[Mengen|Menge]] ist eine [[Abbildungen|Abbildung]] der Form
> > $$M\times M \to M$$
> 
> 
> >[!def] Algebraische Struktur
> > Eine **Algebraische Struktur** ist eine [[Mengen|Menge]] mit einer oder mehreren Verknüpfungen.
> 

^2eb8c1

---
# Monoid
>[!def] Monoid
> Es sei $M$ eine [[Mengen|Menge]] mit der [[#^2eb8c1|Verknüpfung]] 
> $$\bullet:M\times M\to M \;,\;(x,y)\mapsto x \bullet y$$
> Wir nennen $M$ ein **Monoid**, wenn folgende Axiome gelten:
> - Die Verknüpfung assoziativ ist:
>   $(x \bullet y) \bullet z = x \bullet(y \bullet z)$ 
>   
> - Ein neutrales Element $e$ existiert:
>   Es existiert $e\in M$ mit $e \bullet x =e = x \bullet e$ für alle $x\in M$.
> 
> Das Monoid nennen wir *abelsch* oder *kommutativ*, wenn zusätzlich gilt:
>  $x\bullet y = y \bullet x$ für alle $x,y\in M$

## Bemerkungen
- Das neutrale Element $e$ ist eindeutig

## Schreibweisen:
Wenn man keine eigene Notation für die Verknüpfung hat, schreibt man diese oft als $+$ oder $\cdot$ und verwendet bekannte Kurzschreibweisen:
#### Wie $+$ geschrieben:
- $0$ für $e$
- $na$ für $\underbrace{ a+a+\dots+a }_{ n-\text{mal} }$ 
#### Wie $\cdot$ geschrieben:
- $1$ für $e$
- $a^{n}$ für $\underbrace{ a\cdot a\cdot\;\cdots\;\cdot a }_{ n-\text{mal} }$

---
