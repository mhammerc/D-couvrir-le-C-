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

Vous vous rappelez quand je vous ai expliquer comment créer et utiliser des fonctions ? Nous allons étudier ça plus en détails.

Prenez cet exemple :

    int add(int a, int b)
    {
      return a + b;
    }

    int main()
    {
      int a = 9;
      int b = 10;
      int c = add(a, b);
      
      // ...
    }
    
Dans cet exemple, nous utilisons une fonction qui ajoute deux nombre et retourne le résultat (c'est inutile certes, mais c'est pour l'exemple). Que ce passe t'il en interne ?

* Le logiciel crée deux variables a et b et leur assignent une valeure.
* Le logiciel crée la variable c.
* Le logiciel copie les variables a et b dans deux nouvelles variables temporaire : a' et b'.
* Le logiciel additionne a' et b' et le stocke dans une nouvelle variable temporaire c'.
* Le logiciel supprime a' et b'.
* Le logiciel assigne à c la valeur de c'.
* Le logiciel supprime c'.

Comme vous le voyez, le défaut est que le logiciel crée plusieurs variables inutiles ici. En effet, il crée des variables temporaire pour a et b, qui sont inutiles.
