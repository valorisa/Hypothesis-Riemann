# L’hypothèse de Riemann : comprendre la fonction zêta et les nombres premiers

![Statut](https://img.shields.io/badge/statut-problème%20ouvert-orange)
![Langue](https://img.shields.io/badge/langue-fran%C3%A7ais-blue)

## Présentation

L’hypothèse de Riemann est l’un des grands problèmes ouverts des mathématiques. Elle porte sur les zéros non triviaux de la **fonction zêta de Riemann** et affirme que leur partie réelle est toujours égale à $1/2$.

Pourquoi cette propriété intéresse-t-elle autant les mathématiciens ? Parce que la fonction zêta est profondément liée aux nombres premiers. La position de ses zéros permet de comprendre et de contrôler les fluctuations dans leur répartition.

Ce document présente progressivement les notions nécessaires pour comprendre l’énoncé :

1. les nombres premiers et leur répartition ;
2. le théorème des nombres premiers ;
3. la fonction zêta de Riemann ;
4. le produit d’Euler et le lien avec les nombres premiers ;
5. les nombres complexes et la variable $s$ ;
6. les zéros triviaux et non triviaux ;
7. la bande critique, la droite critique et l’équation fonctionnelle ;
8. le rôle de l’hypothèse dans l’étude des fluctuations des nombres premiers.

---

## 1. Les nombres premiers

Un nombre premier est un entier naturel supérieur ou égal à 2 qui possède exactement deux diviseurs positifs : 1 et lui-même.

Les premiers nombres premiers sont :

$$
2,\ 3,\ 5,\ 7,\ 11,\ 13,\ 17,\ 19,\ 23,\ 29,\ldots
$$

Les écarts entre deux nombres premiers consécutifs ne sont pas constants :

| Nombres premiers consécutifs | Écart |
|---|---:|
| $2 \rightarrow 3$ | 1 |
| $3 \rightarrow 5$ | 2 |
| $5 \rightarrow 7$ | 2 |
| $7 \rightarrow 11$ | 4 |
| $11 \rightarrow 13$ | 2 |
| $13 \rightarrow 17$ | 4 |
| $17 \rightarrow 19$ | 2 |
| $19 \rightarrow 23$ | 4 |
| $23 \rightarrow 29$ | 6 |
| $29 \rightarrow 31$ | 2 |
| $31 \rightarrow 37$ | 6 |

Il n’existe donc pas de progression arithmétique simple qui donne tous les nombres premiers. Leur succession présente des irrégularités.

Cependant, à grande échelle, leur répartition suit une loi remarquable : les nombres premiers deviennent moins fréquents lorsque les entiers augmentent, mais cette raréfaction peut être décrite statistiquement.

### 1.1. La fonction de comptage des nombres premiers

On note $\pi(x)$ le nombre de nombres premiers inférieurs ou égaux à $x$ :

$$
\boxed{\pi(x)=\#\{p\leq x\mid p\text{ est premier}\}}
$$

Par exemple :

$$
\pi(10)=4
$$

car les nombres premiers inférieurs ou égaux à 10 sont 2, 3, 5 et 7.

Quelques valeurs exactes :

| $x$ | $\pi(x)$ |
|---:|---:|
| 10 | 4 |
| 100 | 25 |
| 1 000 | 168 |
| 10 000 | 1 229 |
| 100 000 | 9 592 |
| 1 000 000 | 78 498 |

La proportion de nombres premiers parmi les entiers jusqu’à $x$ diminue lorsque $x$ augmente.

---

## 2. Le théorème des nombres premiers

Le théorème des nombres premiers décrit la densité moyenne des nombres premiers. Il affirme que, lorsque $x$ tend vers l’infini, le nombre de nombres premiers inférieurs ou égaux à $x$ est équivalent à $x/\ln(x)$ :

$$
\boxed{\pi(x)\sim\frac{x}{\ln(x)}}
$$

Ici, $\ln(x)$ désigne le logarithme naturel de $x$.

Le symbole $\sim$ signifie que le quotient des deux expressions tend vers 1 :

$$
\boxed{
\lim_{x\to+\infty}
\frac{\pi(x)}{x/\ln(x)}=1
}
$$

Il s’agit d’une approximation asymptotique, et non d’une égalité exacte.

### 2.1. Exemples numériques

Pour $x=100$ :

$$
\frac{100}{\ln(100)}\approx 21{,}71
$$

alors que $\pi(100)=25$.

Pour $x=1\,000$ :

$$
\frac{1\,000}{\ln(1\,000)}\approx 144{,}76
$$

alors que $\pi(1\,000)=168$.

Pour $x=1\,000\,000$ :

$$
\frac{1\,000\,000}{\ln(1\,000\,000)}
\approx 72\,382
$$

alors que $\pi(1\,000\,000)=78\,498$.

L’approximation devient relativement meilleure à mesure que $x$ augmente.

### 2.2. Une densité locale approximative

Le théorème des nombres premiers suggère qu’un entier proche d’une grande valeur $x$ a une probabilité heuristique d’être premier de l’ordre de :

$$
\boxed{\frac{1}{\ln(x)}}
$$

Cette expression décrit une densité moyenne locale. Elle ne constitue pas une affirmation d’indépendance entre les entiers : les propriétés de divisibilité créent des dépendances arithmétiques.

---

## 3. L’intégrale logarithmique

Une approximation particulièrement précise de la fonction de comptage des nombres premiers utilise l’intégrale logarithmique, notée $\mathrm{li}(x)$.

Pour $x>2$, on peut la définir par :

$$
\boxed{
\mathrm{li}(x)=\int_2^x\frac{dt}{\ln(t)}
}
$$

Dans cette intégrale :

- $t$ est la variable d’intégration ;
- $dt$ indique que l’intégration se fait par rapport à $t$ ;
- $\ln(t)$ est le logarithme naturel de $t$ ;
- $2$ est la borne inférieure ;
- $x$ est la borne supérieure.

Par exemple :

$$
\mathrm{li}(10)
=\int_2^{10}\frac{dt}{\ln(t)}
\approx 5{,}12
$$

Or :

$$
\pi(10)=4
$$

L’intégrale logarithmique fournit donc une estimation du nombre de nombres premiers, mais elle ne donne pas leur nombre exact.

Le théorème des nombres premiers peut également s’écrire :

$$
\boxed{\pi(x)\sim\mathrm{li}(x)}
$$

Cela signifie que :

$$
\lim_{x\to+\infty}\frac{\pi(x)}{\mathrm{li}(x)}=1
$$

La différence entre ces deux fonctions sera importante pour comprendre les conséquences de l’hypothèse de Riemann.

---

## 4. La fonction zêta de Riemann

La fonction zêta de Riemann est initialement définie, pour les valeurs complexes $s$ dont la partie réelle est strictement supérieure à 1, par la série :

$$
\boxed{
\zeta(s)=\sum_{n=1}^{\infty}\frac{1}{n^s}
}
$$

Cette notation signifie que l’on additionne les termes :

$$
\zeta(s)=
1+\frac{1}{2^s}+\frac{1}{3^s}
+\frac{1}{4^s}+\cdots
$$

La lettre grecque $\zeta$ désigne la fonction. La lettre $s$ est sa variable.

### 4.1. Exemples de valeurs de $s$

La variable $s$ peut être un nombre réel ou un nombre complexe.

Un nombre complexe s’écrit :

$$
\boxed{s=a+bi}
$$

où :

- $a$ est la partie réelle de $s$ ;
- $b$ est la partie imaginaire de $s$ ;
- $i$ est l’unité imaginaire, définie par $i^2=-1$.

Exemples :

| Valeur de $s$ | Partie réelle | Partie imaginaire |
|---|---:|---:|
| $2+0i$ | 2 | 0 |
| $3+0i$ | 3 | 0 |
| $2+i$ | 2 | 1 |
| $2+3i$ | 2 | 3 |
| $1+5i$ | 1 | 5 |
| $\frac12+14i$ | 0,5 | 14 |
| $\frac12-14i$ | 0,5 | -14 |

Ainsi, $s$ n’est pas une constante : c’est une variable qui peut prendre une infinité de valeurs complexes.

On note souvent :

$$
s=\sigma+it
$$

où $\sigma=\mathrm{Re}(s)$ est la partie réelle et $t=\mathrm{Im}(s)$ la partie imaginaire.

### 4.2. Quelques exemples dans la série

Pour $s=2$ :

$$
\zeta(2)=1+\frac{1}{2^2}+\frac{1}{3^2}
+\frac{1}{4^2}+\cdots
$$

Cette série converge et sa somme est :

$$
\boxed{\zeta(2)=\frac{\pi^2}{6}}
$$

Il s’agit du résultat célèbre associé au problème de Bâle, résolu par Euler.

Pour $s=3$ :

$$
\zeta(3)=1+\frac{1}{2^3}+\frac{1}{3^3}
+\frac{1}{4^3}+\cdots
$$

Cette série converge également.

Pour $s=2+i$ :

$$
\zeta(2+i)=
1+\frac{1}{2^{2+i}}+\frac{1}{3^{2+i}}+\cdots
$$

Les termes et la somme sont alors complexes.

### 4.3. Domaine de convergence et prolongement analytique

La série définissant directement la fonction zêta converge absolument lorsque :

$$
\boxed{\mathrm{Re}(s)>1}
$$

La série ne suffit donc pas à définir directement la fonction dans toute la bande critique.

Grâce au **prolongement analytique**, on étend la fonction zêta à presque tout le plan complexe. La fonction ainsi prolongée est méromorphe et possède un pôle simple en $s=1$.

C’est cette fonction prolongée qui intervient dans l’hypothèse de Riemann.

---

## 5. Le produit d’Euler : le lien avec les nombres premiers

La fonction zêta possède une seconde expression fondamentale, découverte par Euler :

$$
\boxed{
\zeta(s)=
\prod_{p\ \mathrm{premier}}
\frac{1}{1-p^{-s}}
}
\qquad \bigl(\mathrm{Re}(s)>1\bigr)
$$

Le symbole $\prod$ désigne un produit infini. Ici, chaque facteur correspond à un nombre premier $p$.

On peut écrire les premiers facteurs :

$$
\zeta(s)=
\frac{1}{1-2^{-s}}
\times
\frac{1}{1-3^{-s}}
\times
\frac{1}{1-5^{-s}}
\times
\frac{1}{1-7^{-s}}
\times\cdots
$$

Pourquoi ce produit est-il égal à la série de départ ?

Chaque facteur peut être développé en série géométrique :

$$
\frac{1}{1-p^{-s}}
=1+p^{-s}+p^{-2s}+p^{-3s}+\cdots
$$

En multipliant les facteurs associés aux nombres premiers, on obtient les termes correspondant aux entiers naturels, grâce à leur décomposition unique en facteurs premiers.

Par exemple :

$$
12=2^2\times3
$$

Le terme correspondant à 12 apparaît en choisissant $2^{-2s}$ dans le facteur associé à 2 et $3^{-s}$ dans celui associé à 3 :

$$
2^{-2s}\times3^{-s}
=\frac{1}{12^s}
$$

Cette identité repose sur le théorème fondamental de l’arithmétique : tout entier supérieur à 1 possède une décomposition unique en facteurs premiers, à l’ordre des facteurs près.

**Conséquence essentielle :** la fonction zêta relie une somme portant sur tous les entiers positifs à un produit portant exclusivement sur les nombres premiers.

C’est ce lien qui rend la fonction zêta si importante dans l’étude de la répartition des nombres premiers.

---

## 6. Les zéros de la fonction zêta

Un zéro d’une fonction est une valeur de sa variable pour laquelle la fonction s’annule.

Pour la fonction zêta, on cherche donc les valeurs de $s$ telles que :

$$
\boxed{\zeta(s)=0}
$$

Il existe deux catégories de zéros.

### 6.1. Les zéros triviaux

Les zéros triviaux sont les entiers pairs strictement négatifs :

$$
\boxed{-2,\ -4,\ -6,\ -8,\ldots}
$$

Ils se trouvent sur l’axe réel négatif.

### 6.2. Les zéros non triviaux

Les zéros non triviaux se trouvent dans la bande critique :

$$
\boxed{0<\mathrm{Re}(s)<1}
$$

Ils sont au cœur de l’hypothèse de Riemann.

Il est important de comprendre que $s$ est un point du plan complexe. La partie réelle donne sa position horizontale et la partie imaginaire sa position verticale.

---

## 7. La bande critique et la droite critique

Le plan complexe permet de représenter les valeurs de $s$ comme des points de coordonnées :

$$
\bigl(\mathrm{Re}(s),\mathrm{Im}(s)\bigr)
$$

La bande critique est la région comprise entre les deux droites verticales :

$$
\mathrm{Re}(s)=0
\qquad\text{et}\qquad
\mathrm{Re}(s)=1
$$

Les zéros non triviaux se trouvent dans cette bande.

Au milieu de celle-ci se trouve la droite :

$$
\boxed{\mathrm{Re}(s)=\frac12}
$$

Cette droite est appelée **droite critique**.

L’hypothèse de Riemann affirme que tous les zéros non triviaux se trouvent exactement sur cette droite.

Autrement dit, chaque zéro non trivial devrait être de la forme :

$$
\boxed{s=\frac12+it}
$$

où $t$ est un nombre réel.

Attention : cela ne signifie pas que tous les zéros valent $1/2$. Leur partie imaginaire varie. C’est uniquement leur partie réelle qui devrait toujours être égale à $1/2$.

Le premier zéro non trivial situé au-dessus de l’axe réel est approximativement :

$$
\boxed{s=\frac12+14{,}134725\,i}
$$

Son conjugué est également un zéro :

$$
\boxed{s=\frac12-14{,}134725\,i}
$$

Les zéros non triviaux apparaissent ainsi par paires conjuguées.

---

## 8. L’équation fonctionnelle et la symétrie

Une fonction zêta complétée est définie par :

$$
\boxed{
\Lambda(s)=
\pi^{-s/2}
\Gamma\left(\frac{s}{2}\right)
\zeta(s)
}
$$

où $\Gamma$ est la fonction gamma, qui généralise la factorielle aux arguments complexes.

Cette fonction complétée vérifie l’équation fonctionnelle :

$$
\boxed{\Lambda(s)=\Lambda(1-s)}
$$

Cette égalité exprime une symétrie par rapport à la droite critique.

En effet, si :

$$
s=\sigma+it
$$

alors :

$$
1-s=(1-\sigma)-it
$$

La partie réelle est transformée de $\sigma$ en $1-\sigma$.

Le point fixe de cette transformation satisfait :

$$
\sigma=1-\sigma
$$

D’où :

$$
2\sigma=1
$$

et finalement :

$$
\boxed{\sigma=\frac12}
$$

La droite critique est donc l’axe de symétrie associé à cette transformation.

### 8.1. Attention à une distinction logique essentielle

La symétrie ne démontre pas l’hypothèse de Riemann.

Elle implique qu’un zéro non trivial situé d’un côté de la droite critique a un zéro correspondant de l’autre côté. Elle ne prouve pas que ces deux zéros doivent être confondus sur la droite.

L’hypothèse de Riemann affirme précisément que tous les zéros non triviaux se trouvent sur cette droite.

---

## 9. Le lien entre les zéros et la répartition des nombres premiers

Nous avons vu que le théorème des nombres premiers donne une approximation de la quantité de nombres premiers :

$$
\pi(x)\sim\frac{x}{\ln(x)}
$$

Une approximation particulièrement précise utilise l’intégrale logarithmique :

$$
\pi(x)\sim\mathrm{li}(x)
$$

avec :

$$
\mathrm{li}(x)=
\int_2^x\frac{dt}{\ln(t)}
$$

Mais cette approximation ne donne pas le nombre exact de nombres premiers.

On peut étudier l’écart :

$$
\boxed{
E(x)=\pi(x)-\mathrm{li}(x)
}
$$

Cet écart représente la différence entre le nombre réel de nombres premiers et l’estimation donnée par l’intégrale logarithmique.

L’hypothèse de Riemann est équivalente à la borne suivante :

$$
\boxed{
\pi(x)=\mathrm{li}(x)
+O\left(\sqrt{x}\ln(x)\right)
}
$$

La notation $O$ signifie ici que l’erreur est majorée, à une constante multiplicative près, par $\sqrt{x}\ln(x)$ lorsque $x$ devient grand.

L’hypothèse de Riemann permettrait donc de contrôler très précisément les fluctuations de la répartition des nombres premiers autour de leur estimation principale.

Il faut distinguer deux niveaux :

- **Le théorème des nombres premiers** décrit la tendance générale de la répartition des nombres premiers.
- **L’hypothèse de Riemann** impose une contrainte beaucoup plus forte sur l’amplitude des fluctuations autour de cette tendance.

La succession individuelle des nombres premiers reste irrégulière. L’hypothèse ne prétend pas rendre leurs écarts constants : elle concerne la précision avec laquelle leur répartition globale peut être décrite.

---

## 10. Ce qui est démontré et ce qui reste conjectural

L’hypothèse de Riemann demeure un problème ouvert.

Plusieurs résultats importants sont néanmoins établis :

- Le théorème des nombres premiers est démontré.
- Le lien entre la fonction zêta et les nombres premiers, donné par le produit d’Euler dans son domaine de convergence, est démontré.
- L’équation fonctionnelle de la fonction zêta complétée est démontrée.
- Hardy a démontré en 1914 qu’une infinité de zéros non triviaux se trouvent sur la droite critique.
- Des résultats ultérieurs ont démontré que certaines proportions positives de zéros se trouvent sur cette droite.
- De nombreux zéros ont été vérifiés par calcul, mais une vérification numérique, même très étendue, ne démontre pas que tous les zéros non triviaux sont sur la droite critique.

L’hypothèse de Riemann fait partie des sept problèmes du millénaire du Clay Mathematics Institute. Le prix associé à sa résolution est d’un million de dollars, sous réserve des règles officielles de l’institut.

**À retenir :** l’hypothèse de Riemann n’est pas une propriété démontrée de la fonction zêta. C’est une conjecture qui affirme une régularité extrêmement précise dans la position de tous ses zéros non triviaux.

---

## 11. Synthèse : le raisonnement en quelques étapes

Le cheminement peut se résumer ainsi :

1. Les nombres premiers semblent irréguliers lorsqu’on observe leur succession.
2. Leur répartition globale suit néanmoins une loi asymptotique : le théorème des nombres premiers.
3. La fonction zêta de Riemann est reliée aux nombres premiers par le produit d’Euler.
4. Les zéros non triviaux de cette fonction se trouvent dans la bande critique $0<\mathrm{Re}(s)<1$.
5. L’équation fonctionnelle révèle une symétrie autour de la droite $\mathrm{Re}(s)=1/2$.
6. L’hypothèse de Riemann affirme que tous les zéros non triviaux se trouvent sur cette droite.
7. Si elle est vraie, elle fournit une borne très précise sur l’erreur dans le comptage des nombres premiers.

La question fondamentale reste donc :

> Pourquoi tous les zéros non triviaux de la fonction zêta devraient-ils se trouver exactement sur la droite verticale d’abscisse $1/2$, et comment pourrait-on le démontrer ?

---

## 12. Ressources pour approfondir

- [Riemann Hypothesis Explorer](https://mathandcobb.org/riemann-hypothesis-explorer/) — explorateur interactif consacré à l’hypothèse de Riemann et à ses généralisations.
- [Clay Mathematics Institute — Riemann Hypothesis](https://www.claymath.org/millennium/riemann-hypothesis/) — présentation du problème du millénaire.
- [Encyclopedia of Mathematics — Riemann zeta function](https://encyclopediaofmath.org/wiki/Riemann_zeta-function) — présentation mathématique de la fonction zêta.
- [Terence Tao — The prime number theorem and the Riemann hypothesis](https://terrytao.wordpress.com/) — ressources et exposés sur les nombres premiers et l'analyse.

---

## Licence

Ce document est destiné à un usage pédagogique et à l’étude personnelle des mathématiques. Il peut être adapté et enrichi selon les besoins du projet.
