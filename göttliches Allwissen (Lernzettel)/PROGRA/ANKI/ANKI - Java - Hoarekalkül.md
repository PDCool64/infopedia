TARGET DECK: PROGRA

Zuweisungsregel  #flashcard
$$
\frac{}{{\color{red}{<\varphi[x/t ]>}}\;\text{ x=t; }{\color{red}{<\varphi>}}}
$$
<!--ID: 1768586729996-->




Konsequenzregel 1
(stärkere Vorbedingung)  #flashcard
$$
\frac{
{\color{red}{<\varphi>}}
\text{ P }
{\color{red}{<\psi>}}\quad{\color{red}{\alpha}}\implies{\color{red}{\varphi}}
}{
{\color{red}{<\alpha>}}\;\text{ P }{\color{red}{<\psi>}}
}
$$
<!--ID: 1768586730001-->




Konsequenzregel 2
(schwächere Nachbedingung)  #flashcard
$$
\frac{
{\color{red}{<\varphi>}}
\text{ P }
{\color{red}{<\psi>}}\quad{\color{red}{\psi}}\implies{\color{red}{\beta}}
}{
{\color{red}{<\varphi>}}\;\text{ P }{\color{red}{<\beta>}}
}
$$
<!--ID: 1768586730004-->




Sequenzregel #flashcard
$$
\frac{
{\color{red}{<\varphi>}}
\text{ P }
{\color{red}{<\psi>}}\quad
{\color{red}{<\psi>}}
\text{ Q }
{\color{red}{<\beta>}}}
{
{\color{red}{<\varphi>}}\;\text{ P Q }{\color{red}{<\beta>}}
}
$$
<!--ID: 1768586730008-->




Bedingungsregel 1
(``if``-Anweisung) #flashcard
$$
\frac{
{\color{red}{<\varphi \land \text{B}>}}
\text{ P }
{\color{red}{<\psi>}}\quad
{\color{red}{\psi \land \neg B}}\implies{\color{red}{\psi}}}
{
{\color{red}{<\varphi>}}\;\text{ if (B) \{P\} }{\color{red}{<\psi>}}
}
$$
<!--ID: 1768586730012-->




Bedingungsregel 2
(``if-else``-Anweisung) #flashcard
$$
\frac{
{\color{red}{<\varphi \land \text{B}>}}
\text{ P }
{\color{red}{<\psi>}}\quad
{\color{red}{<\varphi \land \neg\text{B}>}}
\text{ Q }
{\color{red}{<\psi>}}}
{
{\color{red}{<\varphi>}}\;\text{ if (B) \{P\} else \{Q\} }{\color{red}{<\psi>}}
}
$$
<!--ID: 1768586730016-->




Schleifenregel  #flashcard
$$ \frac{
{\color{red}{<\varphi \land \text{B}>}}
\text{ P }
{\color{red}{<\varphi>}}}
{
{\color{red}{<\varphi>}}\;\text{ while (B) \{P\} }{\color{red}{<\varphi \land \neg \text{B}>}}
}
$$
<!--ID: 1768586730020-->





3 Anforderungen für eine nützliche Schleifeninvariante  #flashcard
1. Muss tatsächlich invariant sein
2. muss aus der Vorbedingung folgen
3. muss mit negierter Schleifenbedingung die Nachbedingung implizieren
<!--ID: 1768586730024-->




An welchen 4 Stellen fügt man die Schleifeninvariante ein  #flashcard
1. Vor der Schleife
2. Am Anfang des Schleifenrumpfs zusammen mit Schleifenbedingung
3. Am Ende des Schleifenrumps
4. Nach der Schleife zusammen mit negierter Schleifenbedingung
<!--ID: 1768586730027-->




Terminierungsregel  #flashcard
Für jede Schleife ``while (B) {P}`` finde einen ``int``-Ausdruck $V$ (**Variante der Schleife**), so dass:
- $B\implies V\ge 0$
- ${\color{red}{<V=m \land B>}}\text{ P }{\color{red}{<V<m>}}$
<!--ID: 1768586730031-->



