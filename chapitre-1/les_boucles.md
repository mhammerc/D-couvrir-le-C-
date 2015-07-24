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