---
marp: true
theme: gaia
size: 16:9
paginate: true
backgroundImage: url('https://marp.app/assets/hero-background.jpg')
header: 'Git - Mise en pratique'
footer: 'Auteur : Alexandre GIRARD'
---

![bg](https://images8.alphacoders.com/430/430944.jpg)

--- 

# Mettre en place un projet git

* Créer un nouveau projet `html-to-app` en local et l'initialiser avec git
* Ajouter les fichiers `index.html`, `style.css` et `script.js` au projet (https://alex1dregirard.github.io/memo-html/exercices/)
* Afficher le statut du projet
* Ajouter les fichiers à l'index
* Afficher le statut du projet
* Commiter les fichiers avec le message `Initial commit`
* Afficher le statut du projet

---

# Apporter des modifications au projet

* Modifier les fichiers nécessaires pour ajouter le code qui modifie la balise `h1` du fichier `index.html` en JavaScript
* Ajouter les fichiers à l'index
* Commiter avec le message `Modifie le titre de la page dynamiquement`
* Afficher l'historique des commits

---

# Améliorer le code du projet

* Restructurer le code du fichier `script.js` en créant une fonction `changeTitle` qui modifie le titre de la page
* Ajouter les fichiers à l'index
* Commiter avec le message `Améliore le code du projet`
* Afficher l'historique des commits

---

# Ajouter des fonctionnalités au projet

:warning: Appliquer les bonnes pratiques git en séparant les fonctionnalités dans des commits séparés

* Ajouter le sous-titre `Welcome to the javascript world` en JavaScript
* Ajouter l'heure actuelle en JavaScript
* Afficher les différences entre l'index et le dernier commit

---

# Mettre de côté les modifications en cours

* Ajouter la fonctionnalité qui fait bouger l'image et le tableau en JavaScript
* Mettre de côté les modifications en cours, en ajoutant un message
* Ajouter la fonctionnalité qui modifie la liste des items en JavaScript
* Commiter la nouvelle fonctionnalité 

--- 

# Outiller le projet

:warning: Ne pousser que les fichiers nécessaires au projet

* Ajouter `browser-sync` au projet
* Configurer `browser-sync` pour qu'il lance le serveur web et qu'il ouvre le navigateur
* Ajouter le script `start` au fichier `package.json`
* Ajouter le fichier `.gitignore` au projet
* Commiter les modifications 

---

# Reprendre les modifications mises de côté

* Reprendre les modifications mises de côté
* Ajouter les fichiers à l'index
* Commiter avec le message `Ajoute la fonctionnalité qui fait bouger l'image et le tableau en JavaScript`

---

# Pousser le projet sur GitHub

* Créer un nouveau repo `html-to-app` sur GitHub
* Ajouter le repo distant au projet
* Pousser le projet sur GitHub

---

# Cloner le projet

* Cloner le projet `html-to-app` sur GitHub dans un nouveau dossier `html-to-app-clone`
* Installer les dépendances du projet
* Lancer le serveur web
* Vérifier que le projet fonctionne correctement