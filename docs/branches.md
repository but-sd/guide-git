# Les Branches
 
Les branches constituent un élément central de Git. Elles permettent de travailler sur plusieurs versions d'un même projet en parallèle. Elles sont, par exemple, très utiles pour travailler sur des fonctionnalités en cours de développement sans impacter le code de production. Ceci permet aussi de développer une nouvelle fonctionalité sur une branche dédiée sans risquer d’altérer le code de la branche principale, qui reste stable à tout moment.

Lors de la création d'une branche, celle-ci est dupliquée à partir de la branche courante. Les modifications apportées à cette branche n'impactent pas les autres branches. Une fois les modifications terminées, il est possible de fusionner la branche avec la branche courante.

```mermaid
gitGraph
   commit
   commit
   branch branch1
   commit
   checkout main
   branch branch2
   commit
   commit
   checkout branch1
   commit
   checkout branch2
   commit
   commit
   checkout main
   merge branch1
   checkout main
   merge branch2
   checkout main
   commit
   branch branch3
   commit
```

## Lister les branches

Pour lister les branches d'un projet, il suffit d'utiliser la commande `git branch`.

```bash
git branch
```

Cette commande affiche la liste des branches du projet. La branche courante est indiquée par un astérisque.

```bash
* main
  branch1
  branch2
```

L'option `-a` permet d'afficher toutes les branches du projet, y compris les branches distantes.

```bash
git branch -a
```

```bash
* main
  branch1
  branch2
  remotes/origin/HEAD -> origin/main
  remotes/origin/main
  remotes/origin/branch1
  remotes/origin/branch2
```

L'option `-v` permet d'afficher les derniers commits de chaque branche.

```bash
git branch -v
```

```bash
* main   5f4a4b2 [origin/main] Update readme.md
  branch1 5f4a4b2 Update readme.md
  branch2 5f4a4b2 Update readme.md
```

L'option `--list` permet d'afficher les branches qui correspondent à un motif.

```bash
git branch --list "feat*"
```

```bash
  feature1
  feature2
```

Enfin, quelques autres options s’avèrent utiles :

- `--contains <commit>` affiche toutes les branches contenant un commit donné,
- `--no-contains` fait le contraire de la précédente,
- `--no-merge` affiche les branches qui n’ont pas été mergées avec la branche courante,
- `--merge` fait le contraire de la précédente.


## Créer une branche

Pour créer une branche, il suffit d'utiliser la commande `git branch` suivie du nom de la branche à créer.

```bash
git branch branch1
```

Cette commande crée une nouvelle branche nommée `branch1` à partir de la branche courante.

## Changer de branche

Pour changer de branche, il suffit d'utiliser la commande `git switch` suivie du nom de la branche à utiliser.

```bash
git switch branch1
```

La branch `branch1` doit exister pour pouvoir changer de branche. Elle devient la branche courante. Il est possible de passer l'option `-c` pour créer une nouvelle branche et la définir comme branche courante.

```bash
  main
* branch1
  branch2
```

Cette commande permet de passer de la branche `main` à la branche `branch1`. Il est aussi possible d'utiliser le mot clé `checkout` à la place de `switch`. Le mot clé `checkout` est déprécié et sera supprimé dans une prochaine version de Git.

```bash
git checkout branch1
```

Cette commande permet de fusionner la branche `branch1` avec la branche courante. La branche `branch1` n'est pas supprimée. 

Il est possible que la fusion de branches génère des conflits. Dans ce cas, il faut résoudre les conflits avant de pouvoir fusionner les branches. Nous verrons comment résoudre les conflits dans un prochain chapitre.

## Supprimer une branche

Pour supprimer une branche, il suffit d'utiliser la commande `git branch` suivie du nom de la branche à supprimer et de l'option `-d`.

```bash
git branch -d branch1
```

Cette commande supprime la branche `branch1`. Il n'est pas possible de supprimer la branche courante. Il faut donc changer de branche avant de pouvoir supprimer une branche.

## Renommer une branche

Pour renommer une branche, il suffit d'utiliser la commande `git branch` suivie du nom de la branche à renommer et de l'option `-m`.

```bash
git branch -m branch1 branch3
```

Cette commande renomme la branche `branch1` en `branch3`. Il n'est pas possible de renommer la branche courante. Il faut donc changer de branche avant de pouvoir renommer une branche.

## Fusionner des branches

Pour fusionner des branches, il suffit d'utiliser la commande `git merge` suivie du nom de la branche à fusionner.

```bash
git merge branch1
```

Cette commande permet de fusionner la branche `branch1` avec la branche courante. La branche `branch1` n'est pas supprimée.

### Fast-forward

Lorsque la branche courante n'a pas été modifiée depuis la création de la branche à fusionner, la fusion est dite *fast-forward*. Dans ce cas, la branche courante est mise à jour avec les modifications de la branche à fusionner.

```mermaid
gitGraph
   commit
   commit
   branch branch1
   commit
   checkout main
   commit
   commit
   checkout branch1
   commit
   checkout main
   merge branch1
```

### 3-way merge

Lorsque la branche courante a été modifiée depuis la création de la branche à fusionner, la fusion est dite *3-way merge*. Dans ce cas, Git crée un nouveau commit de fusion qui contient les modifications des deux branches.

```mermaid
gitGraph
   commit
   commit
   branch branch1
   commit
   checkout main
   commit
   commit
   checkout branch1
   commit
   checkout main
   commit
   merge branch1
```

Dans l'exemple ci-dessus, la branche `main` a été modifiée depuis la création de la branche `branch1`. La fusion de la branche `branch1` avec la branche `main` crée un nouveau commit de fusion qui contient les modifications des deux branches. 

La branche `main` est mise à jour avec les modifications de la branche `branch1`. La branche `branch1` n'est pas supprimée. 

