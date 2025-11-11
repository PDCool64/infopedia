---
tags:
  - AFI
status: rot
---
---
# Gauß'sche Summenformel
>[!def] Gauß'sche Summenformel
> 
> $$
> \sum_{i=1}^{n}k=\frac{n(n+1)}{2}
> $$

---
# Binomische Formel

>[!def] Binomische Formel
> Für $n\in \mathbb{N}_{0}$ und alle reellen Zahlen $a,b$ gilt:
> $$
> (a+b)^{n}=\sum_{k=0}^{n}\binom{n}{k}a^{k}b^{n-k}=\sum_{k=0}^{n}\binom{n}{k}a^{n-k}b^{k}
> $$

## Umformungen des Binomialkoeffizienten:
$$
\binom{n}{k}=\binom{n}{n-k}
$$
$$
\binom{n}{k-1}+\binom{n}{k}=\binom{n+1}{k} \quad\text{falls}\;k>0
$$
und grundsätzlich:
$$
\binom{n}{k}=\frac{n!}{k!\cdot(n-k)!}
$$

---
# Geometrische Summenformel

>[!def] Geometrische Summenformel
> Für $n\in \mathbb{N}_{0}$ und jedes $q\in K,q\neq 1$ gilt:$$ \sum_{k=0}^{n}q^{k}=\frac{q^{n+1}-1}{q-1}$$
> und allgemeiner für alle $n\in \mathbb{N}_{0}$ und alle $a,b\in K$ mit $a\neq b$ gilt:$$\sum_{k=0}^{n}a^{k}b^{n-k}=\frac{a^{n+1}-b^{n+1}}{a-b}$$


>[!def] Standardfaktorisierung:
> Aus obiger Formel ergibt sich auch die **Standardfaktorisierung**:
> 
> $$q^{n}-1=(q-1)\cdot \sum_{k=0}^{n-1}q^{k}$$

---
