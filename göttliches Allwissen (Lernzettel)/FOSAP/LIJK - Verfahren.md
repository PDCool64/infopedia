---
tags:
status: rot
---
---

>[!def] LIJK - Verfahren
>Bestimmt einen  [[Reguläre Ausdrücke und Sprachen#Reguläre Ausdrücke|regulären Ausdruck]] aus einem [[Deterministische Endliche Automaten|DFA]].
>
>Gegeben sei der Automat $M=\{ Q,\Sigma,\delta,q_{1},F \}$ mit durchnummerierten Zuständen $Q=\{ q_{1},\dots,q_{n} \}$
>
>Sei $L_{ij}^{k}$ die Sprache, mit der man von Zustand $q_{i}$ zu Zustand $q_{j}$ kommt, dabei aber nur die Zustände $\{ q_{1},\dots,q_{k} \}$ verwendet.
>
>Definiere den *Basisfall*:
>$$ L_{ij}^{0} :=\begin{cases} \{ a\in \Sigma \mid \delta(q_{i},a)=q_{j} \} &,\text{falls }i\neq j \\ \{ a\in\Sigma \mid \delta(q_{i},a)=q_{i} \} \cup \{  \varepsilon\} &,\text{falls } i=j
\end{cases}$$
Reduziere dann die gesuchte Sprache *rekursiv*:$$ L_{ij}^k := L_{ij}^{k-1} \cup L_{ik}^{k-1}(L_{kk}^{k-1})^{*}L_{kj}^{k-1}\quad\text{für }k>0$$
>
>




