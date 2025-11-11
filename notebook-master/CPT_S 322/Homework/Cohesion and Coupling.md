**Charles Liu**
Dr. Parteek Kumar
$11/9/2025$

___

### **Part A: Cohesion**

**1. Calculator Class**

```cpp
class Calculator {
public:
    int add(int a, int b) {
        return a + b;
    }
    
    int multiply(int a, int b) {
        return a * b;
    }
};

int main() {
    Calculator calc;
    int sum = calc.add(5, 3);
    int product = calc.multiply(4, 2);
    return 0;
}
```

*Type of Cohesion:* Functional Cohesion
*Explanation:* The functions each perform a specific task to achieve a cohesive goal
*Fix:* The current design is already strong. You could add private attributes to make operations on shared data, but this may already be sufficient. You could also work on making the whole process have a better goal.

---

**2. StringProcessor Class**

```cpp
class StringProcessor {
public:
    std::string readString() {
        return "Hello World!";
    }
    
    int getStringLength(const std::string& str) {
        return str.length();
    }
};

int main() {
    StringProcessor processor;
    std::string text = processor.readString();
    int length = processor.getStringLength(text);
    return 0;
}
```

*Types of Cohesion:* Sequential cohesion
*Explanation:* Main calls related functions that produce data, then pass output into the next one.
*Fix:* The current design is already strong. Small improvements could be more meaningful functions and grouping related tasks, or storing data like text in private attributes in the class. Also making the whole process have a clearer goal.

---

**3. Statistics Class**

```cpp
class Statistics {
public:
    void calculateAverage(int arr[], int size) {
        // Calculates the average
    }

    void findMax(int arr[], int size) {
        // Finds the maximum value
    }
};

int main() {
    int data[] = {5, 10, 15, 20};
    Statistics stats;
    stats.calculateAverage(data, 4);
    stats.findMax(data, 4);
    return 0;
}
```

*Types of Cohesion:* Communicational Cohesion
*Explanation:* Functions like `calculateAverage` and `findMax` operate on the same data outside the `stats` object, providing higher risk of side effects.
*Fix:* Incorporate `data[]` as a private parameter in `Statistics` that can be operated on. Remove `data` as parameters from `calculateAverage` and `findMax`.

---

**4. FileProcessor Class**

```cpp
class FileProcessor {
public:
    void openFile() {
        // Opens the file
    }

    void readFile() {
        // Reads the file
    }

    void closeFile() {
        // Closes the file
    }
};

int main() {
    FileProcessor file;
    file.openFile();
    file.readFile();
    file.closeFile();
    return 0;
}
```

*Type of Cohesion:* Procedural Cohesion
*Explanation:* This executes file reading in the specific order that is required, open, read, and close. Its grouped based off this order.
*Fix:* Group all the file procedure stuff into a single function inside the file attribute to show a clearer goal.

---

**5. SystemInitializer Class**

```cpp
class SystemInitializer {
public:
    void initializeLogging() {
        // Set up logging
    }

    void initializeNetwork() {
        // Set up network connection
    }

    void initializeDatabase() {
        // Set up database connection
    }
};

int main() {
    SystemInitializer initializer;
    initializer.initializeLogging();
    initializer.initializeNetwork();
    initializer.initializeDatabase();
    return 0;
}
```

*Type of Cohesion*: Logical Cohesion
*Explanation:* It groups related tasks like initializing logging, network, and database together.
*Fix:* Group all together in an initialization function in the `SystemInitializer` class.

___

### **Part B: Coupling**

**1. Direct Field Access Between Classes**

```cpp
class ClassA {
public:
    int data;
    void setData(int value) {
        data = value;
    }
};

class ClassB {
public:
    void modifyData(ClassA& a) {
        a.data = 100; // Direct access
    }
};

int main() {
    ClassA a;
    ClassB b;
    a.setData(10);
    b.modifyData(a);
    return 0;
}
```

*Type of Coupling:* Content Coupling
*Explanation:* Class B's modify data takes in the whole A object, not just needed parameter, then makes a direct change without using the proper setter (characteristic of content coupling).
*Fix:* Only pass in the parameter needed (`a.data`), and modify with `setData()`.

---

**2. Global Variable** 

```cpp
int sharedVariable = 0;

void function1() {
    sharedVariable += 10;
}

void function2() {
    sharedVariable *= 2;
}

int main() {
    function1();
    function2();
    return 0;
}
```

*Type of Coupling:* Common Coupling
*Explanation:* `function1()` and `function2()` both share the `sharedVariable` which is basically global in this case. This highly increases likelihood of side effects.
*Fix:* Get rid of global variable and instead pass local variable as parameter to the functions.

---

**3. Process Class**

```cpp
class Process {
public:
    void execute(int controlFlag) {
        if (controlFlag == 1) {
            // Action 1
        } else {
            // Action 2
        }
    }
};

int main() {
    Process process;
    process.execute(1);
    return 0;
}
```

*Type of Coupling:* Control Coupling
*Explanation:* The process object is controlled a passed in control flag.
*Fix:* Get rid of the control flag as it creates dependencies and decreases code readability, and instead separate the two actions into clear and explicit functions.

---

**4. Person Class**

```cpp
struct Person {
    std::string name;
    int age;
};

class Process {
public:
    void displayPersonInfo(const Person& person) {
        std::cout << "Name: " << person.name << std::endl;
    }
};

int main() {
    Person person = {"John Doe", 30};
    Process process;
    process.displayPersonInfo(person);
    return 0;
}
```

*Type of Coupling:* Stamp Coupling
*Explanation:* Instead of just passing in the needed parameter in `displayPersonInfo` (which is `name`), it passes the whole `Person` object.
*Fix:* Only pass the needed parameter `name`.

---

**5. Calculator Class**

```cpp
class Calculator {
public:
    int add(int a, int b) {
        return a + b;
    }
};

int main() {
    Calculator calc;
    int sum = calc.add(5, 10);
    std::cout << "Sum: " << sum << std::endl;
    return 0;
}
```

*Type of Coupling:* Data Coupling
*Explanation:* This function only passes the attributes it needs to calculate a sum, and each part has a cohesive goal.
*Fix:* Nothing much needed to do here, perhaps add a private storage of the two variables `a,b` in calculator that are changed based on user input and setters.

___

### **Reflection**

Understanding and analyzing coupling/cohesion can help prevent errors and improve readability/maintainability of code. Designing with coupling/cohesion in mind is just as important. High cohesion helps make sure each module/class has a single clear purpose. Low coupling ensures few dependencies between modules, decreasing risk. From this activity, I learned that small adjustments, like passing parameters instead of objects, or adding more attributes to classes, can make a big difference in improving structure. In future projects, I will apply these principles to write cleaner, modular code.