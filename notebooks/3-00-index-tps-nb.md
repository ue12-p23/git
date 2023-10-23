---
jupytext:
  cell_metadata_filter: all,-hidden,-heading_collapsed
  formats: md:myst
  notebook_metadata_filter: all,-language_info,-toc,-jupytext.text_representation.jupytext_version,-jupytext.text_representation.format_version
  text_representation:
    extension: .md
    format_name: myst
kernelspec:
  display_name: Calysto Bash
  language: bash
  name: calysto_bash
language_info:
  help_links:
  - text: MetaKernel Magics
    url: https://metakernel.readthedocs.io/en/latest/source/README.html
  name: bash
nbhosting:
  title: quelques TPs
---

Licence CC BY-NC-ND, Thierry Parmentelat & Valérie Roy

```{code-cell}
%%python
from IPython.display import HTML
HTML(filename="_static/style.html")
```

# quelques TPs pour pratiquer `git`

+++ {"tags": []}

## tp-add-by-lines

````{admonition} les changements ligne par ligne
:class: seealso

quand on a fait plusieurs modifications distinctes, et qu'on veut les grouper en plusieurs commits, il faut pouvoir gérer **finement les ajouts dans l'index**, c'est-à-dire au niveau du bloc ou de la ligne

<https://github.com/ue12-p23/git-tp-add-by-lines>
````

+++ {"tags": []}

## tp-conflict

````{admonition} résoudre un conflit
:class: seealso

un tp à faire individuellement  
on crée délibérément un conflit pour savoir reconnaître les symptômes, et s'entrainer à résoudre le conflit

<https://github.com/ue12-p23/git-tp-conflict>
````

+++

## tp-pending-changes

````{admonition} faire et défaire
:class: seealso

travail individuel

1. créer un repo, ajouter dedans un commit avec un `README.md` vide
1. faites une modification avec vs-code
1. ajoutez-la dans l'index
1. vous changez d'avis, vous ne la voulez plus dans l'index, défaites 3.
1. et en fait vous ne voulez plus du tout de cette modife, vous la jetez complètement
1. on vérifie avec `git status` que le repo est propre
````

on peut envisager deux versions de ce TP

* la plus simple: on fait tout sous vs-code
  * pour 3., il faut chercher **`+`**
  * et assez logiquement pour 4, il faut chercher **`-`**
  * pour 5. le verbe est *discard*
* un peu moins simple: on fait la modife (2.) avec vs-code, et le reste dans le terminal
  * voyez le notebook **`1-05`** pour les commandes à utiliser 

+++

## tp-amend

````{admonition} oops, j'ai raté mon commit
travail individuel

1. créer un repo, ajouter un commit avec un `README.md` vide
1. ajouter du texte dans le `README.md`, mettez ça dans un commit
1. grâce à `git commit --amend`, refaites le commit, et pour cela
  * retouchez le `README.md` sous vs-code
  * ajoutez la nouvelle modife avec `git add`
  * refaites le commit avec `git commit --amend`
1. vérifiez que vous avez bien 2 commits et pas 3, et que le deuxième contient bien ce qu'il faut

````

+++ {"tags": []}

## tp-clone-pull

````{admonition} tirer - pousser: dans le bon ordre
:class: seealso

nos cours sont publiés sur github, et vous les **clonez** chez vous  
puis pour le cours suivant, le prof publie une **nouvelle version** du cours

comment faire pour réconcilier votre copie locale avec la nouvelle version du cours ?

et que se passe-t-il alors exactement dans votre copie locale, si vous avez vous-même fait des changements dans les notebooks ?

ce TP demande une préparation spécifique par groupe  
suivez les instructions de votre enseignant   
une fois que c'est prêt vous devrez visiter une URL **dans le genre de**  
*`https://github.com/ue12-p23/git-tp-clone-pull-groupe1`*  
avec bien sûr le bon numéro de groupe
````

+++ {"tags": []}

## tp-killing-push

````{admonition} vous n'arrivez pas à pousser ?
:class: seealso

vous travaillez à plusieurs dans un repo, et vous n'**arrivez pas à pousser un commit** ?  
c'est sûrement que quelqu'un d'autre a poussé avant vous…

<https://github.com/ue12-p23/git-tp-killing-push>
````

+++ {"tags": []}

## tp-teamwork

````{admonition} en équipe
:class: seealso

un tp plus complet où on simule un travail en groupe  
à faire en groupes de 3 ou 4

<https://github.com/ue12-p23/git-tp-teamwork>
````

+++ {"tags": []}

## tp-pull-request

un TP à faire à deux  

* élève `A` crée un repo sur github, avec du contenu; le repo est **public**
* pour la suite, c'est essentiellement élève `B` qui bosse, élève `A` peut profitablement regarder :)
* élève `B` clone le repo, fait une modification et la met dans un commit
* élève `B` essaie de pousser son nouveau commit dans le github de `A`, mais échoue car il n'a pas les droits
* élève `B` demande à github de lui créer **un *fork***
* élève `B` pousse son commit dans son *fork* (il a le droit cette fois)
* élève `B` crée (dans le repo de `A`) un *pull request**
* élève `A` consulte le pull request, et accepte (merge) le changement
* on vérifie que la modification de `B` est bien dans le repo de `A`

on recommence en inversant les rôles...

````{admonition} indice
:class: tip

dans l'écran de création du PR, il y a un bouton ***"compare across forks"*** qu'il faut cliquer pour pouvoir créer une PR entre deux repos distincts
````

+++

## tp-class-text

un TP à faire à toute la classe

<https://github.com/ue12-p23-git-tp-class-text-reference>

demande une préparation très courte de la part du prof

````{admonition} à faire par le prof
:class: dropdown seealso

à destination des avancés, et pour illustrer le cours, voici comment le prof peut faire la préparation pour cet exo

```bash
  # cloner localement le repo de référence
git clone git@github.com:ue12-p23/git-tp-class-text-reference.git
  # aller dedans
cd git-tp-class-text-reference
  # créer le repo sur github - il faut avoir les droits
gh repo create --public ue12-p23/git-tp-class-text-groupe4
  # ajouter un remote qui pointe vers ce nouveau repo (vide pour l'instant)
git remote add my-group git@github.com:ue12-p23/git-tp-class-text-groupe4.git
  # pousser dedans
git push my-group main
```
````
