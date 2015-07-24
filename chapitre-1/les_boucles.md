## Les boucles

Parfois, dans la logique de votre application vous aurez besoin de répéter une
action x fois. Par exemple vous devez dire bonjour 30 fois. Vous n'allez
pas écrire ```cout << "Bonjour !" << endl;``` 30 fois ! Se serai du suicide pur
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

```while``` en anglais se traduit ici par **Tant que**. On peut donc lire cette
boucle par *Tant que ```message``` n'est pas égal à "je valide", affiche un 
texte et rempli la variable ```message``` par le texte que l'utilisateur
entrera.*

**Mais attention !** Faites bien attention à l'expression que vous entrerez dans
la boucle car si elle reste valide à l'infini (donc tout le temps ```true```),
vous serez dans une boucle infinie qui ne cessera jamais ! Elle tournera sans
jamais s'interrompre. Votre expression, au bout d'un moment, selon la logique
de votre application doit évaluer à ```false``` au bout d'un moment afin
de sortir de la boucle.

### La boucle ```do...while```

La boucle ```do...while``` est une variante à la boucle ```while```. Observez
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

Vous le voyez j'ai aussi enlevé les accolades ici, si le code tient sur une seule
ligne vous pouvez les enlever. Mais vous n'êtes pas obligé, tout est question de
préférences et d'habitudes.