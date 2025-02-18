---
title: Methods in Python
description: Learn about methods in Python. Methods are functions defined within a class. They encapsulate behavior that is specific to instances of the class. Understanding methods is essential for effective object-oriented programming. Let's delve into the properties, advantages, and potential disadvantages of methods in Python classes. You are going to talk about different types of methods in Python classes Like Instance Methods, Class Methods, Static Methods, Abstract Methods, Magic Methods, Getter and Setter Methods.
sidebar: 
    order: 82
---

## Methods in Class in Python: A Comprehensive Guide

In Python, methods are functions defined within a class. They encapsulate behavior that is specific to instances of the class. Understanding methods is essential for effective object-oriented programming. Let's delve into the properties, advantages, and potential disadvantages of methods in Python classes.

### Properties of Methods in Python Classes:

1. **Encapsulation:**
   - **Description:** Methods encapsulate behavior, grouping related functionality within a class.
   - **Advantage:** Encapsulation promotes code organization, making it easier to manage and maintain.

2. **Self Parameter:**
   - **Description:** All methods in a class have `self` as their first parameter, representing the instance calling the method.
   - **Advantage:** Allows methods to access and manipulate the state of the instance, ensuring proper encapsulation.

3. **Access to Class Attributes:**
   - **Description:** Methods have access to the class's attributes and can modify them using the `self` parameter.
   - **Advantage:** Facilitates the manipulation of object state, contributing to the concept of encapsulation.

4. **Behavior Definition:**
   - **Description:** Methods define the behavior of objects instantiated from the class.
   - **Advantage:** Enables the modeling of real-world actions, providing a blueprint for how instances should operate.

5. **Code Reusability:**
   - **Description:** Methods can be reused across different instances of the same class.
   - **Advantage:** Promotes code reusability, reducing redundancy and improving maintainability.

### Advantages of Methods in Python Classes:

1. **Modularity:**
   - **Description:** Methods contribute to the modularity of code by organizing functionality into discrete units.
   - **Advantage:** Enhances code readability, maintenance, and the ability to make targeted updates.

2. **Object-Specific Behavior:**
   - **Description:** Methods allow for the definition of behavior specific to each instance of a class.
   - **Advantage:** Enables objects to exhibit unique actions based on their state.

3. **Inheritance:**
   - **Description:** Methods support the inheritance mechanism, allowing subclasses to override or extend methods from their superclass.
   - **Advantage:** Facilitates code reuse and the creation of specialized classes.

4. **Code Clarity:**
   - **Description:** Methods contribute to a clearer organization of code by associating related actions with a specific class.
   - **Advantage:** Improves code maintainability and makes it easier for developers to understand the functionality of a class.

5. **Encapsulation of State:**
   - **Description:** Methods work in conjunction with attributes to encapsulate the state of an object.
   - **Advantage:** Promotes data integrity and makes it easier to manage and control access to object state.

### Potential Disadvantages of Methods in Python Classes:

1. **Complexity:**
   - **Description:** As the number of methods in a class increases, the complexity of the class may also rise.
   - **Disadvantage:** A highly complex class can be challenging to understand and maintain.

2. **Tight Coupling:**
   - **Description:** Methods may introduce dependencies between different parts of a class, leading to tight coupling.
   - **Disadvantage:** High coupling can make the class less flexible and harder to modify without affecting other components.

3. **Overhead:**
   - **Description:** Adding numerous methods to a class might introduce a slight runtime overhead.
   - **Disadvantage:** While typically negligible, excessive method calls could impact performance in some scenarios.

4. **Overuse of Accessors and Mutators:**
   - **Description:** Excessive use of accessor and mutator methods (getters and setters) might violate principles of good design.
   - **Disadvantage:** It can lead to classes that are overly focused on exposing internal state, potentially undermining encapsulation.

5. **Learning Curve:**
   - **Description:** For individuals new to object-oriented programming, understanding the concept of methods and their proper use can pose a learning curve.
   - **Disadvantage:** Novice programmers may initially find it challenging to grasp when and how to use methods effectively.

### Types of Methods in Python Classes:
- **Instance Methods**
- **Class Methods**
- **Static Methods**
- **Getter and Setter Methods**

