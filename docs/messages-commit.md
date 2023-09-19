# Bien écrire ses messages de commit

## Pourquoi bien écrire ses messages de commit ?

Les messages de commit sont importants car ils permettent de comprendre l'historique d'un projet, de savoir pourquoi une modification a été faite. Ils permettent également de retrouver une modification en particulier.

Afin d'avoir un message de commit clair et explicite, il est important de respecter certaines règles. Mais surtout il faut que les modifications soient cohérentes et qu'elles soient petites. Il est préférable de faire plusieurs petits commits plutôt qu'un seul gros commit. Si un commit est trop gros, il est difficile de comprendre la modification et donc de l'expliquer dans le message de commit.

Il sera aussi plus facile d'annuler un commit si celui-ci est petit. Il suffira de faire un `git reset HEAD~1` pour annuler le dernier commit. Si le commit est trop gros, il sera plus difficile de l'annuler.

## Les 7 règles d'or

source : [https://chris.beams.io/posts/git-commit/](https://chris.beams.io/posts/git-commit/)

Un message de commit doit être court et explicite. Il doit permettre de comprendre rapidement la modification apportée.

**1. Séparer le titre du corps par une ligne vide**

```
Ajoute une nouvelle fonctionnalité au projet

Ce commit ajoute une nouvelle fonctionnalité au projet. Cette fonctionnalité permet de faire ceci et cela. Elle est accessible via le menu principal.
```

**2. Limiter le titre à 50 caractères**

Un titre trop long est difficile à lire. Il est préférable de limiter le titre à 50 caractères. La description permet de donner plus de détails sur la modification.

**3. Commencer le titre par une majuscule**

Mettre la première lettre du titre en majuscule facilite la lecture.

**4. Ne pas terminer le titre par un point**

Le titre est une phrase courte. Il n'est pas nécessaire de mettre un point à la fin, sachant que l'on essaie de limiter le titre à 50 caractères.

**5. Utiliser l'impératif**

L'impératif est un mode qui permet d'exprimer un ordre. Il est utilisé pour les titres de commit car il permet de décrire ce que fait le commit.

**6. Utiliser 72 caractères pour le corps du message**

Le corps du message permet de donner plus de détails sur la modification. Il est préférable de limiter le corps du message à 72 caractères. Cela permet de faciliter la lecture du message, notamment sur les terminaux qui ne sont pas très larges. Le fait aussi de garder des caractères pour indenté le texte et ainsi le rendre plus lisible.

**7. Décrire dans le corps du message le pourquoi et non le comment**

Le corps du message permet de donner plus de détails sur la modification. Il est préférable de décrire le pourquoi de la modification plutôt que le comment. Le comment est visible dans le code. Le pourquoi permet de comprendre la modification.

## Emojis

Il est possible d'utiliser des emojis dans les messages de commit. Cela permet de donner plus de sens au message. Il existe des extensions pour Visual Studio Code qui permettent d'ajouter des emojis dans les messages de commit. Par exemple : [Gitmoji](https://marketplace.visualstudio.com/items?itemName=seatonjiang.gitmoji-vscode).

Attention toutefois à ne pas en abuser. Il faut que le message reste lisible. Il est préférable de se limiter à un seul emoji par message. Et il faut que l'emoji soit en rapport avec la modification. Il ne faut pas mettre un emoji juste pour mettre un emoji.

Il est aussi conseiller de limiter le nombre d'emojis utilisés. Il est préférable d'utiliser les emojis les plus courants. 

Voici une liste d'emojis courants :

- 🎉 `:tada:` : Ajout d'une nouvelle fonctionnalité
- 🐛 `:bug:` : Correction d'un bug
- 📝 `:memo:` : Documentation
- 🚀 `:rocket:` : Amélioration des performances
- 🔖 `:bookmark:` : Versionnage
- 🚧 `:construction:` : Travail en cours
- 🎨 `:art:` : Amélioration du code
- 🚚 `:truck:` : Déplacement ou renommage de fichiers
- 📦 `:package:` : Mise à jour des dépendances
- 🚑 `:ambulance:` : Correction d'un crash en urgence
- ✅ `:white_check_mark:` : Ajout de tests
- 🔒 `:lock:` : Correction d'une faille de sécurité

