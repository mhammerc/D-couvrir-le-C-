
### Les tableaux dynamiques

Imaginez, vous êtes un développeur dans une jeune startup qui est en train de créer un jeu révolutionnaire. Dans ce jeu, vous contrôlez un personnage qui possède une seule et unique arme : un lanceur de boules.

Bien entendu, le joueur a la possibilité de tirer avec l'arme. Mais que ce passe t'il lorsque qu'il presse la détente ? Une boule est tirée. Bien entendu, chaque boule réagit à la physique et doit donc rester dans le monde virtuel.

Comment stocker les boules ? On ne peut pas utiliser un tableau statique car ceci ont une taille fixe hors notre joueur peut tirer autant de boules qu'il le souhaite. Il faut donc utiliser un tableau à taille variable. Ces tableaux sont des tableaux dynamiques.

Nous allons voir le tableau dynamique le plus simple, le ```vector```. Il en existe d'autres, que nous verront par la suite.

Le ```vector``` est très simple d'utilisation, voici un premier exemple déjà très complet :

    #include <iostream>
    #include <vector>

    int main()
    {
      std::vector<int> bullets;
  
      // Imaginons que le joueur tire 9 boules
      for (int i = 0; i < 9; ++i)
      bullets.push_back(i);

      std::cout << "Le joueur a tire " << bullets.size() << " boules : " << std::endl;

      for (int i = 0; i < bullets.size(); ++i)
      {
        std::cout << "\t- Boule " << bullets[i] << std::endl;
      }

      // Le joueur joue...

      // Imaginons que le joueur retire 3 boules
      for (int i = 0; i < 3; ++i)
        bullets.push_back(bullets.size());

      std::cout << std::endl << "Le joueur a tire " << bullets.size() << " boules : " << std::endl;

      for (int i = 0; i < bullets.size(); ++i)
      {
        std::cout << "\t- Boule " << bullets[i] << std::endl;
      }

      std::cin.ignore();
    }