## Instance Methods
Instance methods are the most common type of methods in Python classes. They are defined within a class and are accessible only through an instance of the class. Instance methods have access to the instance's state through the `self` parameter. They can also access the class's attributes and other methods using the `self` parameter.

### Syntax of Instance Methods in Python Classes:
```python title="method.py" showLineNumbers{1} {1-3}
class ClassName:
    def method_name(self, parameters):
        # Method body
```

### Example of Instance Methods in Python Classes:
```python title="instance_method.py" showLineNumbers{1} {5-7, 11-12}
class Employee:
    def __init__(self, name, salary):
        self.name = name
        self.salary = salary
    def display(self):
        print('Name:', self.name)
        print('Salary:', self.salary)

employee1 = Employee('John', 10000)
employee2 = Employee('Bob', 20000)
employee1.display()
employee2.display()
```

Output:
```cmd title="command" showLineNumbers{1} {2-7}
C:\Users\username>python instance_method.py
Name: John
Salary: 10000
Name: Bob
Salary: 20000
```

In the above example, we have created two instance variables named `name` and `salary`. We have initialized the `name` and `salary` variables to the `name` and `salary` parameters of the `__init__()` method. We have printed the `name` and `salary` variables using the `employee1` and `employee2` objects. The output shows that the `name` and `salary` variables are unique to the object.

Another Example of Instance Methods in Python Classes:

```python title="instance_method.py" showLineNumbers{1} {5-7, 11-12}
class Student:
    def register(self, name, roll):
        self.name = name
        self.roll = roll

    def display(self):
        print('Name:', self.name)
        print('Roll:', self.roll)

student1 = Student()
student1.register('John', 1)
student1.display()
```

Output:
```cmd title="command" showLineNumbers{1} {2-7}
C:\Users\username>python instance_method.py
Name: John
Roll: 1
```

In the above example, we have created two instance variables named `name` and `roll`. We have initialized the `name` and `roll` variables to the `name` and `roll` parameters of the `register()` method. We have printed the `name` and `roll` variables using the `student1` object. The output shows that the `name` and `roll` variables are unique to the object.

## Class Methods
Class methods are methods that are bound to a class rather than its instances. They are defined using the `@classmethod` decorator and have access to the class's state through the `cls` parameter. Class methods can be used to create factory methods, which are methods that return an instance of the class. They can also be used to modify a class's state that applies across all instances of the class. Class methods are commonly used as alternative constructors.


### Syntax of Class Methods in Python Classes:
```python title="Syntax" showLineNumbers{1} {1-3}
class ClassName:
    @classmethod
    def method_name(cls, parameters):
        # Method body
```

### Example of Class Methods in Python Classes:
```python title="class_method.py" showLineNumbers{1} {8-11, 14}
class Employee:
    def __init__(self, name, salary):
        self.name = name
        self.salary = salary
    def display(self):
        print('Name:', self.name)
        print('Salary:', self.salary)
    @classmethod
    def from_string(cls, emp_str):
        name, salary = emp_str.split('-')
        return cls(name, salary)

employee1 = Employee('John', 10000)
employee2 = Employee.from_string('Bob-20000')
employee1.display()
employee2.display()
```

Output:
```cmd title="command" showLineNumbers{1} {2-7}
C:\Users\username>python class_method.py
Name: John
Salary: 10000
Name: Bob
Salary: 20000
```

In the above example, we have created two instance variables named `name` and `salary`. We have initialized the `name` and `salary` variables to the `name` and `salary` parameters of the `__init__()` method. We have printed the `name` and `salary` variables using the `employee1` and `employee2` objects. The output shows that the `name` and `salary` variables are unique to the object. We have created a class method named `from_string()` using the `@classmethod` decorator. We have called the `from_string()` method using the `Employee` class and `employee2` object. The output shows that the `from_string()` method is accessible through both the `Employee` class and `employee2` object.

Another Example of Class Methods in Python Classes:

