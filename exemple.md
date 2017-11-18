# Etape 1

![Image Etape 1](https://img4.hostingpics.net/pics/954371237183495200081683688521437108332n.png)


carFactory.java
```java
public interface carFactory {
	public car getCar();
}
```


# Etape 2

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

![Image Etape 4](https://img4.hostingpics.net/pics/954371237183495200081683688521437108332n.png)

# Etape 5

![Image Etape 5](https://img4.hostingpics.net/pics/954371237183495200081683688521437108332n.png)

# Etape 6

![Image Etape 6](https://img4.hostingpics.net/pics/954371237183495200081683688521437108332n.png)

# Etape 7

![Image Etape 7](https://img4.hostingpics.net/pics/954371237183495200081683688521437108332n.png)

# Quizz

