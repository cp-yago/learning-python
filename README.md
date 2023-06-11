# Learning Python

## About

Welcome to the "Learning Python" guide! This comprehensive resource is designed to help you learn Python and build a strong foundation in the language. Whether you're a beginner or looking to expand your Python knowledge, this guide has you covered.

The guide covers a wide range of topics, carefully curated with the assistance of [ChatGPT](https://chat.openai.com), to ensure a comprehensive learning experience. Each topic is explained in clear terms and accompanied by practical code examples to help you grasp the concepts effectively

## Table of Contents
The guide covers the following topics:

  - [Variable types](#variable-types)
    - [Number](#number)
    - [String](#string)
    - [Boolean](#boolean)
    - [List](#list)
    - [Tuple (immutable)](#tuple-immutable)
    - [Dictionary](#dictionary)
    - [Set (unique & unordered)](#set-unique--unordered)
  - [Operators](#operators)
    - [Arithmetic ( + - * / // % ** )](#arithmetic---)
    - [Assignment](#assignment)
    - [Comparison ( == != > < >= <= )](#comparison----)
    - [Logical ( and or not )](#logical--and-or-not-)
    - [Identity ( is is not )](#identity--is-is-not-)
    - [Membership ( in not in )](#membership--in-not-in-)
  - [Control Flow Structures](#control-flow-structures)
    - [Conditional Statements ( if elif else )](#conditional-statements--if-elif-else-)
    - [Loops ( for loop, while loop )](#loops--for-loop-while-loop-)
    - [Break and Continue](#break-and-continue)
    - [Exception Handling ( try, except, finally )](#exception-handling--try-except-finally-)
    - [Pass Statement](#pass-statement)
  - [Functions](#functions)
    - [Defining a Function](#defining-a-function)
    - [Passing Arguments](#passing-arguments)
    - [Returning Values](#returning-values)
    - [Variable Scope](#variable-scope)
    - [Using Functions](#using-functions)
  - [Lists and iteration](#lists-and-iteration)
    - [Creating a List](#creating-a-list)
    - [Adding Elements to a List](#adding-elements-to-a-list)
    - [Accessing Elements in a List](#accessing-elements-in-a-list)
    - [Iterating through a List](#iterating-through-a-list)
    - [Removing elements](#removing-elements)
    - [Updating elements](#updating-elements)
    - [List length](#list-length)
  - [String Manipulation](#string-manipulation)
    - [Concatenation](#concatenation)
    - [String Formatting](#string-formatting)
    - [Indexing](#indexing)
    - [Slicing](#slicing)
    - [Useful String Methods](#useful-string-methods)
  - [Input and output](#input-and-output)
    - [Receiving User Input using input()](#receiving-user-input-using-input)
    - [Displaying Information using print()](#displaying-information-using-print)
  - [Exception Handling](#exception-handling)
    - [Using Try-Except Blocks](#using-try-except-blocks)
    - [Using Finally Blocks](#using-finally-blocks)
    - [Handling Multiple Exceptions](#handling-multiple-exceptions)

## Variable types

### Number
Numbers in Python can be represented using different data types such as integers (int) and floating-point numbers (float). For example, max_velocity = 100 assigns the integer value 100 to the variable max_velocity, while rate = 15.75 assigns the floating-point value 15.75 to the variable rate.

```python
max_velocity = 100
rate = 15.75
```

### String
Strings are used to represent text data in Python. They can be enclosed in either single quotes (') or double quotes ("). 

```python
name = "John"
nickname = 'J'
```

### Boolean
Boolean variables in Python can hold either True or False values. They are used to represent logical conditions or states.

```python
is_active = True
```

### List
Lists are ordered collections that can contain elements of different types. In Python, lists are created using square brackets ([]).

```python
numbers = [1, 2, 3, 4, 5]
names = ["John", "Mary", "Bob"]
```

### Tuple (immutable)
Tuples are similar to lists but are immutable, meaning their elements cannot be modified after creation. Tuples are created using parentheses (()).

```python
numbers_2 = (1, 2, 3, 4, 5)
names_2 = ("John", "Mary", "Bob")
```

### Dictionary
Dictionaries are unordered collections of key-value pairs. They are created using curly braces ({}). Each element in a dictionary consists of a key and its corresponding value, separated by a colon (:). 

```python
person = {
    "name": "John",
    "age": 30,
    "is_active": True
}
```

### Set (unique & unordered)
Sets are unordered collections of unique elements. They are useful when you need to store a collection of items without duplicates. Sets are created using curly braces ({})


```python
numbers_3 = {1, 2, 3, 4, 5}
```

## Operators

### Arithmetic ( + - * / // % ** )
Perform basic arithmetic operations like addition, subtraction, multiplication, division, and more.

Example:
```python
x = 10
y = 3
print(x + y) # 13
```

### Assignment
Assign values to variables.

Example:
```python
x = 10
y = 5

x += y    # Equivalent to x = x + y, assigns 15 to x
x -= y    # Equivalent

 to x = x - y, assigns 5 to x
x *= y    # Equivalent to x = x * y, assigns 50 to x
x /= y    # Equivalent to x = x / y, assigns 2.0 to x
x %= y    # Equivalent to x = x % y, assigns 0 to x
x **= y   # Equivalent to x = x ** y, assigns 100000 to x
```

### Comparison ( == != > < >= <= )
Compare two values and return True or False.

Example:
```python
x = 10
y = 5

equal = x == y          # False
not_equal = x != y      # True
greater_than = x > y    # True
less_than = x < y       # False
greater_equal = x >= y  # True
less_equal = x <= y     # False
```

### Logical ( and or not )
Perform logical operations and return boolean results.

Example:
```python
x = True
y = False

logical_and = x and y   # False
logical_or = x or y     # True
logical_not = not x     # False
```

### Identity ( is is not )
Compare the objects, not if they are equal, but if they are actually the same object, with the same memory location.

Example:
```python
x = 10
y = 10

is_same = x is y         # True
is_not_same = x is not y # False
```

### Membership ( in not in )
Check if a value exists in a sequence.

Example:
```python
numbers = [1, 2, 3, 4, 5]

contains = 3 in numbers      # True
not_contains = 6 not in numbers  # True
```

## Control Flow Structures
Python provides several control flow structures that allow you to control the flow of your program based on conditions and perform repetitive tasks.

### Conditional Statements ( if elif else )
Execute different blocks of code based on specified conditions.

Example:
```python
x = 10

if x > 0:
    print("Positive")
elif x < 0:
    print("Negative")
else:
    print("Zero")
```

### Loops ( for loop, while loop )
Execute a block of code repeatedly based on a condition.

#### For Loop 
Iterate over a sequence (such as a list, string, or range) or any iterable object. 

Example:
```python
fruits = ["apple", "banana", "orange"]

for fruit in fruits:
    print(fruit)
```

#### While Loop 
Execute a block of code as long as a specified condition is True.

Example:
```python
count = 0

while count < 5:
    print(count)
    count += 1

```

### Break and Continue
Break and continue are used inside for and while loops to alter their normal behavior.

#### Break
Exit the loop prematurely.

Example:
```python
numbers = [1, 2, 3, 4, 5]

for num in numbers:
    if num == 3:
        break
    print(num)

```

#### Continue
Skip the current iteration and continue with the next one.

Example:
```python
numbers = [1, 2, 3, 4, 5]

for num in numbers:
    if num == 3:
        continue
    print(num)

```

### Exception Handling ( try, except, finally )
Handle and manage exceptions that may occur during the execution of code.

Example:
```python
try:
    x = 10 / 0
except ZeroDivisionError:
    print("Error

: Division by zero")
finally:
    print("Finally block")

```

### Pass Statement
Acts as a placeholder, allowing you to create empty code blocks that do nothing.

Example:
```python
x = 10

if x > 0:
    pass  # Placeholder for future code
else:
    print("Negative")

```

## Functions
Functions in Python allow you to encapsulate reusable blocks of code. Here's how you can define and use functions, and understand passing arguments, returning values, and variable scope:


### Defining a Function:
To define a function in Python, you use the def keyword followed by the function name and parentheses. You can specify parameters inside the parentheses if the function requires any.

Example:
```python
def greet():
    print("Hello, world!")
```

### Passing Arguments:
You can pass arguments to a function by including them inside the parentheses when defining the function. These arguments allow you to provide input values to the function.


Example:
```python
def greet(name):
    print("Hello, " + name + "!")
```

### Returning Values:
Functions can also return values using the return keyword. This allows the function to produce a result that can be used or stored for further processing.

Example:
```python
def add_numbers(a, b):
    return a + b

```

### Variable Scope:
Variables defined inside a function have local scope, meaning they are only accessible within that function. Variables defined outside any function have global scope and can be accessed from anywhere in the code.

Example:
```python
def calculate():
    x = 10  # local variable
    print(x)  # Accessible within the function

x = 5  # global variable
calculate()
print(x)  # Accessible outside the function
```

### Using Functions:
To use a function, you simply call it by its name followed by parentheses. If the function takes arguments, you pass the values within the parentheses.

Example:
```python
greet()  # Output: Hello, world!

greet("Alice")  # Output: Hello, Alice!

result = add_numbers(5, 3)
print(result)  # Output: 8
```

## Lists and iteration
Lists in Python are versatile data structures that allow you to store and manipulate collections of items. Here's a guide on using lists and common operations:

### Creating a List:
To create a list in Python, you enclose items inside square brackets ([]), separating them with commas.

Example:
```python
fruits = ["apple", "banana", "orange"]
```

### Adding Elements to a List:
You can add elements to a list using the append() method to add an item at the end of the list, or the insert() method to add an item at a specific position.

Example:
```python
fruits.append("grape")  # Adds "grape" to the end of the list

fruits.insert(1, "mango")  # Adds "mango" at index 1, shifting other elements
```

### Accessing Elements in a List:
You can access individual elements in a list using their index, starting from 0. Negative indices can be used to access elements from the end of the list.

Example:
```python
print(fruits[0])  # Output: "apple"

print(fruits[-1])  # Output: "orange"
```

### Iterating through a List:
You can iterate through a list using a for loop to perform actions on each element.

Example:
```python
for fruit in fruits:
    print(fruit)
```

### Removing elements:
- Use the remove() method to remove a specific item by value.
- Use the pop() method to remove an

 item at a specific index.
- Use the del keyword to remove an item at a specific index or delete the entire list.

Example:
```python
fruits.remove("banana")  # Removes "banana" from the list

fruits.pop(0)  # Removes the item at index 0

del fruits[1]  # Removes the item at index 1

del fruits  # Deletes the entire list
```

### Updating elements:
You can update the value of an element in a list by assigning a new value to a specific index.

Example:
```python
fruits[0] = "kiwi"  # Updates the value at index 0 to "kiwi"
```

### List length:
To get the length of a list (number of elements), you can use the len() function.

Example:
```python
length = len(fruits)
print(length)  # Output: 3
```

## String Manipulation
String manipulation is a common task in Python. Here's a guide on performing string manipulation tasks using concatenation, string formatting, indexing, slicing, and useful string methods:

### Concatenation:
You can concatenate (combine) strings using the + operator. This allows you to join strings together.

Example:
```python
name = "Alice"
greeting = "Hello, " + name + "!"
```

### String Formatting:
String formatting allows you to insert dynamic values into a string. There are multiple ways to achieve string formatting in Python. Here are two commonly used methods:

#### Using f-strings (formatted string literals):
Place the variable or expression inside curly braces {} within a string preceded by an f or F.

Example:
```python
name = "Alice"
age = 25
message = f"My name is {name} and I am {age} years old."
```

#### Using the format() method:
Call the format() method on a string and pass the values as arguments.

Example:
```python
name = "Alice"
age = 25
message = "My name is {} and I am {} years old.".format(name, age)
```

### Indexing:
You can access individual characters in a string using indexing. Indexing starts from 0, and negative indices can be used to access characters from the end of the string.

Example:
```python
message = "Hello, world!"

print(message[0])    # Output: "H"
print(message[-1])   # Output: "!"
```

### Slicing:
Slicing allows you to extract a portion of a string by specifying the start and end indices. The end index is exclusive.

Example:
```python
message = "Hello, world!"

print(message[7:12])  # Output: "world"
print(message[:5])    # Output: "Hello"
print(message[7:])    # Output: "world!"
```

### Useful String Methods:
Python provides several built-in string methods that can be helpful for various manipulations. Here are a few commonly used ones:

- upper() and lower(): Convert a string to uppercase or lowercase.
- strip(): Remove leading and trailing whitespace from a string.
- split(): Split a string into a list of substrings based on a delimiter.
- replace(): Replace occurrences of a substring with another substring.

Example:
```python
text = "   Hello, World!   "
uppercase = text.upper()          # "   HELLO, WORLD!   "
lowercase = text.lower()          # "   hello, world!   "
stripped = text.strip()           # "Hello, World!"
words = text.split(",")           # ['   Hello', ' World!   ']
replaced = text.replace("Hello", "Hi")  # "   Hi, World!   "
```

## Input and output:
In Python, you can use the input() function to receive user input and the print() function to display information on the screen.

### Receiving User Input using input():
The input() function allows you to prompt the user for input and store the entered value in a variable. You can provide an optional prompt message as an argument to input().

Example:
```python
name = input("Enter your name: ")
print("Hello, " + name + "!")
```

### Displaying Information using print():
The print() function is used to display information on the screen. You can pass one or more arguments to print(), and they will be printed sequentially. You can also format the output using string concatenation or string formatting techniques.

Example:
```python
name = "Alice"
age = 25
print("My name is", name, "and I am", age, "years old.")

# Alternatively, using string formatting:
print("My name is {} and I am {} years old.".format(name, age))
```

## Exception Handling
Allows you to handle errors and exceptions that may occur during program execution. Here's a guide on using try-except-finally blocks to handle exceptions, along with some code examples:

### Using Try-Except Blocks:
A try-except block is used to catch and handle exceptions. The code that might raise an exception is placed inside the try block, and the exception handling code is placed inside the except block.

```python
try:
    # Code that might raise an exception
    num1 = int(input("Enter a number: "))
    num2 = int(input("Enter another number: "))
    result = num1 / num2
    print("Result:", result)
except ValueError:
    print("Invalid input. Please enter a valid number.")
except ZeroDivisionError:
    print("Cannot divide by zero.")
```

### Using Finally Blocks:
A finally block is used to define code that should be executed regardless of whether an exception occurs or not. It is typically used for cleanup operations, such as closing files or releasing resources.

```python
try:
    # Code that might raise an exception
    file = open("data.txt", "r")
    content = file.read()
    print(content)
except FileNotFoundError:
    print("File not found.")
finally:
    # Code that will be executed regardless of exceptions
    file.close()
```

### Handling Multiple Exceptions:
You can handle multiple exceptions in a single try-except block by specifying multiple except blocks, each targeting a specific exception.

```python
try:
    # Code that might raise an exception
    age = int(input("Enter your age: "))
    if age < 0:
        raise ValueError("Age cannot be negative.")
    print("Your age is:", age)
except ValueError as e:
    print("Invalid input:", str(e))
except:
    print("An error occurred.")
```

## Modules and Packages
Importing and using modules and packages in Python allows you to extend the functionality of your program by utilizing existing code and libraries.

### Module:
A module is a single file containing Python code. It can define functions, classes, variables, or any other Python code that can be executed or imported. Modules are used to break down a program into smaller, manageable components.

### Package:
A package is a collection of modules organized in a directory hierarchy. It is used to group related modules together. A package consists of a directory that contains one or more module files, as well as a special __init__.py file, which indicates that the directory is a Python package.

### Importing Modules:
To import a module in Python, you can use the import statement. Once imported, you can access the functions, classes, and variables defined in the module.

```python
import math

result = math.sqrt(16)
print(result)  # Output: 4.0
```

### Importing Specific Items from a Module:
If you only need specific items from a module, you can import them directly using the from keyword.

```python
from math import sqrt, pi

result = sqrt(25)
print(result)  # Output: 5.0

circumference = 2 * pi * 5
print(circumference)  # Output: 31.41592653589793
```

### Importing Modules with Aliases:
You can provide an alias (alternative name) for a module when importing it using the as keyword. Aliases are helpful to avoid naming conflicts or to provide a shorter name for convenience.

```python
import datetime as dt

current_date = dt.date.today()
print(current_date)  # Output: 2023-06-11
```

### Importing Packages:
Packages are directories that contain multiple Python modules. To import a module from a package, you specify the package name followed by the module name, separated by dots.

```python
import os.path

file_exists = os.path.exists("myfile.txt")
print(file_exists)  # Output: False
```

### Importing All Items from a Module:
To import all items from a module, you can use the * wildcard character. However, it is generally recommended to import only the specific items you need to maintain clarity and avoid naming conflicts.

```python
from math import *

result = sqrt(9)
print(result)  # Output: 3.0
```

📫 My contacts:

[Linkedin](https://www.linkedin.com/in/yagocunha) | [Instagram](https://www.instagram.com/cp_yago/) or email me yago.cunha123@gmail.com
