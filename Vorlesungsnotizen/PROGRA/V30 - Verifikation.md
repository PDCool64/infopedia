---
date: 2025-10-23
tags:
  - PROGRA
status: rot
Vorlesungsfolien:
Skriptfolien:
---
---


> Es geht hier nicht mehr um Syntax (das kann der Compiler für uns überprüfen), sondern um *semantische* Korrektheit.

- Spezifikation, *was* ein Programm tun soll
	- natürliche Sprache
	- grafische Sprache (UML,...)
	- logische Sprachen (Z,VDM,...)
- Testen: Überprüfen für endlich viele Eingaben
	- aber: keine 100% Sicherheit (man kann nicht alles ausprobieren)
- Verifikation: *Mathematischer Beweis der Korrektheit*
	- Terminierung: Hält das Programm immer an?
	- Partielle Korrektheit: Falls Programm anhälgt, erfüllt es die Spezifikation?
	- Totale Korretheit: Sowohl Terminierung als auch partielle Korrektheit.


> Warum: 100% Sicherheit ist bei Sicherheitskritischen Anwendungen wichtig. (Autopilot von Flugzeug, Steuersoftware in Kraftwerk, Arbeit mit sensiblen Daten)

---
# Bsp: Fakultätsprogramm

Spezifikation: 
	Programm berechnet in `res` die Fakultät von `n`

Terminierung:
	Programm hält definitiv an, weil `i` in jedem Schleifendurchlauf kleiner wird.
	



# Hoare-Kalkül
> Benannt nach Tony Hoare


$$
<\varphi> P <\psi>
$$
Wenn vor der Ausführung von P die **Vorbedingung** $\varphi$ ...

Mit den Regeln gibt das Hoare-Kalkül einen Rahmen/Anleitung zur Verifikation


Da jeder Schritt eine der 7 Regeln sein muss, kann man eine gegeben Verifikation sehr leicht automatisierbar


Es gibt für jedes Java-Konstrukt eine Regel - weil wir uns nur für eine kleine Teilmenge von java anschauen, gibt es nur 7 (Konstrukte sind, while, for, if usw.)

Schreibweise der Regeln:
$$
\frac{\text{Wenn das hier wahr ist}}{\text{Dann ist auch das hier war}}
$$

# Zuweisungsregel
![[Pasted image 20251023161735.png]]
- Oberhalb des Strichs steht *nichts* d.h. die Aussage unter dem Strich ist *immer* wahr.
- Damit nach der Ausführung von `x=t;` die Nachbedingung $\psi$ gilt, muss vorher
  $\phi[x/ t]$ gegolten haben

   > Schreibweise : $\phi$`[x/t]` heißt, dass wieder $\varphi$ gelten soll, nur dass in dr "neuen Version"alle Vorkommen von $x$ durch $t$ ersetzt werden müssen.
   > 
   > d.h. $<5\geq y>\;x=5$...
   
Man schreibt in der Praxis diese Assertions/Zusicherung mit <...>" direkt in dem Programmcode rein.
Man ergänzt also den Programmcode mit diesen Zusicherungen/Assertions, die wahre Aussagen über die Programmvariablen an dieser Stelle enthalten. 

(Java kann diese Assertions auch direkt testen!) -  Man kann Zusicherungen direkt mit `assert` ins Java-Programm schreiben. Bei Ausführung werden diese standardmäßig ignoriert, setzt man aber die Flag `-ea` für `enable assertions`, dann werden die Assertions mit überprüft.
   
> Oft geht man bei den Zusicherungen und dem Aufstellen der Vorbedingungen von hinten nach vorne durch


# Konsequenzregel 1 (Stärkere Vorbedingung)
![[Pasted image 20251023161751.png]]
Das $\alpha\implies \varphi$ kann man direkt als Implikation lesen - $\alpha$ ist stärker, weil es hinreichend für $\varphi$ ist.

