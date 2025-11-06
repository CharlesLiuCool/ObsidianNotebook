**Charles Liu**
Dr. Parteek Kumar
$11/5/2025$

___

### **Snippet 1**

```py
def calculate_total(price, quantity):  
    return price * quantity

def checkout():  
    total = calculate_total(10, 3)  
    print(total)
```

*Type of Coupling*: Data coupling. The two functions only share data through paramaters required, nothing more nothing less.

___

### **Snippet 2**

```py
def toggle_feature(flag):  
    if flag:  
        print("Feature ON")  
    else:  
        print("Feature OFF")

toggle_feature(True)
```

*Type of Coupling*: Control coupling. One module passes information that influences the logic of another. `True` is passed which changes `toggle_feature()` to do `ON` logic or `OFF` logic.

___

### **Snippet 3**

```py
class User:  
    def __init__(self, name):  
        self.name = name

def greet_user(user_obj):  
    print("Hello", user_obj.name)
```

*Type of Coupling*: Stamp coupling. We are passing the whole `user_obj` object while only using the name part.

___

### **Snippet 4**

```py
class Account:  
    def __init__(self):  
        self._pin = "4455"   

def show_pin(account):  
    print(account._pin)
```

*Type of Coupling*: Content coupling. We are accessing the internals of the account object in another module.

___

### **Snippet 5**

```py
settings = {"theme": "light"}

def enable_dark_mode():  
    settings["theme"] = "dark"

def print_theme():  
    print("Current theme:", settings["theme"])

  
enable_dark_mode()  
print_theme()
```

*Type of Coupling*: Common coupling. You're making changes in functions to global variables and accessing them.

___