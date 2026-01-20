---
title: Traces écrites 1G Math TC
course:
  classe: 1G
  chapitre: Janvier 2026
lieu: Lycée Alphonse Daudet
revision: 7 janvier 2026
preambule: 
type: 
  eval: false
  bac: false
answers: false # set to true to show answers
bac:
  annee: 
  date: 
  dernierepage: 
---

**7 janvier 2026 : H1**

**CHAPITRE : Fonctions affines**

# Définition et Vocabulaire

::: definition
Une fonction $f$ définie sur $\mathbb{R}$ est une **fonction affine** s'il existe deux nombres réels $a$ et $b$ tels que pour tout réel $x$ :
$$f(x) = ax + b$$

* Le nombre $a$ est le **coefficient directeur** (ou taux d'accroissement). Il dirige la pente de la droite.
* Le nombre $b$ est l'**ordonnée à l'origine** (valeur initiale à $x=0$).
:::

::: exemple
* $f(x) = 2x - 3$ est affine ($a=2, b=-3$).
* $g(x) = -x + 5$ est affine ($a=-1, b=5$).
* $h(x) = 4$ est affine constante ($a=0, b=4$).
* $k(x) = 3x$ est affine **linéaire** ($a=3, b=0$).
:::

**7 janvier 2026 : H2**

# Représentation graphique

La représentation graphique d'une fonction affine est une **droite**.

* L'ordonnée à l'origine $b$ est l'endroit où la droite coupe l'axe vertical (axe des ordonnées).
* Le coefficient directeur $a$ indique "de combien on monte (ou descend) quand on avance de 1 unité vers la droite".

\begin{center}
\begin{tikzpicture}
    \draw[->] (-1,0) -- (4,0) node[right] {$x$};
    \draw[->] (0,-1) -- (0,4) node[above] {$y$};
    \draw[dashed, gray] (0,0) grid (4,4);
    
    % Droite y = 0.5x + 1
    \draw[thick, blue] (-1, 0.5) -- (4, 3) node[right] {$f(x)=0,5x+1$};
    
    % Illustration de b
    \fill[red] (0,1) circle (2pt) node[left] {$b=1$};
    
    % Illustration de a
    \draw[->, red, thick] (2,2) -- (3,2) node[midway, below] {+1};
    \draw[->, red, thick] (3,2) -- (3,2.5) node[midway, right] {$a=0,5$};
\end{tikzpicture}
\end{center}

# Sens de variation

Le sens de variation d'une fonction affine dépend uniquement du signe de $a$.

::: propriete
Soit $f(x) = ax + b$.

* Si $a > 0$, la fonction est **strictement croissante**.
* Si $a < 0$, la fonction est **strictement décroissante**.
* Si $a = 0$, la fonction est **constante**.
:::

# Taux d'accroissement

Pour tous nombres réels distincts $x_1$ et $x_2$, le coefficient directeur $a$ se calcule par la formule :
$$a = \frac{f(x_2) - f(x_1)}{x_2 - x_1} = \frac{\Delta y}{\Delta x}$$

> **Interprétation :** Dans un modèle linéaire, la variation absolue de la grandeur est proportionnelle à la variation de la variable.

\newpage

**21 janvier 2026**

