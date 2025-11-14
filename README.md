# Système linéaire invariant avec retard pur

## Introduction

L'étude de la stabilité d'un système bouclé en présence d'un retard pur ne peut pas faire appel à certains critères classiques utilisés pour les systèmes linéaires invariants, tels que les propriétés sur les pôles ou les critères algébriques (Routh). Le seul critère qui aboutit dans ce contexte est le critère du revers appliqué sur le diagramme de Nyquist de la boucle ouverte.

## Exemple choisi

Pour l'exemple, la fonction de transfert $\mu(p)\beta(p)$ en boucle ouverte est exprimée avec

$$\mu(p)=\dfrac{K}{1+\tau p}$$

et

$$\beta(p)=\exp(-Tp)$$

## Diagramme de Nyquist de la boucle ouverte

<img width="597" height="459" alt="image" src="https://github.com/user-attachments/assets/7f29b690-87fd-4f72-a9cb-cde04d2948c5" />


## Equation différentielle avec retard pour la boucle fermée

En boucle fermée :

$$\dfrac{\mu(p)}{1+\mu(p)\beta(p)}=\dfrac{K}{1+\tau p+K\exp(-Tp)}=\dfrac{Y(p)}{U(p)}$$

L'équation différentielle  associée est :

$$y'(t) = -\dfrac{y(t)}{\tau}-\dfrac{Ky(t-T)}{\tau}+\dfrac{Ku(t)}{\tau}=F(t,y(t),y(t-T),u(t))$$

Il s'agit d'une EDR (Equation Différentielle avec Retard).

## Résolution numérique par la méthode des pas

L'intervalle de temps sur lequel on évalue numériquement la solution est découpé en intervalles de longueur $T$. Dans chaque intervalle $[nT, (n+1)T]$ avec $n$ entier, la fonction $y(t-T)$ est la solution obtenue dans l'intervalle précédent. Pour $n=0$, on suppose que $y(t-T)=0$. On s'intéresse par ailleurs à la réponse indicielle, avec $u(t)=1$ pour $t \geq 0$.

La résolution numérique est effectuée pour le gain $K$ faisant passer le lieu de Nyquist par le point critique $-1$.

<img width="556" height="413" alt="image" src="https://github.com/user-attachments/assets/b20fb4d2-e8c3-4f58-a238-396f995ced38" />

## Conclusion de l'essai en réponse indicielle

Pour un lieu de Nyquist passant par le point critique $-1$, on retrouve bien une solution $y(t)$ qui oscille indéfiniment.

## Approximation de Pade

La fonction de transfert $\exp(-Tp)$ du retard pur peut être approximée par une fonction de transfert $R(p)$ qui est une fraction rationnelle. On retrouve ainsi un système linéaire invariant sans retard, dont l'étude de la stabilité peut reprendre les outils classiques.

<img width="597" height="459" alt="image" src="https://github.com/user-attachments/assets/ffa9c247-dd62-4e2a-ab1c-37b52bcdb422" />

<img width="597" height="459" alt="image" src="https://github.com/user-attachments/assets/6d9a72e5-8ded-466c-891f-87d0f7ee38b5" />

## Le notebook

Il est proposé [ici](retard_pur.ipynb)

Sur Google Colaboratory [ici](https://colab.research.google.com/drive/1w7wsGE231QJTqFdW24FGKDz9liDjbkAs?usp=sharing)
