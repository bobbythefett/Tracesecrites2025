---
title: Traces écrites Sec07
course:
  classe: Sec07
  chapitre: CHAPITRE 6 -- Généralités sur les fonctions
lieu: Lycée Alphonse Daudet
revision: 29 janvier 2026
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

**29 janvier 2026**


