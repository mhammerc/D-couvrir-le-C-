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

Premièrement cette expression peut être une comparaison entre deux valeurs,
selon le tableau suivant :

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
    else // S'exécutera
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
particulier dans le sens où il ne peut contenir que deux valeurs : ```true``` et
```false```. Si vous mettez un ```bool``` qui vaut ```true``` dans une condition,
celle-ci sera exécuté, sinon non. Un ```bool``` peut être utilisé de multiples
manières, voyez ci-contre :

    bool a = true;
    bool b = false;
    bool c = 0; // False
    bool d = 1; // True
    bool e = 80; // True
    bool f = -80; // True
    bool g = a != b; // True
    
Et oui, regarder bien le dernier exemple ! En réalité, les opérateur de
comparaisons que nous avons eu plus haut retourne un booléen et vous pouvez donc
stocker le résultat dans une variable si l'envie vous prend. Ainsi vous pouvez
directement passer une variable ```bool``` à une condition si cela vous arrange.
Et devinez quoi ! Automatiquement, puisque un nombre non nul se "transforme" en
```true``` et un nombre nul en ```false```, vous pouvez directement passer un
```int``` ou un ```long``` ou ce genre de variables dans une condition !

Pratique non :-D ?

### Les petits bonus

Car j'aime vous offrir des cadeaux et que je pense à vous, je vais vous offrir
une astuce. En effet, vous pouvez mettre plusieurs expressions dans une
condition avec les opérateurs logiques qui concatènent (un drôle de moi oui oui)
deux ```bool``` en un seul ! Voici un tableau les présentants :

| Mot clé | Explication | Exemple |
| -- | -- | -- |
| && | Opérateur logique ET | ```true && true // True``` et ```true && false // False``` |
| &#124;&#124; | Opérateur logique OU | ```false  &#124;&#124; true // True``` et ```false  &#124;&#124; false // False``` | | ! | Opérateur logique NON | ```!true // False``` et ```!false // True``` |