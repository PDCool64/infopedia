>[!def] Innere direkte Summe
> Man schreibt $V=U_{1} \oplus U_{2}$ aus den beiden UVRs $U_{1},U_{2}$ gdw.
> 1. $V=U_{1}+U_{2}$ d.h. Jedes $v\in V$ lässt sich schreiben als
>    $v=u_{1}+u_{2}$ 
>    für $u_{1}\in U_{1}\;,\;u_{2}\in U_{2}$
> 2. $U_{1}\cap U_{2}=\{ 0 \}$
> 
>    ---
>    **Komplement:**
>    Für jedes $U_{1}\le V$ existiert ein $U_{2}$ sodass $U_{1} \oplus U_{2} = V$.
>    - Wähle dafür eine Basis $B_{1}=(b_{1},\dots,b_{n})$ von $U_{1}$.
>    - Ergänze dieser zu einer Basis $(b_{1},\dots,b_{n},a_{1},\dots,a_{m})$ von $V$
>    - Setze $U_{2}:=\langle a_{1},\dots,a_{m} \rangle$



>[!def] Projektion
> Für $V=U_{1} \oplus U_{2}$  und $i=1,2$ ist die **Projektion auf $U_{i}$** definiert als lineare Abbildung$$\text{pr}_{i}:V\to U_{i} \;,\; v=u_{1}+u_{2}\mapsto u_{i}$$
> 
> ---
> Jede lineare Abbildung $\varphi$ mit
>$$\varphi \circ \varphi = \varphi$$
>ist eine Projektion.
>Standardkonstruktion für die passenden UVR:
>- $U_{1}=\text{Bild}(\varphi)$
>- $U_{2}=\text{Kern}(\varphi)$
>  Diese Zerlegung ist eindeutig.


