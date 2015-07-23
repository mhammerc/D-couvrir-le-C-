## Les conditions

Allez on garde du courage, on ne désespère pas ! Ce chapitre et le chapitre
suivant seront très simple !

Jusque ici notre programme était cantonné à un déroulement fixe, et prévisible.
Si seulement nous pourrions rajouter comme des modules qui s'exécutent seulement
et seulement si une condition x est vérifiée...

### La structure générale

Mais rassurez vous c'est possible en C++ ! Et c'est même enfantin. Les conditions
(ou *structure de contrôle* techniquement parlant) sont un composant que l'on
retrouve dans absolument tous les langages de programmation à ma connaissance.

Voici leur syntaxe :

    if(condition)
    {
        // ...
    }
    else if(condition2)
    {
        // ...
    }
    else
    {
        // ...
    }
    
Si vous êtes un tantinet anglophone, vous comprendrez aisément le principe. Les
conditions en C++ se forment avec trois différents blocs. Le premier bloc est
obligatoire et détermine le début d'une structure de contrôle. C'est ce ```if```
qui signifie *si* en anglais.

Son utilisation reste simple, vous écrivez ```if``` puis entre parenthèses vous
mettez votre condition (par exemple "si l'utilisateur à 3 ans") et enfin entre
les accolades ```{``` et ```}``` vous écrivez le code à exécuter en cas de
succès.

Concrètement, la condition est une *expression* qui peut être pleins de choses
(nous allons voir juste après). Si elle est évalué comme étant **true**, le code
entre accolades sera exécuté sinon l'expression sera évalué comme étant **false**
et le code entre accolades ne sera pas exécuté.

Une expression pour une condition peut être différente choses. Premièrement elle
peut être une comparaison entre deux valeurs, selon le tableau suivant :

| Signe | Exemple | Correspondance |
| -- | -- | -- |
| ```==``` | ```if(3 == 4)``` | Egal à |
| ```!=``` | ```if(3 != 4)``` | Différent de |
| ```<``` | ```if(3 < 4)``` | Inférieur à |
| ```<=``` | ```if(3 <= 4)``` | Inférieur ou égal à |
| ```>``` | ```if(3 > 4)``` | Supérieur à |
| ``` >=``` | ```if(3 >= 4)``` | Supérieur ou égal à |

Ainsi en pratique voici plusieurs exemples :

    if(3 == 3)
    {
        cout << "3 est bien egal a 3" << endl;
    }
    
    // On peut aussi utiliser des variables
    
    int a = 3;
    int b = 4;
    
    if(a == b) // Ne s'exécutera pas
    {
        cout << "a et b sont identiques" << endl;
    }
    else if(a != b) // S'exécutera
    {
        cout << "a est different de b" << endl;
    }
    
    // Le else if permet de créer un nouveau bloc si le bloc précédent
    // est invalide
    
    if(a < b) // S'exécutera
        cout << "a est plus petit que b" << endl;
    else if(a > b) // Ne s'exécutera pas
        cout << "b est plus petit que a" << endl;
    
    // Une forme raccourcie est possible, sans les accolades mais uniquement
    // pour insérer une seule instruction.
    
    if(a == b) // Ne s'exécutera pas
        cout << "a et b sont identiques" << endl;
    else
    {
        cout << "a et b ne sont pas identiques" << endl;
        cout << "Ceci est un else" << endl;
    }
    
    // Le else se lancera que si les précédentes conditions n'ont pas été
    // validées.

*Note : je n'utilise pas d'accents car la console Windows a, de base, un peu
de mal à les afficher.*

### Les ```bool```

On en avait parlé il y a quelque chapitres, revenons dessus. C'est un type assez
particulier dans le sens dans