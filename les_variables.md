## Les variables

Soyons clair, ce chapitre est le **premier** vrai chapitre de programmation. On
ne vas plus observer et modifier, je vais vous apprendre syntaxes, des
manipulations, des règles. Alors comprenez bien ce chapitre dans son intégralité
car partout où vous irez dans la programmation informatique, vous retrouverez
des variables.

### Une variable, c'est quoi ?

C'est une chose que vous allez aimer. Un concept que vous allez adorer. Une
notion que vous [allez] utiliser tous les jours. Oui.

> Une variable permet de stocker une information. Une variable possède une
> durée de vie et est le plus généralement stocké dans la mémoire vive.

Tout simplement !

Par exemple imaginons que vous créez un jeu révolutionnaire et que votre
personnage principal a un nombre de points de vie qui peut *varier*. Nous allons alors
créer une variable pour sauvegarder ce nombre de points de vie pour ensuite
l'afficher à l'écran.

Techniquement parlant, les variables ne sont pas forcément stockés dans la
mémoire vive, étant donné que les processeurs modernes possèdent des registres
relativement grand qui agissent comme une mémoire vive mais encore plus rapide.

### Et en C++, ça donne quoi ?

Tous les langages de programmations possèdent des variables. Mais chacun a ses
spécificités.

Le C++ est un langage fortement typé, c'est à dire que vous **devez** préciser
le type de la variable que vous déclarez (enfin presque, nous verrons dans un
futur chapitre des subtilités). Pas d'inquiètude c'est très simple. Les 
différents types sont par exemple les nombres, ou des caractères.

Prenons un exemple avec ```int``` qui représente un nombre (*integer* qui
signifie entier en anglais).

    int qi;
    qi = 9;
    cout << qi << endl;
    
Placez tout ceci dans le ```main()``` comme je l'ai précisé dans le chapitre
précédent et voyez le résultat !

![](Screenshot_2015-07-21_17-42-09.png)

Pour tous les types que nous allons voir ici, vous pouvez les passer à ```cout```
via l'opérateur de flux ```<<``` afin d'afficher la variable dans la console.

Comme vous le voyez, créer une variable est assez simple, voici la syntaxe :
  
    TYPE NOM;

Voyez plutôt ce code :

    int x; // 1)
    x = 0; // 2)
    
    cout << x << endl;
    
    x = x + 5; // 3)
    
    cout << x << endl;
    
Première nouveauté ici, vous pouvez **commenter** votre code avec //. Placez un
// n'importe où dans votre code et vous pourrez insérer sur tous le reste de la
ligne du texte ou tout ce que vous voulez, ce ne sera pas pris en compte dans le
logiciel.

J'ai ici classé le code en 3 étapes.

+ 1) On **déclare** la variable. On dit que elle doit être réservé dans
la mémoire, désormais elle nous appartient.
+ 2) On **initialise** la variable. En effet la variable était créée mais était
inutilisable car elle n'avais aucune valeur. Ici on lui donne une valeur, 
c'est à dire zéro.
+ 3) On **assigne** une nouvelle valeur à la variable. Cette valeur vaut ```x + 5```
c'est à dire ```0 + 5``` donc désormais ```x``` vaut 5.

Normalement si tout se passe bien votre console affichera 0 puis 5 sur des lignes
différentes.

**Attention**, vous devez **toujours** initialiser une variable avant de
l'utiliser. Sinon votre programme pourra réagir étrangement ou avoir des
comportements indéfinis. Si vous le souhaitez vous pouvez lui donner une valeur
dès sa déclaration, ce qui emboîte les deux étapes :

    int x = 0;
    
Voici les différents type de variable que nous allons voir dans ce chapitre :

| Mot clé | Description | Taille en octet |
| -- | -- | -- |
| long | Un très grand nombre entier | 8 |
| int | Un nombre entier | 4 |
| short | Un petit nombre entier | 2 |
| char | Représente un caractère ASCII ou un tout petit nombre | 1 |
| float | Représente à nombre à virgule (un nombre flottant) | 4 |
| double | Représente un nombre à virgule avec une *très* grande précision | 8 |
| bool | Représente vrai (true) ou faux (false) | 4 |

Ce ne sont que des types primitifs c'est à dire qu'ils sont inclus de base dans
le C++ sans aucune manipulation supplémentaire. Notez que chacun de ces types
supportent les nombres négatifs. Voici des exemples d'utilisation
de ces types :

    float flottant = 8.9;
    char lettre = 'c';
    bool condition = true;
    
    std::cout << flottant << endl << lettre << endl << condition << endl;

Ce qui affichera :

![](Screenshot_2015-07-21_18-21-35.png)

Notez que le type ```bool``` affiche 1 s'il vaut ```true``` sinon il affiche 0. Nous
verrons par la suite comment utiliser un boolean pour établir des conditions.

Bien sur, nous pouvons utiliser nos variables avec des opérateurs. Ces opérateurs
nous permettent de calculer un peu tout et n'importe quoi, les voilà :

| Nom | Symbole | Exemple |
| -- | -- | -- |
| Addition | + | ```int x = 5 + 8; // 13``` |
| Soustraction | - | ```int x = 5 - 8; // -3``` |
| Multiplication | * | ```int x = 5 * 8; // 40``` |
| Division | / | ```int x = 10 / 2; // 5``` |
| Reste de la division (modulo) | % | ```int x = 10 % 3; // 1``` |

Leur utilisation est très simple comme vous le voyez. Dans les exemples fourni,
on calcule l'opération avec des valeurs fixes mais vous pouvez tout aussi bien
mettre des variables du même type à la place des nombres.

Chacun de ces opérateur a une variante. Au lieu d'écrire 30 lignes pour
l'expliquer, je vais vous le démontrer avec un exemple :

    int x = 5;
    x += 8; // Revient à écrire x = x + 8;
    x -= 8; // Revient à écrire x = x - 8;
    x *= 8; // Revient à écrire x = x * 8;
    //etc...
    
Se conclue ainsi le chapitre sur les variables. Gardez bien en tête que ce n'était
qu'une très brève introduction et nous verrons les variables plus en détail
plus tard. Pour l'instant je vous propose d'étudier un nouveau type, les 
```string``` !

