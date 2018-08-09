
# Quand a-t-on besoin de faire ca?
- Si vous avez des problèmes à clone/fetch/push/pull/etc et que le projet à été déplacé sur gitlab. Vous devriez avoir reçu un courriel avec la commande à exécuter pour changer l'url du projet.
- Quand vous changez de protocole entre HTTP et SSH ([en savoir plus](Configuration-SourceTree-avec-clée-SSH))


# Comment faire?


## En command-line

+ Vous devriez avoir reçu un courriel avec la commande à exécuter pour changer l'url du projet.
+ Il faut exécuter la commande à la racine du projet.
+ La commande ressemble à ce qui suit:  
```
git remote set-url origin ssh://git@git.sarbakan.com:10023/sarbakan/RnD/arcade-analytics/analytics-backend.git
```


## Avec SourceTree
Comme la ligne de commande fait peur, voici comment le faire dans SourceTree:
- 1: Accéder aux settings du projet  
![](img/settings.png)

- 2: Modifier l'URL dans lk'onglet `remotes`  
![](img/edit-remote-url.png)
