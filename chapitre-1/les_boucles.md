## Les boucles

Parfois, dans la logique de votre application vous aurez besoin de répéter une
action x fois. Par exemple vous devez dire bonjour 30 fois. Vous n'allez
pas écrire ```cout << "Bonjour !" << endl;``` 30 fois ! Se serai du suicide pur
et simple.

Non, les boucles permettent de faire cela automatiquement et super simplement.
Il existe *grosso-modo* 3 types de boucles que nous allons voir ici.

### La boucle ```while```

La boucle ```while``` est clairement la plus simple. Elle fonctionne comme une
condition (si si vous savez, le ```if()```) mais tant que l'expression sera
valide, le contenu du ```while``` s'exécutera (le code entre le ```{``` et le
```}``` ). Voici un exemple assez simple :

    #include <iostream>
    #include <string>
    
    using 