# Ex.No:3(b) POLYMORPHISM

## QUESTION:
 Write a Java program to create a class Vehicle with a method called speedUp(). Create two subclasses Car and Bicycle. Override the speedUp() method in each subclass to increase the vehicle's speed differently.

For example:
<img width="566" height="165" alt="image" src="https://github.com/user-attachments/assets/7d5c44e2-feee-491e-8109-8e7dc0c3d08c" />

## AIM:

To create a Vehicle class with subclasses Car and Bicycle and demonstrate method overriding with speedUp().

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'.
3.	Create a base class Vehicle with an integer variable speed and method speedUp().
4.	Create subclasses Car and Bicycle that extend Vehicle.
5.	Override the speedUp() method in each subclass to increase speed differently.
6.	In the main method, read the vehicle type and increment value from the user.
7.	Create the appropriate object (Car or Bicycle) and call speedUp() with the increment.
8.	Display the updated speed.
9.	Stop the program.




## PROGRAM:
 ```
/*
Program to implement a Polymorphism using Java
Developed by: Sabitha P
RegisterNumber:  212222040137
*/
```

## SOURCE CODE:


```
import java.util.Scanner;

class Vehicle {
    int speed;

    Vehicle() {
        this.speed = 0;
    }

    public void speedUp(int increment) {
        speed += increment;
        System.out.println("Vehicle speed increased to: " + speed + " km/h");
    }
}

class Car extends Vehicle {
    @Override
    public void speedUp(int increment) {
        speed += increment * 2; 
        System.out.println("Car speed increased to: " + speed + " km/h");
    }
}

class Bicycle extends Vehicle {
    @Override
    public void speedUp(int increment) {
        speed += increment; 
        System.out.println("Bicycle speed increased to: " + speed + " km/h");
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        String type = scanner.nextLine().trim().toLowerCase();
        int increment = scanner.nextInt();

        Vehicle v;

        if (type.equals("car")) {
            v = new Car();
        } else if (type.equals("bicycle")) {
            v = new Bicycle();
        } else {
            System.out.println("Unknown vehicle type.");
            scanner.close();
            return;
        }

        v.speedUp(increment);
        scanner.close();
    }
}

```

## OUTPUT:
<img width="1104" height="400" alt="image" src="https://github.com/user-attachments/assets/529931b6-c444-4747-86ff-e37a139bc2dd" />



## RESULT:
The program successfully overrides the speedUp() method in subclasses and increases the speed according to the vehicle type.