Man kann also die Vorbedingung verschärfen.
(s.h. PXL Foto, das Beispiel auf den Folien mit `true` verschärft nicht wirklich, sondern ersetzt nur. Schöner war das mit $x\le 3\implies x \le 5$

- Schreibweise: Wenn 2 Zuweisungen direkt untereinander stehen, dann *muss* die untere Zusicherung direkt aus der oberen folgen.
- Wenn zwischen zwei Zusicherungen eine Anweisung steht, dann muss es einer Anwendung einer Regel des H-Kalküls entsprechen.

# Konsequenzregel 2 (Schwächer Nachbedingung)
![[Pasted image 20251023161800.png]]
Man kann die Nachbedingung abschwächen. Wieder einfach $\psi\implies\beta$ als Implikation lesen.

Die Schreibweise " Wenn 2 Zuweisungen direkt untereinander stehen, dann *muss* die untere Zusicherung direkt aus der oberen folgen." funktioniert hier genauso.

> Anstatt so einfachen Formel wie $x\ge 2$ kann man da auch beliebige Boolesche ausdrücke reinpacken.

# Sequenzregel
![[Pasted image 20251023161812.png]]
Erlaubt es, ein Programm in zwei Hälften zu zerlegen, und dann beide Teilbeweise wieder zusammenzuführen,
*Wenn die Nachbedingung des ersten Programms die Vorbedingung des zweiten ist*
![[V30 - Verifikation 2025-10-23 15.15.23.excalidraw]]

# Bedingungsregel 1
![[Pasted image 20251023161822.png]]
Für If-Anweisungen ohne else
![[V30 - Verifikation 2025-10-23 15.22.45.excalidraw]]

> Wirklich immer alles immer komplett schematisch machen und nacheinander die regeln anwenden. es ist eigentlich gar nicht kompliziert

# Bedingungsregel 2
![[Pasted image 20251023161839.png]]
Für If-Anweisung mit else
![[V30 - Verifikation 2025-10-23 15.31.38.excalidraw]]
# Schleifenregel
![[Pasted image 20251023161856.png]]
Das ist die einzige Regel, für die man *Kreativität* braucht -  die anderen Regeln kriegt auch der Rechner sehr stumpf hin.

Idee: 
	Finde eine **Schleifeninvariante** $\varphi$ mir folgenden Eigenschaften: Wenn sie vor dem Schleifenrumpf galt, dann gilt sie auch nach der Ausführung des Schleifenrumpfs. (Invariante = Unverändert; Die Aussage bleibt gültig)
	$\;$
	"Wenn $\varphi$ vor dem Schleifenrumpf gilt und der Schleifenrumpf wird ausgeführt (weil die Bedingung $B$ gilt), dann gilt $\varphi$ nach dem Schleifenrumpf immer noch."

> `true` währe eine Schleifeninvariante, aber eine sehr nutzlose

Man muss eine geeignete Schleifeninvariante finden, die also drei Eigenschaften erfüllt.
- $\varphi$ Muss tatsächlich eine Schleifeninvariante sein.
- $\varphi$ muss aus der Vorbedingung folgen (und dafür meist eher schwach sein)
- Die gewünschte Nachbedingung muss aus der Schleifeninvariante $\varphi$ und der negierten Schleifenbedingung $\neg B$ folgen. (`true` ist beispielsweise viel zu schwach, um daraus viel folgern zu können)

> Diese schwach genug und schwach genug erzeugt ein schwieriges Spannungsfeld


> Tipp: Fange von unten an, und fange mit der Nachbedingung als mögliche Schleifeninvariante an. Meist muss man diese aber so anpassen, das daraus eine Schleifeninvariante wird. 


Am besten führt man zum Testen die Schleife mal mit typischen Variablen aus und probiert, ob das ganze eine Schleifeninvariante sein kann
  


| i   | res                | n   |
| --- | ------------------ | --- |
| 4   | 1                  | 4   |
| 3   | 4                  | 4   |
| 2   | 4*3                | 4   |
| 1   | $4\cdot 3 \cdot 2$ | 4   |

wir versuchen es mal mit der Nachbedingung $res=n!$ als Schleifeninvariante.
Das stimmt zwar in der untersten Zeile, davor aber nicht.

was (wie am Aufbau der Fakultät aber ersichtlich ist): Wir wandeln unsere Bedingung ab zu:
$i!\cdot res= n!$
An unserer Tabelle sieht man, dass es am Fall 4 funktioniert - man muss es aber noch allgemein beweisen.


![[V30 - Verifikation 2025-10-23 15.51.53.excalidraw|600]]

