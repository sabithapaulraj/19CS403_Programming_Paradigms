# Ex.No:3(F) WRAPPER CLASS

## QUESTION:
Write a Java program to check if a number is an Armstrong number using Math.pow() and the Integer wrapper class. Take input from the user.

| Input | Result   |
|-------|----------|
|  153  | 153 is an Armstrong Number. |

## AIM:
To write a Java program that checks whether a given number is an Armstrong number by summing each digit raised to the power of the total number of digits.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Read an integer input from the user.
4. Count the number of digits in the given number.
5. Extract each digit using modulus, raise it to the power of the digit count, and accumulate the sum.
6. Repeat the process until all digits are processed.
7. Compare the final sum with the original number and display whether it is an Armstrong number.


## PROGRAM:
```txt
Program to implement a Wrapper Class using Java
Developed by: Sabitha P
RegisterNumber: 212222040137
```

## SOURCE CODE:
```java 
import java.util.*;

public class ArmstrongCheck {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int num = Integer.parseInt(sc.nextLine());
        int digits = Integer.toString(num).length();
        int sum = 0, temp = num;

        while (temp > 0) {
            int d = temp % 10;
            sum += (int) Math.pow(d, digits);
            temp /= 10;
        }

        if (sum == num)
            System.out.println(num + " is an Armstrong number.");
        else
            System.out.println(num + " is not an Armstrong number.");
    }
}
```
## OUTPUT:
<img width="771" height="244" alt="image" src="https://github.com/user-attachments/assets/4dbfb72f-fa21-42f8-82d0-82479fa27566" />

## RESULT:
The program correctly reads a number, computes the sum of its digits raised to the required power, and successfully determines whether the given number is an Armstrong number or not.

