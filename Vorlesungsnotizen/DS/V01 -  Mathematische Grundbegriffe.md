---
"date:": 2025-10-14
tags:
  - DS
status: gelb
---
---

# Aussagen
Definition und Beispiele für Aussagen

Auch gesagt, dass der Wahrheitswert nicht bekannt sein muss, damit etwas eine Aussage ist

Wichtig/Interessant:
$a^{2}+b^{2}=c^{2}$ ist für ihn *keine* Aussage : Weil nicht klar ist, was $a,b,c$ seien sollen : Kontext unbekannt.
Es wird erst zu einer Aussage, wenn man die Information hinzugibt, dass $a$ und $b$ die Längen der Katheten eines Rechtwinkligen Dreiecks ist und $c$ die Länge der Hypotenuse ist.


## Zusammengesetzte Aussagen
Wahrheitswert von zusammengesetzten Aussagen hängt ab von
- der logischen Struktur / Der Art der zusammengesetzten Aussage
- Wahrheitswerte der Einzelaussagen
- *nicht* von den Einzelaussagen selbst (kommt gleich mehr Info)
  ($A\wedge B$ ist davon unabhängig, ob $A$ und $B$ Aussagen über das Wetter, die Existenz von Primzahlen oder sonst was sind. *Es ist egal, wo die Wahrheitswerte der Aussage herkommt -> nur er selbst entscheidet*

Schöne Tabelle:
![[Pasted image 20251014171331.png]]


Interssant:

$A\to B$ ist gleichbedeutend mit:
- "Wenn $A$, dann $B$"
- "$A$ ist hinreichend für $B$"
- "$B$ ist notwendig für $A$"


Haben XOR gemacht
Haben die Bijunktion (Äquivalenz) gemacht

Mal wieder die Verneinung von Quantoren gemacht - Sollte mal eine schöne Notiz machen bzw. die Quantor-Notiz mit der Aussagenlogik>Verneinung Notiz verknüpfen.


# Wichtige Schreibweisen:
Ist $(A\to B)$ wahr, dann schreiben wir (auf der Metaebene?) $A\implies B$
Ebenso für $\leftrightarrow$ vs. $\iff$

D.h. wenn $A\to B$ falsch ist, darf man nicht schreiben $A\implies B$ , sondern nur $A \to B$

Hier nochmal bzgl. Richtigkeit drüberschauen.
**Subjunktion $\neq$ Implikation**
**Bijunktion $\neq$ Äquivalenz**

https://lehrerfortbildung-bw.de/u_matnatech/mathematik/gym/bp2016/fb9/02_logik/13_subj/zpgvkm_02_aus_32_vertiefung_unterschied_subjunktion_und_implikation.pdf

## "Punkt vor Strich" und andere Rechenregeln
Die UND Verknüpfung bindet stärker als die ODER Verknüpfung:

$(A\wedge B)\vee C \leftrightarrow A\wedge B\vee C$


$(A\to B)\to C$ und $A\to(B\to C)$ sind verschieden.

Die Negation ist ist stärker als und/oder


## Beispiel

| A   | B   | C   | $A\vee B$ | $A\wedge C$ | $(A\wedge B)\to(A\vee C)$ |
| --- | --- | --- | --------- | ----------- | ------------------------- |
| 1   | 1   | 1   |           |             | 1                         |
| 1   | 1   | 0   |           |             | 0                         |
| 1   | 0   | 1   |           |             | 1                         |
| 1   | 0   | 0   |           |             | 0                         |
| 0   | 1   | 1   |           |             | 0                         |
| 0   | 1   | 0   |           |             | 0                         |
| 0   | 0   | 1   |           |             | 1                         |
| 0   | 0   | 0   |           |             | 1                         |
# Logische Terme : Alphabet der Aussagenlogik

Alphabet der Aussagenlogik:
- Variablen: $A,B,C,\dots$ 
- Konstanten: $0,1$
- Symbole: $\neg,\vee,\wedge,\to,\leftrightarrow$

"Sinnvoll" aus dem Alphabet zusammengesetzte Wörter: 
(***HIER KOMMEN DIE GRUNDLEGENDEN REGELN mit denen man dann andere Wörter herleiten kann)*** 
WICHTIG
- ...
- ..
  
  
(s.h. Bild):
![[Pasted image 20251014175103.png]]

>[!def] aussagenlogischer Term
> Ein Terme sind aus dem Alphabet der Aussagenlogik zusammengesetzte Wörter.
> Durch Belegung der Variablen mit Wahrheitswerten bekommt der Term selbst einen Wahrheitswert


Beispiele für Logische Terme
...

Keine Logische Terme:
$A\to B\to C$ ist keine Aussage, weil es ohne Klammern nicht eindeutig ist: $(A\to B)\to C$ und $A\to(B\to C)$ sind verschieden.

Terme sind Wörter aus dem Alphabet der Aussagenlogik.
Man kann Terme dann als Aussage interpretieren und ihnen abhängig von den Werten der Variablen einen Wahrheitswert haben.

$\equiv$ wenn zwei Terme für alle Variablenkombinationen jeweils die gleichen Wahrheitswerte aufweisen.

---








NOCHMAL FRAGEN
$\equiv$ vs $\iff$ vs $\leftrightarrow$ ![[V01 -  Mathematische Grundbegriffe 2025-10-14 18.26.16.excalidraw]]
### Semi glaubwürdige ChatGPT Antwort:

Sehr gute Fragen — das zeigt, dass du die Grundlagen der Aussagenlogik wirklich verstehen willst.  
Lass uns das Schritt für Schritt sauber klären:

---

### **1️⃣ Sind Terme wieder Aussagen?**

👉 **Ja**, logische **Terme sind wieder Aussagen.**

**Begründung:**

- Ein **logischer Term** (oder eine **aussagenlogische Formel**) wird aus **Aussagevariablen** (wie (A, B, C)) und **logischen Verknüpfungen** (¬, ∧, ∨, →, ↔ usw.) **nach festen Regeln** zusammengesetzt.
    
- Sobald du **den Variablen Wahrheitswerte** (0 oder 1, also „falsch“ oder „wahr“) **zuordnest**, bekommt der ganze Term **selbst einen Wahrheitswert**.
    
- Damit **ist der Term selbst wieder eine Aussage**, weil er „wahr“ oder „falsch“ sein kann.
    

🔹 Beispiel:  
[  
A ∨ (¬B)  
]

- Wenn (A = 1) und (B = 0), dann ist (A ∨ (¬B) = 1 ∨ 1 = 1) (also wahr).  
    → Der Term ist also **eine Aussage**, deren Wahrheitswert von (A) und (B) abhängt.
    

---

### **2️⃣ Unterschied zwischen ( \iff ) und ( \equiv )**

Das ist eine häufige, aber sehr wichtige Unterscheidung:

|Symbol|Bedeutung|Anwendung|
|:--|:--|:--|
|( \boldsymbol{\iff} )|**logische Verknüpfung innerhalb** eines Terms|Teil einer Formel|
|( \boldsymbol{\equiv} )|**logische Äquivalenz zwischen zwei ganzen Formeln**|Metasprache: Aussage _über_ Formeln|

---

#### 🔸 ( A \iff B )

- ist **selbst eine neue Aussage** (ein logischer Term)
    
- bedeutet: „A genau dann, wenn B“
    
- hat **einen Wahrheitswert** (wahr oder falsch)
    

Beispiel:  
[  
A \iff B  
]  
ist wahr genau dann, wenn (A) und (B) denselben Wahrheitswert haben.

---

#### 🔸 ( A \equiv B )

- ist **keine Aussage innerhalb der Logik**, sondern eine **Behauptung in der Metasprache** (also auf der Ebene _über_ der Logik).
    
- bedeutet: „A und B sind logisch äquivalent“, d. h. sie haben **unter jeder möglichen Belegung** dieselben Wahrheitswerte.
    
- (A \equiv B) ist also **eine Aussage über Formeln**, nicht selbst eine Formel.
    

Beispiel:  
[  
A → B \equiv ¬A ∨ B  
]  
heißt: Die Formeln (A → B) und (¬A ∨ B) liefern **in jeder möglichen Belegung denselben Wahrheitswert**.  
→ Sie sind **gleichbedeutend** (äquivalent), aber die Gleichung selbst ist **keine logische Formel**, sondern eine Aussage _über_ Formeln.

---

### 🔹 Kurz gesagt:

|Ausdruck|Bedeutung|Art|
|:--|:--|:--|
|(A \iff B)|„A genau dann, wenn B“|**Formel** der Aussagenlogik|
|(A \equiv B)|„A und B sind logisch äquivalent (haben in jeder Belegung denselben Wahrheitswert)“|**Metaaussage** über Formeln|

---

### 🔍 Merksatz:

> Jeder **logische Term** ist selbst wieder eine **Aussage**,  
> aber ( \equiv ) ist eine **Aussage über Aussagen**, kein Bestandteil der Logik selbst.

---

Möchtest du, dass ich dir dazu eine kleine Wahrheitstabelle zeige, um den Unterschied zwischen (A \iff B) und (A \equiv B) zu veranschaulichen?

)


# \END chatgpt


Frage:

$(\text{Ich weiß, dass }''A\equiv B''\text{ stimmt})\implies(A\iff B)$