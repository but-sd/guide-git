# Réécrire l'historique

TODO

## Ré-écrire l'historique

Il est possible de modifier l'historique avec la commande suivante :
```bash
git rebase -i HEAD~3
```

Cette commande ouvre un éditeur de texte qui permet de modifier l'historique. Il est possible de modifier le message d'un commit, de supprimer un commit ou de fusionner deux commits.

### Modifier le message d'un commit

Pour modifier le message d'un commit, il faut remplacer le mot pick par reword devant le commit.

### Supprimer un commit

Pour supprimer un commit, il faut supprimer la ligne correspondant au commit.

### Fusionner deux commits

Pour fusionner deux commits, il faut remplacer le mot pick par squash devant le commit.

Il est possible de fusionner plusieurs commits en ajoutant plusieurs squash devant les commits.

Ces actions peuvent aussi être faite directement dans l'ide, ce qui peut être plus simple. 

Par exemple avec l'extension git lens de Visual Studio Code:

![git rebase -i](images/git-rebase-i-git-lens.png)
