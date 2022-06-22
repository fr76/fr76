# Contribution

Ce compte GitHub a pour vocation de regrouper tous les projets de développement de l'association.

Chaque projet est hébergé dans un dépôt Git qui lui est propre. Pour pouvoir contribuer à un projet, la méthode préférée
est l'ajout en tant que collaborateur. Pour demander à être ajouté comme collaborateur, il faut envoyer un mail à
l'administrateur du compte en fournissant son identifiant GitHub. Vous recevrez ensuite un email de confirmation de
GitHub pour accepter la demande d'ajout.

## Collaboration avec Git et GitHub

Cette documentation est destinée aux membres de l'association qui doivent collaborer sur ces différents projets. Le but
ici est de définir l'organisation du travail et les règles de la collaboration entre les différents membres impliqués
dans les projets. Ceci afin de garantir une collaboration efficace tout en garantissant une production de la plus grande
qualité possible. Pour ce faire, l'association utilise Git et GitHub, qui sont des outils très performants, mais aussi
assez techniques à prendre en main.

Sachant que votre maîtrise de ces outils peut-être variable selon les cas, cette documentation a été découpée en
instruction adaptée à chaque niveau, que vous soyez débutant ou que vous maîtrisiez déjà bien ces outils. Ainsi :

- Si vous ne connaissez pas Git et GitHub, commencez votre lecture à partir de la partie 1.
- Si vous maîtrisez ces notions, commencez à partir de la partie 2 :
    - Ce qu'est un dépôt Git.
    - Les commits et les pushs.
    - La différence entre Git et GitHub.
- Si vous maîtrisez les notions de branches et de merge, lisez la partie 3.

Dans tous les cas, il est très important de prendre le temps de maîtriser ces outils, même pour vous-même, c'est une
compétence très utile et qui vous sera donc très souvent demandée si travaillez dans l'informatique et la programmation.

### Partie 1

Git est ce qu'on appelle un outil de gestion de versions. Dans les grandes lignes, il sert à enregistrer les différentes
versions du code source d'un projet donné, au fur et à mesure que des changements sont apportés. Chaque version est
appelée un **commit** et enregistre les modifications depuis la dernière version.

Il permet également d'envoyer ces commits sur un serveur distant pour pouvoir le partager avec les autres membres du
projet. Github est un exemple d'un tel serveur : Il s'agit héberge les projets et fournit un site pour les consulter et
les administrer depuis le web.

Voici un bon cours pour apprendre les bases de Git et GitHub qu'il est important de suivre pour comprendre la
suite : [https://openclassrooms.com/fr/courses/7162856-gerez-du-code-avec-git-et-github](https://openclassrooms.com/fr/courses/7162856-gerez-du-code-avec-git-et-github)

Voici un rappel des commandes les plus utiles :

Télécharger le code source d'un projet depuis GitHub :

1. Rendez-vous sur la page GiHub du projet.
2. Repérer le lien pour cloner le projet d'après la capture d'écran
   suivante : ![](res/contribution%20-%20git%20clone.png)
3. tapez la commande suivante dans un terminal (pensez à vous mettre dans le dossier dans lequel vous voulez
   travailler) : `git clone [lien]`

Créer un nouveau commit :

1. Ajouter les fichiers qu'on veut sauvegarder dans le commit :
    - `git add [fichier1] [fichier2] ...` pour ajouter certains fichiers.
    - `git add .` pour ajouter tous les fichiers du projet.
2. créer le commit : `git commit -m "un message descriptif des changements"`. On peut consulter la liste des commits
   récents avec `git log`.

Manipuler les branches :

- Changer de branche : `git checkout [branche]`.
- Créer une branche et s'y rendre immédiatement `git checkout -b [branche]`.

Fusionner une branche A dans une branche B :

- Se rendre dans la branche B (celle qui recevra la branche A) : `git checkout B`.
- Fusionnez A dans B `git merge --no-ff A`.

Gérer son code avec GitHub :

- Envoyer son code : `git push origin [branche]`.
- Télécharger les mises à jour :
    1. `git fetch origin`.
    2. `git checkout [branche]`.
    3. `git pull origin [branche]`.

### Partie 2

### Partie 3