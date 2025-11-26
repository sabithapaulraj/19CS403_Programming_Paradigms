# Ex.No:4(A) EXCEPTION HANDLING

## QUESTION:
If an Integer object is set to null, and you attempt to call .toString() on it, what happens? How can you prevent your code from throwing an exception in such cases?


## AIM:

To write a Java program to demonstrate NullPointerException when calling .toString() on a null Integer object and to handle the exception using try-catch.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Read an integer value from the user.
4. Assign null if the user enters 0 (or a specific case).
5. Try to call .toString() method on the Integer object.
6. Catch the NullPointerException and display a meaningful message.
7. Display output and end the program.

## PROGRAM:
 ```
Program to implement a Exception Handling using Java
Developed by: Sabitha P
Register Number: 212222040137
```

## SOURCE CODE:
```
import java.util.Scanner;

public class NullCheck
{
    public static void main(String[] args) 
    {
        Scanner sc = new Scanner(System.in);
        Integer num = sc.nextInt(); 
        try 
        {
            if (num == 0) 
            {
                num = null;
            }
            System.out.println(num.toString());

        } 
        catch (NullPointerException e) 
        {
            System.out.println("Null Integer");
        }
    }
}
```




## OUTPUT:
<img width="474" height="290" alt="image" src="https://github.com/user-attachments/assets/590ec314-d1ea-4421-b96e-fc2f34de4324" />


## RESULT:
Thus, the program demonstrates that calling .toString() on a null object causes a NullPointerException, and the exception can be prevented using a try-catch block.



