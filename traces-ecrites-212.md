---
title: Traces écrites Sec12
course:
  classe: Sec12
  chapitre: CHAPITRE 6 -- Généralités sur les fonctions
lieu: Lycée Alphonse Daudet
revision: 28 janvier 2026
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

**28 janvier 2026**

# Notion de fonction et vocabulaire

::: definition
Une **fonction** $f$ est un processus (une "machine") qui, à tout nombre réel $x$ d'un ensemble de départ $\mathcal{D}$, associe un **unique** nombre réel noté $f(x)$.
:::

::: vocabulaire
* L'ensemble $\mathcal{D}$ est appelé **ensemble de définition** de la fonction $f$.
* Le nombre $x$ est la **variable**.
* Le nombre $f(x)$ est l'**image** de $x$ par $f$.
* Si $y = f(x)$, on dit que $x$ est un **antécédent** de $y$ par $f$.
:::

\begin{center}
\begin{tikzpicture}[scale=1]
    % --- Ensemble de départ (D) ---
    % On dessine une ellipse bleue pour l'ensemble de définition
    \draw[fill=blue!5, draw=blue, thick] (0,0) ellipse (2cm and 1.8cm);
    \node[blue, font=\bfseries] at (0, 3.3) {$\mathcal{D}$}; 
    \node[blue, font=\small] at (0, 2.8) {(Ensemble de définition)};

    % --- Ensemble d'arrivée (R) ---
    % On dessine une ellipse rouge pour l'ensemble d'arrivée (les réels)
    \draw[fill=red!5, draw=red, thick] (7,0) ellipse (3cm and 2cm);
    \node[red, font=\bfseries] at (7, 3.3) {$\mathbb{R}$};
    \node[red, font=\small] at (7, 2.8) {(Ensemble des nombres réels)};

    % --- Les points (x et f(x)) ---
    
    % Le point x (variable / antécédent)
    \node (X) at (0, 0.5) {$\bullet$};
    \node[left, font=\large] at (X) {$x$};
    \node[blue!80!black, below=0.2cm, align=center, font=\small] at (0, 0.5) {\textbf{Variable}\\(ou Antécédent)};

    % Le point f(x) (image)
    \node (Y) at (7, 0.5) {$\bullet$};
    \node[right, font=\large] at (Y) {$y = f(x)$};
    \node[red!80!black, below=0.2cm, align=center, font=\small] at (7, 0.5) {\textbf{Image}\\(Unique)};

    % --- La flèche (La fonction f) ---
    % C'est le processus qui relie x à f(x)
    \draw[->, very thick, violet, >=latex] (X) to[bend left=20] node[midway, above, font=\bfseries\large, yshift=0.2cm] {$f$} (Y);
    \node[violet, font=\small] at (3.5, 2.3) {(Le processus / la machine)};

    % --- Note sur l'unicité ---
    \node[draw=gray, dashed, inner sep=5pt, font=\small, align=left] at (3.5, -3) {
        \textbf{Règle d'or :} \\
        De chaque $x$ part une \\
        \textbf{seule} flèche.
    };

\end{tikzpicture}
\end{center}

::: remarque
**Attention aux confusions fréquentes :**

* Un nombre $x$ a une **unique** image.
* Un nombre $y$ peut avoir **aucun**, **un** ou **plusieurs** antécédents.
:::

::: exemple
Soit la fonction $f$ définie sur $\mathbb{R}$ par $f(x) = x^2 - 1$.

* **Calcul de l'image de 3 :**  
    $f(3) = 3^2 - 1 = 9 - 1 = 8$.  
    L'image de 3 par $f$ est $8$.

* **Recherche des antécédents de 15 :**  
    On cherche $x$ tel que $f(x) = 15$.  
    $$x^2 - 1 = 15 \iff x^2 = 16$$
    $$x = 4 \quad \text{ou} \quad x = -4$$
    Le nombre 15 a deux antécédents : $-4$ et $4$.
:::

# Représentation graphique

## Courbe représentative

::: definition
Dans un repère $(O; I, J)$ du plan, la **courbe représentative** de la fonction $f$, notée $\mathcal{C}_f$, est l'ensemble des points $M$ de coordonnées $(x ; y)$ tels que :

1.  $x \in \mathcal{D}$ (l'abscisse est dans l'ensemble de définition).
2.  $y = f(x)$ (l'ordonnée est l'image de l'abscisse).
:::

::: center
\begin{tikzpicture}[scale=2]
    % Grille et Axes
    \draw[gray!20, step=0.5] (-.5,-.5) grid (4,3);
    \draw[->, thick] (-.5,0) -- (4.2,0) node[right] {$x$};
    \draw[->, thick] (0,-.5) -- (0,3.2) node[above] {$y$};
    
    % Courbe
    \draw[blue, thick, smooth, samples=100, domain=-0.5:3.62] plot (\x, {0.2*(\x+1)*(\x-3)*(\x-1) + 1.5});
    \node[blue, above] at (3.75, 2.5) {$\mathcal{C}_f$};

    % Lecture de l'image de a
    \def\a{2.5}
    \def\fa{0.975}
    
    \draw[dashed, red, thick] (\a, 0) -- (\a, \fa);
    \draw (\a, 0) node[red, below] {$x$};
    \draw[dashed, red, thick] (\a, \fa) -- (0, \fa) node[left] {$f(x)$};
    \fill[red] (\a, \fa) circle (2pt);
    \node[red, below right] at (\a, \fa) {$M(x; f(x))$};
\end{tikzpicture}
:::


::: methode
**Savoir si un point appartient à la courbe**

Le point $A(x_A ; y_A)$ appartient à la courbe $\mathcal{C}_f$ si et seulement si $y_A = f(x_A)$.
:::

## Lecture graphique (Images et Antécédents)

Pour lire graphiquement, il est essentiel de connaître l'orientation des axes :

* L'axe des **abscisses** (horizontal) correspond aux **antécédents** ($x$).
* L'axe des **ordonnées** (vertical) correspond aux **images** ($f(x)$).

\begin{center}
\begin{tikzpicture}[scale=1.2]
    % Grille
    \draw[gray!20, very thin] (-1,-1) grid (5,4);
    
    % Axes
    \draw[->, thick] (-1,0) -- (5,0) node[right] {$x$ (Antécédents)};
    \draw[->, thick] (0,-1) -- (0,4) node[above] {$y=f(x)$ (Images)};
    
    % Courbe
    \draw[blue, thick, smooth, domain=0:5] plot (\x, {0.2*\x*\x - 0.5*\x + 1});
    \node[blue] at (4.5, 3.5) {$\mathcal{C}_f$};
    
    % Lecture Image
    \draw[dashed, red] (3,0) node[below] {$a$} -- (3,1.3);
    \draw[dashed, red, ->] (3,1.3) -- (0,1.3) node[left] {$f(a)$};
    \fill[red] (3,1.3) circle (2pt);
    \node[red, above] at (1.5, 3) {Lecture de l'image};

    % Lecture Antécédent
    \draw[dashed, green!60!black] (0,2.092) node[left] {$k$} -- (3.9,2.092);
    \draw[dashed, green!60!black, ->] (3.9,2.092) -- (3.9,0) node[below] {$x_1$};
    \fill[green!60!black] (3.9,2.092) circle (2pt);
    \node[green!60!black, right] at (3.9, 1) {Lecture antécédent};

\end{tikzpicture}
\end{center}

* Pour trouver l'image de $a$ : On part de $a$ sur l'axe des abscisses, on monte vers la courbe, puis on lit la valeur sur l'axe des ordonnées.
* Pour trouver les antécédents de $k$ : On trace la droite horizontale $y=k$, on repère les points d'intersection avec la courbe, et on lit leurs abscisses.

\newpage

**29 janvier 2026**


