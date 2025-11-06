**Charles Liu and Seth Aguilar**
Dr. Parteek Kumar
$11/3/2025$

___

### **Task 1**

```py
def helper():
	print("Connecting to server...")
	total = 0
	for i in range(5):
		total += i
	save_to_file("log.txt", "Finished")
```

*Cohesion Type:* Coincidental cohesion

*Reason*: It performs a bunch of unrelated tasks, like connecting, iterating, and saving.

*Improvement*: Split into multiple functions
```py
def connect_to_server():
	print("Connecting to server...")
	
def calculate_total():
	total = 0
	for i in range(5):
		total += i
	return total

def log_status():
	save_to_file("log.txt", "Finished")
```

___

### **Task 2**

```py
def handle_event(event_type, data):
    if event_type == "click":
        print("Clicked:", data)
    elif event_type == "keypress":
        print("Key pressed:", data)
    elif event_type == "hover":
        print("Hovered over:", data)
```

*Cohesion Type*: Logical cohesion

*Reason*: It uses a bunch of events that are triggered under different conditions (click, keypress, hover).

*Improvement*: Split it into functions for each keypress
```py
def handle_event(event_type,data):
	handlers = {
        "click": handle_click,
        "keypress": handle_keypress,
        "hover": handle_hover
    }
    handler = handlers.get(event_type)
    if handler:
	    handler(data)
	else:
		print("Unknown event:", event_type)

def handle_click(data):
    print("Clicked:", data)

def handle_keypress(data):
    print("Key pressed:", data)

def handle_hover(data):
    print("Hovered over:", data)
```

___

### **Task 3**

```py
def startup_sequence():
	load_settings()
    connect_to_database()
    open_log_file()
    display_welcome_message()
```

*Cohesion Type*: Temporal cohesion

*Reason*: Executes functions based on time

*Improvement*: Split up functions into groups in specific files related to completing a whole task.
```py
# initialize.py
def initialize():
	load_settings()
	connect_to_database()
	
# logging.py
def prepare_log():
	open_log_file()

# welcome.py
def greet_user():
	display_welcome_message()
	
#startup.py
def startup_sequence():
	initialize_system()
	prepare_logging()
	greet_user()
```

___


### **Task 4**

```py
settings = {"theme": "dark", "autosave": True}

def read_settings():
    return settings["theme"]

def update_settings(key, value):
    settings[key] = value
```

*Cohesion Type*: Communicational Cohesion

*Reason*: Both function operate on the same data structure (settings), sharing input/output and are related for the same purpose of managing settings.

*Improvement*: Add a class to make crucial data structures related to a given task encapsulated, and not global.

```py
class SettingsManager
	def __init__(self):
	    self.settings = {"theme": "dark", "autosave": True}
	
	def read_setting(self, key):
		return self.settings.get(key)

	def update_setting(self, key, value):
		self.settings[key] = value

	def show_all_settings(self):
		return self.settings
```

___

### **Task 5**

```py
def process_order(order):
    items = validate_items(order)
    total = calculate_total(items)
    receipt = generate_receipt(order, total)
    email_receipt(receipt)
```

*Cohesion Type*: Sequential cohesion

*Reason*: Each step uses the output from the previous step, receipt uses total calculation which uses item validation. They are connected in input/output style.

*Improvement*: 
```py
def validate_order(order):
	return validate_items(order)
```

___

### **Task 6**

```py
def prepare_student_profile(student):
    student.id = assign_id()
    student.status = "active"
    student.balance = 0
    notify_advisor(student)
```


*Cohesion Type*: Procedural Cohesion

*Reason*: Each tasks performs a specific task and is grouped together in logical order.

*Improvement*:  Break up related parts, notify advisor is different from initialization.
```py
def initialize_student_profile(student):
    student.id = assign_id()
    student.status = "active"
    student.balance = 0

def prepare_student(student):
    initialize_student(student)
    notify_advisor(student)
```
___

1. Which task shows the _weakest cohesion_?

Task 1, coincidental. It combines totally unrelated stuff together in a not very modular fashion.
  
2. Which one is closest to _functional cohesion_?

Task 6, since it mostly groups related tasks but could be further subdivided. It is much better than the rest though.

3. How does increasing cohesion affect debugging and maintenance?

It makes it easier to debug, as you can pinpoint precisely what is breaking, and makes it easier to maintain since functions are more readable and manageable.

___