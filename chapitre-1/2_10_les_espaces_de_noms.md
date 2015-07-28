## Les espaces de noms

Vous utilisez les espaces de noms depuis le début de ce livre sans même vous
en rendre compte. Mais c'est quoi cette drôle de bête ?

### Que sont les espaces de noms ?

Imaginez que votre application est contenu dans des boites. Chaque boite est
un espace de nom et contient des fonction, des variables, enfin tout ce que vous
voulez !

Les espaces de noms permettent de *classer*, de *ranger* le code dans des zones
indépendantes les unes des autres. Après une fois que vous avez rangé vos fonctions
dans un espace de nom, pour pouvoir utiliser ces fonctions, vous allez devoir
dire "Utilise cet espace de nom". Et c'est la fameuse instruction
```using namespace std;``` !

### L'espace de nom ```std```

Avec le C++ est fourni un série d'outils plus ou moins utiles qui permettent de
faire absolument pleins de choses. Tout ces outils, pour ne pas "concurrencer"
vos propres outils ou d'autres outils venant d'un tierce sont rangés dans
l'espace de nom ```std```.

```std``` est le diminutif de ```standard```. Ce sont les outils *standard* du
C++, ou de son vrai nom la *librairie standard*.