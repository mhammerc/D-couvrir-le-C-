### Les tableau statiques en C++

#### C++11

Qu'est-ce que le C++11 ? Excellente question. Le C++ est un langage en constante évolution, et des *mises à jours* officielles sont à rythme régulier crées. La dernière mise à jour majeure est le C++11, sortie en 2011. La dernière mise à jour qui est mineur est le C++14, sortie en 2014. La prochaine grosse mise à jour qui apportera plein de nouveautés sortira en 2017 avec le C++17.

Le C++11 a apporté de très nombreuses choses, dont les ```array```. Le C++11, bien qu'assez ancien maintenant, n'est peut être pas sur votre machine si vous n'avais pas vos logiciels à jours. Si ce chapitre ne fonctionne pas chez vous, c'est que le C++11 n'est pas activé chez vous. Je vous laisse donc le soin de chercher sur Internet comment l'activer sur notre plateforme.

#### Les mêmes propriétés que les tableaux statiques du C

Les tableaux statiques du C++ proposent les même propriété que celle du C, avec des fonctionnalités en plus. Le nombre d'élément inclu au tableau est **fixe**, vous ne pourez pas rajouter ou supprimer un élément. Le type d'élément que contient le tableau est **fixe** lui aussi, si vous y mettez des ```int```, ce sera toujours des ```int```.

#### Comment les utiliser ?

Tout d'abords, nous devons incluer un nouveau fichier, le fichier **array**.

    #include <array>
    
Ensuite nous les utilisons comme suit :

    #include <array>
    #include <iostream>
    
    int main()
    {
        const int size = 6;
        array<int, size> x = { 1, 2, 3, 4, 5, 6 };
        
        for(int i = 0; i < size; ++i)
            cout << x[i];
    }