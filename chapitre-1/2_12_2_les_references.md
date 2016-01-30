### Les références

#### Les adresse mémoires

Avant de pouvoir utiliser les références, il faut comprendre un principe très important. Chaque donnée qui est enregistré en mémoire vive a une adresse.

Cette adresse, sous la forme ```0xFFFFFF``` est généralement codé en hexadécimale et est un nombre entier.

Ainsi, lorsque vous utilisez ou créez une variable, votre logiciel réserve un espace dans la mémoire et y enregistre les données. Ensuite, il peut accéder à cet espace à n'importe quel moment grâce à l'adresse.

#### Obtenir et utiliser l'adresse en C++

Vous vous en doutez, nous pouvons obtenir et manipuler cette adresse en C++. Voici comment obtenir l'adresse d'une variable :

    int number = 9; // Nous créons la variable
    cout << "L'adresse de 'number' est " << &number << endl;
    
Comme vous le voyez, pour obtenir l'adresse mémoire d'une variable il faut la préfixer d'une esperluette, une ```&```.

![](2_12_2_basique.png)


