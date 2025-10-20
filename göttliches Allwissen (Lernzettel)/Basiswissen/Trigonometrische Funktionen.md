# Definitionen im rechtwinkligen Dreieck

```tikz
\begin{document}
\begin{tikzpicture}[scale=1.5]
	\draw (0,0)--(0,2)--(4,0)--(0,0);
	
	\node[below left] (A) at (0,0) {$A$};
	\node[below right] (B) at (4,0) {$B$};
	\node[above left] (C) at (0,2) {$C$};
	
	\fill (0,2) circle (1pt);
	\fill (0,0) circle (1pt);
	\fill (4,0) circle (1pt);
	
	% Winkel bei A mit arc
  \draw (0.6,0) arc[start angle=0, end angle=90, radius=0.6];
  \node at (0.27,0.2) {$90^{\circ}$};

  % Winkel bei B
  \draw (3.4,0) arc[start angle=180, end angle=153.4, radius=0.6];
  \node at (3,0.2) {$\beta$};

  % Winkel bei C
  \draw (0,1.4) arc[start angle=270, end angle=333.4, radius=0.6];
  \node at (0.2,1.65) {$\gamma$};
  
  \node at (2,-0.2) {$c=\;$Ankathete von $\beta$};
  \node at (2,-0.5) {$\;\quad\;\,\;\,=\;$Gegenkathete von $\gamma$};
  
  \node[left] at(-0.4,1) {Ankathete von $\gamma=b$};
  \node[left] at(-0.4,0.6) {Gegenkathete von $\beta=\;\;$};
  
  \node[right] at (2,1.4) {$a=\;$Hypothenuse};
	
\end{tikzpicture}
\end{document}
```

---

```tikz
\begin{document}
\begin{tikzpicture}[scale=1.5]
	\draw (0,0)--(0,2)--(4,0)--(0,0);
	\draw[ultra thick,teal] (0,0)--(0,2);
	\draw[ultra thick,lime] (0,2)--(4,0);
	
	\node[below left] (A) at (0,0) {$A$};
	\node[below right] (B) at (4,0) {$B$};
	\node[above left] (C) at (0,2) {$C$};
	
	\fill (0,2) circle (1pt);
	\fill (0,0) circle (1pt);
	\fill (4,0) circle (1pt);
	
	% Winkel bei A mit arc
  \draw (0.6,0) arc[start angle=0, end angle=90, radius=0.6];
  \node at (0.27,0.2) {$90^{\circ}$};

  % Winkel bei B
  \draw[orange,ultra thick] (3.4,0) arc[start angle=180, end angle=153.4, radius=0.6];
  \node[orange] at (3,0.2) {$\beta$};

  % Winkel bei C
  \draw (0,1.4) arc[start angle=270, end angle=333.4, radius=0.6];
  \node at (0.2,1.65) {$\gamma$};
  
  \node at (2,-0.2) {$c$};
 
  
  \node[left,teal] at(-0.1,1) {$b$};

  
  \node[right,lime] at (2,1.1) {$a$};
  
  \node[left] at (-1.8,1) {$\sin({\color{orange}{\beta}})= \frac{{}}{}$};
  \node[centered,teal] at (-1.2,1.15) {Gegenkathete};
  \node[centered,lime] at (-1.2,0.85) {Hypothenuse};
  \draw[thick] (-1.9,1) -- (-0.5,1);
	
\end{tikzpicture}
\end{document}
```

---

```tikz
\begin{document}
\begin{tikzpicture}[scale=1.5]
	\draw (0,0)--(0,2)--(4,0)--(0,0);
	\draw[ultra thick,teal] (0,0)--(4,0);
	\draw[ultra thick,lime] (0,2)--(4,0);
	
	\node[below left] (A) at (0,0) {$A$};
	\node[below right] (B) at (4,0) {$B$};
	\node[above left] (C) at (0,2) {$C$};
	
	\fill (0,2) circle (1pt);
	\fill (0,0) circle (1pt);
	\fill (4,0) circle (1pt);
	
	% Winkel bei A mit arc
  \draw (0.6,0) arc[start angle=0, end angle=90, radius=0.6];
  \node at (0.27,0.2) {$90^{\circ}$};

  % Winkel bei B
  \draw[orange,ultra thick] (3.4,0) arc[start angle=180, end angle=153.4, radius=0.6];
  \node[orange] at (3,0.2) {$\beta$};

  % Winkel bei C
  \draw (0,1.4) arc[start angle=270, end angle=333.4, radius=0.6];
  \node at (0.2,1.65) {$\gamma$};
  
  \node[teal] at (2,-0.2) {$c$};
  \node[left] at(-0.1,1) {$b$};
  \node[right,lime] at (2,1.1) {$a$};
  
  \node[left] at (-1.8,1) {$\cos({\color{orange}{\beta}})= \frac{{}}{}$};
  \node[centered,teal] at (-1.2,1.15) {Ankathete};
  \node[centered,lime] at (-1.2,0.85) {Hypothenuse};
  \draw[thick] (-1.9,1) -- (-0.5,1);
	
\end{tikzpicture}
\end{document}
```

---

