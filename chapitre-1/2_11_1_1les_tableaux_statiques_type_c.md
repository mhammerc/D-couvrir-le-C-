### Les tableaux statiques type C

En C++, il existe de nombreuses méthodes pour créer des tableaux, chaque méthode
ayant ses particularités. Nous allons étudier 3 méthodes ici et dans les
prochains chapitres, et nous découvrirons les autres prochainement.

Comme vous le savez, le C++ hérite du C. Tout ce qui existe en C existe aussi en
C++ ! Cela doit vous faire une belle jambe vu que vous ne connaissez pas le C.
Mais certaines notions du C sont tellement ancrés en C++ malgré tout qu'elles sont
encore utilisés. Ici nous allons étudier les tableaux statiques, héritage du C.

> **Info** Nombreuses sont les personnes qui utilisent encore ces tableaux, et
il n'est pas interdit de continuer à les utiliser. Nous verrons dans le
prochain chapitre l'équivalent en C++ des tableaux statiques.

Comme je vous l'ai dit, les tableaux servent à stocker plusieurs valeurs dans
une seule variable. Vous l'avez peut être remarqué, les variables que nous
avons étudié jusqu'ici ne contiennent qu'une valeur : un nombre ou une chaine
de caractère.

Ici nous allons découvrir comment stocker plusieurs nombres dans une seule
variable.

La particularité des tableaux statiques (contrairement aux tableaux dynamique)
est que leur taille est fixe. Si vous décidez d'y placer 42 éléments, le
tableau aura **toujours** 42 éléments.

#### L'opérateur ```[]```

Cet opérateur est l'élément clé qui va nous permettre d'utiliser et de créer des
tableaux. Pour rappel, la syntaxe de définition d'une variable classique est :

    TYPE NAME;
    
Désormais, pour créer un tableaux, la syntaxe sera :

    TYPE NAME[SIZE];
    
Où ```TYPE``` est le type des éléments contenu dans le tableau, ```NAME``` le
nom du tableau et ```SIZE``` la taille du tableau (le nombre d'éléments).

Notez les crochets qui entourent ```SIZE``` juste après le nom de la variable.
C'est le fameux opérateur ```[]```.