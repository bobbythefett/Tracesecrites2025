---
title: Traces écrites Sec07
course:
  classe: Sec07
  chapitre: Repérage
lieu: Lycée Alphonse Daudet
revision: 6 janvier 2026
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

**5 janvier 2026**

# Notion de Repère

Pour se repérer dans le plan, on utilise trois points non alignés $O$, $I$ et $J$ qui forment un **repère**, noté $(O ; I, J)$.

::: definition
* **L'origine** est le point $O$.
* **L'axe des abscisses** est la droite $(OI)$ (axe horizontal).
* **L'axe des ordonnées** est la droite $(OJ)$ (axe vertical).
* La distance $OI$ donne l'unité sur l'axe des abscisses.
* La distance $OJ$ donne l'unité sur l'axe des ordonnées.
:::

## Les différents types de repères

Il est crucial de savoir distinguer les types de repères car certaines formules (comme la distance) ne fonctionnent que dans un cas précis.

\begin{center}
\renewcommand{\arraystretch}{1.5}
\begin{tabular}{|c|p{8cm}|}
\hline
\textbf{Type de Repère} & \textbf{Caractéristique} \\
\hline
\textbf{Quelconque} & Les droites $(OI)$ et $(OJ)$ sont sécantes, les unités sont quelconques. \\
\hline
\textbf{Orthogonal} & Les droites $(OI)$ et $(OJ)$ sont \textbf{perpendiculaires}. \\
\hline
\textbf{Orthonormé} & Les droites $(OI)$ et $(OJ)$ sont \textbf{perpendiculaires} ET les unités sont égales ($OI = OJ = 1$). \\
\hline
\end{tabular}
\end{center}

::: center
\begin{tikzpicture}[scale=0.8]

    % --- 1. Repère QUELCONQUE ---
    \begin{scope}[xshift=-5cm]
        \draw[thick, ->] (-1,0) -- (3,0) node[right] {$x$};
        \draw[thick, ->] (-.6,-1) -- (1.5,2.5) node[above] {$y$}; % Axe penché
        \draw (0,0) node[above left] {$O$};
        
        % Unité I (Rouge)
        \draw[red, very thick] (0,0) -- (1,0);
        \draw[red] (1, -0.1) -- (1, 0.1) node[below=0.2cm] {$I$};
        
        % Unité J (Bleu) - Plus longue pour l'exemple
        \draw[blue, very thick] (0,0) -- (0.6,1); 
        \draw[blue] (0.5, 1) -- (0.7, 1) node[left=0.1cm] {$J$};
        
        \node[below, font=\bfseries] at (1,-1.5) {1. Quelconque};
        \node[below, align=center, scale=0.8] at (1,-2) {$(OI)$ et $(OJ)$ sécantes \\ $OI \neq OJ$};
    \end{scope}

    % --- 2. Repère ORTHOGONAL ---
    \begin{scope}[xshift=0cm]
        \draw[thick, ->] (-1,0) -- (3,0) node[right] {$x$};
        \draw[thick, ->] (0,-1) -- (0,2.4) node[above] {$y$};
        \draw (0,0) node[below left] {$O$};
        
        % Angle droit
        \draw (0,0.3) -- (0.3,0.3) -- (0.3,0);
        
        % Unité I (Rouge) - Longue
        \draw[red, very thick] (0,0) -- (1.5,0);
        \draw[red] (1.5, -0.1) -- (1.5, 0.1) node[below=0.2cm] {$I$};
        
        % Unité J (Bleu) - Courte
        \draw[blue, very thick] (0,0) -- (0,0.8);
        \draw[blue] (-0.1, 0.8) -- (0.1, 0.8) node[left=0.1cm] {$J$};
        
        \node[below, font=\bfseries] at (1,-1.5) {2. Orthogonal};
        \node[below, align=center, scale=0.8] at (1,-2) {$(OI) \perp (OJ)$ \\ $OI \neq OJ$};
    \end{scope}

    % --- 3. Repère ORTHONORMÉ ---
    \begin{scope}[xshift=5cm]
        \draw[thick, ->] (-1,0) -- (3,0) node[right] {$x$};
        \draw[thick, ->] (0,-1) -- (0,2.4) node[above] {$y$};
        \draw (0,0) node[below left] {$O$};
        
        % Angle droit
        \draw (0,0.3) -- (0.3,0.3) -- (0.3,0);
        
        % Unité I (Rouge)
        \draw[red, very thick] (0,0) -- (1,0);
        \draw[red] (1, -0.1) -- (1, 0.1) node[below=0.2cm] {$I$};
        \node[red] at (0.5, 0) {||}; % Marque égalité
        
        % Unité J (Bleu) - Même longueur
        \draw[blue, very thick] (0,0) -- (0,1);
        \draw[blue] (-0.1, 1) -- (0.1, 1) node[left=0.1cm] {$J$};
        \node[blue] at (0, 0.5) {=}; % Marque égalité
        
        \node[below, font=\bfseries] at (1,-1.5) {3. Orthonormé};
        \node[below, align=center, scale=0.8] at (1,-2) {$(OI) \perp (OJ)$ \\ $OI = OJ$};
    \end{scope}

