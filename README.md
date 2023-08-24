# Manipulation des fichier git

Git est un logiciel de gestion de versions décentralisé. C'est un logiciel libre créé par Linus Torvalds, auteur du noyau Linux, et distribué selon les termes de la licence publique générale GNU version 2.

Git permet de gérer des projets, de suivre l'évolution du code source et de coordonner le travail fait par plusieurs personnes dessus. Il permet de revenir à des versions antérieures du projet, de gérer très facilement les différentes branches de développement et de maintenir des versions distinctes du projet.

Un dépôt git est un dossier qui contient les fichiers du projet ainsi que les informations de versionnage. Il est possible de créer un dépôt git à partir d'un dossier existant ou de créer un dossier à partir d'un dépôt git.

Le concept de commit est au coeur de git. Un commit est une sauvegarde de l'état des fichiers à un instant donné. Un commit représente un ensemble cohérent de modifications. Il est possible de revenir à un commit précédent.

## Les trois états d'un fichier

Un fichier peut être dans trois états différents dans git :
- **non suivi** : le fichier n'est pas dans le dépôt git
- **suivi** : le fichier est dans le dépôt git mais n'a pas été modifié depuis le dernier commit
- **modifié** : le fichier est dans le dépôt git et a été modifié depuis le dernier commit

## Les trois zones d'un dépôt git

Un dépôt git est composé de trois zones :
- **le répertoire de travail** : c'est le dossier qui contient les fichiers du projet
- **l'index** : c'est la zone qui contient les fichiers qui seront commités
- **l'historique** : c'est la zone qui contient les commits

Lors de l'initialisation d'un dépôt git, le répertoire de travail et l'index sont identiques. Lorsqu'on ajoute un fichier à l'index, il est copié dans l'index. Lorsqu'on commit, les fichiers de l'index sont copiés dans l'historique.

Afin d'initialiser un dépôt git, il faut se placer dans le répertoire de travail et exécuter la commande suivante :
```bash
git init
```

Cela crée un dossier .git qui contient les informations de versionnage. Il est possible de voir ce dossier en affichant les fichiers cachés. Par exemple, sous Linux ou avec git-bash, il faut exécuter la commande suivante :
```bash
ls -a
```

## Ajouter un fichier à l'index

Pour ajouter un fichier à l'index, il faut exécuter la commande suivante :
```bash
git add <file>
```

Une fois le fichier ajouté à l'index, il est possible de voir son état avec la commande suivante :
```bash
git status
```

Les fichiers qui sont dans l'index sont affichés en vert. Les fichiers qui ne sont pas dans l'index sont affichés en rouge. Les fichiers qui ont été modifiés depuis le dernier commit sont affichés en rouge. Les fichiers qui ont été modifiés et ajoutés à l'index sont affichés en vert.









Avant de commencer à utiliser git, il faut configurer son nom et son email.

## Configurer son nom
```bash
git config --global user.name "John Doe"
```

## Configurer son email
```bash
git config --global user.email
```

Le concept de commit est au coeur de git. Un commit est une sauvegarde de l'état des fichiers à un instant donné. Il est possible de revenir à un commit précédent.


## Créer un nouveau dépôt
```bash
git init
```

## Ajouter un fichier à l'index
```bash
git add <file>
```

## Ajouter tous les fichiers à l'index
```bash
git add .
```

## Supprimer un fichier de l'index
```bash
git rm <file>
```

## Supprimer un fichier du disque et de l'index
```bash
git rm -f <file>
```

## Supprimer un fichier du disque mais pas de l'index
```bash
git rm --cached <file>
```

## Renommer un fichier
```bash
git mv <old> <new>
```

