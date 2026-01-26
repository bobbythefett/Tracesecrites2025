---
title: Traces écrites Sec07
course:
  classe: Sec07
  chapitre: Janvier 2026
lieu: Lycée Alphonse Daudet
revision: 26 janvier 2026
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

**CHAPITRE 6 : Généralités sur les fonctions**

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

