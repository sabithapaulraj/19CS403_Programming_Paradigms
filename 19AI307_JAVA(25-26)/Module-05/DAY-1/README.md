# Ex.No:5(A) INPUT STREAM READER 

## QUESTION:
Write a program to demonstrate chaining of streams (BufferedReader on top of InputStreamReader on top of System.in)

## AIM:
To demonstrate stream chaining in Java by combining `InputStreamReader` and `BufferedReader` to read user input efficiently from `System.in`.

## ALGORITHM :
1. Create a `BufferedReader` object by chaining `System.in → InputStreamReader → BufferedReader`.
2. Read a line of text from the user and store it as the name.
3. Read the next line, convert it into an integer, and store it as the age.
4. Display the collected user details (name and age) on the screen.
5. Use a try–with–resources block to automatically close the reader and catch any `IOException`.

## PROGRAM:
  ```
/*
Program to implement a input stream reader using Java
Developed by: SABITHA P
RegisterNumber:  212222040137
*/
```

## SOURCE CODE:
```
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;

public class ChainingStreamsExample {
    public static void main(String[] args) {
        // Chaining: System.in -> InputStreamReader -> BufferedReader
        try (BufferedReader br = new BufferedReader(new InputStreamReader(System.in))) {
            
            String name = br.readLine();   // reading input using BufferedReader

            String ageStr = br.readLine(); // reading another line
            int age = Integer.parseInt(ageStr);

            System.out.println("--- User Details ---");
            System.out.println("Name: " + name);
            System.out.println("Age: " + age);

        } catch (IOException e) {
            System.out.println("An error occurred while reading input: " + e.getMessage());
        }
    }
}
```

## OUTPUT:
<img width="649" height="468" alt="image" src="https://github.com/user-attachments/assets/b031453c-3822-49d0-8025-9f0195693c40" />

## RESULT:
The program successfully reads multiple lines of user input using chained input streams and prints the user details. It demonstrates effective use of `BufferedReader` wrapped around `InputStreamReader` for fast and efficient input handling.


