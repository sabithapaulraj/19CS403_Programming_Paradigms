---

# **Ex.No:5(E) MULTITHREADING – SYNCHRONIZATION**

## **QUESTION:**

Write a Java program to print **"Hello"** and **"World"** alternately from two threads using **synchronized blocks**.

---

## **AIM:**

To implement **thread synchronization** using the `synchronized` keyword so that two threads print “Hello” and “World” alternately without mixing the order.

---

## **ALGORITHM:**

1. Start the program.
2. Import necessary packages (`java.util.Scanner`).
3. Create a class `HelloWorldPrinter` containing:

   * A shared counter
   * A lock object
   * Two synchronized methods: `printHello()` and `printWorld()`
4. Use `wait()` and `notifyAll()` to alternate between the two threads.
5. In the `main()` method:

   * Read input `n` (number of times to print)
   * Create two threads
   * Start both threads
6. End the program.

---

## **PROGRAM:**

```
/*
Program to implement a Synchronization concept using Java
Developed by: SABITHA P
RegisterNumber:  212222040137
*/
```

---

## **SOURCE CODE:**

```java
import java.util.Scanner;

class HelloWorldPrinter {
    private int count = 0;   // shared counter
    private int n;           // number of times to print
    private final Object lock = new Object();

    public HelloWorldPrinter(int n) {
        this.n = n;
    }

    public void printHello() {
        for (int i = 0; i < n; i++) {
            synchronized (lock) {
                while (count % 2 != 0) {  // wait until it's Hello's turn
                    try { lock.wait(); } catch (Exception e) {}
                }
                System.out.println("Hello");
                count++;
                lock.notifyAll();
            }
        }
    }

    public void printWorld() {
        for (int i = 0; i < n; i++) {
            synchronized (lock) {
                while (count % 2 == 0) {  // wait until it's World's turn
                    try { lock.wait(); } catch (Exception e) {}
                }
                System.out.println("World");
                count++;
                lock.notifyAll();
            }
        }
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();

        HelloWorldPrinter printer = new HelloWorldPrinter(n);

        Thread t1 = new Thread(() -> printer.printHello());
        Thread t2 = new Thread(() -> printer.printWorld());

        t1.start();
        t2.start();
    }
}
```

---

## **OUTPUT:**

<img width="350" height="220" alt="image" src="https://github.com/user-attachments/assets/3c776d2c-4548-48bf-abb4-dd540972488f" />


---

## **RESULT:**

Thus, the Java program that prints **“Hello”** and **“World”** alternately using **thread synchronization** was successfully executed.

---
