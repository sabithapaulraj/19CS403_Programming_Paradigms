# Ex.No:2(E) ACCESS MODIFIERS

## QUESTION:
Create a class Calculator with: One non-static method add(int a, int b) that returns the sum, One static method info() that says "Calculator is ready".

## AIM:
To write a Java program that demonstrates the use of access modifiers through static and non-static methods in a class.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create a class named Calculator.
4. Declare a non-static method add(int a, int b) to return the sum of two integers.
5. Declare a static method info() to display a message.
6. In the main() method, call the static method using the class name.
7. Create an object of the Calculator class and call the non-static method.
8. Display the output.
9. End the program.

## PROGRAM:
 ```
Program to implement a Access Modifiers using Java
Name: Sabitha P
Register Number: 212222040137
```

## SOURCE CODE:
```
import java.util.Scanner;

class Calculator 
{
    static void show()
    {
        System.out.println("Calculator is ready");
    }
    int sum(int a,int b)
    {
        return a+b;
    }
}

class prog {
    public static void main(String[] args) 
    {
        Scanner sc=new Scanner(System .in);
        Calculator.show();
        int x=sc.nextInt();
        int y=sc.nextInt();
        Calculator calc=new Calculator();
        int result=calc.sum(x,y);
        System.out.println("Sum: "+result);
    }
}
```

## OUTPUT:

![java25](https://github.com/ABINAYA-27-76/19AI307_ODD-25-26-/blob/1d041f830e60c366d7b4eaa39bb473ed78dd8001/19AI307_JAVA(25-26)/Module-02/DAY-5/java25.png)

## RESULT:
Thus, a Java program to implement Access Modifiers with static and non-static methods was executed successfully.

