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

Abstract Factory Pattern est basé sur le Pattern Factory Method, mais qui va jouer en deux ou plusiers classe ou objets.
Donc dans cet exemple, dans le car factory, on a maintenant deux type de voitures.
La classe concrète SportCarFactory, elle, implémente les méthodes dedans de CarFactory.

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
# Quizz

