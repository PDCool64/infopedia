---
tags:
status: rot
---
---
# Was ist Verifkation?
Es geht hier nicht mehr darum, dass eine Programm *syntaktisch* korrekt ist -das kann der Compiler für uns recht einfach machen. (s.h.[[Formale Sprachen und Grammatiken]])- sondern darum dass es *semantisch* d.h. inhaltlich und von der Funktion korrekt ist.

## Begriffe
- **Spezifikation** : Was soll ein Programm tun
	- in natürlicher Sprache
	- in graphischen Sprachen (UML, etc.)
	- in logischen Sprachen (Z, VDZ, etc.)
- **Testen**: Überprüfen des Verhaltens des Programms für endlich viele Eingaben
	- aber: keine 100%-tige Sicherheit: Man kann nicht alle Fälle durchprobieren
	
- **Verifikation**: *Mathematisch rigoroser Beweis der Korrektheit*
	- **Terminierung**: Hält das Programm immer an?
	- **Partielle Korrektheit**: Falls das Programm anhält, erfüllt es die Spezifikation
	- **Totale Korrektheit:** Sowohl Terminierung als auch partielle Korrektheit.
	
> Warum der Aufwand:
> - Sicherheitskritische Anwendungen wie Autopilot eines Flugzeugs, Steuersoftware im Atomkraftwerk, Arbeit mit sensiblen Daten.
>   Schön zu lesen: [Liste an Softwarebugs (mit größeren Konsequenzen)](614GBN@rwth-aachen.de)


