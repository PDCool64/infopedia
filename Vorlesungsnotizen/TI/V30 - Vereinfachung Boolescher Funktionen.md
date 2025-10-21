---
date: 2025-10-21
tags:
  - TI
status: rot
Vorlesungsfolien: "[[Kapitel 3 - Vereinfachung Boolescher Funktionen.pdf]]"
Skriptfolien:
---
---
Warum vereinfachen: Will ich eine boolesche Funktion in hardware realisiert, ist es günstiger/effizienter/kleiner/schneller/effizienter Weniger Gatter = Verknüpfungen zu brauchen.

---

>[!def] Resolutionsregel
> Dieses ganze Kapitel basiert fasst komplett auf der **Resolutionsregel**
> $$
> ab+\bar{a}b=a(b+\bar{b})=a1=a
> $$

Besonders schön kann man diese Regel auf DNFs draufwerfen und so lange vereinfachen, bis nix mehr geht. 

Bsp. s.h. PXL Foto oder [[Kapitel 3 - Vereinfachung Boolescher Funktionen.pdf#page=2]] f.f.

---
# Minimalpolynome
> Polynom = DF(Disjunktive Form) = SoP (Sum of Products)

Minimalpolynome sind das, was hier bei der Vereinfachungen von boolescher suchen.
(Auch wenn man mit anderen Formen, z.B. xor , eine boolesche Funktion noch kürzer schreiben könnte. Allein das finden von Minimalpolynomen ist schon schwer genug)

Die Namenskonvention, disjunktive Formen auch Polynome zu nennen, ist parallel zur Idee des Polynoms in der Mathematik.



# Vereinfachung von OBDDs

## Verjüngungsregel / 4-3 Regel
![[Pasted image 20251021194039.png]]

## Eliminationsregel:
![[Pasted image 20251021194145.png]]

Zur bestmöglichen Vereinfachung, muss man beide Regeln so oft anwenden, bis man in einem Zustand ankommt, in dem keine der beiden mehr Anwendbar ist.
Dadurch, dass man die eine Regel anwendet, kann ein Zustand entstehen, der die Anwendung der anderen Regel ermöglicht.


## Konvertierung zurück:
Hat man den OBDD nach den beiden obigen Regeln vereinfacht, dann kann man aus dem vereinfachten OBDD schnell eine DNF / KNF anwenden.

aber: Die Anzahl an Knoten im OBDD ist nicht immer "proportional" zur Länge von KNF

*Die durch Vereinfachung des OBDD erreichte KNF/DNF ist nicht zwangsweise ein Minimalpolynom*. Es kann sein, dass man danach noch mit Logikgesetzen weitermachen muss.

# Vereinfachung mit Karnaugh-Diagrammen
- Die Blöcke dürfen nur Einsen enthalten
-  Die Kantenlängen der Blöcke müssen Zweierpotenzen sein
- Die Blöcke müssen maximale Größe haben


![[Pasted image 20251021194958.png]]

Man sieht: Blöcke dürfen sich überlappen.

> Fand die Erklärung von Herr teuschler viel schöner. Sollte nochmal in 1note suchen

Man kann eigentlich einfach pro Block eine oder mehrere Variablen ablesen, die für diesen Block *egal* sind - je größer der Block desto mehr variablen sind für ihn egal.

d.h. in dem Blauen Block oben links sind x1 und x3 egal. (s.h. PXL FOto)