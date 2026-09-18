# Ex.No:5(A) INPUTSTREAMREADER 

## QUESTION:
Write a program to read user input from the keyboard using InputStreamReader 

## AIM:
To write a program that read user input from the keyboard using InputStreamReader 

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create an InputStreamReader to read input from the keyboard.
4. Create a BufferedReader using the InputStreamReader.
5. Read the name entered by the user using readLine().
6. Display "Hello, " followed by the entered name and "!".
7. Stop the program.


## PROGRAM:
 ```
/*
Program to implement a InputStreamReader using Java
Developed by: Shreya R
RegisterNumber:  212224060248
*/
```

## SOURCE CODE:
```
import java.io.InputStreamReader;
import java.io.BufferedReader;
import java.io.IOException;
public class Main{
    public static void main(String[] args)throws IOException{
        InputStreamReader isr=new InputStreamReader(System.in);
        BufferedReader br=new BufferedReader(isr);
        String name=br.readLine();
        System.out.println("Hello, "+name+"!");
    }
}
```


## OUTPUT:
<img width="486" height="197" alt="image" src="https://github.com/user-attachments/assets/d04facbb-48f8-48ab-87d5-13795a7bb2ce" />


## RESULT:
Thus, the Java program to read user input from the keyboard using InputStreamReader was executed successfully and the entered input was displayed.
