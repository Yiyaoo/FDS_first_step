# Bienvenue

Bonjour à tous, ce playground a pour but de vous apprendre et de comprendre le pattern Abstract Factory.

# Rappel sur les Design Patterns

Les design patterns sont des solutions d’implémentation de code informatique dans le but de le rendre propre, optimisé, robuste, maintenable et évolutif.  Ce qui permet ainsi de répondre à des problématiques récurrentes de développement, en premier lieu en Programmation Orientée Objet (POO). 

Il existe 3 principaux types de  design pattern :
- les patterns de création
- les patterns de structuration
- les patterns comportementaux 

Dans le cas de notre design pattern Abstract Factory, il appartient à la famille des patterns de création

---

Pour comprendre le pattern d'Abstract Factory, il faut d'abord comprendre ce qu'est une "Factory" que l'on traduit en français par "Fabrique".

# Une fabrique dites-vous?

Ce qu'on entend par fabrique est en fait un autre pattern dit Factory Method.

Son principe est simple: créer une classe qui sera dédier à la construction 

![Fabrique](https://img4.hostingpics.net/pics/275278Designpatternfabrique.png)

Cette classe est comparable à une usine ou l'on va centraliser la création d'objets.

Mais revenons maintenant au Pattern Abstract Factory

# Principe

Définition: 
> Le design pattern Abstract Factory (fabrique abstraite) permet de fournir une interface unique pour instancier des objets d'une même famille sans avoir à connaître les classes à instancier.


Le but de ce patron de conception est d'isoler la création des objets de leur utilisation. L'intérêt est ainsi d'ajouter de nouveaux objets dérivés sans modifier le code qui utilise l'objet de base.

L'utilisation d'une fabrique abstraite permet de facilement remplacer une fabrique par une autre selon les besoins.


Le patron de conception fabrique abstraite peut être interprété et mis en oeuvre de différentes façons.


Schéma du Design Pattern Fabrique Abstraite

Ce diagramme propose une mise en oeuvre possible avec deux familles de deux produits.

![Fabrique Abstraite](https://img4.hostingpics.net/pics/134636creationabstractfactory.png)

Les classes que l'ont utilise ici sont :

 - AbstractFactory : interface pour les fabriques de création d'objets. Elle définit les méthodes nécessaires à la création des objets
 - ConcreteFactory1 et ConcreteFactory2 : fabriques concrètes qui réalisent la création des objets
 - AbstractProductA et AbstractProductB : interfaces des deux familles de produits 
 - ProductA1, ProductA2, ProductB1 et ProductB2 : classes ou les deux produits des deux familles sont implémentées
 - Le client, quant à lui utilise uniquement la fabrique abstraite pour créer ses objets

Les produits appartiennent à une famille. Sur ce schéma le produit A1 et le produit B1 appartiennent à la même famille et sont donc destinés à collaborer ensemble.

# Quiz

?[A quel famille appartient le pattern Abstract Factory  ?]
-[X] aux patterns de création
-[ ] aux patterns de structuration
-[ ] aux patterns comportementaux 

?[Une Fabrique concrète ?]
-[X] implémente les méthodes d'une fabrique Abstraite
-[ ] ne réalise pas la création d'objet
-[ ] déclare les produits à implémenter

?[Un client a besoin de savoir quel fabrique concrete conçoit son objet.]
-[ ] Vrai
-[X] Faux



