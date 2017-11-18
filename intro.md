# Bienvenue

Bonjour à tous, ce playground a pour but de vous apprendre et de comprendre le pattern Abstract Factory.

# Rappel sur les Design Patterns

Les design patterns sont des solutions d’implémentation de code informatique dans le but de le rendre propre, optimisé, robuste, maintenable et évolutif.  Ce qui permet ainsi de répondre à des problématiques récurrentes de développement, en premier lieu en Programmation Orientée Objet (POO). 

Il existe 3 principaux types de  design pattern :
- les patterns de création
- les patterns de structuration
- les patterns comportementaux 

Dans le cas de notre design pattern Abstract Factory, il appartient à la famille des patterns de créations

---

Pour comprendre le pattern d'Abstract Factory, il faut d'abord comprendre ce qu'est une "Factory" que l'on traduit en français par "Fabrique".

# Une fabrique dites-vous?

Ce qu'on appelle fabrique est en fait un autre design pattern de création appelé Factory Method.

Son principe est simple: créer une classe qui sera dédier à la construction 

![Fabrique](https://img4.hostingpics.net/pics/275278Designpatternfabrique.png)

Cette classe est comparable à une usine ou l'on va centraliser la création d'objets.

Mais revenons maintenant au Pattern Abstract Factory

# Principe

Le design pattern Abstract Factory (fabrique abstraite) permet de fournir une interface unique pour instancier des objets d'une même famille sans avoir à connaître les classes à instancier.

L'utilisation de ce motif est pertinente lorsque :

- Le système doit être indépendant de la création des objets qu'il utilise
- Le système doit être capable de créer des objets d'une même famille

Le principal avantage de ce motif de conception est d'isoler la création des objets retournés par la fabrique. L'utilisation d'une fabrique abstraite permet de facilement remplacer une fabrique par une autre selon les besoins.

Le motif de conception fabrique abstraite peut être interprété et mis en oeuvre de différentes façons. Le diagramme UML ci-dessous propose une mise en oeuvre possible avec deux familles de deux produits.

Schéma du Design Pattern Fabrique Abstraite

![Fabrique Abstraite](https://img4.hostingpics.net/pics/712545dp006.png)

Les classes que l'ont utilise ici sont :

 - IProduitFactory : interface pour les fabriques de création d'objets. Elle définit les méthodes nécessaires à la création des objets
 - ProduitFactory1 et ProduitFactory2 : fabriques concrètes qui réalisent la création des objets
 - ProduitA et ProduitB : interfaces des deux familles de produits 
 - ProduitA1, ProduitA2, ProduitB1 et ProduitB2 : classes ou les deux produits des deux familles sont implémentées


# Quiz

?[Quelle est le rôle des fabriques concrètes ?]
-[X] Implémenter les méthodes abstraites de l'interface Fabrique Abstraite
-[ ] Faire jolie
-[ ] 

?[Quand faut-il utiliser le Pattern Abstract Factory ?]
-[X] 
-[ ] 
-[ ] 

?[Quand il veux créer un objet, que fais le code client ]
-[ ] 
-[X] 
-[ ] 

