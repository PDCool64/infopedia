>[!def] Folge
> Eine **Folge [[Zahlenräume#Reelle Zahlen $ mathbb{R}$|reeller]] Zahlen** ist eine [[Abbildungen|Abbildung]] $a:\mathbb{N}\to \mathbb{R},n\to a(n)$ 
> 
> ---
> 
> Meisten schreiben wir eine Folge kurz als
> $(a_{n})_{n\geq 1}$ oder $(a_{n})_{n\in \mathbb{N}}$
> 
> wobei $a_{n}:=a(n)$
> 
> ---
> 
> Die Zahlen $a_{n}$ heißen **Folgenglieder**.

## Rekursive Folgen
Folgen lassen sich auch *rekursiv definieren*, was ein "gleichmächtiger" Ansatz ist.
Bsp. $(a_{n})_{n\geq 1}:a_{n+1}=2a_{n}\;,\;a_{1}=1$ ist gleichbedeutend zu $(\tilde{a}_{n})_{n\geq 1}:a_{n}=2^{n}$

Rekursive folgen müssen, um überhaupt eindeutig definiert zu sein, einen "Anker" haben, d.h. das Folgenglied $a_{1}$ muss angegeben werden.

Obwohl beide Ansätze gleichmächtig sind, ist es sehr oft nicht einfach (auch mit Rechenleistung) möglich, jede rekursive Folge in eine explizite Darstellung zu bringen.

# Monotonie einer Folge
Die Monotonie einer Folge lässt sich mit den gleichen Definitionen bestimmen, wie sie auch bei reellen Funktionen greifen:
[[Monotonie von Funktionen]]. Nicht anwendbar sind hingegen Verfahren der Differenzialrechnung, da "gestückelte" Folgen nicht differenzierbar sind. ^711ffd

# Beschränktheit einer Folge

>[!def] Schranken einer Folge
> 1. Eine Folge $(a_{n})_{n\ge1}$ heißt (absolut) **beschränkt**, wenn es ein [[Intervalle auf den reellen Zahlen#^164ba4|abgeschlossenes Intervall]] $[a,b]$ gibt, mit 
>    $$\forall_{n\in \mathbb{N}}:a_{n}\in[a,b]$$
> 
> 2. Eine (absolute) Schranke der Folge $(a_{n})_{n\ge1}$ ist eine [[Zahlenräume#Reelle Zahlen $ mathbb{R}$|reelle]] Zahl $C\ge 0$ mit $$\forall_{n\in \mathbb{N}}: \left| a_{n} \right| \le C$$
> 
> 3. $(a_{n})_{n\ge 1}$ heißt nach oben beschränkt, wenn ein $c_{o}\in \mathbb{R}$ existiert mit  $\forall_{n\in \mathbb{N}}: a_{n}\le c_{o}$
>    $(a_{n})_{n\ge 1}$ heißt nach unten beschränkt, wenn ein $c_{u}\in \mathbb{R}$ existiert mit  $\forall_{n\in \mathbb{N}}: a_{n}\ge c_{u}$ 
>    
>    $c_{o}$ heißt **obere Schranke**
>    $c_{u}$ heißt **untere Schranke**
>    
>    Schranken sind -*falls* sie existieren- nie eindeutig.

^f4f35f
### Bemerkungen
- $\text{Folge }A \text{ ist beschränkt} \iff\text{Eine absolute Schranke C existiert}$
  ($A$ ist beschränkt auf $[a,b]$ $\implies C=\text{max}(|a|,|b|)$)
  ($C$ ist eine Schranke von $A\implies$ $A$ ist beschränkt auf $[-C,+C]$)

# Konvergenz und Grenzwert von Folgen

>[!def] Konvergenz und Grenzwert eine Folge
> Eine Folge  $(a_{n})_{n\ge1}$ [[Zahlenräume#Reelle Zahlen $ mathbb{R}$|reeller]] Zahlen **konvergiert** gegen die reelle Zahl $g$, wenn gilt:$$\forall_{\varepsilon>0}\exists_{N\in \mathbb{N}}\forall_{n\in \mathbb{N}>N}:|a_{n}-g|<\varepsilon$$
> Dann heißt $g$ **Grenzwert** der Folge und wir schreiben:$$
> g=\lim_{ n \to \infty } a_{n}\quad\text{oder}\quad a_{n} \overset{n\to \infty}{\longrightarrow} g$$
> 
> was bedeutet:
> Für *jedes* $\varepsilon$ findet sich ein (großer) Index $N$, ab dem alle weiteren Folgenglieder in der $\varepsilon$-Umgebung liegen.
> 
> ---
>  
>  Eine Folge kann keinen oder einen Grenzwert haben. Eine Folge kann *nicht* zwei Grenzwerte haben.
>  
> ---
> Ist eine Folge nicht konvergent, heißt sie **divergent**.

^10a5bc
^7e2af7
### Bemerkungen
- Jede [[#^7e2af7|konvergente]] Folge ist [[#^f4f35f|beschränkt]].
- Jede Folge, die [[#^711ffd|monoton]] und [[#^f4f35f|beschränkt]] ist, [[#^7e2af7|konvergiert]].
Bei beiden Aussagen gelten die Umkehrungen *nicht*.

- Um zu zeigen, dass eine Folge [[#^10a5bc|divergent]] ist, kann man u.A. einen Widerspruchsbeweis führen.

## Bestimmte Divergenz

>[!def] Bestimmte Divergenz
> 1. Eine Folge heißt **bestimmt divergent gegen $+\infty$** , wenn gilt:
>    Zu jeder (theoretischen)oberen Schranke $M\in \mathbb{R}$ gibt es ein $N\in \mathbb{N}$ ab dem alle Folgenglieder $a_{n}$ größer als $M$ sind.
>    $\forall_{M\in \mathbb{R}}\exists_{N\in \mathbb{R}}\forall_{n\ge N}:a_{n}>M$
> 2. Eine Folge heißt **bestimmt divergent gegen $-\infty$** , wenn gilt:
>    Zu jeder (theoretischen)unteren Schranke $M\in \mathbb{R}$ gibt es ein $N\in \mathbb{N}$ ab dem alle Folgenglieder $a_{n}$ größer als $M$ sind.
>    $\forall_{M\in \mathbb{R}}\exists_{N\in \mathbb{R}}\forall_{n\ge N}:a_{n}>M$
> 	
> 	Man zeigt also die bestimmte Divergenz darin, dass jede erdenkliche Schranke von der Folge irgendwann über- bzw. unterschritten wird.



>[!def] Häufungspunkt
> Ist $h\in \mathbb{R}$ eine Zahl, so dass für jedes feste $\varepsilon>0$ unendlich viele Glieder $a_{n}$ der Folge innerhalb des Intervalls $(h-\varepsilon;h+\varepsilon)$ liegen, so heißt $h$ **Häufungspunkte der Folge**.
> 
> ---
> Eine Folge kann beliebig viele Häufungspunkte haben.

Bsp. für eine Folge mit zwei Häufungspunkten: $(a_{n})_{n\ge 1}:a_{n}=(-1)^{n}$
## Bemerkungen:
- Jeder [[#Konvergenz und Grenzwert von Folgen|Grenzwert]] ist auch ein Häufungspunkt - nicht jeder Häufungspunkt ist aber auch ein Grenzwert.

# Grenzwertsätze
>[!def] Grenzwertsätze
> Seien $(a_{n})_{n\ge 1}$ und $(b_{n})_{n\ge 1}$ **[[#^10a5bc|konvergente]]** Folgen mit
> $a=\lim_{ n \to \infty }a_{n}$ und
> $b=\lim_{ n \to \infty }b_{n}$ , dann gilt:
> 
> 1. Die Folge $(c_{n})_{n\ge 1}$ mit $c_{n}:=a_{n}+b_{n}$ ist konvergent mit $\lim_{ n \to \infty }c_{n}=a+b$
> 2. Die Folge $(c_{n})_{n\ge 1}$ mit $c_{n}:=a_{n}\cdot b_{n}\;\;$ ist konvergent mit $\lim_{ n \to \infty }c_{n}=a\cdot b$
>    
> 3. Sind sowohl alle $b_{n}$ als auch der Grenzwert $b$ ungleich Null, so ist die Folge $(c_{n})_{n\geq 1}$ mit $c_{n}:=\frac{a_{n}}{b_{n}}$ konvergent mit $\lim_{ n \to \infty }c_{n}=\frac{a}{b}$
>    
>    ---
>    **WICHTIG** : Die Grenzwertsätze sind **nur bei konvergenten Folgen** anwendbar.

Die Grenzwertsätze erlauben es, zusammengesetzte Folgen auf mehrere schon bekannte Fälle zu reduzieren.

## Anwendung der Grenzwertsätze in der Praxis

### Bsp.1
$$
\begin{align}
\lim_{ n \to \infty } \frac{3n^{2}+2}{n^{2}+6}
\end{align}
$$
Da sowohl Zähler als auch Nenner gegen $+\infty$ laufen, finden die [[#Grenzwertsätze]] noch keine Anwendung.
Bei Quotienten empfiehlt es sich fast immer, **die höchste Potenz auszuklammern**:$$
\begin{align}
\lim_{ n \to \infty } \frac{n^{2}\left( 3+\frac{2}{n^{2}} \right)}{n^{2}\left( 1+\frac{6}{n^{2}} \right)}
\end{align}
$$
Denn dann lässt sich kürzen:
$$
\begin{align}
&\lim_{ n \to \infty } \frac{ 3+ \frac{2}{n^{2}}  }{ 1+\frac{6}{n^{2}} } 

\end{align}
$$
Nun hat man zwei tatsächlich [[#^10a5bc|konvergente]] Folgen als Zähler und Nenner und kann die [[#Grenzwertsätze]] anwenden:
$$
\begin{align}
&\frac{\lim_{ n \to \infty } 3+\frac{2}{n^{2}}}{\lim_{ n \to \infty } 1+\frac{6}{n^{2}}} \\ \\

=& \frac{\lim_{ n \to \infty } 3+\lim_{ n \to \infty } \frac{2}{n^{2}}}{\lim_{ n \to \infty } 1+\lim_{ n \to \infty } \frac{6}{n^{2}}}
  \\
 \\
=& \frac{3+0}{1+0}=3
\end{align}

$$

# Bsp.2
$$
\begin{align}
&\lim_{ n \to \infty } \frac{n^{2}+1}{n+1} \\
 \\

=&\lim_{ n \to \infty } \frac{n^2\left( 1+\frac{1}{n^{2}} \right)}{n\left( 1+\frac{1}{n} \right)} \\ \\


=&\lim_{ n \to \infty } n\cdot \underbrace{ \frac{1+\frac{1}{n^{2}}}{1+\frac{1}{n}} }_{\to 1 }

\end{align}
$$
Es wird intuitiv schnell ersichtlich, dass die Folge gegen $+\infty$ läuft - formell kann man dies durch die [[#Bestimmte Divergenz]] gegen $+\infty$ zeigen:
Zu zeigen ist: $$(a_{n})_{n\geq 1}:a_{n}=n\cdot\frac{1+\frac{1}{n^{2}}}{1+\frac{1}{n}}$$ überschreitet jede erdenkliche obere Schranke $M$.

1. $M\in \mathbb{R}_{\ge 0}$ sei eine beliebige obere Schranke. 
2. Es wird gezeigt, dass $\forall_{n\ge N}: a_{n}>M$
   
   
Die Folge$$
n\cdot \frac{1+\frac{1}{n^{2}}}{1+\frac{1}{n}}
$$lässt sich aufteilen in zwei Folgen, wobei $b_{n}:=\frac{1+\frac{1}{n^{2}}}{1+\frac{1}{n}}$ der zweite der beiden Faktoren sein soll.
Für die Folge $b_{n}$ lässt sich zeigen, dass diese den [[#Konvergenz und Grenzwert von Folgen|Grenzwert]] $1$ hat:$$
\begin{align}
&\lim_{ n \to \infty }  \frac{1+\frac{1}{n^{2}}}{1+\frac{1}{n}}  \\ \\

\overset{GWS}{=} &\frac{\lim_{ n \to \infty } 1+\frac{1}{n^{2}}}{\lim_{ n \to \infty } 1+\frac{1}{n}}   \\
 \\
\overset{GWS}{=} &\frac{\lim_{ n \to \infty } 1+\lim_{ n \to \infty } \frac{1}{n^{2}}}{\lim_{ n \to \infty } 1\lim_{ n \to \infty } +\frac{1}{n}}  \\ \\

=& \;\;\frac{1+0}{1+0}=1
\end{align}
$$
Daraus folgt mit der [[#Konvergenz und Grenzwert von Folgen|Konvergenzdefinition]], dass $b_{n}$ für ausreichend große $n$ der $1$ *beliebig* nahe kommt. 
Insbesondere folgt daraus, dass $b_{n}$ für ausreichend große $n$ sicher über Werte wie $\frac{1}{2},0.6,0.999$ usw. hinaussteigen wird.

Somit lässt sich die Folge $b_{n}$ *konservativ* durch $\frac{1}{2}$ nach unten abschätzen.

Für ausreichend große $n$ gilt also:
$$
\begin{align}
a_{n}=n\cdot b_{n}> n\cdot \frac{1}{2}
\end{align}
$$
Es reicht somit zu zeigen, dass ein $N$ existiert, ab dem für alle größeren $n$ gilt :
$$\begin{align}
M&>n\cdot \frac{1}{2} &|\cdot 2 \\
2M &>n \\ \\

\implies N&=2M+1
\end{align}$$
Somit existiert für jede erdenkliche obere Schranke $M$ ein $N=2M+1$, ab dem alle Folgenglieder größer als $M$ sind.
