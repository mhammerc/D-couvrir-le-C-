### Les pointeurs

Autant en C que en C++, les pointeurs sont... mythiques.

Beaucoup prennent peur et s'enfuit lâchement à la vu des pointeurs. Mais, la vérité sur les pointeur c'est qu'il faut bien les comprendre. Une fois assimilé et compris, vous verrez c'est ultra-simple.

#### Les allocations mémoires

##### Le principe

On pourrais confondre les pointeurs avec les références. En effet, ils permettent tous les deux d'accéder à une donnée qu'il ne possèdent pas.

Mais, leur fonctionnement est complètement différent. Avec les variables normales et les références, nous ne contrôlons pas nous même la mémoire. En effet, vous créez une variable normale et votre logiciel alloue une zone de la mémoire automatiquement pour vous. Si votre variable est détruite, alors la zone de la mémoire allouée l'est aussi instantanément.

Avec les pointeurs vous contrôlez vous même la mémoire. Et toute la difficulté est là ! Si vous allouez de la mémoire mais que vous oubliez de la libérer, vous aurez alors une fuite de mémoire.

Les fuites de mémoires sont mortelles ! Imaginez un logiciel qui consomme 4 Gb de mémoire vive alors qu'en réalité il n'en utilise que 200 Mb. Pourquoi ? Parceque il a alloué de la mémoire mais a oublié de la libérer. Vous comprendrez mieux après.

#### La pratique

En pratique un pointeur est une variable à part entière. Plus en détail, c'est un nombre. Et ce nombre représente une adresse mémoire.

Je m'explique. Comme nous l'avons vu dans le chapitre précédent, toute donnée dans la mémoire vive a une adresse qui lui est propre. Un pointeur enregistre donc cette adresse pour que vous puissiez y accéder. Il **pointe** donc sur la donnée.

Regardez plus tôt :

![](2_12_3_les_ptr.png)

Il est très important de comprendre à la perfection ce que vous voyez ici. Premièrement, concentrons nous sur le code.

##### L'opérateur ```new``` et ```delete```

Vous savez que les pointeurs permettent de gérer manuellement la mémoire. En fait c'est *faux*. Ce ne sont pas les pointeurs qui permettent de gérer la mémoire mais les opérateurs ```new``` et ```delete```. Comme leur nom l'indique, ```new``` permet de d'allouer de la mémoire alors que ```delete``` permet de la récupérer.