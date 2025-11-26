# Ex.No:5(D) THREAD PRIORITY

## QUESTION:
Write a java program for determine the priority and name of the current thread.

Note : Read the threadname from the User

## AIM:
To create and execute a thread using the `Runnable` interface, set its name from user input, and display thread properties such as priority and name.

## ALGORITHM :
1. Create a class `A` that implements `Runnable` and override the `run()` method to print the current thread.
2. In the `main` method, create an object of class `A`.
3. Read a thread name from user input using `Scanner`.
4. Create a new `Thread` object by passing the `Runnable` object and the thread name.
5. Display the thread’s priority and name, then start the thread by calling `t.start()`.

## PROGRAM:
 ```
/*
Program to implement a thread priority using Java
Developed by: SABITHA P
RegisterNumber:  212222040137
*/
```

## SOURCE CODE:
```
import java.util.*;

public class A implements Runnable {
    public void run() {
        System.out.println(Thread.currentThread());
    }

    public static void main(String[] args) {
        A a = new A();
        Scanner sc = new Scanner(System.in);
        String thname = sc.nextLine();
        Thread t = new Thread(a, thname);

        System.out.println("Priority of Thread: " + t.getPriority());
        System.out.println("Name of Thread: " + t.getName());
        t.start();
    }
}
```

## OUTPUT:
<img width="751" height="196" alt="image" src="https://github.com/user-attachments/assets/1e5d5ea0-a2c4-43ec-9c65-49e594ce4cf6" />

## RESULT:
The program successfully creates a thread with a user-given name, prints its priority and name, and displays the thread details when executed.


