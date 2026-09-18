# Ex.No:5(C)  FILE HANDLING USING JAVA
## QUESTION:

Write a program to count the number of characters in a file.
## AIM:
To write a program to count the number of characters in a file.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Open the file using FileReader.
4. Read the characters from the file one by one.
5. Increment the character count for each character read.
6. Display the total number of characters.
7. Close the file.
8. Stop the program.


## PROGRAM:
 ```
/*
Program to implement a File Handling using Java
Developed by: Shreya R
RegisterNumber:  212224060248
*/
```

## SOURCE CODE:

```
import java.util.*;
import java.io.*;
public class Main{
    public static void main(String[] args){
        Scanner sc=new Scanner(System.in);
        String fileName="uer.txt";
        String input=sc.nextLine();
        try{
            FileWriter wr=new FileWriter(fileName);
            wr.write(input);
            wr.close();
            FileReader rd=new FileReader(fileName);
            int count=0;
            int ch;
            while((ch=rd.read())!=-1){
                count++;
            }
            rd.close();
            System.out.println("Number of characters written to the file: "+count);
        }
        catch(IOException e){
            System.out.println(e);

        }
    }    
}
```

## OUTPUT:
<img width="1172" height="255" alt="image" src="https://github.com/user-attachments/assets/1cba077e-e92f-4f86-8335-594e0615774a" />



## RESULT:
Thus, the Java program to count the number of characters in a file was executed successfully, and the total number of characters in the file was displayed.
