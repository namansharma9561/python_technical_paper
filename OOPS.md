
# OOPs in Python

Object-Oriented Programming (OOP) is a programming paradigm based on classes and objects.

Python supports the following OOP concepts:

- Class
- Object
- Constructor
- self keyword
- Inheritance
- Polymorphism
- Encapsulation
- Abstraction

---

# 1. Class and Object

## Class

A class is a blueprint for creating objects.

## Object

An object is an instance of a class.

---

## Example

```python
class Student:
    def __init__(self, name):
        self.name = name

    def show(self):
        print("Student Name:", self.name)

s1 = Student("Naman")

s1.show()
```

---

# 2. Constructor (`__init__`)

A constructor is automatically called when an object is created.

---

## Example

```python
class Car:
    def __init__(self, brand):
        self.brand = brand

c1 = Car("Toyota")

print(c1.brand)
```

---

# 3. self Keyword

`self` refers to the current object.

It is used to access variables and methods of the class.

---

## Example

```python
class Employee:
    def __init__(self, name):
        self.name = name

    def display(self):
        print(self.name)

e1 = Employee("Rahul")

e1.display()
```

---

# 4. Inheritance

Inheritance allows one class to use properties and methods of another class.

---

## Example

```python
class Animal:
    def sound(self):
        print("Animal makes sound")

class Dog(Animal):
    def bark(self):
        print("Dog barks")

d1 = Dog()

d1.sound()
d1.bark()
```

---

# 5. Polymorphism

Polymorphism means one method behaves differently for different objects.

---

## Example

```python
class Bird:
    def sound(self):
        print("Bird sound")

class Sparrow(Bird):
    def sound(self):
        print("Chirp Chirp")

class Crow(Bird):
    def sound(self):
        print("Caw Caw")

s = Sparrow()
c = Crow()

s.sound()
c.sound()
```

---

# 6. Encapsulation

Encapsulation means wrapping data and methods into a single unit.

Private variables are created using `__`.

---

## Example

```python
class Bank:
    def __init__(self):
        self.__balance = 1000

    def show_balance(self):
        print(self.__balance)

b1 = Bank()

b1.show_balance()
```

---

# 7. Abstraction

Abstraction hides implementation details and shows only essential functionality.

Python uses the `abc` module for abstraction.

---

## Example

```python
from abc import ABC, abstractmethod

class Vehicle(ABC):

    @abstractmethod
    def start(self):
        pass

class Bike(Vehicle):

    def start(self):
        print("Bike Started")

b1 = Bike()

b1.start()
```

---

# 8. super() Function

`super()` is used to call parent class methods or constructors.

---

## Example

```python
class Person:
    def __init__(self, name):
        self.name = name

class Student(Person):
    def __init__(self, name, grade):
        super().__init__(name)
        self.grade = grade

s1 = Student("Naman", "A")

print(s1.name)
print(s1.grade)
```

---

# 9. Method Overriding

Method overriding occurs when a child class provides its own implementation of a parent method.

---

## Example

```python
class Parent:
    def show(self):
        print("Parent Method")

class Child(Parent):
    def show(self):
        print("Child Method")

c1 = Child()

c1.show()
```

---

# 10. Magic Methods

Magic methods are special methods with double underscores.

Examples:

- `__init__`
- `__str__`

---

## Example

```python
class Book:
    def __init__(self, pages):
        self.pages = pages

    def __str__(self):
        return f"Book has {self.pages} pages"

b1 = Book(200)

print(b1)
```

---

# Author

**Naman Sharma**
