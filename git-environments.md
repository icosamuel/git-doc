[Retour](home)

### Sommaire

Ce document vous présente les différents environments dans lesquels peuvent vivre des changements git. Toutes forme de modification, ajout ou suppression est enregistrée dans git comme un changement. Nous verront dans cet article quels sont les divers environments et comment ils interagissent entre eux.

### Préalables

Les instructions et recommandations dans cet article assument que vous avez un projet de cloné sur votre poste ainsi que l'authentification de base pour communiquer avec le serveur Gitlab. Pour plus d'info, voyez [ce pdf](pdf/sarbakan_sourcetree.pdf)

# Environements

![](img/workflow/environments.jpg)

## Workspace

![](img/workflow/icons-workspace.jpg) 

C'est ici que votre travail est fait. Dans cet environnement, vous éditez les fichiers du projet avec votre éditeur préféré, avec VSCode, Unity, Maya ou Cubase. Il s'agit de **votre copie de travail** et c'est aussi ce que vous pouvez naviguer avec l'explorateur de fichiers windows: 

![](img/workflow/windows-explorer.jpg)

Pensez du Workspace comme votre copie de travail que vous pouvez modifier dirrectement. C'est aussi celle qui sera modifiée lorsqu'on `pull` ou on `checkout`. Le workspace est central à notre workflow de travail, puisqu'il est l'endroit ou toutes vos modification vont avoir lieu. 

On peut le repérer dans SourceTree à l'aide de l'écran de `File Status` ou encore dans l'historique comme une ligne qui est toujours au dèssus de la liste au nom de `uncomitted changes`

![](img/workflow/uncommited-changes.jpg)

À partir de cet environnement, on peut passer des changements à l'[index](#index) ou au [stash](#stash).

## Index

![](img/workflow/icons-index.jpg) 

L'index représente le **Staging Area** (Dans SourceTree). Tout ce qui se trouve dans la section `Staged Files` est considéré dans l'index. C'est une étape nécessaire lorsqu'on veut commiter nos changements.

![](img/workflow/staging-area.jpg)

De cet endroit, on peut faire un `commit` pour enregistrer nos changement au [Local Repository](#local-repository) ou les retirer du staging area pour les enlever de l'index. L'index fait partie du [Workspace](#workspace). C'est-à dire, tous les fichiers qui sont dans l'index sont considérés aussi dans le [Workspace](#workspace).

On peut facilement savoir ce qui est dans l'index avec la ligne de commande `git statut` en voici un exemple ou on a deux fichiers modifiés dans l'index (`Changes to be committed`).

```bash
$ git status 
On branch workflow
Your branch is up to date with 'origin/workflow'.

Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	modified:   img/workflow/commands-workflow.png
	modified:   workflow.md
```

## Local-Repository

![](img/workflow/icons-local-repo.jpg) 

Le répertoire local représentes **votre historique de commits** ainsi que toutes les branches que vous avez déjà `checkout`.

Les branches qui font partie de votre répertoire local sont facile à identifier dans la liste de gauche (SourceTree). Elles font partie de la liste de `Branches`. Quant aux branches du serveur, elles se trouvent dans la liste `Remotes`.

![](img/workflow/checkout.jpg)

Les opérations `clone`, `push`, `pull` et `fetch` sont essentiellement là pour synchroniser le répertoire local du [répertoire serveur](#remote-repository). Et c'est cette étape qui vous permet de partager votre travail avec vos collègues ainsi que récupérer le leur.

## Remote-Repository

![](img/workflow/icons-remote-repo.jpg) 

Le Répertoire distant existe sur notre serveur [Gitlab](https://git.sarbakan.com). Le répertoire Distant est le seul endroit que toute l'équipe peut accéder. C'est grâce à lui si on peut partager notre travail avec notre équipe.

On peut repérer les branches distantes à l'aide du mot clef `origin` (qui est le nom du remote par défaut). Donc par exemple, la branche `origin/FrankenBranch` peut être repérée dans l'historique de commits par son icone portant son nom. On peut aussi les repérer avec la ligne de commande `git branch --all`

```
$ git branch --all
  master
* FrankenBranch
  remotes/origin/master
  remotes/origin/FrankenBranch
```

![](img/workflow/commit-history.jpg)

Pour qu'on puiss travailler avec le répertoire distant ([Gitlab](https://git.sarbakan.com)), il faut fournir à notre répertoire local un URL. Cet url est celui que l'on va chercher sur Gitlab et qui sert à faire le `clone`. On doit parfois changer cette addresse comme expliqué dans [cet article](change-remote-url). Cet url ressemble à quelquechose comme ce qui suit:

```bash
# protocole HTTPS
https://git.sarbakan.com/sarbakan/unity/unity-projects/01733_Playmobil_Crystal_Palace_app.git

# protocole SSH
ssh://git@git.sarbakan.com:10023/sarbakan/unity/unity-projects/01733_Playmobil_Crystal_Palace_app.git
```

## Stash

![](img/workflow/icons-stash.jpg) 

Le Stash est un outil de travail vraiment intéressant. Mais il n'est absolument pas nécessaire afin de travailler. 

Un stash est un groupe de changements (`change-set`) qui est entreposé à l'extérieur du [Workspace](#workspace) et de l'[Index](#index). Il est très utile lorsqu'on doit effectuer un `merge` ou encore lorsqu'on souhaite `commiter` nos changements sur une autre branche. Il s'agit donc d'un espace de mémoire pour y stocker des changements afin de nous permettre d'effectuer des opérationt qui nécessitent un index vide. Il est comparable à un `commit` qui n'est sur aucune branche et que l'on peut développé lorsqu'on le souhaite sur nimporte quelle branche.

Nous verrons des cas d'utilisations dans la prochaine partie.

# Intéractions entre les environments

Maintenant que vous avez une bonne compréhension des divers environments par lesquels nos changements peuvent passer, vous comprendrez beaucoup mieux le schéma suivant qui représente les interactions entre les environments dans git.

![](img/workflow/commands-workflow-reworked.png)

Pour plus de détails sur les opérations (interactions entre les environments) continuez votre lecture sur le [workflow d'opérations git](git-workflow) ou un article en anglais plus technique [ici](https://blog.osteele.com/2008/05/my-git-workflow/)