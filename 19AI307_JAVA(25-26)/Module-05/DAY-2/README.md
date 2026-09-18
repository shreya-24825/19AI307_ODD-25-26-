# Ex.No:5(B) SERIALIZATION AND DESERIALIZATION 

## QUESTION:
Write a Java program to serialize a collection of objects (like ArrayList<Student>) into a file.

## AIM:
To write a Java program to serialize a collection of objects (like ArrayList<Student>) into a file.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create an InputStreamReader object to read input from the keyboard.
4. Create a BufferedReader object using the InputStreamReader.
5. Read the user input using readLine().
6. Display the entered input.
7. Stop the program.



## PROGRAM:
 ```
/*
Program to implement a Serialization and Deserialization using Java
Developed by: Shreya R
RegisterNumber:  212224060248
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
        Scanner sc = new Scanner(System.in);
        List<Student> students = new ArrayList<>();

        int n = sc.nextInt();
        sc.nextLine(); // consume newline

        for(int i=0;i<n;i++){
            int id=sc.nextInt();
            sc.nextLine();
            String name=sc.nextLine();
            double marks=sc.nextDouble();
            students.add(new Student(id,name,marks));
        }
        String fileName="students.dat";
        
        serializeStudents(students,fileName);
        List<Student> deserializedStudents=deserializeStudents(fileName);
        
        // Write your code here

        // Display deserialized data
        if (deserializedStudents != null) {
            System.out.println("\nDeserialized Students:");
            for (Student s : deserializedStudents) {
                System.out.println(s);
            }
        }

        sc.close();
    }
}

```




## OUTPUT:
<img width="1180" height="387" alt="image" src="https://github.com/user-attachments/assets/6f46ba8f-8846-41a5-bbdc-63c61ef178cb" />



## RESULT:
Thus, the Java program to read user input from the keyboard using InputStreamReader was executed successfully and the entered input was displayed.
