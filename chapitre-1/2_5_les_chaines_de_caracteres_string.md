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

Parfois en C++, nous devrons inclure une nouvelle fonctionnalité ou un autre
fichier que nous avons créé. Rien de plus simple, il suffit qu'en haut de votre
fichier texte vous insérez la syntaxe suivante :

    #include <UN FICHIER STANDARD>
    #include "UN FICHIER DE VOTRE PROJET"
    
Par exemple, pour inclure les string dans notre fichier C++, nous écrirons :
```#include <string>``` mais pour inclure un fichier que nous créerons nous
même, nous écrirons plutôt ```#include "monfichier.cpp"```. Notez la
différence ! Mais nous verrons comment fonctionne l'utilisation de plusieurs
fichiers plus tard.

### Comment utiliser les ```string``` ?

Rien de plus simple, prenez ce code et mettez le dans votre IDE.

    #include <iostream>
    #include <string>

    using namespace std;

    int main()
    {
        string name = "Chuck Norris";

        cout << name << endl;
    }
    
Puis lancez l'application et que voyons nous ?

![](Screenshot_2015-07-22_17-30-31.png)

Et oui ! Chuck Norris s'affiche à l'écran, bienvenue dans la magie et la
simplicité du C++ :-D !

Mais, fort heureusement, la puissance des ```string``` ne s'arrête pas là. Nous
pouvons par exemple les concaténer, simplement en utilisant l'opérateur ```+```
entre deux ```string```. Regardez plutôt :

![](Screenshot_2015-07-22_17-35-14.png)

Plutôt simple et efficace.

Je vais maintenant vous présenter une nouvelle notion. Vous devez considérer que
les ```string``` sont un peu comme des grosses variables qui offrent pleins de
possibilités. Par exemple, les ```string``` possèdent comme des informations,
des propriétés qui peuvent être accédées via un ```.``` et avec des ```()``` à la
fin !

Nous verrons le pourquoi du comment, contentez vous d'accepter que c'est une
*méthode d'accès* à des informations ou à des actions. Par exemple pour
connaitre la longueur de votre chaine de caractère, vous devez simplement écrire :

    string name = "Martin";
    cout << name.length() << endl;

Ici la notation est nouvelle. ```length``` veux dire en anglais *longueur*. On
accède donc à la longueur de la chaine concernée via le ```.``` et on termine
la propriété voulue par des ```()``` (vous comprendrez pleinement cette notation
bientôt, ne vous inquiètez pas). Ainsi, écrire ```name.length()``` vous retourne
la longueur de la chaine c'est à dire 6 dans notre cas.

Il existe d'autre méthodes comme ```erase()``` qui permettent de vider 
complètement la chaine et plein d'autres que nous verrons plus tard.

**Attention** : petite subtilité très importante ! Un ```char``` (un caractère)
s'écrit avec des apostrophes alors qu'un ```string``` (une chaine) s'écrit avec
des guillemets !

    char letter = 'a';
    string word = "Hi!";
    
La subtilité est très importante, sinon votre programme risque d'avoir des
comportements indéfinis.