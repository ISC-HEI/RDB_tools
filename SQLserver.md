# SQL Server RDB Joshua Siedel

SQL Server est un système de gestion de base de données en SQL. Il fonctionne sur Windows, Windows Server et Linux.

Il y a une intégration possible dans Visual Studio. (PAS vs code)

Il est possible de faire des requêtes multibase, c'est à dire une requête qui lie deux tables dans 2 bases différentes.

SQL Server fonctionne de manière parallèle avec du multi-thread.

Les opérations de lecture et d'écriture physique bénéficient aussi du parallélisme systématiquement du fait que les opérations d'IO sont effectuées directement par SQL Server et non à travers la couche système comme c'est le cas de PostgreSQL ou MySQL.

Il est possible de créer des vues indexées automatisées. (Les vues se mettent à jour automatiquement)

Il est possible de manipuler des données XML depuis la version 2005.

Il y a un SIG (Système d'Information Géographique) intégré.

Par rapport au SQL, le T-SQL ajoute les fonctionnalités suivantes :

    Éléments de programmation procédurale (boucle, conditions...);
    La possibilité de créer et d'utiliser des variables locales;
    Des fonctions de manipulations de chaîne de caractères, de dates et de calculs mathématiques.


# Où est la table créer par la requête ?
![sql path](https://github.com/user-attachments/assets/6a0c40e5-2f34-4fef-9736-095c6d2f095b)
