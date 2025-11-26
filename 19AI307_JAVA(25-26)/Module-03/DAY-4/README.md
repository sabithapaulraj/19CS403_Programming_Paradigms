## Ex.No:3(D)    INTERFACE 


### QUESTION:
You are developing bots that analyze weather data.  
Each bot must implement a common interface and produce a temperature-based prediction.

### Bot Types:

#### SunBot  
- Predicts `"HOT"` if temperature > 30  
- Else returns `"MODERATE"`

#### RainBot  
- Predicts `"COLD"` if temperature < 20  
- Else returns `"WARM"`

### Input:
- temperature (int)  
- botType → `1` for SunBot, `2` for RainBot  

### Output:
- Prediction string produced by the selected bot

Example:

Input:
```
35 1
```

Output:
```
HOT
```

---

### AIM:
To implement an interface in Java and override methods in different bot classes that analyze temperature and return predictions.

---

### ALGORITHM:

1. Create an interface `WeatherBot` with a method `predict(int temperature)`.  
2. Implement `SunBot` class that overrides `predict()` to return `"HOT"` or `"MODERATE"`.  
3. Implement `RainBot` class that overrides `predict()` to return `"COLD"` or `"WARM"`.  
4. Read temperature and bot type from the user.  
5. Based on bot type, create the respective bot object.  
6. Call the `predict()` method and display the prediction.

---

### PROGRAM:

```
Program to implement weather prediction using interface-based bots
Developed by: Sabitha P
RegisterNumber: 212222040137
```

---

### Sourcecode.java:

```java
import java.util.*;

interface WeatherBot {
    String predict(int temperature);
}

class SunBot implements WeatherBot {
    public String predict(int temperature) {
        if (temperature > 30) return "HOT";
        return "MODERATE";
    }
}

class RainBot implements WeatherBot {
    public String predict(int temperature) {
        if (temperature < 20) return "COLD";
        return "WARM";
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        
        int temperature = sc.nextInt();
        int botType = sc.nextInt();
        
        WeatherBot bot;
        if (botType == 1)
            bot = new SunBot();
        else
            bot = new RainBot();
        
        System.out.println(bot.predict(temperature));
    }
}
```

---

### OUTPUT:
<img width="445" height="173" alt="image" src="https://github.com/user-attachments/assets/c49e80b9-c48d-45e9-86c0-214c6fd77e36" />


---

### RESULT:
Thus, the Java program implementing weather prediction using interfaces and bot classes was successfully executed.

