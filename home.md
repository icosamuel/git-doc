# Tutoriels et rubriques d'aide pour Git, Gitlab et Sourcetree

## Configuration

* [Utilisation de base de SourceTree et Gitlab](pdf/sarbakan_sourcetree.pdf)

* [Configurer SourceTree pour utiliser une clée SSH](Configuration-SourceTree-avec-clée-SSH)

## Support

* [HTTP Basic: Access denied](http-access-denied)

* `You are not allowed to push code to this project`  
    * C'est la manière de Gitlab de vous avertir que vous n'avez pas les droits sur le projet. Demandez à votre Lead ou à un prog R&D pour les authorizations.

* `Error: cannot lock ref`
    * Il faut faire `git gc --prune=now` dans le terminal (bouton en haut à droite dans sourcetree)

* `The requested URL returned error: 500`
    * Visitez le channel #git de rocketchat pour vérifier si vous êtes le seul à avoir ce problème. Si c'est le cas, mentionnez le problème à votre administrateur Gitlab ou un prog R&D

* `git: 'gud' is not a git command. See 'git --help'.`
    * Utiliser git par command-line est une capacité rare et recherchée. Elle vous offrira une capacité à régler vos problèmes rapide et polyvalente. De plus, toute l'aide en ligne offre des solutions dans ce format!