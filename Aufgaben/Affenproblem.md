## Aufgabe 1
Auf $100$ Affen werden $1600$ Kokosnüsse verteilt,
wobei einige Affen auch leer ausgehen können.
Beweisen Sie, dass es — ganz gleich wie die Verteilung erfolgt — stets mindestens vier Affen mit derselben Anzahl von Kokosnüssen gibt.
Dieses Blatt zählt noch nicht für die Zulassung.
Es kann (in Gruppen) abgegeben werden, um den Vorgang auszuprobieren, es wird aber noch nicht korrigiert.

## Aussage
Es gibt mindestens 4 Affen, die die gleiche Anzahl an Kokusnüssen haben. 
## Gegenaussage
Es gibt maximal 3 Affen, die die gleiche Anzahl an Kokusnüssen haben. 

## Gedankengang
Beginnend bei 0 haben immer 3 Affen die selbe Anzahl an Kokusnüssen. 
Das ist eine optimale Verteilung, da kein Vierter Affe die gleiche Anzahl von Kokusnüssen haben darf, auf der anderen Seite aber eine Anzahl von Kokusnüssen, die von weniger als 3 Affen belegt wird, dafür sorgt, dass ein Affe mehr Kokusnüsse hat, als nötig wäre. 
Dementsprechend ist die Anzahl an benötigten Kokusnüssen: 
$$
anzahl_{kokusnüsse} = 33 + \sum_{i=0}^{32}{3i} = 1617
$$
Da wir $100$ Affen haben, können wir sie in 33 3er Gruppen unterteilen und haben $1$ Affen übrig.
Die Affen bekommen von 0 bis 32 Kokusnüsse, je nach Gruppe, der letzte Affe kriegt 33 Nüsse. 

$$
Anzahl_{Kokusnüsse} = 33 + \sum_{i = 0}^{n}3i = 1617
$$