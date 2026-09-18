# Ex.No:5(D) THREAD PRIORITY

## QUESTION:
Write a java program for set the priority and name of the current thread.

Note : Read the threadname from the User 
Set the Priority as 2.


## AIM:
To write a Java program to set the priority and name of the current thread by reading the thread name from the user and setting its priority to 2.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Read the thread name from the user.
4. Get the current thread using Thread.currentThread().
5. Set the name of the current thread using setName().
6. Set the priority of the thread to 2 using setPriority().
7. Display the priority and name of the thread.
8. Display the thread information.
9. Stop the program.

## PROGRAM:
 ```
/*
Program to implement a Thread Priority Concept using Java
Developed by: Shreya R
RegisterNumber: 212224060248 
*/
```

## SOURCE CODE:

```
import java.util.*;
public class A implements Runnable{
    public void run(){
        System.out.println(Thread.currentThread());
    }
    public static void main(String[] args){
        A a= new A();
        Scanner sc=new Scanner(System.in);
        String thname=sc.nextLine();
        Thread t=new Thread(a,thname);
        t.setPriority(2);
        System.out.println("Priority of Thread: "+t.getPriority());
        System.out.println("Name of Thread: "+t.getName());
        t.start();
    }
}
```


## OUTPUT:

<img width="750" height="215" alt="image" src="https://github.com/user-attachments/assets/a44727cb-772a-443d-b78d-f610bb4be877" />


## RESULT:
Thus, the Java program to set the priority and name of the current thread was executed successfully.
