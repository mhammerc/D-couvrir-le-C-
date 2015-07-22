## Les strings

On vient juste de terminer le *premier* chapitre sur les variables et on
enchaine sur... d'autres variables ! Et pour être plus précis sur les
variables de type ```string```.

Les ```string``` vous permettront de stocker des chaines de caractères c'est à
dire des mots, des phrases ou même des romans entier. Leur utilisation est
tout aussi simple que les autres type que nous avons vu.

Par contre, attention ! Ce n'est **pas** un type primitif. Pour rappel un type
primitif est un type qui existe de base en C++ sans la moindre action
supplémentaire. Les ```string``` existe bien de base en C++ mais ont été
codés en C++ avec les types primitif que nous avons vu précédemment.

### Les inclusions

Parfois on C++, nous devrons inclure une nouvelle fonctionnalité ou un autre
fichier que nous avons créé. Rien de plus simple, il suffit qu'en haut de votre
fichier texte vous insérez la syntaxe suivante :

    #include <UN FICHIER STANDARD>
    #include "UN FICHIER DE VOTRE PROJET"
    
Par exemple, pour inclure les string dans notre fichier C++, nous écrirons :
```#include <string>``` mais pour inclure un fichier que nous créerons nous
même nous écrirerions plutôt ```#include "monfichier.cpp"```. Notez la
différence ! Mais nous verrons comment fonctionne l'utilisation de plusieurs
fichiers plus tard.