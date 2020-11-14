# Notes

En informatique classique, les états sont représentés par un ou plusieurs **bits**.
Le terme **bit** n’est autre que la contraction de *binary digit*, ou *chiffre binaire*).
Comme le montre la traduction française, s’il s’agit d’un chiffre binaire, alors il ne peut
prendre que deux valeurs : 0 ou 1 (par opposition au bien connu système décimal qui peut prendre dix valeurs :
0, 1, 2, 3, 4, 5, 6, 7, 8, 9).

Physiquement, il est assez facile de représenter un bit seul : l’absence de courant dans un circuit ou non.
Il suffit d’avoir deux *états mutuellement exclusifs* (comprenez bien cet état de fait, ce sera utile par la suite).

Par convention, dans un ordinateur, on peut représenter le chiffre binaire 1 par la présence de courant et 0 par l’absence de ce dernier.

Notez qu’en fait, on aurait pu choisir la convention opposée ed dire que le chiffre binaire 0 correspond à la présence de courant et 1 à l’absence de ce dernier.

Si vous vous sentez déjà perdus (et il n’y a rien de mal à ça), je vous renvoie vers des ressources théoriques qui permettent de comprendre le codage de l’information
(les bases de chez bases pour tout informaticien qui se respecte et pour toute personne curieuse de la chose).

https://www.apprendre-en-ligne.net/crypto/images/bases.html

En informatique quantique, les choses sont totalement différentes. Si on a en informatique classique des *bits* qui peuvent contenir un seul état à la fois,
alors en informatique quantique on a des **qubits** (la graphie **qbit** est également acceptée) qui contiennent… **une superposition d’états** !

Ce qui signifie que, tant qu’on ne lit pas l’information contenue dans un **qubit**, ce dernier est dans un état indéterminé, avec une probabilité plus ou moins grande d’être dans l’état 0 ou
l’état 1.

Physiquement, la représentation d’un **qubit** tient d’une propriété physique quantique ; c’est-à-dire d’une propriété physique qui n’est déterminée que lorsqu’elle est mesurée : cela peut-être le *spin*
d’un électron (*up* ou *down*), la polarisation d’un photon ou l’état d’un atome (*fondamental* ou *excité*). La difficulté physique réside dans la manipulation de ces objets mais de gros progrès ont été effectués ces dernières années.

Attention maintenant, on va écrire un peu de formules mathématiques (et les expliquer, ne vous en faites pas).

Un état quantique superposé d’un **qubit** se décrit comme suit :

$$|\psi \rangle = \alpha |0 \rangle + \beta |1 \rangle$$

Apprenons d’abord à lire cette formule, et ensuite décrivons-la un peu.

$\psi$ correspond à la lettre grecque *psi*. On aurait pu choisir une autre lettre, mais ici il ne s’agit ni plus ni moins que d’une convention. Je précise cela parce que lorsque je me suis remis aux mathématiques, j’ai été assez embêté à l’idée de ne pas pouvoir lire, ne serait-ce qu’à voix haute, la lettre $\psi$.

L’écriture $|\psi \rangle$ se lit "ket psi". La notation $| \rangle$ correspond à la "notation bra-ket", où | est le bras, et $\rangle$ est le ket. En physique quantique, le ket représente un état quantique (incertain ou mesuré).

Ici, $\alpha$ (lettre grecque « alpha ») et $\beta$ (lettre grecque « beta ») sont tout aussi arbitraires. On aurait pu écrire $\alpha_{0}$ et $\alpha_{1}$ respectivement en lieu et place de $\alpha$ et $\beta$. Il s’agit des coefficients de probabilité des états quantiques $|0 \rangle$ (« ket 0 ») et $|1 \rangle$ (« ket 1 ») tel que :

$$| \alpha |^2 + | \beta |^2 = 1.$$

Parce qu’une probabilité est un nombre toujours compris entre 0 et 1, la somme de probabilité de tous les états quantiques possibles d’un système est donc égale à 1.

Qu’est-ce que tout cela signifie ?

Prenez l’état quantique suivant d’un qubit quelconque : $\sqrt{\frac{1}{3}}|0 \rangle + \sqrt{\frac{2}{3}}|1 \rangle$

On a bien :

$$(\sqrt{\frac{1}{3}})^2 + (\sqrt{\frac{2}{3}})^2 = \frac{1}{3} + \frac{2}{3} = 1.$$

Ce qui signifie que, une fois observé, le qubit en question a une probabilité de $\frac{1}{3}$ de se retrouver dans l’état $|0\rangle$ et une probabilité de $\frac{2}{3}$ de se retrouver dans l’état $|1\rangle$. Il a donc plus de chances de se retrouver dans l’état $|1\rangle$ une fois observé, *mais il peut aussi se retrouver dans l’état $|0\rangle$*.

Vous l’aurez compris : ici il est question de manipulation de ces probabilité avant mesure du résultat, et ensuite l’interprétation demeure facile : un état quantique $|0\rangle$ correspondrait à un *bit* 0 en informatique classique, tandis qu’un état quantique $|1\rangle$ correspondrait à un *bit* 1 en informatique classique.

Nous faisons face à une seconde difficulté : la présence de probabilité (et donc de hasard) peut nous faire aboutir à des erreurs une fois notre calcul mesuré.

Parce que, oui, une fois que la mesure d’un qubit est prise, **son état est figé**.

Mais alors, où se situe l’intérêt quantique ? **En construisant des registres de qubits**. Car dans notre exemple, nous avions un seul qubit et l’intérêt est assez limité.

Mais imaginons que nous avons maintenant **deux qubits**. L’expression de sa superposition d’états serait alors :

$$|\psi \rangle = \alpha |00 \rangle + \beta |01 \rangle + \gamma |10 \rangle + \delta |11 \rangle$$

Avec :

$$| \alpha |^2 + | \beta |^2  + | \gamma |^2  + | \delta |^2 = 1.$$

On a donc une superposition de quatre états. Et une fois le qubit observé, il se retrouve soit dans l’état $|00 \rangle$ (qui correspondrait aux bits 00 en informatique classique), $|01 \rangle$ pour les bits 01, $|10 \rangle$ pour les bits 10 et enfin $|11 \rangle$ pour les bits 11.

L’idée, c’est qu’en manipulant d’une traite ce registre de deux **qubits**, on ait fait **un seul calcul pour quatre éventualités**. Ainsi, si on a un registre de $n$ **qubits**, on peut effectuer $2^{n}$ opérations en une seule fois (avec des probabilités plus ou moins grandes sur l’état qui nous intéresse).

