## Les boucles

Parfois, dans la logique de votre application, vous aurez besoin de répéter une
action x fois. Par exemple vous devez dire bonjour 30 fois. Vous n'allez
pas écrire ```cout << "Bonjour !" << endl;``` 30 fois ! Ce serait du suicide pur
et simple.

Non, les boucles permettent de faire cela automatiquement et super simplement.
Il existe *grosso-modo* 3 types de boucles que nous allons voir ici.

### La boucle ```while```

La boucle ```while``` est clairement la plus simple. Elle fonctionne comme une
condition (si si vous savez, le ```if()```). Tant que l'expression sera
valide (```true```), le contenu du ```while``` s'exécutera (le code entre le ```{``` et le
```}``` ). Voici un exemple assez simple :

    #include <iostream>
    #include <string>
    
    using namespace std;
    
    int main()
    {
        string message;
        
        while(message != "je valide")
        {
            cout << "Vous devez ecrire 'je valide'." << endl;
            getline(cin, message)
        }
    }
    
Ce programme va se contenter de demander à l'utilisateur de rentrer le texte "je
valide". S'il ne le rentre pas, il va lui demander encore et encore.

> **Hint** ```while``` en anglais se traduit ici par *Tant que*. On peut donc lire cette boucle par *Tant que ```message``` n'est pas égal à "je valide", affiche un texte et je remplis la variable ```message``` par le texte que l'utilisateur entrera.*

> **Danger** *Mais attention !* Faites bien attention à l'expression que vous entrerez dans la boucle car si elle reste valide à l'infini (donc tout le temps ```true```), vous serez dans une boucle infinie qui ne cessera jamais ! Elle tournera sans jamais s'interrompre. Votre expression, au bout d'un moment, devra
évaluer à ```false``` au bout d'un moment afin de sortir de la boucle.

### La boucle ```do...while```

La boucle ```do...while``` est une variante de la boucle ```while```. Observez
ce code :

    string message;

    do
    {
        cout << "Vous devez ecrire 'je valide'." << endl;
        getline(cin, message);
    } while(message != "je valide");
    
La boucle ```do...while``` fonctionne exactement comme la boucle ```while``` à
une différence près. En effet si l'expression de votre boucle évalue à ```false```
dès le début, la boucle ne sera jamais exécuté, pas même une seule fois. L'intérêt
de la boucle ```do...while``` est de permettre à la boucle de s'exécuter au moins
une fois quoi qu'il arrive. Par exemple :

    while(false)
        cout << "Bonjour!" << endl;
        
Ici, *Bonjour!* ne s'affichera jamais à l'écran.

    do
        cout << "Bonjour!" << endl;
    while(false);
    
Alors que ici, *Bonjour!* s'affichera une seule fois.

Vous le voyez, j'ai aussi enlevé les accolades ici, si le code tient sur une seule
ligne, vous pouvez les enlever. Mais vous n'êtes pas obligé, tout est question de
goût.


### La boucle ```for```

Voyons directement un exemple :

    for(int i = 0; i < 30; ++i)
    {
        cout << "Bonjour!" << endl;
    }

Comme vous le voyez, ce code dit *Bonjour!* un total de 30 fois. La boucle
```for``` est particulièrement adaptée pour faire un compteur, par exemple.

Cette boucle fonctionne en trois étapes :

* L'initialisation ```int i = 0;``` : on déclare le compteur, cette étape est 
effectuée une seule fois.
* La condition ```i < 30;``` : si c'est condition est fausse, la boucle s'arrête.
* L'action ```++i``` : on incrémente notre compteur. Mais on n'est pas limité à
une simple incrémentation on peut faire ```i += 2``` par exemple. En fait, vous
pouvez mettre n'importe quel instruction ici, mais juste une seule. La plupart du
temps on va incrémenter un compteur. **Surtout ne mettez jamais de ```;``` pour
cette troisième étape!**

Ainsi cette boucle est particulièrement adaptée pour effectuer une action x fois
ou encore pour garder en mémoire le nombre d'itérations de la boucle nécessaires
avant que celle-ci ne se termine. Voici un exemple :

    #include <iostream>
    #include <string>
    
    using namespace std;
    
    int main()
    {
        int i; // Initialisation dans la boucle
        int init = 50;
        int limit = 675;
    
        for(i = init; i < limit; ++i);
    
        cout << "La difference entre " << limit << " et "
             << init << " est de " << i - init << "." << endl;
    }
    
Cet exemple est assez compliqué, je vous propose de le mettre dans votre IDE et
de l'analyser. C'est un algorithme assez simple, complètement inutile mais il
présente bien le principe. Il calcule la différence entre deux nombres
(```init``` et ```limit```).

Vous pouvez remarqué que je n'ai pas mis de bloc de code avec la boucle ```for```,
j'ai directement mis un point virgule. C'est aussi possible avec la boucle
```while``` : ça permet de simplement "attendre" que la boucle soit terminée
sans rien faire (ou dans le cas de la boucle ```for```, en faisant les calculs
du compteur).

### Le petit bonus

Comment faire si, lorsque nous sommes dans une boucle, nous souhaitons en sortir,
**tout de suite** ? Eh bien je vous répondrai : **break;** ! En effet, si
l'instruction ```break;``` est exécutée dans une boucle, le programme sortira
aussitôt de la boucle pour continuer la suite du code. Essayez !