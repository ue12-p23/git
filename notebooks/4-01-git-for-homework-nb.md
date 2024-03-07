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
  title: git pour les cours
---

Licence CC BY-NC-ND, Thierry Parmentelat & Valérie Roy

```{code-cell}
%%python
from IPython.display import HTML
HTML(filename="_static/style.html")
```

# utiliser `git` pour les devoirs

en supposant que vous avez configuré `git` comme indiqué dans le notebook précédent, vous serez également amenés à produire vos devoirs et à les exposer dans un repo sur github; de cette façon votre professeur pourra avoir toujours accès à votre dernière version

+++

### devoir sans starter code

pour les cours de début d'année, on va vous demander d'écrire des morceaux de code  
selon l'exercice, cela pourra être des notebooks, du code Python, etc...

la façon de faire dépend dans tous les cas de votre professeur, mais voici un *workflow* possible:

- au début du cours, vous créez sur github un repo qui va servir tout au long du cours
  par exemple `https://github.com/jeanmineur/numerique-homework`
  qui vous servira à exposer tous les devoirs que vous ferez pendant le cours de PE
- vous avez le choix de créer le repo public ou privé
  - si public, vous envoyez l'URL du repo à votre prof
  - si privé, vous l'invitez pour qu'il puisse y accéder
- et ensuite pour chaque exercice:
  - vous créez un dossier dans le repo, avec un nom qui désigne l'exercice, par exemple `mandelbrot/` (le prof vous donnera peut-être une consigne précise à ce sujet)
  - vous faites add / commit pendant que vous codez
  - et quand vous êtes satisfait vous faites `push`

quelques conseils dans ce cas de figure:

- installez votre repo local `numerique-homework` dans un dossier qui se situe **en dehors** - typiquement, à coté - du repo du cours
  (il est possible de le mettre dans un sous-dossier, mais l'expérience prouve que les débutants ont tendance à s'emmêler les pinceaux avec ce genre de setup)
- cela signifie que vous aurez un layout qui ressemblera à
  ```console
  /Users/jeanmineur/git/ue12-p23/
  /Users/jeanmineur/git/ue12-p23/numerique/           # <- le repo du cours
  /Users/jeanmineur/git/ue12-p23/numerique-homework/  # <- le repo des exercices
  ```
- et du coup pour faire un TP:
  - vous commencez par aller (avec `cd`) dans le dossier `git/ue12-p23/numerique-homework`
  - vous y créez le dossier de l'exercice, genre
    `mkdir mandelbrot/`
  - vous y allez
    `cd mandelbrot`
  - et à cet endroit vous copiez les éventuels artefacts de l'exercice, .zip ou .py ou autres
  - et ensuite vous n'avez plus qu'à faire les *add* / *commit* / *push*

+++

### devoir avec *starter code*

on pourra également vous donner parfois un TP qui se présente sous la forme d'un repo git déjà constitué