```tikz
\begin{document}
\begin{tikzpicture}[scale=1.5]
	\draw (0,0)--(0,2)--(4,0)--(0,0);
	\draw[ultra thick,lime] (0,0)--(4,0);
	\draw[ultra thick,teal] (0,2)--(0,0);
	
	\node[below left] (A) at (0,0) {$A$};
	\node[below right] (B) at (4,0) {$B$};
	\node[above left] (C) at (0,2) {$C$};
	
	\fill (0,2) circle (1pt);
	\fill (0,0) circle (1pt);
	\fill (4,0) circle (1pt);
	
	% Winkel bei A mit arc
  \draw (0.6,0) arc[start angle=0, end angle=90, radius=0.6];
  \node at (0.27,0.2) {$90^{\circ}$};

  % Winkel bei B
  \draw[orange,ultra thick] (3.4,0) arc[start angle=180, end angle=153.4, radius=0.6];
  \node[orange] at (3,0.2) {$\beta$};

  % Winkel bei Ca
  \draw (0,1.4) arc[start angle=270, end angle=333.4, radius=0.6];
  \node at (0.2,1.65) {$\gamma$};
  
  \node[lime] at (2,-0.2) {$c$};
  \node[left,teal] at(-0.1,1) {$b$};
  \node[right] at (2,1.1) {$a$};
  
  \node[left] at (-1.8,1) {$\tan({\color{orange}{\beta}})= \frac{{}}{}$};
  \node[centered,teal] at (-1.2,1.15) {Gegenkathete};
  \node[centered,lime] at (-1.2,0.85) {Ankathete};
  \draw[thick] (-1.9,1) -- (-0.5,1);
	
	%===============COTAN===============
	\def\y{-3.6}
  \draw (0,0+\y)--(0,2+\y)--(4,0+\y)--(0,0+\y);
	\draw[ultra thick,lime] (0,0+\y)--(4,0+\y);
	\draw[ultra thick,teal] (0,2+\y)--(0,0+\y);
	
	\node[below left] (A) at (0,0+\y) {$A$};
	\node[below right] (B) at (4,0+\y) {$B$};
	\node[above left] (C) at (0,2+\y) {$C$};
	
	\fill (0,2+\y) circle (1pt);
	\fill (0,0+\y) circle (1pt);
	\fill (4,0+\y) circle (1pt);
	
	% Winkel bei A mit arc
  \draw (0.6,0+\y) arc[start angle=0, end angle=90, radius=0.6];
  \node at (0.27,0.2+\y) {$90^{\circ}$};

  % Winkel bei B
  \draw[orange,ultra thick] (3.4,0+\y) arc[start angle=180, end angle=153.4, radius=0.6];
  \node[orange] at (3,0.2+\y) {$\beta$};

  % Winkel bei C
  \draw (0,1.4+\y) arc[start angle=270, end angle=333.4, radius=0.6];
  \node at (0.2,1.65+\y) {$\gamma$};
  
  \node[lime] at (2,-0.2+\y) {$c$};
  \node[left,teal] at(-0.1,1+\y) {$b$};
  \node[right] at (2,1.1+\y) {$a$};
  
  \node[left] at (-1.8,1+\y) {cotan$({\color{orange}{\beta}})=\frac{1}{\tan({\color{orange}{\beta}})}= \frac{{}}{}$};
  \node[centered,teal] at (-1.2,0.85+\y) {Gegenkathete};
  \node[centered,lime] at (-1.2,1.15+\y) {Ankathete};
  \draw[thick] (-1.9,1+\y) -- (-0.5,1+\y);
  

	
\end{tikzpicture}
\end{document}
```


---


# Am Einheitskreis


























```tikz
\begin{document}
\begin{tikzpicture}[scale=1.5]

	\draw (0,0)--(0,2)--(4,0)--(0,0);
	\draw[ultra thick,lime] (0,0)--(4,0);
	\draw[ultra thick,teal] (0,2)--(0,0);
	
	\node[below left] (A) at (0,0) {$A$};
	\node[below right] (B) at (4,0) {$B$};
	\node[above left] (C) at (0,2) {$C$};
	
	\fill (0,2) circle (1pt);
	\fill (0,0) circle (1pt);
	\fill (4,0) circle (1pt);
	
	% Winkel bei A mit arc
  \draw (0.6,0) arc[start angle=0, end angle=90, radius=0.6];
  \node at (0.27,0.2) {$90^{\circ}$};

  % Winkel bei B
  \draw[orange,ultra thick] (3.4,0) arc[start angle=180, end angle=153.4, radius=0.6];
  \node[orange] at (3,0.2) {$\beta$};

  % Winkel bei C
  \draw (0,1.4) arc[start angle=270, end angle=333.4, radius=0.6];
  \node at (0.2,1.65) {$\gamma$};
  
  \node[lime] at (2,-0.2) {$c$};
  \node[left,teal] at(-0.1,1) {$b$};
  \node[right] at (2,1.1) {$a$};
  
  \node[left] at (-1.8,1) {cotan$({\color{orange}{\beta}})=\frac{1}{\tan({\color{orange}{\beta}})}= \frac{{}}{}$};
  \node[centered,teal] at (-1.2,0.85) {Gegenkathete};
  \node[centered,lime] at (-1.2,1.15) {Ankathete};
  \draw[thick] (-1.9,1) -- (-0.5,1);
	

\end{tikzpicture}
\end{document}
```


---
