# Ex.No:5(B) SERIALIZATION AND DESERIALIZATION 

## QUESTION:
Write a Java program to serialize a collection of objects (like ArrayList<Student>) into a file.

## AIM:
To write a Java program that serializes a list of `Student` objects into a file and later deserializes them back, demonstrating Java’s object serialization mechanism using `ObjectOutputStream` and `ObjectInputStream`.

## ALGORITHM:
1. **Collect Student Data**  
   Read `n` from the user, then read each student’s `id`, `name`, and `marks`, creating `Student` objects and storing them in a list.
2. **Serialize the Student List**  
   Use `ObjectOutputStream` wrapped around `FileOutputStream` to write the entire `List<Student>` object into a file (`students.dat`).
3. **Deserialize the Student List**  
   Use `ObjectInputStream` wrapped around `FileInputStream` to read the serialized list back into a new list of `Student` objects.
4. **Handle Exceptions**  
   Use try–with–resources to automatically close streams and catch `IOException` and `ClassNotFoundException` for safe file operations.
5. **Display Results**  
   After deserialization, print each `Student` object using its overridden `toString()` method.

## PROGRAM:
 ```
/*
Program to implement a serialization and deserialization using Java
Developed by: SABITHA P
RegisterNumber:  212222040137
*/
```


## SOURCE CODE:
```
import java.io.*;
import java.util.*;

// Student class must implement Serializable
class Student implements Serializable {
    private static final long serialVersionUID = 1L;

    private int id;
    private String name;
    private double marks;

    public Student(int id, String name, double marks) {
        this.id = id;
        this.name = name;
        this.marks = marks;
    }

    @Override
    public String toString() {
        return "Student{id=" + id + ", name='" + name + "', marks=" + marks + "}";
    }
}

public class StudentSerializationUserInput {

    // Serialize list of students
    public static void serializeStudents(List<Student> students, String fileName) {
        try (ObjectOutputStream oos = new ObjectOutputStream(new FileOutputStream(fileName))) {
            oos.writeObject(students);
            System.out.println("Students serialized successfully into: " + fileName);
        } catch (IOException e) {
            System.out.println("Error during serialization: " + e.getMessage());
        }
    }

    // Deserialize list of students
    @SuppressWarnings("unchecked")
    public static List<Student> deserializeStudents(String fileName) {
        List<Student> students = null;
        try (ObjectInputStream ois = new ObjectInputStream(new FileInputStream(fileName))) {
            students = (List<Student>) ois.readObject();
            System.out.println("Students deserialized successfully from: " + fileName);
        } catch (IOException | ClassNotFoundException e) {
            System.out.println("Error during deserialization: " + e.getMessage());
        }
        return students;
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        List<Student> students = new ArrayList<>();

        int n = scanner.nextInt();
        scanner.nextLine(); // consume newline

        for (int i = 0; i < n; i++) {
            int id = scanner.nextInt();
            scanner.nextLine(); // consume newline
            String name = scanner.nextLine();
            double marks = scanner.nextDouble();
            scanner.nextLine(); // consume newline

            students.add(new Student(id, name, marks));
        }

        String fileName = "students.dat";

        // Serialize
        serializeStudents(students, fileName);

        // Deserialize
        List<Student> deserializedStudents = deserializeStudents(fileName);

        // Display deserialized data
        if (deserializedStudents != null) {
            System.out.println("\nDeserialized Students:");
            for (Student s : deserializedStudents) {
                System.out.println(s);
            }
        }

        scanner.close();
    }
}
```

## OUTPUT:
<img width="1170" height="811" alt="image" src="https://github.com/user-attachments/assets/6d0bc941-7520-4870-a9eb-f70d1aa3ea6f" />

## RESULT:
The program successfully serializes a list of dynamically entered student objects into a file and retrieves them back through deserialization, verifying Java’s object persistence mechanism.
