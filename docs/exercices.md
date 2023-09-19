# Exercices

## L'essentiel

### Mettre en place un projet git

1. Créer un nouveau projet
2. Initialiser le projet avec git
3. Créer un fichier `index.html`
4. Ajouter le fichier à l'index
5. Commiter le fichier avec le message `Add index.html`
6. Modifier le fichier `index.html`
7. Ajouter le fichier à l'index
8. Commiter le fichier avec le message `Update index.html`
9. Modifier le fichier `index.html`
10. Ajouter le fichier à l'index
11. Commiter le fichier avec le message `Update index.html`
12. Afficher l'historique des commits

**Solution**

<details>
<summary>Cliquez ici pour voir la solution</summary>

1. Créer un nouveau projet

```bash
mkdir git-commit
cd git-commit
```

2. Initialiser le projet avec git

```bash
git init
```

3. Créer un fichier `index.html`

```bash
echo "<h1>Hello World</h1>" > index.html
```

4. Ajouter le fichier à l'index

```bash
git add index.html
```

5. Commiter le fichier avec le message `Add index.html`

```bash
git commit -m "Add index.html"
```

6. Modifier le fichier `index.html`

```bash
echo "<h1>Hello World !</h1>" > index.html
```

7. Ajouter le fichier à l'index

```bash
git add index.html
```

8. Commiter le fichier avec le message `Update index.html`

```bash
git commit -m "Update index.html"
```

9. Modifier le fichier `index.html`

```bash
echo "<h1>Hello World !</h1><p>This is a new paragraph</p>" > index.html
```

10. Ajouter le fichier à l'index

```bash
git add index.html
```

11. Commiter le fichier avec le message `Update index.html`

```bash
git commit -m "Update index.html"
```

12. Afficher l'historique des commits

```bash
git log
```

</details>

### Comparer les fichiers

1. Comparer le fichier `index.html` avec le dernier commit
2. Comparer le fichier `index.html` avec le commit précédent
3. Comparer le fichier `index.html` avec le commit précédent du commit précédent
4. Comparer le fichier `index.html` avec le premier commit
5. Comparer le fichier `index.html` avec un commit précis

**Solution**

<details>

<summary>Cliquez ici pour voir la solution</summary>

1. Comparer le fichier `index.html` avec le dernier commit

```bash
git diff HEAD index.html
```

2. Comparer le fichier `index.html` avec le commit précédent

```bash
git diff HEAD^ index.html
```

3. Comparer le fichier `index.html` avec le commit précédent du commit précédent

```bash
git diff HEAD^^ index.html
```

4. Comparer le fichier `index.html` avec le premier commit

```bash
git diff HEAD~3 index.html
```

5. Comparer le fichier `index.html` avec un commit précis

```bash
git diff 5f4a4b2 index.html
```

</details>

### Annuler un commit

1. Annuler le dernier commit
2. Annuler le dernier commit et supprimer les fichiers de l'index
3. Annuler le dernier commit et modifier le message du commit

**Solution**

<details>

<summary>Cliquez ici pour voir la solution</summary>

1. Annuler le dernier commit

```bash
git reset --soft HEAD^
```

2. Annuler le dernier commit et supprimer les fichiers de l'index

```bash
git reset --hard HEAD^
```

4. Annuler le dernier commit et modifier le message du commit

```bash
git commit --amend
```

</details>

### Mettre de côté des modifications

1. Créer un fichier `other-file.html`
2. Ajouter le fichier à l'index
3. Mettre de côté les modifications en cours, en ajoutant un message
4. Modifier le fichier `index.html`
5. Ajouter le fichier à l'index
6. Commiter le fichier avec le message `Update index.html`
7. Afficher la liste des modifications mises de côté
8. Appliquer les modifications mises de côté
9. Supprimer les modifications mises de côté


**Solution**

<details>

<summary>Cliquez ici pour voir la solution</summary>

1. Créer un fichier `other-file.html`

```bash
echo "<h1>Other file</h1>" > other-file.html
```

2. Ajouter le fichier à l'index

```bash
git add other-file.html
```

3. Mettre de côté les modifications en cours, en ajoutant un message

```bash
git stash save "Add other-file.html"
```

4. Modifier le fichier `index.html`

```bash
echo "<h1>Hello World !</h1><p>This is a new paragraph</p><p>This is another paragraph</p>" >> index.html
```

5. Ajouter le fichier à l'index

```bash
git add index.html
```

6. Commiter le fichier avec le message `Update index.html`

```bash
git commit -m "Update index.html"
```

7. Afficher la liste des modifications mises de côté

```bash
git stash list
```

8. Appliquer les modifications mises de côté

```bash
git stash apply
```

9. Supprimer les modifications mises de côté

```bash
git stash drop
```

</details>

### Publier un projet sur GitHub

1. Créer un nouveau projet sur GitHub
2. Ajouter le projet local comme remote
3. Publier le projet local sur GitHub

**Solution**

<details>

<summary>Cliquez ici pour voir la solution</summary>

1. Créer un nouveau projet sur GitHub

```
Aller sur https://github.com et créer un nouveau projet.
```

2. Ajouter le projet local comme remote

```bash
git remote add origin <url>
```

3. Publier le projet local sur GitHub

```bash
git push -u origin main
```

</details>

### Récupérer un projet depuis GitHub

1. Récupérer un projet depuis GitHub

**Solution**

<details>

<summary>Cliquez ici pour voir la solution</summary>

1. Récupérer un projet depuis GitHub

```bash
git clone <url>
```

</details>

## Les branches

### Créer une branche

1. Créer une branche `branch1`
2. Faire un commit sur la branche `branch1`
3. Créer une branche `branch2` à partir de la branche principale
4. Faire un commit sur la branche `branch2`
4. Créer une branche `branch3` à partir de la branche `branch1`
5. Faire un commit sur la branche `branch3`
6. Afficher la liste des branches
7. Afficher l'historique des commits



**Solution**

