Dans notre exemple, on va essayer de faire un système pour créer des voitures de plusieurs familles différentes (Sport, Business...) pour différentes sociétés.

# Etape 1

On crée tout d'abord une interface ou une classe abstraite carFactory,
On y inclut une méthode getCar()  dedans pour retourner une voiture

![Image Etape 1](https://img4.hostingpics.net/pics/954371237183495200081683688521437108332n.png)

carFactory.java
```java
public interface carFactory {
	public car getCar();
}
```


# Etape 2

L'interface carFactory a une classe concrète: nous allons l'appeler businessCarFactory et il implémente la méthode getCar() qui va aussi retourner une voiture concrète.

![Image Etape 2](https://img4.hostingpics.net/pics/2552094601.png)

businessCarFactory.java
```java
public class businessCarFactory implements carFactory{
	
	public car getCar(){
		return new businessCar();
	}
}
```


# Etape 3

Bien entendu si l'on veut créer notre voiture, il nous faut une classe voiture, parceque si on sait pas ce que c'est ça va être compliqué d'utiliser l'usine. Mais nous on a une usine qui fabrique des voiture business, nous définissons donc la classe fille businessCar.

![Image Etape 3](https://img4.hostingpics.net/pics/5094513802.png)

car.java
```java
public interface car {
	public void gasUp();
}
```

businessCar.java
```java
public class businessCar implements car{
	public void gasUp() {
        System.out.println("gas up !");
    }
}
```

# Etape 4

Abstract Factory Pattern est basé sur le Pattern Factory Method, mais celui-ci va pouvoir créer maintenant deux ou plusieurs objets différents.
Donc dans cet exemple, dans le car factory, on a maintenant deux type de voitures.
La classe concrète SportCarFactory, elle, implémente les méthodes de CarFactory.

![Image Etape 4](https://img4.hostingpics.net/pics/976063820.png)

CarFactory.java
```java
public interface CarFactory {
	public BenzCar getBenzCar();
    public TeslaCar getTeslaCar();
}
```
SportCarFactory.java
```java
public class SportCarFactory implements CarFactory {
    public BenzCar getBenzCar() {
        return new BenzSportCar();
    }

    public TeslaCar getTeslaCar() {
        return new TeslaSportCar();
    }
}
```
# Etape 5

Maintenant que l'on a deux types d'objets dans le carfactory, on doit donc créer deux interfaces, BenzCar et TeslaCar.

![Image Etape 5](https://img4.hostingpics.net/pics/787834811.png)

BenzCar.java
```java
public interface BenzCar {
	public void gasUp();
}
```
TeslaCar.java
```java
public interface TeslaCar {
	public void charge();
}
```
# Etape 6

Notre fabrique concrète fabrique des voitures de sports, il faut donc créer des sous-classes de BenzCar et TeslaCar.  
Notre fabrique SportCarFactory va regrouper les voitures de sport de ces deux marques.

![Image Etape 6](https://img4.hostingpics.net/pics/154823682.png)

BenzSportCar.java
```java
public class BenzSportCar implements BenzCar{
	public void gasUp() {
        System.out.println("gas for sport !");
    }
}
```
TeslaSportCar.java
```java
public class TeslaSportCar implements TeslaCar {
    public void charge() {
        System.out.println("electricity for sport !");
    }
}
```
# Etape 7

Cependant, ces deux sociétés ne font pas que des voitures de sport, ils font notamment des voitures de business. 
On crée une Fabrique de type BusinessCarFactory et les sous-classes de voiture de type business car, et de la même façon que pour sportcar, la fabrique nouvellement créée fabriquera les voitures de business de BenzCar et TeslaCar.

![Image Etape 7](https://img4.hostingpics.net/pics/372427443.png)

BenzBusinessCar.java
```java
public class BenzBusinessCar implements BenzCar{
	public void gasUp() {
        System.out.println("gas for business");
    }
}
```
TeslaBusinessCar.java
```java
public class TeslaBusinessCar implements TeslaCar {
    public void charge() {
        System.out.println("electricity for business ! ");
    }
}
```
BusinessCarFactory.java
```java
public class BusinessCarFactory implements CarFactory {
    public BenzCar getBenzCar() {
        return new BenzBusinessCar();
    }

    public TeslaCar getTeslaCar() {
        return new TeslaBusinessCar();
    }
}
```
# Quiz

?[ Quel est la différence entre le factory method pattern et l'abstract factory pattern?]
-[X] Dans le cas du Factory Method, new est déporté dans une méthode dédiée, un seul type d’objet est retourné à la fois et dans le cas de Abstract Factory les familles de produit sont liés fonctionnellement, plusieurs fabriques, plusieurs types d’objets sont retournés par chaque fabrique
-[ ] Dans le cas du Abstract Factory, new est déporté dans une méthode dédiée, un seul type d’objet est retourné à la fois et dans le cas de Factory Method les familles de produit sont liés fonctionnellement, plusieurs fabriques, plusieurs types d’objets sont retournés par chaque fabrique
-[ ] C'est la même chose
-[X] Les noms sont différents

![Image Question 2](https://img4.hostingpics.net/pics/870935rtz.png)
?[ Ce diagramme utilise quel design pattern? ]
-[ ] Abstract Factory Pattern
-[X] Factory Method Pattern
-[ ] Je sais pas
![Image Question 3](https://img4.hostingpics.net/pics/419360abstractfactory.png)
?[Ce diagramme utilise quel design pattern?]
-[ ] Aucun des deux
-[ ] Factory Method Pattern
-[X] Abstrat Factory Pattern




Merci d'avoir suivi!
