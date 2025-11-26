# Ex.No:4(C)  COMPOSITION IN JAVA

## QUESTION:
Create animals from two regions: "Africa" and "Asia". Use Abstract Factory to create families of animals (Herbivore, Carnivore). Print the interaction result.



## AIM:
To write a Java program demonstrating Composition and Abstract Factory Pattern by creating animal families of different regions and displaying interactions between herbivores and carnivores.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create interfaces Herbivore and Carnivore.
4. Create concrete animal classes (e.g., Wildebeest, Lion, Deer, Tiger) implementing those interfaces.
5. Create an abstract factory class for producing families of animals.
6. Implement region-based factories (AfricaFactory, AsiaFactory).
7. In the main program, instantiate factories and show interactions.
8. Print the result.
9. Stop the program.

## PROGRAM:
 ```
Program to implement a Composition Concepts in Java
Developed by: Sabitha P
Register Number: 212222040137
```

## SOURCE CODE:
```
import java.util.Scanner;

interface Herbivore {}
interface Carnivore {
    void eat(Herbivore h);
}

class Wildebeest implements Herbivore {}
class Lion implements Carnivore {
    public void eat(Herbivore h) {
        System.out.println("Lion eats Wildebeest");
    }
}

class Buffalo implements Herbivore {}
class Tiger implements Carnivore {
    public void eat(Herbivore h) {
        System.out.println("Tiger eats Buffalo");
    }
}

interface AnimalFactory {
    Herbivore createHerbivore();
    Carnivore createCarnivore();
}

class AfricaFactory implements AnimalFactory {
    public Herbivore createHerbivore() { return new Wildebeest(); }
    public Carnivore createCarnivore() { return new Lion(); }
}

class AsiaFactory implements AnimalFactory {
    public Herbivore createHerbivore() { return new Buffalo(); }
    public Carnivore createCarnivore() { return new Tiger(); }
}

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String region = sc.nextLine().toLowerCase();
        AnimalFactory factory;

        if (region.equals("africa")) factory = new AfricaFactory();
        else if (region.equals("asia")) factory = new AsiaFactory();
        else {
            System.out.println("Invalid region");
            return;
        }

        Carnivore carn = factory.createCarnivore();
        Herbivore herb = factory.createHerbivore();
        carn.eat(herb);
    }
}
```





## OUTPUT:
<img width="520" height="221" alt="image" src="https://github.com/user-attachments/assets/dddd2733-19b4-49f8-9646-befd73cb417e" />



## RESULT:
The program was implemented successfully and verified.




