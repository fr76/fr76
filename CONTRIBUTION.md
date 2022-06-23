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
    - Les branches et les merges.

Les notions présentées dans les parties suivantes sont avant tout des rappels des concepts et des commandes les plus
utilisés. Ces rappels sont très sommaires et des liens sont fournis vers de la documentation plus complète si besoin.
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

#### Télécharger le code source d'un projet depuis GitHub

1. Rendez-vous sur la page GiHub du projet.
2. Repérer le lien pour cloner le projet d'après la capture d'écran
   suivante : ![](res/contribution%20-%20git%20clone.png)
3. tapez la commande suivante dans un terminal (pensez à vous mettre dans le dossier dans lequel vous voulez
   travailler) : `git clone [lien]`

#### Créer un nouveau commit

1. Ajouter les fichiers qu'on veut sauvegarder dans le commit :
    - `git add [fichier1] [fichier2] ...` pour ajouter certains fichiers.
    - `git add .` pour ajouter tous les fichiers du projet.
2. créer le commit : `git commit -m "un message descriptif des changements"`. On peut consulter la liste des commits
   récents avec `git log`.

#### Manipuler les branches

- Changer de branche : `git checkout [branche]`.
- Créer une branche et s'y rendre immédiatement `git checkout -b [branche]`.

Fusionner une branche A dans une branche B :

- Se rendre dans la branche B (celle qui recevra la branche A) : `git checkout B`.
- Fusionnez A dans B `git merge --no-ff A`.

#### Envoyer son code sur GitHub

- Faire un push : `git push origin [branche]`.

⚠ Votre identifiant et votre mot de passer vous seront demandés pour vous connecter à GitHub. Depuis quelque temps, ce
dernier n'accepte plus le mot de passe du compte pour pusher son code, mais utilise à la place un système de token. Pour
générer et utiliser le votre, veuillez lire
cette [documentation](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token)

#### Télécharger les mises à jour depuis GitHub

1. `git fetch origin`.
2. `git checkout [branche]`.
3. `git pull origin [branche]`.

### Partie 2

Cette partie ne porte pas sur l'utilisation de Git en tant que tel, mais sur les conventions dont l'association se sert
pour organiser le travail avec cet outil.

Nous utilisons diverses conventions, telles que :

#### Le modèle de branches Git

Cette convention permet de développement du projet en plusieurs branches. Ces branches ont divers rôles, comme permettre
de ne passer en production que du code testé et mature, d'isoler l'implémentation de chaque nouvelle fonctionnalité dans
une branche spécifique pour l'isoler des perturbations extérieures, ou de contrôler plus facilement le versionnage du
logiciel.

Voici un schéma qui résume son fonctionnement :

![](res/contribution%20-%20modèle%20de%20brances%20git.png)

Pour plus d'informations, visitez ce
lien : [https://nvie.com/posts/a-successful-git-branching-model/](https://nvie.com/posts/a-successful-git-branching-model/)

#### La gestion sémantique des versions

Il s'agit d'une convention permettant de spécifier la manière dont on nomme les versions d'un logiciel que l'on publie.
Une version d'un logiciel est écrite selon la syntaxe `X.Y.Z`, avec `X`, `Y`, `Z` des nombres entiers qui doivent être
incrémentés :

- Pour `X` lorsqu'une nouvelle fonctionnalité est ajoutée, rendant le logiciel **incompatible** avec la version
  précédente.
- Pour `Y` lorsqu'une nouvelle fonctionnalité est ajoutée, gardant le logiciel **compatible** avec la version
  précédente.
- Pour `Z` lorsqu'une modification mineure est apportée, comme la correction d'un bug, sans apporter, modifier ou
  supprimer de fonctionnalité.

Allez visiter [https://semver.org/](https://semver.org/) pour avoir une explication plus complète.
