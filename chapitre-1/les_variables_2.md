### Les variables, la suite

Les variables sont le pilier central du C++. Alors, vous vous en doutez nous n'aurions pas pu rester avec un seul chapitre sur les variables ! Non, je vais vous torturer avec 4 chapitres d'affilé sur les variables !

Courage moussaillon, je crois en vous !

#### Les allocations mémoires

Nous allons maintenant entrer dans un chapitre d'avantage technique. Nous n'écrirons que très peu de code ici !

Comme vous le savez, une variable est une information qui a une taille (en octet) et qui est stocké dans l'un des supports suivant :

- La mémoire vive (aussi nommé la RAM) (prioritaire)
- Les registres CPU (aussi nommé le cache CPU, L1, L2 et L3)
- Le SWAP (uniquement et seulement si la quantité de RAM n'est pas suffisante)

##### Le SWAP

Les utilisateurs de Linux connaissent d'avantage la notion de SWAP que les utilisateurs Windows. Mais, tous les systèmes modernes (Linux, Mac OS et Windows) connaissent et gère le SWAP à merveille.

Comment faire si votre ordinateur n'a plus de mémoire vive disponible ? Nous ne pouvons pas empêcher les nouvelles allocations mémoire, cela planterai le système. Nous ne pouvons pas libérer de mémoire, cela planterai aussi le système.

Non, la seule solution est de trouver de l'espace supplémentaire. Et cet espace est le SWAP, réservé dans le disque dur de votre ordinateur. Si votre OS ressent le besoin de l'utilisé, il l'utilisera comme de la mémoire vive. Dans votre programme, cela ne fait aucun changement ! En pratique, cela réduira juste le temps de réaction de l'ordinateur (car l'accès au disque dur est plus long que l'accès à la RAM) et cela pourra aussi saturer le taux de lecture/écriture du disque dur.

##### Le registre CPU

C'est ici un domaine que je ne maîtrise que *très peu* vois même pas du tout. Mais sachez toujours que en interne votre CPU crée pleins de mini-variables intermédiaires et que ces variables sont stockés dans le registre CPU. Ces données ne restent pas plus de quelques millisecondes, le temps que le CPU l'utilise et les détruise.

Aussi, si dans votre code vous créez une variable que vous utilisez et supprimez juste après, alors, *peut-être* votre CPU l'enregistrera dans son registre. Tout dépend de votre CPU, de votre compilateur et de l'environnement d'exécution.

##### La durée de vie des variables

Voici un sujet épineux. Ce sujet deviendra tabous lorsque nous commencerons les pointeurs !

Mais pour le moment, parlons du *scope* ou de la portée en français. Un scope se représente par une zone virtuelle dans votre code, généralement entre deux accolades ou imbriqués dans une instruction unique suite à une structure. Je m'explique :

    int main()
    {
      // Du code...
      // Encore du code...
    }
    
Vous avez ici un superbe exemple d'un scope. Tout ce qui se trouve dans la fonction ```main()``` est exécuté dans le scope de ```main()```.

    int main()
    {
        int x = 8;
        
        if(x < 10)
        {
          int y = 0;
          x = 5;
          // Du code...
        }
        
        // Du code...
        
        x = 9;
    }
    
Ici un autre exemple. La variable ```x``` est créé dans ```main()``` qui est son scope. Par contre, ```y``` est aussi créé dans ```main()```, mais son scope est la condition ```if(x < 10)```. En effet, le scope d'une variable est la zone virtuelle la plus proche.

Savez vous ce qu'il se passe pour ```y``` quand le programme sors de la condition ? ```y``` est détruit. Il n'existe plus dans la mémoire et n'est plus accessible ailleurs.

Par contre, ```x``` est toujours utilisable après la condition, et est même utilisable dans la condition car le ```if(x < 10)``` est sous-jacent a scope de ```main()```.

C'est ce que nous appelons la portée des variables. **Dès que le programme sors de la portée d'une variable, alors cette variable est détruite.**

Globalement, les différentes portées qui existent dans le C++, ce sont les fonctions, les conditions, et les boucles.

#### Les limites des variables et leur signatures

Voici pour rappel le tableau que je vous ai présenté dans le premier chapitre sur les variables :

| Mot clé | Description | Taille en octet |
| -- | -- | -- |
| long | Un très grand nombre entier | 8 |
| int | Un nombre entier | 4 |
| short | Un petit nombre entier | 2 |
| char | Représente un caractère ASCII ou un tout petit nombre | 1 |
| float | Représente à nombre à virgule (un nombre flottant) | 4 |
| double | Représente un nombre à virgule avec une *très* grande précision | 8 |
| bool | Représente vrai (true) ou faux (false) | 1 |

Si vous êtes un peu curieux, vous vous êtes peut être posé la question jusque combien peut grandir un ```long```, un ```int```, un ```short``` ou les autres types. Avant de vous donner les limites pratique de ces différents nombre, je dois vous parler de la signature des variables.

##### Les signatures

Toutes les variables ne peuvent pas être signés, non. Seul les nombres peuvent être signés.

Un nombre **signé** est un nombre qui peut être négatif. Un nombre **non signé** peut uniquement être positif. Ainsi, pour un nombre non signé, il peut atteindre ```2^n - 1``` où ```n``` est le nombre de bits.

Prenons l'exemple du nombre entier ```int```. Celui-ci a ```4``` octets, ce qui fait ```4 * 8 = 32``` bits (un octet = 8 bits). Ainsi, un ```int``` non signé peut aller jusque ```2^32 - 1 = 4'294'967'295``` ! Cela fait beaucoup tout de même !

