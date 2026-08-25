# Ex.No:4(D) DESIGN PATTERN  ---- BEHAVIOUR PATTERN

## QUESTION:

A smart city has a grid of sensors installed across various zones to monitor Air Quality (AQI).
There are multiple SmartControllers subscribed to this network. Each SmartController is responsible for a specific AQI range:

GreenZoneController: AQI < 100

AlertZoneController: AQI between 100 and 200

DangerZoneController: AQI > 200

When a sensor reports data, only the relevant controller(s) should be notified based on the AQI.

What Students Must Do:
Implement the Observer pattern
SensorNetwork = Subject
Each SmartController = Observer
Each controller decides if it should react to a reported AQI (based on range)
When SensorNetwork receives data, it notifies only relevant observers
## AIM:
To develop a Java program that monitors AQI readings using a sensor network and notifies the appropriate smart controllers based on the reported AQI range.

## ALGORITHM :
1.	Start the program.
2.	Import the necessary package 'java.util'
3.	Create a sensor network to manage AQI readings.
4. Create and register the smart controllers.
5. Read the number of AQI readings.
6. For each reading, read the Sensor ID and AQI value.
7. Display the reported AQI value.
8. Notify the controllers about the AQI reading.
9. Each controller checks whether the AQI falls within its assigned range.
10.The relevant controller takes appropriate action.
11. Repeat for all AQI readings.
12. Stop the program.


## PROGRAM:
 ```
/*
Program to implement a Behaviour Pattern using Java
Developed by: Shreya R
RegisterNumber:  212224060248
*/
```

## SOURCE CODE:
```
import java.util.ArrayList;
import java.util.Scanner;

interface Observer {
    void update(String sensorId, int aqi);
}

class GreenZoneController implements Observer {

    public void update(String sensorId, int aqi) {

        if (aqi < 100) {

            System.out.println("[GreenZoneController]: AQI is good at Sensor "
                    + sensorId + ". No action needed.");
        }
    }
}

class AlertZoneController implements Observer {

    public void update(String sensorId, int aqi) {

        if (aqi >= 100 && aqi <= 200) {

            System.out.println("[AlertZoneController]: Moderate AQI at Sensor "
                    + sensorId + ". Send public health alert.");
        }
    }
}

class DangerZoneController implements Observer {

    public void update(String sensorId, int aqi) {

        if (aqi > 200) {

            System.out.println("[DangerZoneController]: Critical AQI at Sensor "
                    + sensorId + "! Trigger lockdown protocol.");
        }
    }
}

class SensorNetwork {

    ArrayList<Observer> observers = new ArrayList<>();

    void addObserver(Observer o) {
        observers.add(o);
    }

    void notifyObservers(String sensorId, int aqi) {

        System.out.println("Sensor " + sensorId + " reports AQI: " + aqi);

        for (Observer o : observers) {
            o.update(sensorId, aqi);
        }
    }
}

public class Main {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        SensorNetwork network = new SensorNetwork();

        network.addObserver(new GreenZoneController());
        network.addObserver(new AlertZoneController());
        network.addObserver(new DangerZoneController());

        int n = sc.nextInt();

        for (int i = 0; i < n; i++) {

            String sensorId = sc.next();
            int aqi = sc.nextInt();

            network.notifyObservers(sensorId, aqi);
        }

        sc.close();
    }
}
```



## OUTPUT:
<img width="1291" height="221" alt="image" src="https://github.com/user-attachments/assets/902c7201-3cb9-492e-8828-c32a10c68ea7" />



## RESULT:
The program was executed successfully. The sensor network processed the AQI readings and notified the appropriate smart controller based on the AQI range.
