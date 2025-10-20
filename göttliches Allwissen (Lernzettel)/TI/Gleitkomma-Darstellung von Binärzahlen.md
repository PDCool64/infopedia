---
tags:
  - TI
  - PROGRA
status: rot
---
---

>[!def] Gleitkomma-Darstellung
>Die **Gleitkomma** Darstellung ist eine *approximative* Darstellung [[Zahlenräume#Reelle Zahlen $ mathbb{R}$|reeller]] bzw. [[Zahlenräume#Rationale Zahlen $ mathbb{Q}$|rationaler]] Zahlen.
>
>Jede Zahl $z$ wird in der Form $$z=\pm m\cdot b^{\pm e}$$
>dargestellt, wobei wir $m$ **Mantisse**. $e$ **Exponenten** und $b$ **Basis nennen**.
>---
>
>Da rechnerintern im [[Binärsystem]] gearbeitet wird, ist die Basis $b=2$.
>
>---
>*Nicht alle Zahlen in Bereich können exakt dargestellt werden*.


Die Gleitkomma Darstellung versucht, bei gleicher Anzahl an Speicherbits einen deutlich größeren Zahlenbereich als die [[Festkomma-Darstellung von Binärzahlen]] zu erreichen.

Die Funktionsweise der heute angewendeten Gleitkomma-Formate wurde in der Norm [*IEEE 754*](https://de.wikipedia.org/wiki/IEEE_754) vom *Institute of Electrical and Electronics Engineers* festgelegt.

Je nach gewünschter Präzision und Zahlenbereich sowie Speicherlimitierungen gibt es verschiedene Versionen/Größen von Gleitkommaformaten. Häufig sind:
- 16-Bit
- 32-Bit (aka. ``single``)
- 64-Bit (aka. ``double``)
- 128-Bit

> Es gibt online einen praktischen [IEEE-754 Konverter](https://www.h-schmidt.net/FloatConverter/IEEE754de.html).

## Darstellung im Speicher
> Die im Speicher stehenden Werte werden mit Dach  $\hat{}$  geschrieben: $\hat{s},\hat{e},\hat{m}$
> Die zur Berechnung von $z=\pm m\cdot b^{\pm e}$ verwendeten Werte werden ohne Dach geschrieben.

Die Daten werden in drei Feldern gespeichert: 
- Vorzeichen $\hat{s}$ : $1$-Bit am Anfang
	  ist $\hat{s}=0$ wird die Zahl als positiv interpretiert.
	  ist $\hat{s}=1$ wird die Zahl als negativ interpretiert.
	  
- Exponent $\hat{e}$ : $k$-Bit in der Mitte
	  Der Exponent $e$ kann positiv oder negativ sein. 
	  *Gespeichert* wird aber immer nur ein *positiver* Wert $\hat{e}$, was dadurch erreicht wird, dass $e$ um einen sogenannten *bias*-Wert ins Positive verschoben wird. Man spart sich damit die Kodierung von negativen Exponenten, die sonst z.B. durch das [[Negative Binärzahlen durch Komplement - Ganze Zahlen im Binärsystem#Negative Zahlen als Zweier-Komplement|Zweier-Komplement]] umgesetzt werden müsste.
	  
	 **Wahl des *bias*-Werts:**
	 Die gespeicherten $k$-Bit-Muster $\hat{e}=(000\dots 000)$ und $\hat{e}=(111\dots 111)$ sind für spezielle Interpretationen reserviert (s.h. [[#Fallunterscheidungen]]).
	 Es verbleiben also die restlichen $k$-Bit-Muster von $(\dots0001)_{2}=1$ bis $(0111\dots)_{2}=2^{k}-1$ zur Speicherung des Exponenten. Da an beiden Enden sozusagen jeweils ein Bitmuster fehlt, ist die Anzahl dieser verwendbaren Muster $2^{k}-2$. Diese sollen nun zur Hälfte genutzt werden um negative Exponenten zu speichern, während die andere Hälfte positive Exponenten speichert. 
	 Dazu verschiebt man die Exponenten um die Hälfte der Breite: $\frac{2^{k}-2}{2}=2^{k-1}-1$
	 D.h. der *bias*-Wert wird gewählt als $2^{k-1}-1$.
	 
	 >Für eine anders formulierte Erklärung ist der (englische) [Wikipedia Artikel "Exponent bias"](https://en.wikipedia.org/wiki/Exponent_bias) ziemlich lesenswert.
	 
	 Es gilt also:
	 $e=\hat{e}-bias$
	 $\hat{e}=e+bias$
	 
	 **Eselsbrücke zur Verschiebungsrichtung**: 
	 Das $\hat{e}$ mit Dach ist *visuell größer* als das $e$ ohne Dach.
	 
	 $\hat{e}$ wird dann als ganz normale, positive $k$-Bit Zahl ohne Komastellen oder Sonstiges in den Speicher geschrieben.
 	   ^18e0c0
- Mantisse $\hat{m}$ : $n$-Bit am Ende
	  Je nachdem, ob es sich um die [[#Normalisierte Darstellung]] oder die [[#Denormalisierte Darstellung]] handelt, wird die Mantisse unterschiedlich behandelt.

Bei $32$-Bit haben wir $k=8$ und $n=23$
Bei $64$-Bit haben wir $k=11$ und $n=52$

Aufteilung bei $32$-Bit:
>[!wip] Abbildung
> Die Grafik könnte man mal selbst nachbauen - dann wäre sie light/darkmode kompatibel

![[Pasted image 20251019170832.png]]
# Fallunterscheidungen:
Die meisten Zahlen werden in der [[#Normalisierte Darstellung|Normalisierten Darstellung]] gespeichert.
- Diese ermöglicht es, bei 32 Bit Zahlen mit Beträgen von $1.18\cdot 10^{-38}$ zu speichern
- $0$ selbst lässt sich so nicht speichern. sowie Zahlen sehr nah an $0$ lassen außerdem nicht sehr genau speichern.
Für die Zahlen nahe der $0$, sowie die $0$ selbst gibt es die [[#Denormalisierte Darstellung]]

Sonderfälle werden ebenfalls markiert:

![[Gleitkomma-Darstellung von Binärzahlen 2025-10-19 17.08.48.excalidraw|900]]
# Normalisierte Darstellung
Darstellung der meisten Zahlen. Bei $32$-Bit sind *Beträge* von $1.18\cdot 10^{-38}$ bis $3.40\cdot 10^{38}$ möglich.

## Dezimal -> Gleitkomma
am Beispiel $-12.6875$
1. Vorzeichen ablesen: Die Zahl ist negativ also gilt $s=\hat{s}=1$
   
2. Mantisse bestimmen: Rechne $12.6875$ wie eine [[Festkomma-Darstellung von Binärzahlen|Festkommazahl]] ins Binärsystem um:
	   i) Teil vor dem Komma umrechnen: $(12)_{2}=(1100)_{2}$
	   ii) Teil nach dem Komma umrechnen:![[Festkomma-Darstellung von Binärzahlen 2025-10-19 14.04.25.excalidraw|300]]Die Mantisse hat also den Wert $(1100.1011)_{2}$ - sie wird aber *normalisiert* gespeichert d.h. vor dem Komma muss immer *genau* 1 stehen. Dazu verschiebt man das Komma so weit nach links oder rechts, bis dies der Fall ist. Verschiebungen (Bit-Shifts) kommen im Binärsystem der Multiplikation/Division mit $2$ gleich, wodurch automatisch der Exponent $e$entsteht: $(1100.1011)_{2}=(1.1001011)_{2}\cdot 2^{3}$
	   Die zu speichernde Mantisse ist also `10010110000000...`
	   
>[!wip]
>    Hier sollte noch besser erklärt werden wie/warum die Mantisse auf 1,XXX normalisiert wird. Z.B. weil man dann noch einen Bit mehr präzision kriegt weil man sich das Speichern der 1 spart. Auch die "Rückrichtung" der Erklärung à la :"Die bits in der Mantisse $\hat{m}$ werden nur als die Nachkommastellen gelesen. Davor wird immer eine 1,XXX gehängt." könnte eingearbeitet werden.

   
3. Den bei der Mantissen-Bestimmung entstandenen Exponenten $e$ mit dem [[#^18e0c0|bias]] zu $\hat{e}$ verrechnen: 
     $\hat{e}=e+(2^{k-1}-1)=3+127=130$
     
     Dadurch wird dieser zu einer immer positiven Zahl und kann somit einfach ins Binärsystem mit $k$-Bit umgewandelt werden:
     $(130)_{10}=(10000010)_{2}$
     
3. Alles zusammentun:![[Gleitkomma-Darstellung von Binärzahlen 2025-10-19 20.17.04.excalidraw]]
## Gleitkomma -> Dezimal
Gegeben sei die $32$-Bit Gleitkommazahl ``0 10000110 11100001100000000000000``
1. Vorzeichen ablesen: $\hat{s}=s=0\to$ positive Zahl
2. Nachkommastellen der Mantisse ablesen:
	    ``11100001100000000000000`` = $\frac{1}{2}+\frac{1}{4}+\frac{1}{8}+\frac{1}{256}+\frac{1}{512}= \frac{899}{1024}=0.880859375$
	    Die $1$ der normalisierten Darstellung wieder vor das Komma setzen:
	    $m=1.880859375$
3. gespeicherten Exponenten $\hat{e}$ ablesen und zu einer Dezimalzahl machen:
		``10000110`` = $128+4+2=134$ 
		Das *bias* wieder herausrechnen, um den tatsächlichen Exponenten $e$ zu erhalten:
		$e=\hat{e}-127$
		$e=134-127=7$
4. Die Dezimalzahl aus Vorzeichen, Mantisse und Exponenten berechnen:
	   $z= + 1.880859375\cdot 2^{7}= 240.75$
# Denormalisierte Darstellung
Darstellung der $0$ sowie genauere Darstellung von Zahlen sehr nah an der Null.
Es handelt sich um die Denormalisierte Darstellung, wenn der gespeicherte Exponent $\hat{e}$ nur aus Nullen besteht.

 >[!wip]
> 
> Insbesondere die Wahl von $1-bias$ anstatt $0-bias$ beim Exponenten, aber auch die Wahl von 0.XXX anstatt 1.XXX bei der Mantisse könnten noch genauer begründet werden.


## Gleitkomma->Dezimal:
Gegeben sei die $32$-Bit Gleitkommazahl ``0 00000000 10000000000000000000000``
1. Vorzeichen $\hat{s}=s=0\to$ positive Zahl
2. den *Festen* Exponenten berechnen:
	   Eigentlich würde man erwarten, wieder $e=\hat{e}-bias=0-bias$ zu rechnen - Man hat sich aber entschieden stattdessen als festen Exponenten der denormalisierten Darstellung stattdessen $e=1-bias$ zu wählen, weil dies einen gleichmäßigen Übergang zwischen normalisierten und denormalisierten Zahlen erzeugt.
	   Bei $32$-Bit gilt also: $e=1-127=-126$
3. Mantisse ablesen: *Hier wird keine 1.XXX sondern 0.XXX verwendet!*
	   In der gespeicherten Mantisse $\hat{m}=$ ``10000000000000000000000`` sind wieder die Nachkommastellen der Mantisse $m$ kodiert. In diesem Fall handelt es sich um $\frac{1}{2}=.5$
	   Anders als bei der normalisierten Darstellung wird hier aber keine $1$ vor das Komma gehängt, sondern eine $0$. Somit ist plötzlich auch die Darstellung von *genau* Null möglich.
	   Die Mantisse im Beispiel beträgt also $0.5$
4. Die Dezimalzahl aus Vorzeichen, Mantisse und Exponenten berechnen:
	  $z=0.5\cdot 2^{-126}=5.877471754111437539843683\cdot 10^{-39}$

## Dezimal->Gleitkomma
Gegeben sei die Dezimalzahl $1.4\cdot 10^{-43}$
1. Vorzeichen positiv $\to s=\hat{s}=0$
2. Mantisse mit [[Horner Schema]] berechnen (schreibe ich hier nicht auf, weil man $$ )
# Sonderfälle