\end{tikzpicture}
:::

::: remarque
Sauf mention contraire, on travaille généralement dans un **repère orthonormé** pour simplifier les calculs de distances.
:::

# Coordonnées d'un point

::: definition
Dans un repère $(O ; I, J)$, tout point $M$ est repéré par un unique couple de nombres réels $(x_M ; y_M)$.

* $x_M$ est l'**abscisse** de $M$.
* $y_M$ est l'**ordonnée** de $M$.

On note le point : $M(x_M ; y_M)$.
:::

::: exemple
Sur la figure ci-dessous :

* Le point $A$ a pour abscisse $2$ et pour ordonnée $3$. On note $A(2 ; 3)$.
* Le point $B$ a pour abscisse $-1$ et pour ordonnée $-2$. On note $B(-1 ; -2)$.

\begin{center}
\begin{tikzpicture}[scale=0.8]
    % Grille
    \draw[help lines, color=gray!30, dashed] (-3,-3) grid (4,4);
    % Axes
    \draw[->, thick] (-3,0)--(4,0) node[right]{$x$};
    \draw[->, thick] (0,-3)--(0,4) node[above]{$y$};
    % Origine et unités
    \draw (0,0) node[below left]{$O$};
    \draw [thick] (1,-0.1)--(1,0.1) node[below=0.2cm]{$I$};
    \draw [thick] (-0.1,1)--(0.1,1) node[left=0.1cm]{$J$};
    
    % Point A
    \fill [red] (2,3) circle (2pt) node[above right]{$A$};
    \draw [dashed, red] (2,0) -- (2,3) -- (0,3);
    \node [red, below] at (2,0) {$2$};
    \node [red, left] at (0,3) {$3$};

    % Point B
    \fill [blue] (-1,-2) circle (2pt) node[below left]{$B$};
    \draw [dashed, blue] (-1,0) -- (-1,-2) -- (0,-2);
    \node [blue, above] at (-1,0) {$-1$};
    \node [blue, right] at (0,-2) {$-2$};
\end{tikzpicture}
\end{center}
:::

\newpage

**6 janvier**

# Coordonnées du milieu d'un segment

Cette formule est valable dans **tous** les types de repères.

::: propriete
Soient deux points $A(x_A ; y_A)$ et $B(x_B ; y_B)$.
Les coordonnées du milieu $K$ du segment $[AB]$ sont :

$$x_K = \frac{x_A + x_B}{2} \quad \text{et} \quad y_K = \frac{y_A + y_B}{2}$$

*Moyen mnémotechnique : C'est la "moyenne" des coordonnées.*
:::

::: exemple
Soit $A(2 ; 4)$ et $B(-4 ; 6)$.
Calculons les coordonnées de $K$, milieu de $[AB]$ :

