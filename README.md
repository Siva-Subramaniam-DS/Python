# 🧠 Object-Oriented Programming Concepts in Python

## 📚 Table of Contents

1. [Encapsulation](#encapsulation)
2. [Inheritance](#inheritance)
3. [Abstraction](#abstraction)
4. [Polymorphism](#polymorphism)

---

## 🔒 1. Encapsulation

### ✅ Example Code

```python
class BankAccount:
    def __init__(self, owner, balance):
        self.owner = owner
        self.__balance = balance  # Private variable

    def deposit(self, amount):
        if amount > 0:
            self.__balance += amount

    def withdraw(self, amount):
        if 0 < amount <= self.__balance:
            self.__balance -= amount

    def get_balance(self):
        return self.__balance
```

### 💡 Output

```python
account = BankAccount("Alice", 1000)
account.deposit(500)
account.withdraw(300)
print(account.get_balance())  # Output: 1200
```

### 🧾 Pseudocode

```
Class BankAccount
    Private Variable balance
    Public Variable owner

    Constructor(owner, initial_balance)
        Set owner = owner
        Set balance = initial_balance

    Method deposit(amount)
        If amount > 0 Then
            balance = balance + amount

    Method withdraw(amount)
        If amount > 0 AND amount <= balance Then
            balance = balance - amount

    Method get_balance()
        Return balance
End Class
```

---

## 🧬 2. Inheritance

### ✅ Example Code

```python
class Animal:
    def speak(self):
        return "Animal sound"

class Dog(Animal):
    def speak(self):
        return "Bark"

class Cat(Animal):
    def speak(self):
        return "Meow"
```

### 💡 Output

```python
dog = Dog()
cat = Cat()
print(dog.speak())  # Output: Bark
print(cat.speak())  # Output: Meow
```

### 🧾 Pseudocode

```
Class Animal
    Method speak()
        Return "Animal sound"

Class Dog Inherits Animal
    Method speak()
        Return "Bark"

Class Cat Inherits Animal
    Method speak()
        Return "Meow"
```

---

## 🧱 3. Abstraction

### ✅ Example Code

```python
from abc import ABC, abstractmethod

class Vehicle(ABC):
    @abstractmethod
    def start_engine(self):
        pass

class Car(Vehicle):
    def start_engine(self):
        return "Car engine started"
```

### 💡 Output

```python
car = Car()
print(car.start_engine())  # Output: Car engine started
```

### 🧾 Pseudocode

```
Abstract Class Vehicle
    Abstract Method start_engine()

Class Car Inherits Vehicle
    Method start_engine()
        Return "Car engine started"
```

---

## 🌀 4. Polymorphism

### ✅ Example Code

```python
class Bird:
    def sound(self):
        return "Some bird sound"

class Sparrow(Bird):
    def sound(self):
        return "Chirp"

class Parrot(Bird):
    def sound(self):
        return "Squawk"

def make_sound(bird):
    print(bird.sound())
```

### 💡 Output

```python
make_sound(Sparrow())  # Output: Chirp
make_sound(Parrot())   # Output: Squawk
```

### 🧾 Pseudocode

```
Class Bird
    Method sound()
        Return "Some bird sound"

Class Sparrow Inherits Bird
    Method sound()
        Return "Chirp"

Class Parrot Inherits Bird
    Method sound()
        Return "Squawk"

Function make_sound(bird)
    Print bird.sound()
```

---
