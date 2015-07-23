## Dialoguons avec l'utilisateur !

C'est bien beau de pouvoir afficher toute sorte de choses dans la console, mais
maintenant nous aimerions dialoguer avec l'utilisateur.

Par exemple, demandons son nom, demandons ce qu'il fait aujourd'hui, on peut
demander absolument tout ce que l'on souhaite !

*Ce chapitre reste assez basique et ne traitera pas de l'intégralité de ce 
sujet.*

Il existe deux méthodes pour réceptionner des informations depuis l'utilisateur
dans la console.

### La première méthode

Nous utilisons le fameux ```cout``` (qui pour rappelle se prononce *c-out* :
Console OUT). Automatiquement par analogie nous allons découvrir le ```cin```
(*c-in*, Console IN). Voici un exemple d'utilisation tout bête :

    #include <iostream>
    
    using namespace std;
    
    int main()
    {
        int revenu;
        
        cout << "Quel est votre revenu mensuel ?" << endl;
        cout << "Mon revenu mensuel est ";
        cin >> revenu;
        
        cout << endl << "Eh beh, " << revenu 
             << " euros, c'est un grand revenu !" << endl;
    }
    
Ici, deux découvertes. Alors oui, on peux décomposer un ```cout``` sur plusieurs
lignes comme je viens de le faire. N'oubliez pas, c'est le ```;``` qui délimite
la fin d'une instruction (dans le cas présent c'est l'instruction ```cout```).
Sauter une ligne ne délimitera jamais une instruction !

Ensuite, on peux voir le fameux ```cin```. Rien de plus simple vous le voyez,
il suffit d'écrire ```cin``` avec les chevrons dans le sens opposé de
```cout``` (car le flux va dans l'autre sens).