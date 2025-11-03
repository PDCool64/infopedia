---
tags:
  - DS
status: rot
---
---
Für die meisten Anwendungen funktioniert hier alles genau wie sonst, nur beschreibt man hier den "Zuordnung"s-Teil der Abbildung durch **geordnete Paare**. Die Rigorose Definition haben wir nicht, und man will so weit möglich den in Afi -und auch im DS Skript-bestehenden Haken umschiffen, dass man "Abbildung" nur durch ein Synonym, nämlich "Vorschrift" ersetzt hat. 
Um dies hier ein wenig zu verschönern, findet sich die "Verknüpfung"/"Zuordnung"/"Vorschrift" hier in der Menge der geordneten Paare wieder.

---
Seien $M,N$ [[Mengen]]. Eine **Abbildung** $f$ von $M$ nach $N$ ist eine "Vorschrift" (z.B. eine Formel), die jedem $x\in M$ *genau ein* Element $f(x)\in N$ zuordnet, geschrieben$$f:M\to N\;,\;x\mapsto f(x)$$
>[!def] Abbildung
> Eine Abbildung besteht formal aus drei Teilen:
> - $M$ Menge (Definitionsbereich)
> - $N$ Menge (Zielbereich)
> - $f\subseteq M\times N$,
>   so, dass gilt:
>   für jedes $x\in M$ existiert *genau ein* $y\in N$ mit $(x,y)\in f$.

Das passt auch recht **schön** an die Schreibweise, eine Abbildung durch explizites Aufzählen der "Paare":
$$
\{ 1,2,3 \}\to \{ 4,5,6 \}\;,\;1\mapsto 4\;,\;2\mapsto 5\;,\; 3\mapsto 4
$$
Außerdem kann man mit dieser Konvention die Gleichheit zweier Abbildungen schön schreiben, weil die "Abbildungsvorschrift" hier einfach eine stinknormale Menge aus Tupeln ist - Mann kann sie wie jede andere Mengen auch vergleichen: Sei $f:M\to N$ mit den Tupeln $f\subseteq M\times N$, und sei $g:M'\to N'$ mit den Tupeln $g\subseteq M\times N$, dann sind beide Abbildungen genau dann gleich, wenn $M=M'\land N=N'\land f=g$
