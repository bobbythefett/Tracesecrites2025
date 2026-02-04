---
title: Traces écrites Sec07
course:
  classe: Sec07
  chapitre: CHAPITRE 6 -- Généralités sur les fonctions
lieu: Lycée Alphonse Daudet
revision: 3 février 2026
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

**26 janvier 2026**

# Notion de fonction et vocabulaire

## Définition

::: definition
Une **fonction** $f$ est un processus (une "machine") qui, à tout nombre réel $x$ d'un ensemble de départ $\mathcal{D}$, associe un **unique** nombre réel noté $f(x)$.

* L'ensemble $\mathcal{D}$ est appelé **ensemble de définition** de la fonction $f$.
* Le nombre $x$ est la **variable**.
* Le nombre $f(x)$ est l'**image** de $x$ par $f$.
* Si $y = f(x)$, on dit que $x$ est un **antécédent** de $y$ par $f$.

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
:::

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

\newpage

**27 janvier 2026**

# Tableau de signes

## Lien entre Graphique et Algèbre

Avant de dresser des tableaux, il est essentiel de comprendre le lien entre la courbe représentative d'une fonction et son signe.

::: propriete
Soit $f$ une fonction définie sur un intervalle $I$ et $\mathcal{C}_f$ sa courbe représentative.

* Dire que **$f(x) > 0$** (positif) signifie que la courbe $\mathcal{C}_f$ est située **au-dessus** de l'axe des abscisses.
* Dire que **$f(x) < 0$** (négatif) signifie que la courbe $\mathcal{C}_f$ est située **en-dessous** de l'axe des abscisses.
* Dire que **$f(x) = 0$** signifie que la courbe $\mathcal{C}_f$ **coupe** l'axe des abscisses.
:::

## Signe d'une fonction affine $ax + b$

C'est la "brique élémentaire" pour construire n'importe quel tableau de signes en classe de Seconde.

::: rappel
Une fonction affine est définie par $f(x) = ax + b$ avec $a \neq 0$.
Elle est représentée par une droite. Le nombre $a$ est le **coefficient directeur**.
:::

### Cas 1 : $a > 0$ (Fonction croissante)

Si $a > 0$, la fonction est croissante. Elle part des négatifs pour aller vers les positifs.
Elle s'annule en $x = -\frac{b}{a}$.

**Représentation graphique :**
\begin{tikzpicture}
    \draw[->] (-2,0) -- (2,0) node[right] {$x$};
    \draw[->] (0,-1) -- (0,1) node[above] {$y$};
    \draw[thick, blue] (-1.5,-0.75) -- (1.5,0.75) node[right] {$a > 0$};
    \draw[dashed] (-0.5,0) -- (-0.5,0) node[below] {$-\frac{b}{a}$};
    \node[red] at (-1, -0.5) {-};
    \node[green!60!black] at (1, 0.5) {+};
\end{tikzpicture}

**Tableau de signes :**
$$
\begin{array}{|c|ccccc|}
\hline
x & -\infty & & -\frac{b}{a} & & +\infty \\
\hline
\text{Signe de } ax+b & & - & 0 & + & \\
\hline
\end{array}
$$

### Cas 2 : $a < 0$ (Fonction décroissante)

Si $a < 0$, la fonction est décroissante. Elle part des positifs pour aller vers les négatifs.

**Représentation graphique :**
\begin{tikzpicture}
    \draw[->] (-2,0) -- (2,0) node[right] {$x$};
    \draw[->] (0,-1) -- (0,1) node[above] {$y$};
    \draw[thick, red] (-1.5,0.75) -- (1.5,-0.75) node[right] {$a < 0$};
    \draw[dashed] (0.5,0) -- (0.5,0) node[below] {$-\frac{b}{a}$};
    \node[green!60!black] at (-1, 0.5) {+};
    \node[red] at (1, -0.5) {-};
\end{tikzpicture}

**Tableau de signes :**
$$
\begin{array}{|c|ccccc|}
\hline
x & -\infty & & -\frac{b}{a} & & +\infty \\
\hline
\text{Signe de } ax+b & & + & 0 & - & \\
\hline
\end{array}
$$

::: methode
**Moyen mnémotechnique (Règle du signe de $a$) :**  
Dans le tableau de signes d'une fonction affine $ax+b$, on met toujours le **signe de $a$ à droite** du zéro.
:::

# Tableau de signes

