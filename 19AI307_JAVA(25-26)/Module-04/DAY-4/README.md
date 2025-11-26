# Ex.No:4(D) DESIGN PATTERN -- ABSTRACT FACTORY

## QUESTION:
Create a system that builds Car and Bike objects for two companies: "Honda" and "Yamaha". Use Abstract Factory Pattern to choose the brand and output the type and brand for each vehicle.


## AIM:
To write a Java program demonstrating Abstract Factory Pattern by creating related objects (Car and Bike) without specifying their concrete classes.


## ALGORITHM :
1. Create Car and Bike interfaces
2. Implement these interfaces for Honda and Yamaha
3. Create Abstract Factory (VehicleFactory)
4. Implement concrete factories (HondaFactory, YamahaFactory)
5. Use FactoryProducer to get the required factory
6. Create Car and Bike objects using the factory
7. Display the output

## PROGRAM:
 ```
Program to implement a Composition Concepts in Java
Developed by: Sabitha P
Register Number: 212222040137
```

## SOURCE CODE:
```
import java.util.*;
interface Car{
    void create();
}
interface Bike{
    void create();
}

class HondaCar implements Car{
    public void create()
    {
        System.out.println("Honda Car created");
    }
}
class HondaBike implements Bike{
    public void create()
    {
        System.out.println("Honda Bike created");
    }
}

class YamahaCar implements Car{
    public void create()
    {
        System.out.println("Yamaha Car created");
    }
}
class YamahaBike implements Bike{
    public void create()
    {
        System.out.println("Yamaha Bike created");
    }
}

interface VehicleFactory{
    Car createCar();
    Bike createBike();
}

class HondaFactory implements VehicleFactory{
    public Car createCar()
    {
        return new HondaCar();
    }
    public Bike createBike()
    {
        return new HondaBike();
    }
}

class YamahaFactory implements VehicleFactory{
    public Car createCar()
    {
        return new YamahaCar();
    }
    public Bike createBike()
    {
        return new YamahaBike();
    }
}

class FactoryProducer{
    public static VehicleFactory getFactory(String brand)
    {
        if(brand==null) return null;
        switch(brand.toLowerCase())
        {
            case "honda":
                return new HondaFactory();
            case "yamaha":
                return new YamahaFactory();
            default:
                return null;
        }
    }
}

public class Main{
    public static void main(String args[])
    {
        Scanner sc = new Scanner(System.in);
        while(sc.hasNextLine())
        {
        String input = sc.nextLine();
        if(input.isEmpty()) continue;
        VehicleFactory fac = FactoryProducer.getFactory(input);
        
        if (fac!=null)
        {
            fac.createCar().create();
            fac.createBike().create();
        }
        else
        {
            System.out.println("Invalid company");
        }
        }
    }
}
```



## OUTPUT:
<img width="835" height="300" alt="image" src="https://github.com/user-attachments/assets/392f3220-7e40-4c74-86a3-0d0eb53ff89d" />



## RESULT:
The program was implemented successfully and verified.