```python title="class_method.py" showLineNumbers{1} {16-24, 26-29}
class IronMan:
    def suitUp(self):
        print('Suiting up...')
    def startEngine(self):
        print('Starting engine...')
    def workingJarvis(self):
        print('Working Jarvis...')
    def fly(self):
        print('Flying...')
    def land(self):
        print('Landing...')
    def suitDown(self):
        print('Suiting down...')
    def journey(self, location):
        print('Journey started to ' + location)
    @classmethod
    def goToMars(cls):
        cls().suitUp()
        cls().startEngine()
        cls().workingJarvis()
        cls().fly()
        cls().journey('Mars')
        cls().land()
        cls().suitDown()

IronMan.goToMars()
mark1 = IronMan()
mark1.goToMars()
```

Output:
```cmd title="command" showLineNumbers{1} {2-9}
C:\Users\username>python class_method.py
Suiting up...
Starting engine...
Working Jarvis...
Flying...
Journey started to Mars
Landing...
Suiting down...
```

In the above example, we have created seven instance methods named `suitUp()`, `startEngine()`, `workingJarvis()`, `fly()`, `land()`, `suitDown()`, and `journey()`. We have created a class method named `goToMars()` using the `@classmethod` decorator. We have called the `goToMars()` method using the `IronMan` class and `mark1` object. The output shows that the `goToMars()` method is accessible through both the `IronMan` class and `mark1` object.

## Static Methods
Static methods are methods that are bound to a class rather than its instances. They are defined using the `@staticmethod` decorator and do not have access to the class's state. Static methods are commonly used to create utility functions that do not require access to the class's state. They can also be used to group related functionality within a class. Static methods are similar to class methods, but they do not receive the class as an implicit first argument.

### Syntax of Static Methods in Python Classes:
```python title="Syntax" showLineNumbers{1} {1-3}
class ClassName:
    @staticmethod
    def method_name(parameters):
        # Method body
```

### Example of Static Methods in Python Classes:
```python title="static_method.py" showLineNumbers{1} {8-11, 15-16}
class Employee:
    def __init__(self, name, salary):
        self.name = name
        self.salary = salary
    def display(self):
        print('Name:', self.name)
        print('Salary:', self.salary)
    @staticmethod
    def is_valid_salary(salary):
        if salary > 0:
            return True
        else:
            return False

employee1 = Employee('John', 10000)
employee2 = Employee('Bob', 20000)
print(Employee.is_valid_salary(10000))
print(Employee.is_valid_salary(-10000))
```

Output:
```cmd title="command" showLineNumbers{1} {2-7}
C:\Users\username>python static_method.py
True
False
```

In the above example, we have created two instance variables named `name` and `salary`. We have initialized the `name` and `salary` variables to the `name` and `salary` parameters of the `__init__()` method. We have printed the `name` and `salary` variables using the `employee1` and `employee2` objects. The output shows that the `name` and `salary` variables are unique to the object. We have created a static method named `is_valid_salary()` using the `@staticmethod` decorator. We have called the `is_valid_salary()` method using the `Employee` class. The output shows that the `is_valid_salary()` method is accessible through the `Employee` class.


Another Example of Static Methods in Python Classes:

```python title="static_method.py" showLineNumbers{1} {2-13, 15-18}
class Calculator:
    @staticmethod
    def add(a, b):
        return a + b
    @staticmethod
    def subtract(a, b):
        return a - b
    @staticmethod
    def multiply(a, b):
        return a * b
    @staticmethod
    def divide(a, b):
        return a / b

print(Calculator.add(10, 20))
print(Calculator.subtract(10, 20))
print(Calculator.multiply(10, 20))
print(Calculator.divide(10, 20))
```

Output:
```cmd title="command" showLineNumbers{1} {2-7}
C:\Users\username>python static_method.py
30
-10
200
0.5
```

In the above example, we have created four static methods named `add()`, `subtract()`, `multiply()`, and `divide()`. We have called the `add()`, `subtract()`, `multiply()`, and `divide()` methods using the `Calculator` class. The output shows that the `add()`, `subtract()`, `multiply()`, and `divide()` methods are accessible through the `Calculator` class.

## Getter and Setter Methods
Getter and setter methods are methods that are used to access and modify the state of an object. They are commonly used to control access to an object's attributes. Getter methods are used to access an object's attributes, while setter methods are used to modify an object's attributes. Getter and setter methods are also known as accessor and mutator methods.

