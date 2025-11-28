# Lab 9 — Bayesian Inference with PyMC  

## Subpunctul b) Efectul lui Y si θ asupra posteriorului lui n

Modelul folosit:
- n ~ Poisson(10)
- Y | n, θ ~ Binomial(n, θ) cu θ cunoscut.

In medie:
Y ≈ n * θ  →  n ≈ Y / θ

### Efectul lui Y
Pentru θ fix, daca Y creste, valorile plauzibile pentru n devin mai mari.

Exemple observate in rezultate (θ = 0.2):
- Y = 0  → n ≈ 8  
- Y = 5  → n ≈ 13  
- Y = 10 → n ≈ 18  

### Efectul lui θ
Pentru acelasi Y, daca θ este mai mare, avem nevoie de un n mai mic pentru a explica datele.

Exemplu pentru Y = 10:
- θ = 0.2 → n ≈ 18  
- θ = 0.5 → n ≈ 15  

### Rolul priorului
Priorul Poisson(10) trage estimarea lui n spre 10 atunci cand Y este mic sau informatia este slaba (ex. Y = 0 si θ mica).

---

## Subpunctul d) Diferenta dintre posteriorul lui n si distributia predictiva a lui Y*

Posteriorul lui n descrie incertitudinea asupra numarului total de clienti dupa observarea lui Y.  
Este o distributie pe parametrul latent n.

Distributia predictiva pentru un viitor numar de cumparatori Y* este:

\[
p(Y^{*} \mid Y, \theta) = \sum_{n} p(Y^{*} \mid n, \theta)\, p(n \mid Y, \theta)
\]

Aceasta combinatie include:
1. incertitudinea despre n din posterior  
2. variabilitatea binomiala a unui nou experiment (cumparatori viitori)

De aceea, distributia pentru Y* este in general mai larga decat posteriorul lui n:  
Y* descrie un rezultat viitor, nu un parametru latent.