### Fusion avec conflits

Lorsque la branche courante et la branche à fusionner ont été modifiées au même endroit, la fusion génère un conflit. Dans ce cas, il faut résoudre le conflit avant de pouvoir fusionner les branches.

La fusion se fait en trois étapes :

- Git fusionne les fichiers qui n'ont pas été modifiés dans les deux branches,
- Git fusionne les fichiers qui ont été modifiés dans une seule branche,
- Git fusionne les fichiers qui ont été modifiés dans les deux branches.

Le conflit se présente sous la forme suivante :

```bash
<<<<<<< HEAD
<h1 id="title">Hello World</h1>
=======
<h1 id="title">Hello World !</h1>
>>>>>>> branch1
```

La partie `HEAD` correspond à la branche courante. La partie `branch1` correspond à la branche à fusionner. Il faut modifier le fichier pour résoudre le conflit. Dans l'exemple ci-dessus, il faut choisir entre `Hello World` et `Hello World !`. Une fois le conflit résolu, il faut ajouter le fichier à l'index et terminer la fusion.

```bash
git add index.html
git merge --continue
```

## Comparer des branches

Pour comparer des branches, il suffit d'utiliser la commande `git diff` suivie du nom de la branche à comparer.

```bash
git diff branch1
```

Cette commande affiche les différences entre la branche courante et la branche `branch1`. Il est aussi possible de comparer deux branches entre elles.

```bash
git diff branch1 branch2
```

Cette commande affiche les différences entre la branche `branch1` et la branche `branch2`.

## git flow

Git flow est un modèle de gestion de branches. Il permet de gérer les branches d'un projet de manière structurée. Il est composé de deux branches principales :

- `main` : branche principale du projet. Elle contient le code de production,

- `develop` : branche de développement. Elle contient le code en cours de développement.

Il est aussi composé de branches secondaires :

- `feature` : branche de fonctionnalité. Elle contient le code d'une fonctionnalité en cours de développement,

- `release` : branche de release. Elle contient le code en cours de préparation pour une release,

- `hotfix` : branche de hotfix. Elle contient le code en cours de développement pour corriger un bug en production.

### feature

Le schéma ci-dessous illustre la partie feature du git flow. Les développements se font sur la branches `develop` ou via des branches `feature` créées à partir de la branche `develop` pour développer des fonctionnalités. Une fois les fonctionnalités développées, les branches `feature` sont fusionnées avec la branche `develop`.

Il serait possible de fusionner les branches `feature` avec la branche `main`. Cependant, il est préférable de fusionner la branche `develop` avec la branche `main`. Cela permet de s'assurer que le code de production est stable. Il existe des solutions pour protéger la branche `main` et empêcher les modifications directes sur cette branche (nous verrons cela dans un prochain chapitre).

```mermaid

gitGraph
   commit
   commit
   branch develop
   commit
   branch feature1
    commit
    commit
    checkout develop
    commit
    merge feature1
    branch feature2
    commit
    commit
    commit
    checkout develop
    commit
    branch feature3
    commit
    checkout develop
    branch feature4
    commit
    commit
    checkout develop
    merge feature2
    
```

### release

Le schéma ci-dessous illustre la partie release du git flow. La release une version du projet qui est prête à être mise en production. Une release est une version du projet qui est testée et qui est stable. On lui attribue un numéro de version. Par exemple, la version 1.0.0. (nous verrons comment gérer les versions dans un prochain chapitre). Les releases se font via des branches `release` créées à partir de la branche `develop` pour préparer une release. 

La release est une branche de préparation. Elle permet aussi de tester le code avant de le mettre en production. Si un bug est détecté, il est possible de corriger le bug sur la branche `release` et de fusionner la branche `release` avec la branche `develop`.

Une fois la release prête, la branche `release` est fusionnée avec la branche `develop` et la branche `main`.

```mermaid

gitGraph
   commit
   commit
   branch develop
   commit
   branch release1
    commit
    commit
    commit
    checkout develop
    commit
    merge release1
    checkout main
    merge release1
    checkout develop
    commit
```

### hotfix

Le schéma ci-dessous illustre la partie hotfix du git flow. Les hotfix se font via des branches `hotfix` créées à partir de la branche `main` pour corriger un bug en production. Une fois le hotfix développé, la branche `hotfix` est fusionnée avec la branche `develop` et la branche `main`.

Le `hotfix` est une branche de correction. La modification doit être ciblée et la durée de vie de la branche doit être courte. Le `hotfix` est une branche temporaire qui doit être supprimée une fois la correction appliquée. Elle doit être fusionnée avec la branche `develop` et la branche `main` le plus rapidement possible.

```mermaid

gitGraph
   commit
   commit
   branch develop
   commit
   checkout main
   branch hotfix1
    commit
    commit
    checkout main
    merge hotfix1
    checkout develop
    commit
    merge hotfix1
```

**Résumé**

Le schéma [Git flow complet](./git-flow-complet.md) illustre le git flow complet. Les développements se font sur la branches `develop` ou via des branches `feature` créées à partir de la branche `develop` pour développer des fonctionnalités. Une fois les fonctionnalités développées, les branches `feature` sont fusionnées avec la branche `develop`.

Les releases se font via des branches `release` créées à partir de la branche `develop` pour préparer une release. Une fois la release prête, la branche `release` est fusionnée avec la branche `develop` et la branche `main`.

Les hotfix se font via des branches `hotfix` créées à partir de la branche `main` pour corriger un bug en production. Une fois le hotfix développé, la branche `hotfix` est fusionnée avec la branche `develop` et la branche `main`.

## Références

- [Git Branches](https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell)
- [Git Branch](https://git-scm.com/docs/git-branch)
