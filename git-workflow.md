[Retour](home)

### Sommaire

Ce document vous présente une démarche de travail qui s'applique aussi bien au command-line qu'à son utilisation avec SourceTree. Les opérations git seront décrites brièvement ainsi que leur résultats autant en command-line qu'avec Sourcetree.

### Préalables

Les instructions et recommandations dans cet article assument que vous avez lu le dernier article sur [les environments](git-environments). Afin de maximiser la compréhension du sujet exploré, il est fortement conseillé de lire la premiere partie.

# Workflow d'utilisation des opérations Git

![](img/workflow/commands-workflow-reworked.png)

Dans cet article seront présenté en ordre d'utilisation les différentes opérations git 

# Routine-de-Travail



## 1: CHECKOUT

```bash
git checkout feature/new-blue-character
```

## 2: COMMIT

### Staging

```bash
# pour ajouter un ou plusieurs fichiers au staging
git add path/to/my/file.txt
git add tout-le-contenu/de-ce-dossier/*

# pour faire un "stage all"
git add -A

# pour retirer un fichier du staging
git reset path/to/my/file.txt
```

### Commit

SourceTree | Command-line
--- | --- | ---
![](img/operations/commit.jpg) | `git commit -m "votre message +review"` 

## 3: PULL

SourceTree | Command-line
--- | --- | ---
![](img/operations/pull.jpg) | `git pull` 

## 4: PUSH

SourceTree | Command-line
--- | --- | ---
![](img/operations/push.jpg) | `git push` 

```bash
# pour une nouvelle branch
git push --set-upstream origin feature/new-blue-character

# pour une branche qui existe déjà au serveur
git push
```