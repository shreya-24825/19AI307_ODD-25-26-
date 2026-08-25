# Ex.No:4(D) DESIGN PATTERN -- ABSTRACT FACTORY

## QUESTION:

You’re creating a cross-platform UI tool using the Abstract Factory pattern. Implement factories to create Button and Checkbox for "dark" and "light" themes. Let the user choose the theme, then generate UI components and display their types

## AIM:
To develop a Java program that creates Button and Checkbox components based on the theme selected by the user, supporting both dark and light themes.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Define Button, Checkbox, and factory interfaces.
4. Create Dark and Light Button and Checkbox classes.
5. Create separate factories for dark and light themes.
6. Read the theme selected by the user.
7. Select the appropriate factory.
8. Create the Button and Checkbox.
9. Display the created UI components.
10. Stop the program.


## PROGRAM:
 ```
/*
Program to implement a Abstract Factory Pattern using Java
Developed by: Shreya R
RegisterNumber:  212224060248
*/
```

## SOURCE CODE:

```

import java.util.Scanner;

interface Button {
    void create();
}

interface Checkbox {
    void create();
}

class DarkButton implements Button {
    public void create() {
        System.out.println("Dark Button created");
    }
}

class DarkCheckbox implements Checkbox {
    public void create() {
        System.out.println("Dark Checkbox created");
    }
}

class LightButton implements Button {
    public void create() {
        System.out.println("Light Button created");
    }
}

class LightCheckbox implements Checkbox {
    public void create() {
        System.out.println("Light Checkbox created");
    }
}

interface UIFactory {
    Button createButton();
    Checkbox createCheckbox();
}

class DarkUIFactory implements UIFactory {
    public Button createButton() {
        return new DarkButton();
    }

    public Checkbox createCheckbox() {
        return new DarkCheckbox();
    }
}

class LightUIFactory implements UIFactory {
    public Button createButton() {
        return new LightButton();
    }

    public Checkbox createCheckbox() {
        return new LightCheckbox();
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        String theme = sc.nextLine().toLowerCase();

        UIFactory factory;

        if (theme.equals("dark")) {
            factory = new DarkUIFactory();
        } else if (theme.equals("light")) {
            factory = new LightUIFactory();
        } else {
            System.out.println("Invalid theme");
            return;
        }

        Button button = factory.createButton();
        Checkbox checkbox = factory.createCheckbox();

        button.create();
        checkbox.create();
         
    }
}
```


## OUTPUT:
<img width="625" height="297" alt="image" src="https://github.com/user-attachments/assets/67940095-d05a-4921-a59d-fec7f427bca7" />



## RESULT:
The program was executed successfully. Based on the selected theme, the appropriate Button and Checkbox components were created and their types were displayed correctly.