## Le Tableau de Signes -- Produit

Pour étudier le signe d'une expression plus complexe, comme un produit de facteurs $(ax+b)(cx+d)$, on utilise la règle des signes (« moins par moins donne plus », etc.) résumée dans un tableau général.

::: methode
**Protocole de résolution :**
Pour résoudre une inéquation du type $(2x - 4)(3 - x) \geqslant 0$ :

1.  **Racines :** Trouver les valeurs qui annulent chaque facteur.
    * $2x - 4 = 0 \iff 2x = 4 \iff x = 2$
    * $3 - x = 0 \iff -x = -3 \iff x = 3$
2.  **Tableau :** Construire un tableau avec une ligne pour $x$ et une ligne pour chaque facteur.
3.  **Ordre :** Placer les valeurs de $x$ trouvées sur la première ligne **dans l'ordre croissant**.
4.  **Signes :** Remplir les signes de chaque facteur (règle du signe de $a$).
5.  **Bilan :** Faire le produit des signes pour la dernière ligne.
6.  **Conclusion :** Lire l'ensemble des solutions $S$ correspondant à l'inégalité demandée.
:::

::: exemple
**Exemple résolu :** Étudier le signe de $P(x) = (2x - 4)(3 - x)$.

* Facteur 1 : $2x-4$. Ici $a=2$ (positif). Donc $+$ à droite du 0. S'annule en 2.
* Facteur 2 : $3-x$. Ici $a=-1$ (négatif). Donc $-$ à droite du 0. S'annule en 3.

**Tableau de signes :**

$$
\begin{array}{|c|ccccccc|}
\hline
x & -\infty & & 2 & & 3 & & +\infty \\
\hline
\text{Signe de } 2x-4 & & - & 0 & + & | & + & \\
\hline
\text{Signe de } 3-x & & + & | & + & 0 & - & \\
\hline
\text{Signe de } P(x) & & - & 0 & + & 0 & - & \\
\hline
\end{array}
$$

*Si on cherchait à résoudre $(2x - 4)(3 - x) \geqslant 0$, la solution serait $S = [2 ; 3]$.*
:::

## Le Tableau de Signes -- Quotient

La méthode est identique, à une exception près : **la valeur interdite**.

::: definition
Un quotient $\dfrac{A(x)}{B(x)}$ n'existe pas si son dénominateur $B(x)$ est nul.
Dans le tableau de signes, on indique cette **valeur interdite** par une **double barre** $||$ sur la ligne de résultat.
:::

::: exemple
**Exemple résolu :** Résoudre $\dfrac{x+1}{2x-6} \leqslant 0$.

1.  **Valeur interdite (Dénominateur) :** $2x - 6 = 0 \iff 2x = 6 \iff x = 3$.
2.  **Numérateur :** $x + 1 = 0 \iff x = -1$.
3.  **Tableau :**
    * $x+1$ : $a=1 (>0)$, s'annule en $-1$.
    * $2x-6$ : $a=2 (>0)$, s'annule en $3$.

$$
\begin{array}{|c|ccccccc|}
\hline
x & -\infty & & -1 & & 3 & & +\infty \\
\hline
x+1 & & - & 0 & + & | & + & \\
\hline
2x-6 & & - & | & - & 0 & + & \\
\hline
\text{Quotient } Q(x) & & + & 0 & - & || & + & \\
\hline
\end{array}
$$

**Conclusion :**
On cherche où le quotient est négatif ou nul ($\leqslant 0$). On regarde la ligne "Bilan".
C'est le cas entre $-1$ et $3$.
* En $-1$, c'est égal à 0 (autorisé par $\leqslant$), on ferme le crochet.
* En $3$, c'est une valeur interdite (double barre), on ouvre **toujours** le crochet.

