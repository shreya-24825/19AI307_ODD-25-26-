# Ex.No:5(E) MULTITHREADING -SYNCHRONIZATION

## QUESTION:
Use a synchronized block (not method) to safely increment a shared counter using multiple threads.

## AIM:
To write a Java program using a synchronized block to safely increment a shared counter using multiple threads.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Read the number of threads and the number of increments from the user.
4. Create a shared counter and initialize it to 0.
5. Create multiple threads.
6. Inside each thread, use a synchronized block to safely increment the shared counter.
7. Start all the threads.
8. Wait for all threads to complete using join().
9. Display the final value of the counter.
10. Stop the program.

## PROGRAM:
 ```
/*
Program to implement a Synchronization concept using Java
Developed by: Shreya R
RegisterNumber:  212224060248
*/
```

## SOURCE CODE:

```
import java.util.*;
class SharedCounter{
    int count=0;
    synchronized void increment(){
        count++;
    }
}
public class Main{
    public static void main(String[] args) throws Exception{
        Scanner sc=new Scanner(System.in);
        int threads=sc.nextInt();
        int increments=sc.nextInt();
        SharedCounter counter=new SharedCounter();
        Thread[] arr=new Thread[threads];
        for(int i=0;i<threads;i++){
            arr[i]=new Thread(()->{
                for(int j=0;j<increments;j++){
                    counter.increment();
                }
            });
            arr[i].start();
        }
        for(Thread t:arr)t.join();
        System.out.println("Final count: "+counter.count);
    }
}
```

## OUTPUT:
<img width="546" height="312" alt="image" src="https://github.com/user-attachments/assets/65a038ae-0460-4228-ae51-af2d3d3d4a94" />



## RESULT:
Thus, the Java program using a synchronized block to safely increment a shared counter with multiple threads was executed successfully.
