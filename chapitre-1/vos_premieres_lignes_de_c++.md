## Vos premières lignes de C++

Enfin nous entrons dans le coeur du sujet !

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
plus simple que l'on peux écrire en C++. Je vous laisse cliquer sur la flèche
verte, voici ce qui devrai apparaitre :

![](helloworld.png)

Et vous venez juste de lancer votre premier programme C++, **bravo !**

Maintenant je vous propose de remplacer le texte *Hello World!* par *Vive le
C++ !* et de relancer l'application avec la flèche verte. Voici ce qui devrai
apparaitre cette fois ci :

![](helloworld-2.png)

Nous en concluons donc que la syntaxe ```cout << "[UN TEXTE]" << endl;``` permet
d'afficher du texte à l'écran.

**Première règle :** à la fin de chaque instruction, vous devez mettre un point
virgule, qui marque la fin de cette même instruction.

*cout* est un terme qui signifie *Console OUT*. En d'autres mots, ce terme permet
de sortir des informations depuis l'ordinateur vers l'écran, d'où le sens des
flèches. En effet les flèches ramènent le texte que l'on veux afficher vers
le cout et donc vers l'écran en quelque sorte. On appelle ceci un flux.

Notez que ```endl``` permet de passer à la ligne suivante (*end line*).

**Seconde règle :** le point de départ de toutes applications en C++, sauf
exceptions, se trouve dans la fonction main.

    int main()
    {
        ..
    }
    
Nous verrons plus tard ce que c'est, contentez vous pour le moment
d'écrire votre code entre les accolades qui suivent ```ìnt main()```.

Nous verrons le reste de ce code plus tard, désormais je vous propose
d'entamer un nouveau concept, les variables, qui vont rapidement nous devenir
indispensable.