### Syntax of Getter and Setter Methods in Python Classes:
```python title="Syntax" showLineNumbers{1} {1-3}
class ClassName:
    def get_attribute(self):
        # Method body
    def set_attribute(self, value):
        # Method body
```

### Example of Getter and Setter Methods in Python Classes:
```python title="getter_setter_method.py" showLineNumbers{1} {8-15, 17-27}
class Employee:
    def __init__(self, name, salary):
        self.name = name
        self.salary = salary
    def display(self):
        print('Name:', self.name)
        print('Salary:', self.salary)
    def get_name(self):
        return self.name
    def set_name(self, name):
        self.name = name
    def get_salary(self):
        return self.salary
    def set_salary(self, salary):
        self.salary = salary

employee1 = Employee('John', 10000)
employee1.display()
employee1.set_name('Bob')
employee1.set_salary(20000)
employee1.display()
print("Employee Name:", employee1.get_name())
print("Employee Salary:", employee1.get_salary())
```

Output:
```cmd title="command" showLineNumbers{1} {2-9}
C:\Users\username>python getter_setter_method.py
Name: John
Salary: 10000
Name: Bob
Salary: 20000
Employee Name: Bob
Employee Salary: 20000
```

In the above example, we have created two instance variables named `name` and `salary`. We have initialized the `name` and `salary` variables to the `name` and `salary` parameters of the `__init__()` method. We have printed the `name` and `salary` variables using the `employee1` object. The output shows that the `name` and `salary` variables are unique to the object. We have created getter and setter methods for the `name` and `salary` variables. We have called the getter and setter methods using the `employee1` object. The output shows that the getter and setter methods are accessible through the `employee1` object. We have printed the `name` and `salary` variables using the getter methods. The output shows that the getter methods are accessible through the `employee1` object.

Another Example of Getter and Setter Methods in Python Classes:

```python title="getter_setter_method.py" showLineNumbers{1} {8-15, 17-27}
class Student:
    def __init__(self, name, roll):
        self.name = name
        self.age = age
    def display(self):
        print('Name:', self.name)
        print('Age:', self.age)
    def get_name(self):
        return self.name
    def set_name(self, name):
        self.name = name
    def get_age(self):
        return self.age
    def set_age(self, age):
        if age > 18:
            self.age = age
        else:
            print('Age must be greater than 18')

student1 = Student('John', 20)
student1.display()
student1.set_name('Bob')
student1.set_age(15)
student1.set_age(30)
student1.display()
print("Student Name:", student1.get_name())
print("Student Age:", student1.get_age())
```

Output:
```cmd title="command" showLineNumbers{1} {2-9}
C:\Users\username>python getter_setter_method.py
Name: John
Age: 20
Age must be greater than 18
Name: Bob
Age: 30
Student Name: Bob
Student Age: 30
```

In the above example, we have created two instance variables named `name` and `age`. We have initialized the `name` and `age` variables to the `name` and `age` parameters of the `__init__()` method. We have printed the `name` and `age` variables using the `student1` object. The output shows that the `name` and `age` variables are unique to the object. We have created getter and setter methods for the `name` and `age` variables. We have called the getter and setter methods using the `student1` object. The output shows that the getter and setter methods are accessible through the `student1` object. We have printed the `name` and `age` variables using the getter methods. The output shows that the getter methods are accessible through the `student1` object. In the above example, we have used the setter method to validate the `age` variable that it must be greater than 18. If the `age` variable is less than 18, then it will print the message `Age must be greater than 18`. Otherwise, it will set the `age` variable to the `age` parameter of the `set_age()` method.

## Conclusion
In this tutorial, you have learned about methods in Python classes. Methods are functions defined within a class. They encapsulate behavior that is specific to instances of the class. Understanding methods is essential for effective object-oriented programming. Let's delve into the properties, advantages, and potential disadvantages of methods in Python classes. You have also learned about different types of methods in Python classes Like Instance Methods, Class Methods, Static Methods, Getter and Setter Methods. You have also learned about the properties, advantages, and potential disadvantages of methods in Python classes. For more information, visit the [Python Classes](https://docs.python.org/3/tutorial/classes.html) page. For more tutorials like this, visit the Python Central Hub.