$$x_K = \frac{2 + (-4)}{2} = \frac{-2}{2} = -1$$
$$y_K = \frac{4 + 6}{2} = \frac{10}{2} = 5$$

Le milieu est $K(-1 ; 5)$.
:::

# Distance entre deux points

::: remarque
La propriété suivante n'est valable que dans un **repère ORTHONORMÉ**.
:::

::: propriete
Dans un repère orthonormé, la distance entre deux points $A(x_A ; y_A)$ et $B(x_B ; y_B)$ est donnée par la formule :

$$AB = \sqrt{(x_B - x_A)^2 + (y_B - y_A)^2}$$
:::

\begin{center}
\begin{tikzpicture}[scale=1.2]
    % --- 1. Les Axes ---
    % Grille légère pour aider à la lecture (optionnel)
    \draw[help lines, color=gray!20] (-1,-1) grid (5,4);
    
    % Axes X et Y
    \draw[->, thick] (-1,0) -- (5,0) node[right] {$x$};
    \draw[->, thick] (0,-1) -- (0,4) node[above] {$y$};
    \node[below left] at (0,0) {$O$};
    
    % Unités I et J (pour rappeler le repère orthonormé)
    \draw[thick] (1, -0.1) -- (1, 0.1) node[below=0.2cm] {$I$};
    \draw[thick] (-0.1, 1) -- (0.1, 1) node[left=0.1cm] {$J$};

    % --- 2. Définition des points ---
    % On choisit des coordonnées génériques mais positives pour la clarté
    \coordinate (A) at (1, 1.5);
    \coordinate (B) at (4, 3.5);
    % Point H pour former le triangle rectangle (xB, yA)
    \coordinate (H) at (4, 1.5);

    % --- 3. Projections (Pointillés) ---
    % Projections de A
    \draw[dashed, color=gray] (A) -- (1,0) node[below] {$x_A$};
    \draw[dashed, color=gray] (A) -- (0,1.5) node[left] {$y_A$};
    
    % Projections de B
    \draw[dashed, color=gray] (B) -- (4,0) node[below] {$x_B$};
    \draw[dashed, color=gray] (B) -- (0,3.5) node[left] {$y_B$};

    % --- 4. Le Triangle Rectangle (Pythagore) ---
    % Côté horizontal (différence des x) en BLEU
    \draw[thick, blue] (A) -- (H) node[midway, below] {\footnotesize $x_B - x_A$};
    
    % Côté vertical (différence des y) en ROUGE
    \draw[thick, red] (H) -- (B) node[midway, right] {\footnotesize $y_B - y_A$};
    
    % Hypoténuse (Distance AB) en NOIR
    \draw[very thick] (A) -- (B) node[midway, above left, rotate=33] {$d$};

    % --- 5. Finitions ---
    % Points
    \fill (A) circle (1.5pt) node[below left] {$A$};
    \fill (B) circle (1.5pt) node[above right] {$B$};
    
    % Angle Droit en H
    \draw (3.8, 1.5) -- (3.8, 1.7) -- (4, 1.7);
    \node[below right, gray, scale=0.8] at (H) {$H$};
\end{tikzpicture}
\end{center}

::: demo
*(Esquisse)* Cette formule découle directement du **Théorème de Pythagore**. En traçant un triangle rectangle dont l'hypoténuse est $[AB]$, les côtés de l'angle droit mesurent $|x_B - x_A|$ et $|y_B - y_A|$.
:::

::: exemple
Soit $A(1 ; 2)$ et $B(4 ; -2)$. Calculons la longueur $AB$.

1.  On calcule la différence des abscisses : $x_B - x_A = 4 - 1 = 3$.
2.  On calcule la différence des ordonnées : $y_B - y_A = -2 - 2 = -4$.
3.  On applique la formule :
    $$AB = \sqrt{3^2 + (-4)^2}$$
    $$AB = \sqrt{9 + 16}$$
    $$AB = \sqrt{25}$$
    $$AB = 5$$
:::


