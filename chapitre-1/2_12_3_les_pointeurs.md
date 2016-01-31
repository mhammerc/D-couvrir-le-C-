### Les pointeurs

Autant en C que en C++, les pointeurs sont... mythiques.

Beaucoup prennent peur et s'enfuit lâchement à la vu des pointeurs. Mais, la vérité sur les pointeur c'est qu'il faut bien les comprendre. Une fois assimilé et compris, vous verrez c'est ultra-simple.

#### Le principe

On pourrais confondre les pointeurs avec les références. En effet, ils permettent tous les deux d'accéder à une donnée qu'ils ne possèdent pas.

Mais, leur fonctionnement est complètement différent. Avec les variables normales et les références, nous ne contrôlons pas nous même la mémoire. En effet, vous créez une variable normale et votre logiciel alloue une zone de la mémoire automatiquement pour vous. Si votre variable est détruite, alors la zone de la mémoire allouée l'est aussi instantanément.

Avec les pointeurs vous contrôlez vous même la mémoire. Et toute la difficulté est là ! Si vous allouez de la mémoire mais que vous oubliez de la libérer, vous aurez alors une fuite de mémoire.

Les fuites de mémoires sont mortelles ! Imaginez un logiciel qui consomme 4 Gb de mémoire vive alors qu'en réalité il n'en utilise que 200 Mb. Pourquoi ? Parceque il a alloué de la mémoire mais a oublié de la libérer. Vous comprendrez mieux après.

#### La pratique

En pratique un pointeur est une variable à part entière. Plus en détail, c'est un nombre. Et ce nombre représente une adresse mémoire.

Je m'explique. Comme nous l'avons vu dans le chapitre précédent, toute donnée dans la mémoire vive a une adresse qui lui est propre. Un pointeur enregistre donc cette adresse pour que vous puissiez y accéder. Il **pointe** donc sur la donnée.

Voici un code d'exemple ainsi que son résultat.

    int *ptr = new int(9);

    cout << "Valeur de la valeur pointee : " << *ptr << endl;
    cout << "Adresse de la valeur pointee : " << *&ptr << endl << endl;
    cout << "Valeur du pointeur : " << ptr << endl;
    cout << "Adresse du pointeur : " << &ptr << endl << endl;

    cout << "Suppression de la valeur pointee..." << endl << endl;
    delete ptr;
    ptr = nullptr;

    //cout << "Valeur de la valeur pointee : " << *ptr << endl;
    //cout << "Adresse de la valeur pointee : " << *&ptr << endl << endl;
    cout << "Valeur du pointeur : " << ptr << endl;
    cout << "Adresse du pointeur : " << &ptr << endl;

    cin.ignore();

![](2_12_3_les_ptr.png)

Il est très important de comprendre à la perfection ce que vous voyez ici.

##### La création des pointeurs

Il est maintenant temps pour vous d'apprendre à utiliser les pointeurs. Voici comment créer un pointeur :

    TYPE * NAME;
    
En C++, le symbole caractéristique du pointeur est une ```*```. A chaque fois que vous verrez une étoile en C++, c'est qu'un pointeur n'est pas très loin. Comme vous le savez, le pointeur est un *nombre* qui pointe sur une donnée. Donc comme toujours en C++, nous devons donner un type à cette donnée.

Je vous ai dit que les pointeurs permettent de gérer manuellement la mémoire. En fait c'est *faux*. Ce ne sont pas les pointeurs qui permettent de gérer la mémoire mais les opérateurs ```new``` et ```delete```. Comme leur nom l'indique, ```new``` permet de d'allouer de la mémoire alors que ```delete``` permet de la récupérer.

Voici comment allouer de la mémoire : 

    new TYPE;
    
Cela s'appelle l'allocation dynamique. L'opérateur ```new``` va donc allouer dans votre mémoire une zone pour le type ```TYPE``` que vous avez demandé. Et, cette instruction retourne l'adresse mémoire de l'allocation fraîchement effectuée. Or, comme vous le savez, un pointeur sauvegarde les adresses mémoires. Alors fusionnons les !

    TYPE * NAME = new TYPE;
    
Cette instruction va simplement allouer une zone mémoire du type ```TYPE```, et il assignera alors au pointeur ```NAME``` l'adresse de cette mémoire pour que vous puissiez l'utiliser. Si vous souhaitez, vous pouvez aussi assigner directement une valeur après l'initialisation :

    TYPE * NAME = new TYPE(VALUE);
    
Ainsi, voici un exemple en pratique (cf. le code au dessus)

    int *ptr = new int(9);
    
> **Danger** Attention ! Si vous initialisez un pointeur sans l'assigner (donc sans lui donner de valeur), vous faites erreur. Vous devez **toujours** assigner une valeur à votre pointeur. En effet, le pointeur risque de pointer sur une variable aléatoire sur votre ordinateur, et vous pourriez alors créer des instabilités sur votre système. Ainsi, si vous créez un pointeur que vous voulez laisser vide, faites comme suit : ```int *ptr = nullptr```. La constante ```nullptr``` provient du C++11 et est essentielle.
    
