## Les espaces de noms

Vous utilisez les espaces de noms depuis le début de ce livre sans même vous
en rendre compte.

### Que sont les espaces de noms ?

Imaginez que votre application est contenue dans des boîtes. Chaque boîte est
un espace de nom et contient des fonction, des variables, enfin tout ce que vous
voulez !

Les espaces de noms permettent de *classer*, de *ranger* le code dans des zones
indépendantes les unes des autres. Une fois que vous avez rangé vos fonctions
dans un espace de nom, pour pouvoir utiliser ces fonctions, vous allez devoir
dire "Utilise cet espace de nom" (ou utiliser l'opérateur de portée). Et c'est 
la fameuse instruction ```using namespace std;``` !

### L'espace de nom ```std```

Avec le C++ est fournie une série d'outils plus ou moins utiles qui permettent de
faire absolument plein de choses. Tous ces outils, pour ne pas "concurrencer"
vos propres outils ou d'autres outils venant d'un tiers sont rangés dans
l'espace de nom ```std```.

```std``` est le diminutif de ```standard```. Ce sont les outils *standard* du
C++, ou de son vrai nom la *librairie standard*.

### Les deux manières d'accéder à un espace de nom

Ainsi pour utiliser un espace de nom vous devez écrire ```using namespace```
suivi de son nom puis d'un ```;``` (car c'est une instruction !). A partir de
ce point, tout le reste du fichier actuel aura un accès intégral aux fonctions
de l'espace de nom que vous avez inclus. Par exemple ```using namespace std;```
ou ```using namespace sf;``` pour la [SFML](http://www.sfml-dev.org/index-fr.php).

Mais, il existe une autre manière d'accéder à un composant d'un espace de nom,
via *l'opérateur de portée*. Nous ne l'avons pas encore vu jusqu'ici. Voici un
code qui devrait vous rappeler des souvenirs : 

    #include <iostream>
    
    using namespace std;
    
    int main()
    {
        cout << "Hello world!" << endl;
        return 0;
    }

Le fameux ```Hello world``` ! Nous allons donc supprimer l'instruction
```using namespace std;``` afin d'utiliser à la place l'opérateur de portée.

    #include <iostream>
    
    int main()
    {
        std::cout << "Hello world!" << std::endl;
        return 0;
    }

Comme vous pouvez le deviner, ```cout``` et ```endl``` sont deux composants de
l'espace de nom ```std``` et sont inclus depuis le fichier ```iostream```.

L'utilisation de l'opérateur de portée est simple. Voici la syntaxe :
```ESPACE_DE_NOM::COMPOSANT```. Vous écrivez le nom de l'espace de nom suivi de
deux doubles points (le fameux opérateur de portée). Une fois que l'opérateur de
portée est inséré, vous vous retrouvez **dans** cet espace de nom le temps
**d'une** instruction. Ce qui vous donne le loisir d'utiliser un composant de cet
espace de nom, par exemple ```cout``` !

Ainsi l'utilisation de ```cout``` avec l'opérateur de portée se fait de cette
manière : ```std::cout```.

*Nous étudierons la création d'espaces de noms dans un futur chapitre.*