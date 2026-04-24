---
tags:
  - FOSAP
status: rot
---
---

> [!def] Deterministischer Endlicher Automat (DFA)
> Ein **deterministischer, endlicher Automat** (DFA) ist ein 5-Tupel
> $M=(Q,\Sigma,\delta,q_0,F)$ mit
> - $\Sigma$, dem endlichen nichtleeren Eingabealphabet
> - $Q$, der endlichen Menge der Zustände
> - $\delta: Q\times\Sigma \to Q$, der Zustandsübergangsfunktion
> - $q_0$, dem Anfangszustand sowie
> - $F\subseteq Q$, der Menge der Endzustände (F auf Englisch für Final-states)

## Vom DFA zur Sprache

#### Bestimme, in welchem Zustand ein gesamtes Wort endet
Erweitere die Zustandsübergangsfunktion $\delta$ -welche einzelne *Symbole* verwendet- auf die neue Funktion $\hat{\delta}$ -welche ganze *Wörter* verwendet:
- Setze den Rekursionsanker: $\hat{\delta}(q,\varepsilon):=q$ 
  (D.h. wenn das Wortende erreicht ist: stehen bleiben)
- Definiere als rekursive Anwendung der Zustandsübergangsfunktion $\delta$:$$
\hat{\delta}(q,wa):=\delta\left(\hat{\delta}(q,w)\;,\;a\right)
$$
#### Bilde die Menge aller Wörter, die in einem akzeptierenden Endzustand landen
$$
L(M):=\{ w\in \Sigma^{*}\mid \hat{\delta}(w)\in F \}
$$