$$S = [-1 ; 3[$$
:::

\newpage

**2 février 2026**

# Variations de fonctions

::: definition
Soit $f$ une fonction définie sur un intervalle $I$. Soient $a$ et $b$ deux réels de $I$.

* **Croissante :** $f$ est croissante sur $I$ si elle conserve l'ordre.
    $$Si \quad a \leqslant b \quad \text{alors} \quad f(a) \leqslant f(b)$$
    *(La courbe "monte" quand on la parcourt de la gauche vers la droite)*.

* **Décroissante :** $f$ est décroissante sur $I$ si elle inverse l'ordre.
    $$Si \quad a \leqslant b \quad \text{alors} \quad f(a) \geqslant f(b)$$
    *(La courbe "descend")*.

\begin{center}
\begin{tikzpicture}[scale=1.5]
    % --- Graphique Croissant ---
    \begin{scope}[xshift=0cm]
        \draw[->] (-0.5,0) -- (3,0) node[right] {$x$};
        \draw[->] (0,-0.5) -- (0,3) node[above] {$y$};
        \draw[blue, very thick, domain=0.2:2.8] plot (\x, {0.3*\x*\x + 0.5});
        \node[blue] at (1.5, 3.6) {\textbf{Fonction Croissante}};
        \node[below] at (1.5, -0.5) {Si $x$ augmente, $f(x)$ augmente};
        
        % Points a et b
        \draw[dashed] (1,0) node[below]{$a$} -- (1,0.8);
        \draw[dashed] (2,0) node[below]{$b$} -- (2,1.7);
    \end{scope}

    % --- Graphique Décroissant ---
    \begin{scope}[xshift=6cm]
        \draw[->] (-0.5,0) -- (3,0) node[right] {$x$};
        \draw[->] (0,-0.5) -- (0,3) node[above] {$y$};
        \draw[red, very thick, domain=0.2:2.8] plot (\x, {-0.3*\x*\x + 2.8});
        \node[red] at (1.5, 3.6) {\textbf{Fonction Décroissante}};
        \node[below] at (1.5, -0.5) {Si $x$ augmente, $f(x)$ diminue};

        % Points a et b
        \draw[dashed] (1,0) node[below]{$a$} -- (1,2.5);
        \draw[dashed] (2,0) node[below]{$b$} -- (2,1.6);
    \end{scope}
\end{tikzpicture}
\end{center}
:::

## Étudier le sens de variation -- La méthode de la différence

Pour savoir comment une fonction $f$ évolue sur un intervalle $I$, on ne peut pas se contenter de regarder sa courbe (ce n'est pas une preuve). Il faut comparer les images de deux nombres quelconques.

::: definition
**Rappel des définitions :**  
Soient $a$ et $b$ deux nombres réels de l'intervalle $I$ tels que **$a < b$**.

* Si **$f(a) \leqslant f(b)$** (l'ordre est conservé), la fonction est **croissante**.
* Si **$f(a) \geqslant f(b)$** (l'ordre est inversé), la fonction est **décroissante**.
:::

Pour comparer $f(a)$ et $f(b)$ sans connaître leurs valeurs, la méthode la plus sûre est d'étudier le **signe de leur différence**.

::: propriete
**Critère de la différence :**
On calcule $f(b) - f(a)$.

1.  Si **$f(b) - f(a) > 0$**, cela signifie que $f(b) > f(a)$.  
    $\implies$ La fonction a "monté", elle est **croissante**.
    
2.  Si **$f(b) - f(a) < 0$**, cela signifie que $f(b) < f(a)$.  
    $\implies$ La fonction a "descendu", elle est **décroissante**.
:::

**La Méthode pas à pas :**

Pour étudier les variations d'une fonction $f$ sur un intervalle $I$ :

::: methode
1.  **Initialisation :** On choisit deux nombres quelconques $a$ et $b$ dans l'intervalle $I$ et on pose l'hypothèse de départ : **$a < b$**.
2.  **Calcul :** On écrit la différence $f(b) - f(a)$.
3.  **Transformation :** On développe, réduit et surtout **factorise** l'expression obtenue pour faire apparaître le terme $(b-a)$.
4.  **Étude du signe :**
    * On sait que $(b-a) > 0$ (car on a choisi $a < b$).
    * On étudie le signe du reste de l'expression en utilisant le fait que $a$ et $b$ sont dans $I$.
5.  **Conclusion :** On applique la règle des signes pour trouver si le résultat est positif ou négatif, et on conclut sur les variations.
:::

::: exemple
**Exemple d'application détaillé**

Soit $f$ la fonction définie sur $\mathbb{R}$ par $f(x) = 2x^2 + 3$.
Démontrons que $f$ est **strictement croissante** sur l'intervalle $[0 ; +\infty[$.

**Étape 1 : Initialisation**

Soient $a$ et $b$ deux nombres réels de l'intervalle $[0 ; +\infty[$ tels que $0 \leqslant a < b$.

**Étape 2 : Calcul de la différence**
$$f(b) - f(a) = (2b^2 + 3) - (2a^2 + 3)$$
$$f(b) - f(a) = 2b^2 + 3 - 2a^2 - 3$$
$$f(b) - f(a) = 2b^2 - 2a^2$$

**Étape 3 : Factorisation**

On met 2 en facteur :
$$f(b) - f(a) = 2(b^2 - a^2)$$
On reconnaît l'identité remarquable $b^2 - a^2 = (b-a)(b+a)$ :
$$f(b) - f(a) = 2(b - a)(b + a)$$

**Étape 4 : Étude du signe**

On regarde le signe de chaque morceau du produit :

* **$2$** est positif.
* **$(b - a)$** est strictement positif (car on a supposé $a < b$).
* **$(b + a)$** est strictement positif (car $a$ et $b$ sont dans $[0 ; +\infty[$ et ne sont pas tous les deux nuls).

**Étape 5 : Conclusion**

Le produit de nombres positifs est positif.  
Donc : $f(b) - f(a) > 0$.  
Cela revient à dire que $f(b) > f(a)$.

L'ordre est conservé ($a < b \implies f(a) < f(b)$).  
**La fonction $f$ est donc strictement croissante sur $[0 ; +\infty[$.**
:::

## Tableau de variations

On résume les variations d'une fonction dans un tableau. Les flèches indiquent la croissance ou la décroissance.

\begin{center}
\begin{tikzpicture}
    \tkzTabInit[lgt=3, espcl=4]{$x$ / 1, $f$ / 2}
    {$-6$, $-2$, $3$, $10$}
    \tkzTabVar{-/ $-2$, +/ $5$, -/ $-3$, +/ $4$}
\end{tikzpicture}
\end{center}

*Lecture du tableau :*

* La fonction est définie sur $[-6 ; 10]$.
* La fonction est croissante sur $[-6 ; -2]$ et sur $[3 ; 10]$.
* La fonction est décroissante sur $[-2 ; 3]$.
* Le **maximum** est $5$ (atteint en $x=-2$).
* Le **minimum** est $-3$ (atteint en $x=3$).

\newpage

**3 février 2026**

# Résolution graphique d'équations et inéquations

Soit $f$ une fonction définie sur un intervalle et $\mathcal{C}_f$ sa courbe.

## Équations $f(x) = k$

::: methode
Les solutions de l'équation $f(x) = k$ sont les **abscisses** des points d'intersection de la courbe $\mathcal{C}_f$ avec la droite horizontale d'équation $y = k$.
:::

## Inéquations $f(x) < k$ (ou $f(x) > k$)

::: methode
* Les solutions de $f(x) < k$ sont les abscisses des points de la courbe situés **au-dessous** de la droite $y = k$.
* Les solutions de $f(x) > k$ sont les abscisses des points de la courbe situés **au-dessus** de la droite $y = k$.
:::

\begin{center}
\begin{tikzpicture}[scale=1.3]
    % Grille et Axes
    \draw[gray!20, very thin] (-3,-2) grid (4,3);
    \draw[->, thick] (-3,0) -- (4,0) node[right] {$x$};
    \draw[->, thick] (0,-2) -- (0,3) node[above] {$y$};
    \node[below left] at (0,0) {$O$};

    % Courbe Cf
    \draw[blue, very thick, smooth, domain=-2.5:3.885] plot (\x, {0.2*(\x+2)*(\x-1)*(\x-3)});
    \node[blue, above] at (3, 1.5) {$\mathcal{C}_f$};

    % Droite y = k
    \draw[red, thick] (-3, .5) -- (4, .5) node[right] {$y=k$};

    % Points d'intersection
    % On suppose ici approximativement x1 = -1.8, x2 = 0.6, x3 = 3.2 pour l'illustration
    \coordinate (A) at (-1.8, .5);
    \coordinate (B) at (0.6, .5);
    \coordinate (C) at (3.2, .5);

    % Projections sur l'axe des abscisses (Solutions de l'équation)
    \draw[dashed, thick, black] (A) -- (-1.8, 0) node[below] {$x_1$};
    \draw[dashed, thick, black] (B) -- (0.6, 0) node[below] {$x_2$};
    \draw[dashed, thick, black] (C) -- (3.2, 0) node[below] {$x_3$};

    \fill[black] (A) circle (2pt);
    \fill[black] (B) circle (2pt);
    \fill[black] (C) circle (2pt);

    % Zone solution de l'inéquation f(x) >= k
    % La courbe est au-dessus entre x1 et x2, et après x3
    \draw[green!60!black, line width=2pt] (-1.8, 0) -- (0.6, 0);
    \draw[green!60!black, line width=2pt] (3.2, 0) -- (4, 0);
    
    % Crochets pour l'intervalle
    \node[green!60!black] at (-1.8, 0) {\large $[$};
    \node[green!60!black] at (0.6, 0) {\large $]$};
    \node[green!60!black] at (3.2, 0) {\large $[$};

    % Légende
    \node[anchor=north west, fill=white, draw=black, thin] at (5, 1) {
        \scriptsize
        \begin{tabular}{l}
        \textbf{Équation} $f(x)=k$ : \\
        Solutions : $\{x_1 ; x_2 ; x_3\}$ \\
        \\
        \textbf{Inéquation} $f(x) \geqslant k$ : \\
        \textcolor{green!60!black}{\textbf{---}} Solutions : $S = [x_1 ; x_2] \cup [x_3 ; +\infty[$
        \end{tabular}
    };

\end{tikzpicture}
\end{center}

## Équations $f(x) = g(x)$

::: methode
Les solutions sont les abscisses des points d'intersection des deux courbes $\mathcal{C}_f$ et $\mathcal{C}_g$.
:::

## Inéquations $f(x) < g(x)$ (ou $f(x) > g(x)$)

::: methode
* Les solutions de $f(x) < g(x)$ sont les abscisses des points de la courbe représentative de $f$ situés **au-dessous** de celle de $g$.
* Les solutions de $f(x) > k$ sont les abscisses des points de la courbe représentative de $f$ situés **au-dessus** de celle de $g$.
:::

\begin{center}
\begin{tikzpicture}[scale=1.3]
    % Grille et Axes
    \draw[gray!20, very thin] (-3,-1) grid (4,4);
    \draw[->, thick] (-3,0) -- (4,0) node[right] {$x$};
    \draw[->, thick] (0,-1) -- (0,4) node[above] {$y$};
    \node[below left] at (0,0) {$O$};

    % Courbe f (Parabole tournée vers le bas)
    \draw[blue, very thick, smooth, domain=-2.5:2.5] plot (\x, {3 - 0.5*\x*\x});
    \node[blue, right] at (1, 3) {$\mathcal{C}_f$};

    % Courbe g (Droite affine)
    \draw[red, very thick, domain=-2.5:3.5] plot (\x, {0.5*\x + 1});
    \node[red, below right] at (3, 2.5) {$\mathcal{C}_g$};

    % Points d'intersection (Solutions de f(x) = g(x))
    % 3 - 0.5x^2 = 0.5x + 1 => 0.5x^2 + 0.5x - 2 = 0 => x^2 + x - 4 = 0
    % Delta = 17. x approx -2.56 et 1.56. 
    % Pour le dessin, on place les points visuellement aux intersections
    \coordinate (I1) at (-2.56, -0.28);
    \coordinate (I2) at (1.56, 1.78);

    \fill[black] (I1) circle (2pt);
    \fill[black] (I2) circle (2pt);

    % Projections
    \draw[dashed, thick, black] (I1) -- (-2.56, 0) node[above] {$x_1$};
    \draw[dashed, thick, black] (I2) -- (1.56, 0) node[below] {$x_2$};

    % Zone solution f(x) > g(x) (f au-dessus de g)
    \draw[green!60!black, line width=2pt] (-2.56, 0) -- (1.56, 0);
    \node[green!60!black] at (-2.56, 0) {\large $]$};
    \node[green!60!black] at (1.56, 0) {\large $[$};

    % Légende
    \node[anchor=south west, fill=white, draw=black, thin] at (5, 1) {
        \scriptsize
        \begin{tabular}{l}
        \textbf{Intersection} $f(x)=g(x)$ : \\
        Solutions : $\{x_1 ; x_2\}$ \\
        \\
        \textbf{Position relative} $f(x) \geqslant g(x)$ : \\
        (\textcolor{blue}{$C_f$} au-dessus de \textcolor{red}{$C_g$}) \\
        \textcolor{green!60!black}{\textbf{---}} Solutions : $S = [x_1 ; x_2]$
        \end{tabular}
    };
\end{tikzpicture}
\end{center}

