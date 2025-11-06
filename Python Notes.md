# The Ultimate Python Guide for Beginners

## Table of Contents
1. [Introduction to Python](#introduction)
2. [Setting Up Python](#setup)
3. [Basic Syntax and Variables](#basics)
4. [Data Types](#data-types)
5. [Control Flow](#control-flow)
6. [Functions](#functions)
7. [Data Structures](#data-structures)
8. [Object-Oriented Programming](#oop)
9. [File Handling](#file-handling)
10. [Error Handling](#error-handling)
11. [Modules and Packages](#modules)
12. [Advanced Topics](#advanced)

---

## 1. Introduction to Python <a name="introduction"></a>

### What is Python?
Python is a high-level, interpreted programming language known for its simplicity and readability. It's used for:
- Web development
- Data science
- Artificial intelligence
- Automation
- Scientific computing

### Key Features:
- Easy to learn and read
- Cross-platform compatibility
- Large standard library
- Supports multiple programming paradigms

---

## 2. Setting Up Python <a name="setup"></a>

### Installation
1. Download from [python.org](https://python.org)
2. Verify installation:
```bash
python --version
# or
python3 --version
```

### Your First Python Program
```python
# hello_world.py
print("Hello, World!")
```

Run it:
```bash
python hello_world.py
```

---

## 3. Basic Syntax and Variables <a name="basics"></a>

### Comments
```python
# This is a single-line comment

"""
This is a multi-line comment
or docstring
"""

# Variables don't need type declaration
name = "John"
age = 25
height = 5.11
is_student = True
```

### Variable Naming Rules
```python
# Valid variable names
my_variable = "hello"
variable2 = "world"
_private_var = "private"
MAX_SIZE = 100  # Constants (convention)

# Invalid variable names
# 2variable = "invalid"  # Cannot start with number
# my-variable = "invalid"  # No hyphens
```

### Basic Input/Output
```python
# Getting user input
name = input("Enter your name: ")
age = int(input("Enter your age: "))  # Convert to integer

# Output
print("Hello,", name)
print(f"You are {age} years old")  # f-string (formatted string)
```

---

## 4. Data Types <a name="data-types"></a>

### Numeric Types
```python
# Integers
x = 10
y = -5
z = 0

# Floating-point numbers
pi = 3.14159
temperature = -10.5

# Complex numbers
complex_num = 3 + 4j

# Operations
a = 10
b = 3

print(a + b)  # Addition: 13
print(a - b)  # Subtraction: 7
print(a * b)  # Multiplication: 30
print(a / b)  # Division: 3.333...
print(a // b) # Floor division: 3
print(a % b)  # Modulus: 1
print(a ** b) # Exponentiation: 1000
```

### Strings
```python
# String creation
single_quotes = 'Hello'
double_quotes = "World"
triple_quotes = """This is a 
multi-line string"""

# String operations
text = "Python Programming"

print(len(text))           # Length: 18
print(text.upper())        # PYTHON PROGRAMMING
print(text.lower())        # python programming
print(text.title())        # Python Programming
print(text.find("Pro"))    # 7
print(text.replace("Python", "Java"))  # Java Programming

# String slicing
print(text[0:6])    # Python
print(text[7:])     # Programming
print(text[-11:])   # Programming
print(text[::2])    # Pto rgamn (every 2nd character)

# String formatting
name = "Alice"
age = 30
print(f"{name} is {age} years old")  # f-string
print("{} is {} years old".format(name, age))  # format method
```

### Boolean Type
```python
is_true = True
is_false = False

# Boolean operations
print(True and False)  # False
print(True or False)   # True
print(not True)        # False

# Comparison operators
x = 10
y = 5

print(x == y)  # Equal to: False
print(x != y)  # Not equal to: True
print(x > y)   # Greater than: True
print(x < y)   # Less than: False
print(x >= y)  # Greater than or equal: True
print(x <= y)  # Less than or equal: False
```

### None Type
```python
# Represents absence of value
empty_value = None
print(empty_value)  # None
```

---

## 5. Control Flow <a name="control-flow"></a>

### Conditional Statements
```python
# if-elif-else
age = 18

if age < 13:
    print("Child")
elif age < 20:
    print("Teenager")
elif age < 65:
    print("Adult")
else:
    print("Senior")

# Multiple conditions
temperature = 25
is_sunny = True

if temperature > 20 and is_sunny:
    print("Perfect weather!")
elif temperature > 30 or not is_sunny:
    print("Not ideal weather")

# Ternary operator
result = "Even" if age % 2 == 0 else "Odd"
print(result)
```

### Loops
```python
# For loop
print("Counting from 1 to 5:")
for i in range(1, 6):
    print(i)

# Looping through a list
fruits = ["apple", "banana", "cherry"]
for fruit in fruits:
    print(fruit)

# While loop
count = 0
while count < 5:
    print(f"Count: {count}")
    count += 1

# Loop control statements
for i in range(10):
    if i == 3:
        continue  # Skip this iteration
    if i == 7:
        break     # Exit loop
    print(i)
```

### Practical Example: Number Guessing Game
```python
import random

def guessing_game():
    secret_number = random.randint(1, 100)
    attempts = 0
    max_attempts = 7
    
    print("Welcome to the Number Guessing Game!")
    print(f"I'm thinking of a number between 1 and 100. You have {max_attempts} attempts.")
    
    while attempts < max_attempts:
        try:
            guess = int(input("Enter your guess: "))
            attempts += 1
            
            if guess < secret_number:
                print("Too low!")
            elif guess > secret_number:
                print("Too high!")
            else:
                print(f"Congratulations! You guessed the number in {attempts} attempts!")
                break
            
            print(f"Attempts left: {max_attempts - attempts}")
            
        except ValueError:
            print("Please enter a valid number!")
    
    else:
        print(f"Sorry! The number was {secret_number}")

# Uncomment to play the game
# guessing_game()
```

---

## 6. Functions <a name="functions"></a>

### Basic Functions
```python
# Simple function
def greet():
    print("Hello, World!")

greet()

# Function with parameters
def greet_person(name):
    print(f"Hello, {name}!")

greet_person("Alice")

# Function with return value
def add_numbers(a, b):
    return a + b

result = add_numbers(5, 3)
print(f"5 + 3 = {result}")

# Function with default parameters
def introduce(name, age=25, city="Unknown"):
    print(f"Name: {name}, Age: {age}, City: {city}")

introduce("Bob")
introduce("Charlie", 30, "New York")

# Function with keyword arguments
introduce(age=35, name="David", city="London")
```

### Advanced Function Concepts
```python
# Variable number of arguments
def calculate_average(*numbers):
    if len(numbers) == 0:
        return 0
    return sum(numbers) / len(numbers)

print(calculate_average(1, 2, 3, 4, 5))  # 3.0

# Keyword arguments
def create_profile(**details):
    for key, value in details.items():
        print(f"{key}: {value}")

create_profile(name="Emma", age=28, profession="Engineer")

# Lambda functions (anonymous functions)
square = lambda x: x ** 2
print(square(5))  # 25

# Using lambda with map and filter
numbers = [1, 2, 3, 4, 5]
squared = list(map(lambda x: x ** 2, numbers))
evens = list(filter(lambda x: x % 2 == 0, numbers))

print(squared)  # [1, 4, 9, 16, 25]
print(evens)    # [2, 4]
```

### Practical Example: Calculator
```python
def calculator():
    def add(a, b):
        return a + b
    
    def subtract(a, b):
        return a - b
    
    def multiply(a, b):
        return a * b
    
    def divide(a, b):
        if b == 0:
            return "Error: Division by zero"
        return a / b
    
    operations = {
        '+': add,
        '-': subtract,
        '*': multiply,
        '/': divide
    }
    
    print("Simple Calculator")
    print("Operations: +, -, *, /")
    
    try:
        num1 = float(input("Enter first number: "))
        operator = input("Enter operator: ")
        num2 = float(input("Enter second number: "))
        
        if operator in operations:
            result = operations[operator](num1, num2)
            print(f"{num1} {operator} {num2} = {result}")
        else:
            print("Invalid operator!")
    
    except ValueError:
        print("Please enter valid numbers!")

# Uncomment to use calculator
# calculator()
```

---

## 7. Data Structures <a name="data-structures"></a>

### Lists
```python
# Creating lists
fruits = ["apple", "banana", "cherry"]
numbers = [1, 2, 3, 4, 5]
mixed = [1, "hello", 3.14, True]

# List operations
fruits.append("orange")           # Add item
fruits.insert(1, "grape")         # Insert at position
fruits.remove("banana")           # Remove item
popped = fruits.pop()             # Remove and return last item

print(len(fruits))                # Length: 4
print("apple" in fruits)          # Check existence: True

# List slicing
numbers = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
print(numbers[2:5])     # [2, 3, 4]
print(numbers[:3])      # [0, 1, 2]
print(numbers[7:])      # [7, 8, 9]
print(numbers[::2])     # [0, 2, 4, 6, 8] (every 2nd)
print(numbers[::-1])    # [9, 8, 7, 6, 5, 4, 3, 2, 1, 0] (reverse)

# List comprehension
squares = [x**2 for x in range(1, 6)]
print(squares)  # [1, 4, 9, 16, 25]

even_squares = [x**2 for x in range(1, 11) if x % 2 == 0]
print(even_squares)  # [4, 16, 36, 64, 100]
```

### Tuples
```python
# Creating tuples (immutable)
coordinates = (10, 20)
single_element = (5,)  # Note the comma
mixed_tuple = (1, "hello", 3.14)

# Tuple operations
print(coordinates[0])        # 10
print(coordinates[1])        # 20
x, y = coordinates          # Unpacking
print(f"x: {x}, y: {y}")    # x: 10, y: 20

# Tuples are immutable
# coordinates[0] = 15  # This would cause an error
```

### Dictionaries
```python
# Creating dictionaries
person = {
    "name": "Alice",
    "age": 30,
    "city": "New York"
}

# Accessing values
print(person["name"])        # Alice
print(person.get("age"))     # 30
print(person.get("country", "Unknown"))  # Default value

# Modifying dictionaries
person["age"] = 31           # Update value
person["country"] = "USA"    # Add new key-value pair
del person["city"]           # Remove key-value pair

# Dictionary operations
print(person.keys())         # dict_keys(['name', 'age', 'country'])
print(person.values())       # dict_values(['Alice', 31, 'USA'])
print(person.items())        # dict_items([('name', 'Alice'), ...])

# Dictionary comprehension
squares = {x: x**2 for x in range(1, 6)}
print(squares)  # {1: 1, 2: 4, 3: 9, 4: 16, 5: 25}
```

### Sets
```python
# Creating sets (unique, unordered elements)
fruits = {"apple", "banana", "cherry"}
numbers = {1, 2, 3, 4, 5, 5, 4}  # Duplicates removed

# Set operations
fruits.add("orange")
fruits.remove("banana")

set1 = {1, 2, 3, 4, 5}
set2 = {4, 5, 6, 7, 8}

print(set1.union(set2))           # {1, 2, 3, 4, 5, 6, 7, 8}
print(set1.intersection(set2))    # {4, 5}
print(set1.difference(set2))      # {1, 2, 3}
```

### Practical Example: Student Management System
```python
class StudentManager:
    def __init__(self):
        self.students = {}
    
    def add_student(self, student_id, name, grade):
        self.students[student_id] = {"name": name, "grade": grade}
        print(f"Student {name} added successfully!")
    
    def remove_student(self, student_id):
        if student_id in self.students:
            name = self.students[student_id]["name"]
            del self.students[student_id]
            print(f"Student {name} removed successfully!")
        else:
            print("Student not found!")
    
    def display_students(self):
        if not self.students:
            print("No students in the system.")
            return
        
        print("\nStudent List:")
        for student_id, info in self.students.items():
            print(f"ID: {student_id}, Name: {info['name']}, Grade: {info['grade']}")
    
    def get_average_grade(self):
        if not self.students:
            return 0
        
        total = sum(info['grade'] for info in self.students.values())
        return total / len(self.students)

# Example usage
manager = StudentManager()
manager.add_student(101, "Alice", 85)
manager.add_student(102, "Bob", 92)
manager.add_student(103, "Charlie", 78)

manager.display_students()
print(f"Average grade: {manager.get_average_grade():.2f}")

manager.remove_student(102)
manager.display_students()
```

---

## 8. Object-Oriented Programming <a name="oop"></a>

### Classes and Objects
```python
class Dog:
    # Class attribute
    species = "Canis familiaris"
    
    # Constructor method
    def __init__(self, name, age, breed):
        # Instance attributes
        self.name = name
        self.age = age
        self.breed = breed
    
    # Instance method
    def bark(self):
        return f"{self.name} says woof!"
    
    def describe(self):
        return f"{self.name} is a {self.age}-year-old {self.breed}"

# Creating objects
dog1 = Dog("Buddy", 3, "Golden Retriever")
dog2 = Dog("Max", 5, "German Shepherd")

print(dog1.bark())        # Buddy says woof!
print(dog2.describe())    # Max is a 5-year-old German Shepherd
print(Dog.species)        # Canis familiaris
```

### Inheritance
```python
class Animal:
    def __init__(self, name, species):
        self.name = name
        self.species = species
    
    def make_sound(self):
        return "Some generic sound"
    
    def describe(self):
        return f"{self.name} is a {self.species}"

class Cat(Animal):
    def __init__(self, name, breed, indoor=True):
        super().__init__(name, "Felis catus")
        self.breed = breed
        self.indoor = indoor
    
    # Method overriding
    def make_sound(self):
        return "Meow!"
    
    def purr(self):
        return f"{self.name} is purring..."

class Bird(Animal):
    def __init__(self, name, can_fly=True):
        super().__init__(name, "Bird")
        self.can_fly = can_fly
    
    def make_sound(self):
        return "Chirp!"
    
    def fly(self):
        if self.can_fly:
            return f"{self.name} is flying!"
        else:
            return f"{self.name} cannot fly"

# Using inheritance
cat = Cat("Whiskers", "Siamese")
bird = Bird("Tweety", True)

print(cat.describe())     # Whiskers is a Felis catus
print(cat.make_sound())   # Meow!
print(bird.fly())         # Tweety is flying!
```

### Encapsulation and Properties
```python
class BankAccount:
    def __init__(self, account_holder, initial_balance=0):
        self.account_holder = account_holder
        self._balance = initial_balance  # Protected attribute
        self._transaction_history = []
    
    # Property getter
    @property
    def balance(self):
        return self._balance
    
    # Methods to control access
    def deposit(self, amount):
        if amount > 0:
            self._balance += amount
            self._transaction_history.append(f"Deposited: ${amount}")
            return f"Successfully deposited ${amount}"
        return "Invalid deposit amount"
    
    def withdraw(self, amount):
        if 0 < amount <= self._balance:
            self._balance -= amount
            self._transaction_history.append(f"Withdrew: ${amount}")
            return f"Successfully withdrew ${amount}"
        return "Insufficient funds or invalid amount"
    
    def get_transaction_history(self):
        return self._transaction_history.copy()  # Return a copy

# Using the class
account = BankAccount("Alice", 1000)
print(account.deposit(500))    # Successfully deposited $500
print(account.withdraw(200))   # Successfully withdrew $200
print(f"Balance: ${account.balance}")  # Balance: $1300

# This would not work (attribute is protected)
# print(account._balance)  # Not recommended
```

### Practical Example: Library Management System
```python
class Book:
    def __init__(self, title, author, isbn, copies=1):
        self.title = title
        self.author = author
        self.isbn = isbn
        self.copies_available = copies
        self.total_copies = copies
    
    def borrow(self):
        if self.copies_available > 0:
            self.copies_available -= 1
            return True
        return False
    
    def return_book(self):
        if self.copies_available < self.total_copies:
            self.copies_available += 1
            return True
        return False
    
    def __str__(self):
        return f"'{self.title}' by {self.author} - {self.copies_available}/{self.total_copies} available"

class Library:
    def __init__(self):
        self.books = {}
    
    def add_book(self, book):
        if book.isbn in self.books:
            # Book already exists, add copies
            existing_book = self.books[book.isbn]
            existing_book.total_copies += book.total_copies
            existing_book.copies_available += book.copies_available
        else:
            self.books[book.isbn] = book
    
    def remove_book(self, isbn, copies=1):
        if isbn in self.books:
            book = self.books[isbn]
            if copies >= book.total_copies:
                del self.books[isbn]
            else:
                book.total_copies -= copies
                book.copies_available = min(book.copies_available, book.total_copies)
    
    def borrow_book(self, isbn):
        if isbn in self.books and self.books[isbn].borrow():
            return f"Successfully borrowed '{self.books[isbn].title}'"
        return "Book not available for borrowing"
    
    def return_book(self, isbn):
        if isbn in self.books and self.books[isbn].return_book():
            return f"Successfully returned '{self.books[isbn].title}'"
        return "Return failed"
    
    def display_books(self):
        if not self.books:
            print("No books in library")
            return
        
        print("\nLibrary Collection:")
        for book in self.books.values():
            print(f"  - {book}")

# Example usage
library = Library()

# Add books
book1 = Book("The Great Gatsby", "F. Scott Fitzgerald", "12345", 3)
book2 = Book("To Kill a Mockingbird", "Harper Lee", "67890", 2)
book3 = Book("1984", "George Orwell", "11111", 1)

library.add_book(book1)
library.add_book(book2)
library.add_book(book3)

library.display_books()

# Borrow and return books
print(library.borrow_book("12345"))  # Successfully borrowed
print(library.borrow_book("12345"))  # Successfully borrowed
print(library.return_book("12345"))  # Successfully returned

library.display_books()
```

---

## 9. File Handling <a name="file-handling"></a>

### Reading Files
```python
# Reading entire file
try:
    with open("example.txt", "r") as file:
        content = file.read()
        print(content)
except FileNotFoundError:
    print("File not found!")

# Reading line by line
with open("example.txt", "r") as file:
    for line_num, line in enumerate(file, 1):
        print(f"Line {line_num}: {line.strip()}")

# Reading all lines into a list
with open("example.txt", "r") as file:
    lines = file.readlines()
    print(f"Total lines: {len(lines)}")
```

### Writing Files
```python
# Writing to a file (overwrites existing content)
with open("output.txt", "w") as file:
    file.write("Hello, World!\n")
    file.write("This is a new line.\n")

# Appending to a file
with open("output.txt", "a") as file:
    file.write("This line was appended.\n")

# Writing multiple lines
lines_to_write = ["First line\n", "Second line\n", "Third line\n"]
with open("multi_line.txt", "w") as file:
    file.writelines(lines_to_write)
```

### Working with CSV Files
```python
import csv

# Writing CSV
data = [
    ["Name", "Age", "City"],
    ["Alice", 30, "New York"],
    ["Bob", 25, "London"],
    ["Charlie", 35, "Paris"]
]

with open("people.csv", "w", newline="") as file:
    writer = csv.writer(file)
    writer.writerows(data)

# Reading CSV
with open("people.csv", "r") as file:
    reader = csv.reader(file)
    for row in reader:
        print(row)

# Reading as dictionary
with open("people.csv", "r") as file:
    reader = csv.DictReader(file)
    for row in reader:
        print(f"Name: {row['Name']}, Age: {row['Age']}, City: {row['City']}")
```

### Practical Example: Personal Diary
```python
import datetime
import os

class PersonalDiary:
    def __init__(self, filename="diary.txt"):
        self.filename = filename
    
    def write_entry(self):
        timestamp = datetime.datetime.now().strftime("%Y-%m-%d %H:%M:%S")
        print("Write your diary entry (type 'END' on a new line to finish):")
        
        entry_lines = []
        while True:
            line = input()
            if line.strip().upper() == "END":
                break
            entry_lines.append(line)
        
        entry = "\n".join(entry_lines)
        
        with open(self.filename, "a") as file:
            file.write(f"\n--- Entry on {timestamp} ---\n")
            file.write(entry + "\n")
            file.write("--- End of Entry ---\n")
        
        print("Entry saved successfully!")
    
    def read_entries(self):
        if not os.path.exists(self.filename):
            print("No entries found.")
            return
        
        with open(self.filename, "r") as file:
            content = file.read()
            if content:
                print("\nYour Diary Entries:")
                print(content)
            else:
                print("No entries found.")
    
    def search_entries(self, keyword):
        if not os.path.exists(self.filename):
            print("No entries found.")
            return
        
        found_entries = []
        with open(self.filename, "r") as file:
            current_entry = ""
            for line in file:
                if line.startswith("--- Entry on"):
                    if keyword.lower() in current_entry.lower():
                        found_entries.append(current_entry)
                    current_entry = line
                else:
                    current_entry += line
            
            # Check the last entry
            if keyword.lower() in current_entry.lower():
                found_entries.append(current_entry)
        
        if found_entries:
            print(f"\nEntries containing '{keyword}':")
            for entry in found_entries:
                print(entry)
                print("-" * 50)
        else:
            print(f"No entries found containing '{keyword}'")

# Example usage
diary = PersonalDiary()

# Uncomment to use the diary
# while True:
#     print("\nPersonal Diary")
#     print("1. Write new entry")
#     print("2. Read all entries")
#     print("3. Search entries")
#     print("4. Exit")
#     
#     choice = input("Choose an option (1-4): ")
#     
#     if choice == "1":
#         diary.write_entry()
#     elif choice == "2":
#         diary.read_entries()
#     elif choice == "3":
#         keyword = input("Enter search keyword: ")
#         diary.search_entries(keyword)
#     elif choice == "4":
#         print("Goodbye!")
#         break
#     else:
#         print("Invalid choice!")
```

---

## 10. Error Handling <a name="error-handling"></a>

### Basic Exception Handling
```python
# Try-except block
try:
    number = int(input("Enter a number: "))
    result = 10 / number
    print(f"10 / {number} = {result}")
except ValueError:
    print("That's not a valid number!")
except ZeroDivisionError:
    print("You can't divide by zero!")
except Exception as e:
    print(f"An unexpected error occurred: {e}")
else:
    print("Division completed successfully!")
finally:
    print("This always executes, regardless of errors")
```

### Custom Exceptions
```python
class InvalidAgeError(Exception):
    """Custom exception for invalid age"""
    def __init__(self, age, message="Age must be between 0 and 150"):
        self.age = age
        self.message = message
        super().__init__(self.message)
    
    def __str__(self):
        return f"{self.message}: {self.age}"

def set_age(age):
    if not (0 <= age <= 150):
        raise InvalidAgeError(age)
    return f"Age set to {age}"

# Using custom exception
try:
    print(set_age(25))   # Valid
    print(set_age(200))  # Invalid
except InvalidAgeError as e:
    print(f"Error: {e}")
```

### Practical Example: Robust Calculator
```python
class AdvancedCalculator:
    @staticmethod
    def calculate(expression):
        try:
            # Security note: Using eval can be dangerous with user input
            # In production, use a proper expression evaluator
            result = eval(expression)
            return f"{expression} = {result}"
        except ZeroDivisionError:
            return "Error: Division by zero is not allowed"
        except SyntaxError:
            return "Error: Invalid expression syntax"
        except NameError:
            return "Error: Invalid characters in expression"
        except Exception as e:
            return f"Error: {str(e)}"

def safe_calculator():
    calculator = AdvancedCalculator()
    
    print("Advanced Calculator")
    print("Enter 'quit' to exit")
    
    while True:
        expression = input("\nEnter expression: ").strip()
        
        if expression.lower() == 'quit':
            print("Goodbye!")
            break
        
        if not expression:
            continue
        
        print(calculator.calculate(expression))

# Uncomment to use calculator
# safe_calculator()
```

---

## 11. Modules and Packages <a name="modules"></a>

### Creating and Using Modules
```python
# math_operations.py (save this as a separate file)
"""
A module for basic math operations
"""

def add(a, b):
    """Returns the sum of a and b"""
    return a + b

def subtract(a, b):
    """Returns the difference between a and b"""
    return a - b

def multiply(a, b):
    """Returns the product of a and b"""
    return a * b

def divide(a, b):
    """Returns the quotient of a divided by b"""
    if b == 0:
        raise ValueError("Cannot divide by zero")
    return a / b

# Using the module (in another file)
# import math_operations as mo
# 
# result = mo.add(5, 3)
# print(result)  # 8
```

### Standard Library Modules
```python
import math
import random
import datetime
import os

# Math module
print(math.sqrt(25))          # 5.0
print(math.pi)                # 3.141592653589793
print(math.factorial(5))      # 120

# Random module
print(random.randint(1, 10))  # Random integer between 1-10
print(random.choice(["apple", "banana", "cherry"]))  # Random choice

# Datetime module
now = datetime.datetime.now()
print(f"Current date and time: {now}")
print(f"Year: {now.year}, Month: {now.month}, Day: {now.day}")

# OS module
print(f"Current working directory: {os.getcwd()}")
print(f"Files in current directory: {os.listdir('.')}")
```

### Creating Packages
```
my_package/
    __init__.py
    math_utils.py
    string_utils.py
    data_processor.py
```

```python
# my_package/math_utils.py
def is_prime(n):
    if n < 2:
        return False
    for i in range(2, int(n**0.5) + 1):
        if n % i == 0:
            return False
    return True

def fibonacci(n):
    a, b = 0, 1
    for _ in range(n):
        yield a
        a, b = b, a + b

# my_package/__init__.py
from .math_utils import is_prime, fibonacci
from .string_utils import reverse_string, count_vowels

# Using the package
# from my_package import is_prime, fibonacci, reverse_string
# 
# print(is_prime(17))  # True
# print(list(fibonacci(10)))  # [0, 1, 1, 2, 3, 5, 8, 13, 21, 34]
```

---

## 12. Advanced Topics <a name="advanced"></a>

### Decorators
```python
import time
from functools import wraps

def timer(func):
    """Decorator that measures function execution time"""
    @wraps(func)
    def wrapper(*args, **kwargs):
        start_time = time.time()
        result = func(*args, **kwargs)
        end_time = time.time()
        print(f"{func.__name__} took {end_time - start_time:.4f} seconds")
        return result
    return wrapper

def debug(func):
    """Decorator that prints function call details"""
    @wraps(func)
    def wrapper(*args, **kwargs):
        print(f"Calling {func.__name__} with args: {args}, kwargs: {kwargs}")
        result = func(*args, **kwargs)
        print(f"{func.__name__} returned: {result}")
        return result
    return wrapper

@timer
@debug
def slow_function(n):
    """Simulate a slow function"""
    time.sleep(1)
    return n * 2

# Using decorated function
result = slow_function(5)
print(f"Result: {result}")
```

### Generators
```python
def countdown(n):
    """Generator function that counts down from n to 1"""
    while n > 0:
        yield n
        n -= 1

# Using generator
for number in countdown(5):
    print(number)  # Prints 5, 4, 3, 2, 1

# Generator expression
squares = (x**2 for x in range(1, 6))
print(list(squares))  # [1, 4, 9, 16, 25]

# Practical generator: Reading large files
def read_large_file(filename):
    """Generator to read large files line by line"""
    with open(filename, 'r') as file:
        for line in file:
            yield line.strip()

# Usage
# for line in read_large_file("large_file.txt"):
#     process_line(line)
```

### Context Managers
```python
class DatabaseConnection:
    """Custom context manager for database connections"""
    
    def __init__(self, db_name):
        self.db_name = db_name
        self.connection = None
    
    def __enter__(self):
        print(f"Connecting to database: {self.db_name}")
        # Simulate connection
        self.connection = f"Connection to {self.db_name}"
        return self.connection
    
    def __exit__(self, exc_type, exc_val, exc_tb):
        print(f"Closing connection to {self.db_name}")
        self.connection = None
        if exc_type:
            print(f"An error occurred: {exc_val}")
        return False  # Don't suppress exceptions

# Using context manager
with DatabaseConnection("my_database") as db:
    print(f"Using: {db}")
    # Database operations here
# Connection automatically closed
```

### Comprehensive Final Project: Task Manager
```python
import json
import datetime
from typing import List, Dict, Any

class Task:
    def __init__(self, title: str, description: str = "", priority: int = 1, 
                 due_date: str = None, completed: bool = False):
        self.title = title
        self.description = description
        self.priority = priority  # 1-5, where 5 is highest
        self.due_date = due_date
        self.completed = completed
        self.created_at = datetime.datetime.now().isoformat()
        self.id = hash(f"{title}{self.created_at}")
    
    def to_dict(self) -> Dict[str, Any]:
        return {
            'id': self.id,
            'title': self.title,
            'description': self.description,
            'priority': self.priority,
            'due_date': self.due_date,
            'completed': self.completed,
            'created_at': self.created_at
        }
    
    @classmethod
    def from_dict(cls, data: Dict[str, Any]) -> 'Task':
        task = cls(
            title=data['title'],
            description=data['description'],
            priority=data['priority'],
            due_date=data['due_date']
        )
        task.id = data['id']
        task.completed = data['completed']
        task.created_at = data['created_at']
        return task
    
    def __str__(self) -> str:
        status = "✓" if self.completed else "✗"
        priority_stars = "★" * self.priority
        due_info = f" | Due: {self.due_date}" if self.due_date else ""
        return f"[{status}] {self.title} {priority_stars}{due_info}"

class TaskManager:
    def __init__(self, filename: str = "tasks.json"):
        self.filename = filename
        self.tasks: List[Task] = []
        self.load_tasks()
    
    def load_tasks(self) -> None:
        try:
            with open(self.filename, 'r') as file:
                tasks_data = json.load(file)
                self.tasks = [Task.from_dict(task_data) for task_data in tasks_data]
        except FileNotFoundError:
            self.tasks = []
    
    def save_tasks(self) -> None:
        with open(self.filename, 'w') as file:
            tasks_data = [task.to_dict() for task in self.tasks]
            json.dump(tasks_data, file, indent=2)
    
    def add_task(self, title: str, **kwargs) -> Task:
        task = Task(title, **kwargs)
        self.tasks.append(task)
        self.save_tasks()
        return task
    
    def remove_task(self, task_id: int) -> bool:
        initial_length = len(self.tasks)
        self.tasks = [task for task in self.tasks if task.id != task_id]
        removed = len(self.tasks) < initial_length
        if removed:
            self.save_tasks()
        return removed
    
    def get_task(self, task_id: int) -> Task:
        for task in self.tasks:
            if task.id == task_id:
                return task
        raise ValueError(f"Task with ID {task_id} not found")
    
    def mark_completed(self, task_id: int) -> bool:
        try:
            task = self.get_task(task_id)
            task.completed = True
            self.save_tasks()
            return True
        except ValueError:
            return False
    
    def get_tasks(self, completed: bool = None, priority: int = None) -> List[Task]:
        tasks = self.tasks
        
        if completed is not None:
            tasks = [task for task in tasks if task.completed == completed]
        
        if priority is not None:
            tasks = [task for task in tasks if task.priority == priority]
        
        return sorted(tasks, key=lambda x: x.priority, reverse=True)
    
    def display_tasks(self, completed: bool = None, priority: int = None) -> None:
        tasks = self.get_tasks(completed, priority)
        
        if not tasks:
            print("No tasks found.")
            return
        
        title = "All Tasks"
        if completed is True:
            title = "Completed Tasks"
        elif completed is False:
            title = "Pending Tasks"
        
        if priority:
            title += f" (Priority {priority})"
        
        print(f"\n{title}:")
        print("-" * 50)
        
        for i, task in enumerate(tasks, 1):
            print(f"{i}. {task}")
        
        print("-" * 50)

def main():
    manager = TaskManager()
    
    while True:
        print("\n📝 Task Manager")
        print("1. Add Task")
        print("2. View All Tasks")
        print("3. View Pending Tasks")
        print("4. View Completed Tasks")
        print("5. Mark Task as Completed")
        print("6. Remove Task")
        print("7. View Tasks by Priority")
        print("8. Exit")
        
        choice = input("\nChoose an option (1-8): ").strip()
        
        if choice == "1":
            title = input("Enter task title: ").strip()
            if not title:
                print("Title cannot be empty!")
                continue
            
            description = input("Enter task description (optional): ").strip()
            priority = input("Enter priority (1-5, default 1): ").strip()
            due_date = input("Enter due date (YYYY-MM-DD, optional): ").strip()
            
            try:
                priority = int(priority) if priority else 1
                if not 1 <= priority <= 5:
                    raise ValueError
            except ValueError:
                print("Invalid priority! Using default (1)")
                priority = 1
            
            task = manager.add_task(
                title=title,
                description=description,
                priority=priority,
                due_date=due_date if due_date else None
            )
            print(f"✅ Task added: {task.title}")
        
        elif choice == "2":
            manager.display_tasks()
        
        elif choice == "3":
            manager.display_tasks(completed=False)
        
        elif choice == "4":
            manager.display_tasks(completed=True)
        
        elif choice == "5":
            manager.display_tasks(completed=False)
            if manager.get_tasks(completed=False):
                try:
                    task_num = int(input("Enter task number to mark as completed: "))
                    pending_tasks = manager.get_tasks(completed=False)
                    if 1 <= task_num <= len(pending_tasks):
                        task = pending_tasks[task_num - 1]
                        manager.mark_completed(task.id)
                        print(f"✅ Task '{task.title}' marked as completed!")
                    else:
                        print("Invalid task number!")
                except ValueError:
                    print("Please enter a valid number!")
        
        elif choice == "6":
            manager.display_tasks()
            if manager.tasks:
                try:
                    task_num = int(input("Enter task number to remove: "))
                    if 1 <= task_num <= len(manager.tasks):
                        task = manager.tasks[task_num - 1]
                        manager.remove_task(task.id)
                        print(f"🗑️ Task '{task.title}' removed!")
                    else:
                        print("Invalid task number!")
                except ValueError:
                    print("Please enter a valid number!")
        
        elif choice == "7":
            try:
                priority = int(input("Enter priority level (1-5): "))
                if 1 <= priority <= 5:
                    manager.display_tasks(priority=priority)
                else:
                    print("Priority must be between 1 and 5!")
            except ValueError:
                print("Please enter a valid number!")
        
        elif choice == "8":
            print("Goodbye! 👋")
            break
        
        else:
            print("Invalid choice! Please try again.")

if __name__ == "__main__":
    main()
```

---

## Conclusion

This comprehensive guide covers Python from absolute basics to advanced concepts. Here are the key takeaways:

### What You've Learned:
1. **Fundamentals**: Variables, data types, operators
2. **Control Structures**: Conditionals, loops
3. **Functions**: Definition, parameters, return values
4. **Data Structures**: Lists, tuples, dictionaries, sets
5. **OOP**: Classes, objects, inheritance, encapsulation
6. **File Handling**: Reading, writing, CSV processing
7. **Error Handling**: Exceptions, custom errors
8. **Modules**: Creating and using modules/packages
9. **Advanced Topics**: Decorators, generators, context managers

### Next Steps:
1. **Practice**: Build small projects regularly
2. **Explore Libraries**: NumPy, Pandas, Matplotlib, Django
3. **Learn Testing**: pytest, unittest
4. **Study Algorithms**: Data structures and algorithms
5. **Contribute**: Open source projects

### Remember:
- Python emphasizes readability and simplicity
- Practice is key to mastering programming
- Don't hesitate to experiment and make mistakes
- The Python community is large and supportive

This guide provides a solid foundation, but Python has much more to offer. Continue exploring, building projects, and most importantly, have fun coding! 🐍✨
