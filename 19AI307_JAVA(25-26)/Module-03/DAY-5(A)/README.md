## Ex.No:3(E) INNER CLASS


### QUESTION:
Write an enum `VehicleType` with constants:
- **CAR**
- **BIKE**
- **BUS**

Each enum constant must have a constructor that stores its number of wheels.  
Read user input (vehicle name) and print the corresponding wheel count.

Example:

Input:
```
car
```

Output:
```
CAR has 4 wheels.
```

---

### AIM:
To write a Java program demonstrating enums with constructors and methods by printing the wheel count of different vehicle types.

---

### ALGORITHM:

1. Create an enum `VehicleType` with constants CAR, BIKE, and BUS.  
2. Assign each constant a wheel count using a constructor.  
3. Implement a getter method `getWheels()`.  
4. In the main method, read a vehicle type from the user.  
5. Convert input to uppercase and match it with enum constant using `valueOf()`.  
6. Print the wheel count or display an error message for invalid input.

---

### PROGRAM:

```
Program to demonstrate enum with constructor and methods for vehicle types
Developed by: Sabitha P
RegisterNumber: 212222040137
```

---

### Sourcecode.java:

```java
import java.util.*;

enum VehicleType {
    CAR(4),
    BIKE(2),
    BUS(6);

    private int wheels;

    VehicleType(int wheels) {
        this.wheels = wheels;
    }

    int getWheels() {
        return wheels;
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String input = sc.nextLine().toUpperCase();

        try {
            VehicleType type = VehicleType.valueOf(input);
            System.out.println(type + " has " + type.getWheels() + " wheels.");
        } catch (IllegalArgumentException e) {
            System.out.println("Invalid vehicle type entered.");
        }
    }
}
```

---

### OUTPUT:
<img width="797" height="247" alt="image" src="https://github.com/user-attachments/assets/a6a4bace-1595-4f7e-8155-e3d9e9bdd752" />


---

### RESULT:
Thus, the Java program using an enum with a constructor to represent vehicle types and their wheel counts was successfully executed.
