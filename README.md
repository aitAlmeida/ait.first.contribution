Inspiré par [First Contributions](https://github.com/firstcontributions/first-contributions) de [Roshan Jossey](https://github.com/Roshanjossey)


# Ma première contribution

C'est toujours compliqué la première fois que l'on fait quelque chose. La peur de faire des fautes n'est pas du tout confortable, spécialement quand vous collaborez. Mais le monde du logiciel libre est fait de collaboration et de travail de groupe. Aussi, nous voulons simplifier l'apprentissage des nouveaux contributeurs au logiciel libre en vous enseignant à contribuer pour la première fois.  

Lire des articles et des tutoriels peut aider, mais qu'y a-t-il de mieux que d'essayer sans pouvoir faire d'erreurs ? Ce projet a pour ambition de fournir des conseils et simplifier la manière dont les apprentis font leur première contribution. Souvenez-vous : plus vous êtes serein, mieux vous apprenez. Si vous aspirez à faire votre première contribution, suivez tout simplement les étapes suivantes. Promis, ce sera amusant.

<img align="right" width="300" src="assets/fork.png" alt="embrancher ce repertoire" />

Si vous n'avez pas git sur votre ordinateur, [ installez-le ]( https://help.github.com/articles/set-up-git/ ).

## Embranchez le répertoire (Fork)

Embranchez ce répertoire en cliquant sur le bouton de fork en haut de la page.
Cela va créer une copie du répertoire sur votre compte.

## Clonez le répertoire

<img align="right" width="300" src="assets/clone.png" alt="clonez ce répertoire" />

Maintenant, clonez ce répertoire sur votre ordinateur. Cliquez sur le bouton clone puis cliquez sur l'icone *copier dans le presse-papier*.

Ouvrez un invite de commande et exécutez les commandes git suivantes :

```
git clone "l'url que vous venez de copier"
```
où "l'url que vous venez de copier" (sans les guillemets) est l'url du répertoire. Voir la section précédente afin d'obtenir l'url.

<img align="right" width="300" src="assets/copy-to-clipboard.png" alt="copier l'URL dans le presse-papier" />

Par exemple :
```
git clone https://github.com/aitAlmeida/ait.first.contribution.git 
```
où `votre-nom-d-utilisateur` est votre nom d'utilisateur GitHub. Ici vous êtes en train de copier le contenu du répertoire `first-contributions` depuis GitHub sur votre ordinateur.


## Créez une branche

Déplacez-vous dans le répertoire du projet nouvellement cloné (si vous n'y êtes pas encore) :

```
cd ait.first.contributions
```
Maintenant créez une branche avec le commande `git checkout` :
```
git checkout -b <add-votre-nom>
```

Par exemple :
```
git checkout -b add-ait-contrib
```
(Le nom de la branche n'a pas besoin de contenir le terme *add*, mais c'est raisonnable de l'inclure parce que l'objectif de cette branche est d'ajouter votre nom à une liste.)

## Effectuez les modifications nécessaires et engagez-les

Maintenant, ouvrez le fichier `Contributors.md` dans un éditeur de texte, ajoutez-y votre nom, et enregistrez-le. Si vous ouvrez l'invite de commande et vous exécutez la commande  `git status`, vous verrez qu'il y a des modifications. Ajoutez ces modifications à la branche que vous venez de créer avec la commande  `git add` :
```
git add Contributors.md
```

Maintenant engagez ces modifications avec la commande `git commit`:
```
git commit -m "Add <votre-nom> to Contributors list"
```
en remplaçant `<votre-nom>` par votre nom.

## Envoyer les modifications vers GitHub

Envoyer vos modifications avec la commande `git push` :
```
git push origin <add-votre-nom>
```
en remplaçant `<add-votre-nom>` avec le nom de la branche précédemment créée.

## Soumettez vos changements pour révision

Si vous visitez votre répertoire sur Github, vous verrez un bouton  `Compare & pull request`.  Cliquez sur ce bouton.

<img style="float: right;" src="assets/compare-and-pull.png" alt="create a pull request" />

Maintenant soumettez la demande.

<img style="float: right;" src="assets/submit-pull-request.png" alt="submit pull request" />

Sous peu j'aurai fusionné toutes vos modifications avec la branche master de ce projet. Vous recevrez un mail de notification dès que la fusion sera effectuée.

La branche master de votre embranchement ne subira pas de modification à cet instant. Pour que votre embranchement soit synchronisé avec le mien, suivez les étapes suivantes.

## Gardez votre embranchement synchronisé avec ce répertoire

 D'abord, basculez sur la branche master
 ```
 git checkout master
 ```

 Et ajouter l'url de mon répertoire comme  `upstream remote url` :
```
git remote add upstream https://github.com/aitAlmeida/ait.first.contribution
```
Ceci est une manière de dire à git qu'une autre version de ce répertoire existe à l'adresse spécifiée et que nous l'appelons  `upstream`. Une fois les modifications fusionnées, cherchez la nouvelle version de mon répertoire :
```
git fetch upstream
```

Ici nous cherchons toutes les modification dans mon embranchement  (upstream remote). Maintenant, vous devez fusionner la nouvelle révision de mon répertoire avec votre branche master :
```
git rebase upstream/master
```
Ici nous appliquons toutes les modifications que vous avez cherché à la branche master. Si vous poussez la branche master maintenant, votre embranchement aussi aura les modifications :
```
git push origin master
```
Avertissement: Cette fois, vous poussez au répertoire distant appelé origin.

A ce niveau j'ai fusionné votre branche  `<add-votre-nom>` avec ma branche master, et vous avez fusionné ma branche master avec votre branche master. Votre branche `<add-votre-nom>` n'est plus utile, donc vous pouvez la supprimer :
```
git branch -d <add-votre-nom>
```
et vous pouvez supprimer sa version dans le répertoire distant aussi :
```
git push origin --delete <add-votre-nom>
```
Ceci n'est pas nécessaire, mais le nom de la branche montre que son objectif est assez spécifique. Sa durée de vie peut être courte.