## Introduction

Git peut utiliser 2 méthodes pour s'identifier: HTTP(s) et SSH. L'identification HTTP est plus simple d'utilisation, mais elle est moins rapide et nécéssite d'entrer son identifiant et mot de passe à chaque interaction (à moins de faire "souvenir le mot de passe", ce qui entraîne alors un problème lors du changement trimestriel de mot de passe). Ce tutorial vous guidera pour configurer l'utilisation d'une clée SSH dans SourceTree.

### Générer la clée SSH

Dans SourceTree, cliquez sur "Outils", ensuite "Créer ou importer une clé SSH"
![2018-06-04_14_09_03-Window](/uploads/fa552d8cf7d244d901df51141f629ce7/2018-06-04_14_09_03-Window.png)

Une nouvelle fenêtre s'ouvrira, cliquez "Generate". 
![2018-06-04_14_09_35-PuTTY_Key_Generator](/uploads/b2ef00972fa61770a2c4d5a17f0938cf/2018-06-04_14_09_35-PuTTY_Key_Generator.png)

Vous devrez bouger la sourie **à l'intérieur de la fenêtre** afin de générer des nombres aléatoires. Lorsque le processus sera terminé, vous verrez la partie publique de votre clée SSH apparaître (une clée SSH est composée de 2 parties, un clée publique et une clée privée). Copiez l'entièreté de la clée publique:
![2018-06-04_14_10_16-Window](/uploads/602de903b380ff65b854331933958861/2018-06-04_14_10_16-Window.png)

**Ne fermez pas la fenêtre "PuTTY Key Generator"**, nous y reviendrons dans quelques instants.

### Ajout de la clée sur GitLab

Allez sur notre GitLab (https://git.sarbakan.com) et cliquez sur l'icône de votre profile en haut à droite ([ou en cliquant ici](https://git.sarbakan.com/profile)):

![2018-06-04_14_10_53-Projects___Dashboard___GitLab_-_Chromium](/uploads/a2437cf5d18da84eb6ae133c8c9bd8fa/2018-06-04_14_10_53-Projects___Dashboard___GitLab_-_Chromium.png)

À gauche, cliquez sur "SSH Keys"

![2018-06-04_14_11_19-Window](/uploads/03988d8a4468b5c2a90ac74777048bfe/2018-06-04_14_11_19-Window.png)

Collez votre clée publique dans la boîte prévue à cet effet:

![2018-06-04_14_12_06-SSH_Keys___User_Settings___GitLab_-_Chromium](/uploads/cee39baeedc523e8c36bb276296edf6c/2018-06-04_14_12_06-SSH_Keys___User_Settings___GitLab_-_Chromium.png)

Vous pouvez lui donner un titre (il est possible d'avoir plusieurs clés SSH, par exemple une pour votre ordi au travail et une autre pour votre ordi à la maison). Cliquez sur "Add key".

### Sauvegarder la clée privée

Retournez dans la fenêtre "PuTTY Key Generator", entrez un mot de passe (ce mot de passe servira à décrypter votre clé) et cliquez sur "Save private key", **sauvegardez votre clée privée où bon vous semble.** Attention de ne pas perdre ce fichier. Si vous le perdez, vous devrez reccomencer ce tutoriel.

Vous pouvez maintenant fermer la fenêtre "PuTTY Key Generator".

### Configurer SourceTree pour utiliser notre clée privée

Dans SourceTree, cliquez sur Outils, ensuite sur "Lancer l'agent SSH..."

![2018-06-04_14_13_01-Sourcetree](/uploads/aa0e7d04cbb1878eb166cb162944470e/2018-06-04_14_13_01-Sourcetree.png)

Un petit icône apparaîtra dans votre barre de tâche Windows, cliquez droit sur cet icône et ensuite sur "View Keys".

![2018-06-04_14_13_30-](/uploads/ea6cfd718d3b4b116189cd4051a49b7d/2018-06-04_14_13_30-.png)

Dans la nouvelle fenêtre, cliquez sur "Add Key":

![2018-06-04_14_13_49-Pageant_Key_List](/uploads/2f0affc58f4571575a378a118079a23a/2018-06-04_14_13_49-Pageant_Key_List.png)

Sélectionnez votre clée privée que vous avez sauvegardé plus tôt

![2018-06-04_14_14_01-Select_Private_Key_File](/uploads/e8275e925f96633eda99f4144ec9f9cb/2018-06-04_14_14_01-Select_Private_Key_File.png)

Vous aurez peut-être besoin d'entrer le mot de passe de votre clée privée.

Vous pourrez maintenant utiliser git avec SSH!

### Utilisation

Vous pouvez maintenant cloner les projets en utilisant SSH:

![2018-06-04_14_14_29-sarbakan___unity___UnityFramework___GitLab_-_Chromium](/uploads/9469e214d8c19c88105ed70723ca8d42/2018-06-04_14_14_29-sarbakan___unity___UnityFramework___GitLab_-_Chromium.png)

Pour les projets déjà clonés, vous devrez [changer l'URL](change-remote-url.md) pour celle avec SSH dans SourceTree. Pour ce faire, cliquez sur le bouton "settings" en haut à droite ![settingbutton](/uploads/88f89412565aa9d4dc3b964fe6533270/settingbutton.png)

Sélectionner la ligne avec l'URL, cliquez sur "edit" et changez l'URL pour la version SSH: ![changerurl](/uploads/c7c3943a8ef767201a25cc61c2714742/changerurl.png)

### Ajouter sa clée comme clée par défaut.

Dans les préférences de SourceTree: ![toolsoption](/uploads/751cf789d81f36d05d18fa1de85fafcf/toolsoption.png)

Ajoutez votre clée SHH dans le champs prévu à cet effet (à l'aide du bouton `...`): ![settingssh](/uploads/29e327a248ef100d8365a74850f545de/settingssh.png)

**Redémarrez SourceTree après ces manipulations**

### Problèmes

#### Avertissements
Il est possible que SourceTree vous donne des avertissements lors des premières utilisations de votre clée SSH avec notre GitLab, ceci est normal et ne cause aucun problème, vous n'avez qu'à accepter les avertissements que SourceTree vous donne.

![2018-06-04_14_14_51-](/uploads/8b1af67e0f97abe8dd528c202af47917/2018-06-04_14_14_51-.png)

#### Le bouton "cloner" reste désactivé (gris)
Essayez de redémarrer SourceTree, si le problème persiste, [contactez-nous](https://chat.sarbakan.com/channel/R%2526D-connect)!

#### Problèmes d'authentification avec les sous-modules et/ou la ligne de commande
Ce problème devrait être réglé automatiquement dans le futur (une demande TI a été créé). Pour le régler manuellement, il faut ajouter une variable d'environnement nommée `GIT_SSH` et qui a comme valeur l'emplacement du fichier "plink.exe" de SourceTree, qui est normalement `C:\Program Files (x86)\Atlassian\Sourcetree\tools\putty\plink.exe`

Pour ce faire, ouvrez une invite de commande en tant qu'administrateur:
![cmdAdmin](/uploads/596d5c00fec3f0c43d284c54eee5f6cb/cmdAdmin.png)

Entrez la commande suivante (assurez vous que c'est le bon chemin vers `plink.exe`):
```
setx GIT_SSH "C:\Program Files (x86)\Atlassian\Sourcetree\tools\putty\plink.exe" /M
```

Vous devrez ensuite fermer et réouvrir SourceTree et/ou la ligne de commande concernée.