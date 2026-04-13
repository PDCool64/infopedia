---
tags:
  - DSAL
status: rot
---
---

# Probleme vs. Probleminstanzen

>[!def] Probleme 
>Probleme (auch "**Problemklassen**" genannt) sind gegeben durch eine Eingabe und eine Ausgabe:
>
>Eingabe:
>- Eine Liste von typisierten *Eingabevariablen* $\vec{T}\,\vec{x}$
>  (auch genannt Parameter mit *Typ* $\vec{T}$ und *Name* $\vec{x}$)
>- Eine *Vorbedingung* $\varphi(\vec{x})$, die für *jede* Instanz des Problems gilt.
>
>Ausgabe:
>- Eine Liste von typisierten *Ausgabevariablen* $\vec{T}\vec{y}$ 
>- Eine Nachbedingung $\psi(\vec{x},\vec{y})$, die die gesuchten Lösungen des Problems in Abhängigkeit von den Eingabe- und Ausgabevariablen eindeutig beschreibt.
> 
>---
> 
> -  Eine *Instanz* eines Problems ist spezifiziert durch die Belegung der Eingabevariablen, welche die Vorbedingung erfüllt.
> - Eine *Lösung* einer Probleminstanz ist spezifiziert durch eine Belegung der Ausgabevariablen, welche die Nachbedingung erfüllt.

### Beispiele:
Unterscheidung:
- Probleminstanz: Wie fährt man am schnellsten von Aachen nach Kiel?
  Problemklasse: Wie fährt man am schnellsten von Stadt $x$ nach Stadt $y$?