##### L'utilisation des pointeurs

Maintenant que nous avons notre pointeur, comment pouvons nous l'utiliser ? Rien de plus simple.

Pour accéder à la valeur que le pointeur pointe, utilisez l'opérateur ```*``` (oui encore).

Regardez plutôt :

    int *ptr = new int(9);
    int value = *ptr;
    
Alors, ```value``` vaudra ```9```. Par contre, si vous enlevez l'étoile, vous accéderez à l'adresse mémoire de la valeur pointée. Par exemple :

    int *ptr = new int(9);
    cout << *ptr << endl; // Affichera 9
    cout << ptr << endl; // Affichera l'adresse mémoire de la valeur pointée
    
C'est tout ! Et oui c'est aussi simple !

##### La suppression de la mémoire allouée

Si vous allouez de la mémoire dynamiquement avec l'opérateur ```new```, celle-ci ne sera jamais libéré autrement que par vous même. Vous **devez** donc la libérer aussi tôt que vous ne l'utilisez plus. Pour ce faire, utiliser l'opérateur ```delete```. Il suffit de donner à cet opérateur une adresse mémoire, et il va libérer la mémoire.

    int *ptr = new int(9); // Allocation de la mémoire
    delete ptr; // Libération de la mémoire
    
#### Analysons l'exemple

Pour rappel, je vous redonne l'exemple :

![](2_12_3_les_ptr.png)

Voici l'analyse en détail instruction par instruction.

* Nous allouons un ```int```, nous lui assignons la valeur ```9``` et nous créons et assignons un pointeur sur cette même mémoire.
* Nous affichons la valeur du nombre grâce à l'opérateur ```*```.
* Nous affichons l'adresse mémoire du nombre en pointant dessus puis en demandant son adresse (voir chapitre précédent) grâce aux deux opérateurs ```*&```.
* Nous affichons la valeur du pointeur en lui même (valeur identique à l'adresse mémoire du nombre comme vous pouvez le voir).
* Nous affichons l'adresse du pointeur en lui même.
* Nous supprimons le nombre et remettons le pointeur à zéro.
* Nous ne pouvons plus afficher la valeur pointée ni l'adresse de la valeur pointée car celle-ci n'existe plus. Laisser ces deux lignes commentées résultera en un plantage de votre application.
* Nous affichons la valeur du pointeur en lui même (qui vaut donc ```0```, c'est à dire ```nullptr```).
* Et enfin nous affichons l'adresse du pointeur qui n'a pas changé.

Si vous avez bien suivi, vous devriez désormais être capable de comprendre et d'utiliser cet exemple. Voici maintenant des petites astuces d'utilisations.

#### Lier un pointeur à une variable classique

Si un jour vous aimeriez que votre pointeur pointe sur une variable normale, vous devrez utiliser l'opérateur ```&```, qui pour rappel permet d'obtenir l'adresse mémoire d'une variable.

    int x = 10;
    int *ptr = &x;
    cout << *ptr << endl; // Affichera 10;
    
> **Hint** Notez que vous devez utiliser ```delete``` que si la mémoire a été créé par l'opérateur ```new```. Ici, vous n'avez pas besoin de libérer la mémoire par vous même car le propriétaire de la mémoire est une variable classique : quand elle sera détruite, la mémoire le sera aussi.
    
#### Les pointeurs et les fonctions

Il peut être très utile d'utiliser les pointeurs avec des fonctions. En effet, en somme, un pointeur n'est qu'un nombre donc très rapide à copier. Beaucoup plus rapide que copier une grosse variable ! Donc n'hésitez pas à passer des pointeurs dans les fonctions.

    int add(int * a, int * b)
    {
        return *a + *b;
    }
    
    int main()
    {
      int *a = new int(9);
      int *b = new int(12);
      
      int c = add(a, b);
      
      delete a;
      a = nullptr;
      delete b;
      b = nullptr;
    }
    
#### Le pourquoi du comment !

Je vais vous fournir une petite dernière explication pour ceux qui n'auraient pas encore très bien compris.

Voici une variable classique :

    int x = 0;
    
Ici, ```x``` représente la variable en elle même. ```x``` **est** la mémoire. Ainsi, si ```x``` est détruit, alors la mémoire est libéré.

Voici un pointeur :

    int *ptr = new int(0);
    
Nous avons ici ```ptr```. C'est un nombre qui représente l'adresse mémoire d'une autre variable (un nombre aussi ici). Si ```ptr``` est détruit, le nombre qui représente l'adresse mémoire du second est aussi supprimé, mais pas le second nombre.

    delete ptr;
    
Cette instruction ne vas pas détruire ```ptr```. Elle va détruire ```*ptr```, c'est à dire la variable que pointe ```ptr```.

Vous allez peut être me détester, mais après cette grosse leçon je vais vous informer que... j'ai mieux que les pointeurs ! Les *pointeurs intelligents*.