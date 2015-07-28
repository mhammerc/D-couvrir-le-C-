## Vos premières lignes de C++

Enfin nous entrons dans le cœur du sujet !

Normalement vous avez ce code-ci à l'écran (après avoir créé un nouveau projet)
:

    #include <iostream>
    
    using namespace std;
    
    int main()
    {
        cout << "Hello World!" << endl;
        return 0;
    }

Ce code vous parait peut être compliqué mais c'est en réalité le programme le
plus simple que l'on peut écrire en C++. Je vous laisse cliquer sur la flèche
verte, voici ce qui devrait apparaitre :

![](2_3_helloworld.png)

Et vous venez juste de lancer votre premier programme C++, **bravo !**

Maintenant je vous propose de remplacer le texte *Hello World!* par *Vive le
C++ !* et de relancer l'application avec la flèche verte. Voici ce qui devrait
apparaître cette fois ci :

![](2_3_helloworld-2.png)

Nous en concluons donc que la syntaxe ```cout << "[UN TEXTE]" << endl;``` permet
d'afficher du texte à l'écran.

> **Info** *cout* est un terme qui signifie *Console OUT*. En d'autres mots, ce terme permet de sortir des informations depuis l'ordinateur vers l'écran, d'où le sens des flèches. En effet les flèches ramènent le texte que l'on veut afficher vers le cout et donc vers l'écran, en quelque sorte. On appelle ceci un flux.


> **Info** Notez que ```endl``` permet de passer à la ligne suivante (*end line*).

**Première règle :** à la fin de chaque instruction, vous devez mettre un point
virgule, qui marque la fin de cette même instruction.

**Seconde règle : Ne JAMAIS oublier la première règle.**

> **Danger** Oublier un ```;``` est très dangereux. Déjà il empêchera votre logiciel de fonctionner, puis vous chercherez bêtement pendant 3 heures où est le problème jusqu'à ce que vous vous rendez compte que le problème est simplement un ```;``` qui manque. Croyez-moi, ceci est arrivé à tout le monde et vous arrivera ! Les effets secondaires de cet oubli sont très dangereux comme *la dépression*, *l'abandon de la lecture de ce livre* et bien d'autres... Soyez avertis ! Considérez cela comme la sélection naturelle, celui qui oublie le ```;``` n'arrivera pas à coder en C++ et sera naturellement éliminé. Alors prenez votre courage à deux main et n'oubliez jamais le ```;``` !

**Troisième règle :** le point de départ de toutes applications en C++, sauf
exceptions, se trouve dans la fonction main.

    int main()
    {
        ..
    }
    
Nous verrons plus tard ce que c'est, contentez vous pour le moment
d'écrire votre code entre les accolades qui suivent ```ìnt main()```.

Nous verrons le reste de ce code plus tard, désormais je vous propose
d'entamer un nouveau concept, les variables, qui vont rapidement nous devenir
indispensables.