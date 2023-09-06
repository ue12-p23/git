---
jupytext:
  cell_metadata_filter: all,-hidden,-heading_collapsed
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
  title: github
---

Licence CC BY-NC-ND, Thierry Parmentelat & Valérie Roy

```{code-cell}
%%python
from IPython.display import HTML
HTML(url="https://raw.githubusercontent.com/ue12-p23/git/main/notebooks/_static/style.html")
```

# github

+++

## c'est quoi ?

jusqu'ici on a vu le socle de git

mais on n'a encore rien dit sur github (ou gitlab ou bitbucket...) qui est un service qui va **au delà** du système git à proprement parler

pour ajouter **une dimension sociale** et offrir des possibilités de collaboration avec .. la terre entière !

+++

## les noms

* chaque **compte** a un nom unique (votre identifiant github par exemple), et  
  on peut ranger autant de repos qu'on veut dans cet espace
* on peut aussi créer des **organisations** (`ue12-p23` par exemple)  
  et pareil, dans une organisation on peut mettre autant de repos qu'on veut
* que ce soit dans un compte ou une orga, l'URL d'un repo est toujours de la forme  
  *https://github.com/le-compte-ou-l-orga/le-nom-du-repo*  
  comme par exemple, pour ce cours justement:  
  <https://github.com/ue12-p23/git>

````{admonition} le remote *origin*
:class: dropdown

toujours au sujet des noms, vous pouvez noter que le plus souvent,
si vous avez dans votre repo local un *remote* qui s'appelle `origin`, 
avec nos pratiques le plus souvent ce remote correspond au repo sur github:

```bash
# pour lister les remotes
$ git remote
origin
# pour voir à quelle URL correspond le remote 'origin'
$ git remote get-url origin
git@github.com:ue12-p23/git.git
```
````

+++

## les accès

* signalons aussi que chaque repo peut être public ou privé  
  pour la suite si on ne précise rien ce sera pour parler de repos publics
* un repo public peut être  
  **lu**, et donc aussi cloné, par tout le monde  
  **écrit** (ou pourra pousser dedans) par une liste finie de gens définie dans les *Settings* du repo
* un repo privé quant à lui peut être  
  **lu** ou **écrit** par une liste finie de gens (idem)

+++

## le workflow usuel

### Alice publie du code

dans un scénario typique:
1. Alice commence à écrire un bout de code - appelons-le `rhubarbe` - sur son ordi
  tout au long du codage, elle le met dans un repo git
1. lorsqu'elle est contente elle va "mettre cela sur github"
  c'est-à-dire créer un repo vide dans `https://github.com/alice/rhubarbe`
  et **pousser** son repo dedans
1. son travail devient donc accessible à tout le monde, et Bob le remarque
1. il télécharge alors le contenu du repo sur son ordi
  avec un `git clone`

+++

### d'autres gens s'en servent: les *Issues*

5. les gens qui utilisent le logiciel ont à leur disposition (dans le repo d'Alice) un espace qui s'appelle ***Issues***
1. dans lequel ils peuvent remercier Alice, poser des questions, signaler des soucis  
   et de manière générale discuter librement autour du projet  
   c'est le premier outil de la dimension sociale de ces plateformes collaboratives  
   ça se passerait dans `https://github.com/alice/rhubarbe/issues`

+++

### Bob modifie le code pour ses besoins

7. à ce stade Bob a tout sur son ordi, il peut modifier ce qu'il veut...
1. toujours en utilisant git bien sûr, il n'a pas besoin de l'avis ni de l'autorisation d'Alice pour créer des commits, c'est tout de même son ordi

+++

### Bob veut soumettre ses changements à Alice : le Fork

9. là par contre ça se corse un peu
   il faut prendre en compte le fait que, si ça se trouve, Alice n'a jamais entendu parler de Bob et ignore même jusqu'à son existence !  
   du coup, pour commencer, Bob ne fait pas partie des gens qui ont le droit de modifier le repo d'Alice
1. pour contourner ça, et pour pouvoir a minima exposer son idée à Alice, Bob va se **créer un fork**  
   un *fork*, c'est tout simplement, **encore un clone** du repo, mais cette fois dans l'espace de Bob,  
   donc dans `https://github.com/bob/rhubarbe`
1. et la différence c'est que cette fois, **Bob a le droit** d'écrire dans ce *fork*
   il peut donc pousser ses nouveaux commits dans ce *fork* repo

+++

### Bob veut soumettre ses changements à Alice : le PR

12. mais ça n'est pas exactement suffisant, car à ce stade Alice n'a toujours aucune connaissance de l'existence de Bob, ni a fortiori de nouveaux commits
1. pour se manifester, Bob va créer ce qu'on appelle un ***PR*** (pour *Pull Request*)
   qui se trouvent ici `https://github.com/alice/rhubarbe/pulls`
1. ce PR est créé **dans le repo d'Alice** en indiquant  
   ￮ où se trouvent les changements proposés (typiquement en indiquant le fork de Bob, et accessoirement dans quelle branche)  
   ￮ et la branche dans le repo d'Alice où on propose de merger les nouveaux commits
1. dans ce PR va se nouer une discussion entre les deux protagonistes
   Alice peut soit refuser complètement, soit accepter tel quel, ou bien le plus souvent demander quelques modifications  
1. pendant cette discussion Bob continue à écrire dans son repo, pour tenir compte des demandes d'Alice
1. enfin, si/quand on arrive à un accord, Alice peut en un clic merger les changements de Bob dans son propre repo  
1. du coup les modifications de Bob profitent à tout le monde  
   et Bob n'a plus besoin de s'embêter à gérer sa version custom de `rhubarbe`  
   et là Bob est très content 🙂
1. et Alice aussi 🙂  
   parce que d'autres peuvent de cette manière la décharger de certains aspects du projet
