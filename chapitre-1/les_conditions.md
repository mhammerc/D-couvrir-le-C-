## Les conditions

Allez on garde du courage, on ne désespère pas ! Ce chapitre et le chapitre
suivant seront très simple !

Jusque ici notre programme était cantonné à un déroulement fixe, et prévisible.
Si seulement nous pourrions rajouter comme des modules qui s'exécutent seulement
et seulement si une condition x est vérifiée...

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
| ```!=``` | ```if(3 != 4)``` | Different de ||

    