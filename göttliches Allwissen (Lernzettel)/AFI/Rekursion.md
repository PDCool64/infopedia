---
tags:
  - AFI
status: rot
---
---
Es geht hier um den *Rekursionssatz von Dedekind*, nicht um Rekursion in der Programmierung - wenn beide Themen auch sehr verwandt sind.

---

>[!def] Rekursion
> Es sei $M$ eine nicht-leere [[Mengen|Menge]]. Für jedes $n\in \mathbb{N}$ sei $g_{n}:M\to M$ eine [[Abbildungen|Abbildung]]. Weiter sei $b\in M$.
> Dann gibt es *genau eine* Abbildung $r:\mathbb{N}\to M$ mit den Eigenschaften
> - $r(1)=b$
> - $r(n+1)=g_{n}(r(n))$
> 

$r$ ist hier die Abbildung, die dem "Anwender" letztendlich für jede natürliche Zahl $n$ als Eingabe, das Ergebnis nach $n$ Rekursionsschritten gibt.

$g_{n}$ hingegen ist die Abbildung, welche den Rekursionsschritt selbst definiert, d.h. definiert wie genau man für diese speziellen Sachverhalt vom $n$-ten auf den $n+1$-ten Wert kommt.

> d.h. : Zu jeder rekursiven Folge die durch Rekursionsschritt $g_{n}$ und einen Startwert definiert ist, existiert auch eine eindeutige "explizite" Abbildung $r$. 

## Anders herum gedacht: (DS)
>[!def] Rekursionssatz von Dedekind (DS)
> Es sei $N$ eine Menge, $f:N\to N$ [[Abbildungen|Abbildung]] und $a\in N$.
> Dann gibt es genau eine [[Folgen (Alt)|Folge]] $(a_{n})_{n\in \mathbb{N}}$ mit:
> - $a_{1=a}$
> - $a_{n+1}=f(a_{n})$ für $n\in \mathbb{N}$
> 

> D.h. zu jeder "expliziten" Abbildung $f$ existiert eine eindeutige rekursive Folge, die die Funktionswerte an den natürlichen Zahlen nachbildet.


## Wichtige Bemerkung: Existenz $\neq$ Praktisch
- Die reine Existenz und Eindeutigkeit einer Expliziten Abbildung ist nur dies, und nichts mehr. Die explizite Form ist oft:
	- nicht konstruierbar
	- nicht als Formel aufschreibbar
	- nicht berechenbar
- Aus expliziten Formen kann man formell immer eine triviale rekursive Form bauen, auch wenn diese oft keine "schönen" kleinen Rekusionsschritte ergeben.

---
# Rekursion für [[Summenzeichen und Produktzeichen]]

>[!def]
> Es seien reelle Zahlen $a_{k},k\in \mathbb{N}$ gegeben.
> Für jedes $n\in \mathbb{N}$ definiere die Summe $\sum_{k=1}^{n}a_{k}$ rekursiv durch
> $$\sum_{k=1}^{1}a_{k}:=a_{1}$$
> und $$\sum_{k=1}^{n+1}a_{k}:=\left( \sum_{k=1}^{n}a_{k} \right)+a_{n+1}$$
> Analog definiert man das Produkt $\prod_{k=1}^{n}a_{k}$ durch $$\prod_{k=1}^{1}a_{k}:=a_{1}$$
> und $$\prod_{k=1}^{n+1}a_{k}:=\left( \prod_{k=1}^{n}a_{k} \right)+a_{n+1}$$
