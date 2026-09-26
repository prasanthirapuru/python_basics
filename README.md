# Python Interview Questions — Explained Properly

Yes — **now I understand exactly what you want**. You don't want interview answers that contain technical words you would then have to memorize separately. You want the answer to **teach you the technical words while answering the interview question**.

For example, instead of:

> "Python is a high-level, interpreted programming language."

I should explain:

> **Interpreted** means Python code is executed by the Python interpreter rather than being directly turned into machine code ahead of time.
> **High-level** means the language is designed to be easier for humans to read and write than low-level machine instructions.

And if I say **libraries**, I should immediately give examples such as `NumPy`, `Pandas`, `Requests`, etc.

So I'll use this format from now on:

**Question → Simple interview answer → Technical terms explained → Example → How you can say it naturally**

I'll also make sure the explanations don't become unnecessarily complicated.

---

## Table of Contents

1. [What is Python, and what are its main features?](#1-what-is-python-and-what-are-its-main-features)
2. [What is the difference between a list, tuple, set, and dictionary?](#2-what-is-the-difference-between-a-list-tuple-set-and-dictionary)
3. [What is the difference between mutable and immutable objects?](#3-what-is-the-difference-between-mutable-and-immutable-objects)
4. [What are Python's built-in data types?](#4-what-are-pythons-built-in-data-types)
5. [What is the difference between `==` and `is`?](#5-what-is-the-difference-between--and-is)
6. [What are `*args` and `**kwargs`?](#6-what-are-args-and-kwargs)
7. [What is list comprehension?](#7-what-is-list-comprehension)
8. [What is the difference between shallow copy and deep copy?](#8-what-is-the-difference-between-shallow-copy-and-deep-copy)
9. [What is the purpose of `self` in Python classes?](#9-what-is-the-purpose-of-self-in-python-classes)
10. [What is the difference between a function and a method?](#10-what-is-the-difference-between-a-function-and-a-method)
11. [What are decorators in Python?](#11-what-are-decorators-in-python)
12. [What are generators?](#12-what-are-generators)
13. [What is the difference between an iterator and an iterable?](#13-what-is-the-difference-between-an-iterator-and-an-iterable)
14. [Explain `try`, `except`, `else`, and `finally`.](#14-explain-try-except-else-and-finally)
15. [What is a lambda function?](#15-what-is-a-lambda-function)
16. [Difference between instance method, class method, and static method?](#16-difference-between-instance-method-class-method-and-static-method)
17. [Explain inheritance, encapsulation, polymorphism, and abstraction.](#17-explain-inheritance-encapsulation-polymorphism-and-abstraction)
18. [What is the Python GIL?](#18-what-is-the-python-gil)
19. [Difference between multiprocessing, multithreading, and asynchronous programming?](#19-difference-between-multiprocessing-multithreading-and-asynchronous-programming)
20. [How would you optimize a slow Python program?](#20-how-would-you-optimize-a-slow-python-program)
21. [The way I want you to study these](#-the-way-i-want-you-to-study-these)

---

# Python — 20 Interview Questions Explained Properly

## 1. What is Python, and what are its main features?

### Simple answer

Python is a **high-level programming language** that is known for being simple and readable.
It is **interpreted**, which means Python code is executed by the Python interpreter.
Python supports **object-oriented, procedural, and functional programming**, and it has many **libraries and frameworks** that make development easier.

### What do those terms mean?

* **High-level language** → A programming language that is relatively easy for humans to understand and write. Python is high-level compared with languages such as Assembly.
* **Interpreted** → Python code is executed by an interpreter rather than requiring you to manually convert it into machine instructions before running it.
* **Object-oriented programming (OOP)** → Organizing programs around **objects and classes**. For example, a `Student` class can contain a student's name, age, and related methods.
* **Procedural programming** → Writing a program as a sequence of procedures/functions that perform tasks.
* **Functional programming** → A programming style where functions are treated as important building blocks and can be passed around or used to transform data.
* **Library** → Pre-written code that you can use instead of writing everything yourself. Examples of Python libraries include **NumPy, Pandas, Requests, Matplotlib**.
* **Framework** → A larger structure that provides a way to build an application. Examples include **Django, Flask, and FastAPI**.

### Example

If you need to make an HTTP request, instead of writing all the networking code yourself, you can use the Python `requests` library:

```python
import requests

response = requests.get("https://example.com")
```

### How you can explain it to an interviewer

> "Python is a high-level and interpreted programming language with simple syntax. It supports different programming styles like object-oriented, procedural, and functional programming. It also has many libraries and frameworks, such as Requests, NumPy, Django, and Flask, which make development easier."

---

## 2. What is the difference between a list, tuple, set, and dictionary?

### Simple answer

These are four commonly used **collection data types** in Python.

* **List** → ordered and can be changed.
* **Tuple** → ordered but cannot be changed.
* **Set** → stores unique values.
* **Dictionary** → stores data as key-value pairs.

### What does "ordered" mean?

Ordered means the elements have a defined position that Python can access.

```python
numbers = [10, 20, 30]

print(numbers[0])
```

Output:

```text
10
```

### What does "mutable" mean?

**Mutable** means we can change the object after creating it.

```python
numbers = [10, 20, 30]
numbers[0] = 100
```

The list is changed.

A tuple cannot be changed:

```python
numbers = (10, 20, 30)
# numbers[0] = 100  # Error
```

### What is a key-value pair?

A dictionary connects a **key** to a **value**:

```python
student = {
    "name": "John",
    "age": 20
}
```

Here:

```text
"name" → key
"John" → value
```

### What does "unique" mean in a set?

A set doesn't keep duplicate values:

```python
numbers = {10, 20, 20, 30}

print(numbers)
```

The duplicate `20` is removed.

### Easy way to remember

**List → ordered + changeable**
**Tuple → ordered + unchangeable**
**Set → unique values**
**Dictionary → key + value**

---

## 3. What is the difference between mutable and immutable objects?

### Simple answer

**Mutable** means an object can be changed after it is created.
**Immutable** means an object cannot be changed after it is created.

For example, a **list is mutable**, while a **string and tuple are immutable**.

### Example

```python
numbers = [1, 2, 3]

numbers[0] = 100
```

This is allowed because a list is mutable.

But:

```python
name = "John"

# name[0] = "M"
```

This is not allowed because strings are immutable.

### Why does this matter?

It matters when you're working with data and objects because changing a mutable object can affect other variables that refer to the same object.

### Easy interview explanation

> "Mutable objects can be modified after creation, such as lists and dictionaries. Immutable objects cannot be modified after creation, such as strings, integers, and tuples."

---

## 4. What are Python's built-in data types?

### Simple answer

**Data types** tell Python what kind of data a value represents.

Some common built-in types are:

| Type       | Meaning              | Example            |
| ---------- | -------------------- | ------------------ |
| `int`      | Whole number         | `10`               |
| `float`    | Decimal number       | `10.5`             |
| `str`      | Text                 | `"Hello"`          |
| `bool`     | True/False           | `True`             |
| `list`     | Collection           | `[1, 2, 3]`        |
| `tuple`    | Immutable collection | `(1, 2, 3)`        |
| `set`      | Unique collection    | `{1, 2, 3}`        |
| `dict`     | Key-value data       | `{"name": "John"}` |
| `complex`  | Complex number       | `2 + 3j`           |
| `NoneType` | No value             | `None`             |

### Example

```python
age = 20              # int
price = 99.5          # float
name = "John"         # str
is_student = True     # bool
```

### Easy interview explanation

> "Python provides built-in data types such as integers, floats, strings, booleans, lists, tuples, sets, and dictionaries. They allow Python to represent different kinds of data."

---

## 5. What is the difference between `==` and `is`?

This one is **very commonly asked**, so understand the difference clearly.

### Simple answer

`==` checks whether two objects have the **same value**.

`is` checks whether two variables refer to the **same object**.

### Example

```python
a = [1, 2, 3]
b = [1, 2, 3]

print(a == b)
```

Output:

```text
True
```

Because their values are the same.

But:

```python
print(a is b)
```

Output:

```text
False
```

because they are two separate list objects.

### What does "object" mean?

An **object** is a value stored and managed by Python. It has an identity, a type, and a value.

### Easy interview explanation

> "`==` is used to compare values, while `is` checks whether two variables refer to the same object. For example, two separate lists can have the same values, so `==` can be true while `is` is false."

---

## 6. What are `*args` and `**kwargs`?

### First understand "argument"

An **argument** is a value that you pass to a function.

```python
def greet(name):
    print(name)

greet("John")
```

Here `"John"` is an argument.

### `*args`

`*args` allows a function to accept **any number of positional arguments**.

```python
def add(*args):
    print(args)

add(10, 20, 30)
```

Python collects them into a tuple.

### `**kwargs`

`**kwargs` allows a function to accept **any number of keyword arguments**.

```python
def student(**kwargs):
    print(kwargs)

student(name="John", age=20)
```

Python collects them into a dictionary.

### What is positional vs keyword?

**Positional:**

```python
student("John", 20)
```

The values are identified by their position.

**Keyword:**

```python
student(name="John", age=20)
```

The values are identified by their names.

### Easy interview explanation

> "`*args` allows a function to receive multiple positional arguments, while `**kwargs` allows it to receive multiple keyword arguments. They are useful when we don't know in advance how many arguments the function will receive."

---

## 7. What is list comprehension?

### Simple answer

List comprehension is a **short way of creating a list using an existing iterable**, such as another list or a range.

Instead of:

```python
squares = []

for x in range(5):
    squares.append(x * x)
```

We can write:

```python
squares = [x * x for x in range(5)]
```

### What is an iterable?

An **iterable** is something Python can loop through, such as:

```python
list
tuple
string
range
dictionary
set
```

### Easy interview explanation

> "List comprehension is a concise way to create a new list from an iterable. It is useful when the logic is simple and makes the code shorter and more readable."

---

## 8. What is the difference between shallow copy and deep copy?

### First understand "copy"

Suppose we have:

```python
original = [[1, 2], [3, 4]]
```

We want another copy.

There are two important types.

### Shallow copy

A shallow copy creates a new **outer object**, but nested objects can still be shared.

### Deep copy

A deep copy creates a completely independent copy, including nested objects.

```python
import copy

shallow = copy.copy(original)
deep = copy.deepcopy(original)
```

### What does "nested object" mean?

It simply means an object inside another object.

For example:

```python
[[1, 2], [3, 4]]
```

The inner lists are nested inside the outer list.

### Easy interview explanation

> "A shallow copy creates a new outer object but can share nested objects with the original. A deep copy recursively copies the nested objects as well, so changes to the copied structure don't affect the original."

---

## 9. What is the purpose of `self` in Python classes?

### First understand "class"

A **class** is like a blueprint for creating objects.

For example:

```python
class Student:
    pass
```

We can create objects from it:

```python
student1 = Student()
student2 = Student()
```

### What is an object/instance?

`student1` and `student2` are **objects (instances)** of the `Student` class.

### What is `self`?

`self` refers to the **current object**.

```python
class Student:
    def __init__(self, name):
        self.name = name
```

When we do:

```python
student1 = Student("John")
```

`self` refers to `student1`.

### Easy interview explanation

> "`self` represents the current instance of a class. It allows us to access the variables and methods belonging to that particular object."

---

## 10. What is the difference between a function and a method?

### Function

A **function** is a reusable block of code that can be called independently.

```python
def add(a, b):
    return a + b
```

### Method

A **method** is a function that is defined inside a class and is associated with an object or class.

```python
class Student:
    def greet(self):
        print("Hello")
```

`greet()` is a method.

### Example from Python itself

```python
len(numbers)
```

`len()` is a function.

```python
numbers.append(10)
```

`append()` is a method of the list object.

### Easy interview explanation

> "A function can generally be called independently, while a method is a function associated with a class or object. For example, `len()` is a built-in function, while `append()` is a list method."

---

## 11. What are decorators in Python?

### Simple answer

A **decorator** is a function that adds or changes the behavior of another function **without modifying the original function's code**.

Think of it like putting an extra layer around a function.

### Example use cases

Decorators are commonly used for:

* **Logging** → recording when a function runs
* **Authentication** → checking whether a user is allowed to perform an action
* **Timing** → measuring how long a function takes
* **Access control** → controlling who can use something

### Example

```python
@my_decorator
def hello():
    print("Hello")
```

The `@my_decorator` syntax tells Python to apply the decorator to `hello()`.

### Easy interview explanation

> "A decorator is a function that extends or modifies another function's behavior without changing its original code. They are commonly used for logging, authentication, and timing."

---

## 12. What are generators?

### Simple answer

A **generator** is a special function that produces values **one at a time** using the `yield` keyword.

Instead of creating all the results in memory at once, it gives us the next value when we need it.

```python
def numbers():
    for i in range(5):
        yield i
```

### What is `yield`?

`yield` produces a value and **pauses the function**. When the next value is requested, the function continues from where it stopped.

### Why use generators?

They are particularly useful when dealing with **large amounts of data**, because they don't need to keep all the values in memory at once.

### Easy interview explanation

> "A generator produces values one at a time using `yield`. Unlike creating a complete list, it produces values only when needed, which can save memory when working with large data."

---

## 13. What is the difference between an iterator and an iterable?

### Iterable

An **iterable** is something you can loop over.

Examples:

```python
list
tuple
string
set
dictionary
```

For example:

```python
numbers = [1, 2, 3]

for number in numbers:
    print(number)
```

### Iterator

An **iterator** is an object that gives you the next item using `next()`.

```python
numbers = [1, 2, 3]

iterator = iter(numbers)

print(next(iterator))
print(next(iterator))
```

Output:

```text
1
2
```

### What do `iter()` and `next()` mean?

* `iter()` → creates an iterator from an iterable.
* `next()` → gets the next value from the iterator.

### Easy interview explanation

> "An iterable is an object that we can loop over, such as a list. An iterator is the object that actually provides the values one by one using `next()`. We can create an iterator from an iterable using `iter()`."

---

## 14. Explain `try`, `except`, `else`, and `finally`.

These are used for **exception handling**.

### What is an exception?

An **exception** is an error that happens while a program is running.

For example:

```python
10 / 0
```

causes a `ZeroDivisionError`.

### `try`

Contains code that might cause an exception.

### `except`

Handles the exception.

### `else`

Runs if no exception happened.

### `finally`

Runs whether an exception happened or not.

```python
try:
    x = 10 / 2
except ZeroDivisionError:
    print("Cannot divide by zero")
else:
    print("Success")
finally:
    print("Finished")
```

### Easy interview explanation

> "`try` contains code that may cause an exception, and `except` handles the error. `else` runs when there is no error, while `finally` runs in both cases and is commonly used for cleanup."

---

## 15. What is a lambda function?

### Simple answer

A **lambda** is a small anonymous function.

**Anonymous** simply means it doesn't need a normal function name.

Normal function:

```python
def square(x):
    return x * x
```

Lambda:

```python
square = lambda x: x * x
```

Both perform the same basic operation.

### When is it useful?

Lambda functions are useful when you need a **small, simple function temporarily**, especially with functions like `sorted()`, `map()`, or `filter()`.

### Easy interview explanation

> "A lambda is a small anonymous function used for simple operations. It is useful when we need a short function and don't want to define a full function using `def`."

---

## 16. Difference between instance method, class method, and static method?

This becomes easy if you understand **instance** and **class**.

### Instance method

Works with a particular object and receives `self`.

```python
def greet(self):
    ...
```

### Class method

Works with the class itself and receives `cls`.

```python
@classmethod
def create(cls):
    ...
```

`cls` means the **class itself**.

### Static method

Doesn't automatically receive either `self` or `cls`.

```python
@staticmethod
def add(a, b):
    return a + b
```

It is basically a utility function placed inside the class because it logically belongs there.

### Easy way to remember

**Instance method → object → `self`**

**Class method → class → `cls`**

**Static method → neither automatically**

### Interview explanation

> "An instance method works with an object and receives `self`. A class method works with the class and receives `cls`. A static method doesn't automatically receive either one and is useful for utility operations related to the class."

---

## 17. Explain inheritance, encapsulation, polymorphism, and abstraction.

These are four important **Object-Oriented Programming (OOP)** concepts.

### 1. Inheritance

One class can reuse properties and methods from another class.

Think:

**Animal → Dog**

A dog can inherit common behavior from an animal.

**Inheritance = reuse**

---

### 2. Encapsulation

Keeping data and the methods that operate on that data together, while controlling how internal details are accessed.

Think of a **bank account**: you interact with methods like `deposit()` and `withdraw()` instead of directly changing internal account details.

**Encapsulation = control/protect**

---

### 3. Polymorphism

**Poly = many**
**Morphism = forms**

It means the same method/interface can behave differently depending on the object.

For example, different animals could have a `speak()` method:

```text
Dog → bark
Cat → meow
```

**Polymorphism = different behavior**

---

### 4. Abstraction

Showing only the necessary information and hiding complicated implementation details.

For example, when you use:

```python
car.start()
```

you don't need to know every internal step required to start the engine.

**Abstraction = hide complexity**

### Easy interview answer

> "The four main OOP concepts are inheritance, encapsulation, polymorphism, and abstraction. Inheritance is about reusing code, encapsulation is about controlling access to data, polymorphism allows different objects to behave differently through a common interface, and abstraction hides unnecessary implementation details."

---

## 18. What is the Python GIL?

### First: what is a thread?

A **thread** is a path of execution within a program.

A program can have multiple threads working on different tasks.

### What is GIL?

GIL stands for **Global Interpreter Lock**.

In standard **CPython** (the most commonly used Python implementation), the GIL allows only one thread at a time to execute Python bytecode within a process.

### Why does it matter?

This means Python threads don't generally give true parallel execution for **CPU-heavy Python code** in standard CPython.

For CPU-heavy tasks, **multiprocessing** can be useful because separate processes can execute in parallel.

### What is CPU-heavy?

A **CPU-heavy task** spends most of its time doing calculations.

Examples:

* complex mathematical calculations
* image processing
* large computations

### Easy interview explanation

> "GIL stands for Global Interpreter Lock. In standard CPython, it allows only one thread at a time to execute Python bytecode within a process, which limits CPU-bound parallelism with threads. For CPU-heavy work, multiprocessing can be used."

---

## 19. Difference between multiprocessing, multithreading, and asynchronous programming?

This is another question where understanding the words makes everything easier.

### Multithreading

Uses multiple **threads** inside one process.

It is particularly useful for **I/O-bound tasks**.

### What is I/O?

I/O means **Input/Output**.

Examples:

* reading a file
* making an API request
* communicating with a database
* downloading something

The program often spends time **waiting** for these operations.

---

### Multiprocessing

Uses multiple **processes**.

A process is an independent running instance of a program.

It is useful for **CPU-bound tasks**, where the computer spends most of its time performing calculations.

---

### Asynchronous programming

Uses an **event loop** to manage many tasks efficiently, especially tasks that spend time waiting for I/O.

Python commonly uses `async` and `await` for this.

```python
async def get_data():
    result = await some_request()
```

### Easy way to remember

> **Multithreading → multiple threads → often useful for I/O**

> **Multiprocessing → multiple processes → useful for CPU-heavy work**

> **Async → efficiently handle many waiting I/O operations**

### Interview answer

> "Multithreading uses multiple threads and is commonly useful for I/O-bound tasks. Multiprocessing uses separate processes and is useful for CPU-bound tasks. Asynchronous programming uses an event loop to efficiently handle many I/O operations without blocking while each operation waits."

---

## 20. How would you optimize a slow Python program?

### First understand "optimization"

**Optimization** means making a program use resources more efficiently or finish its work faster.

But you shouldn't immediately start changing code.

### Step 1 — Profile

**Profiling** means measuring where the program spends most of its time.

You might discover that the problem is:

```text
Database query → 70% of time
Python code → 20%
API request → 10%
```

Then you know where to focus.

### Step 2 — Improve the actual bottleneck

Depending on the problem, you might:

* improve the algorithm
* use a better data structure
* reduce unnecessary loops
* reduce database queries
* use caching
* batch operations
* use asynchronous programming for suitable I/O tasks

### What is caching?

**Caching** means temporarily storing frequently used data so you don't have to calculate or retrieve it repeatedly.

For example, instead of querying the database every time for the same information, you might temporarily store the result.

### Easy interview answer

> "First, I would profile the program to identify the actual bottleneck instead of guessing. Then I would optimize that specific area, for example by improving the algorithm, reducing database or API calls, using caching, or using appropriate concurrency for I/O-heavy work."

---

# ⭐ The way I want you to study these

Don't memorize this:

> "Python is a high-level interpreted programming language..."

Instead, build a **mental chain**:

**Python → high-level → easy for humans → interpreted → Python interpreter executes code → supports OOP/procedural/functional styles → libraries → reusable code → frameworks → structure for building applications.**

Then if the interviewer asks:

> **"What is interpreted?"**

you already know.

If they ask:

> **"What is a library?"**

you already know.

If they ask:

> **"Give me examples of Python libraries."**

you can say:

> "NumPy, Pandas, Requests, and Matplotlib."

If they ask:

> **"What are Python frameworks?"**

you can say:

> "Django, Flask, and FastAPI are examples of Python web frameworks."

And if they ask:

> **"What's the difference between a library and a framework?"**

you can explain:

> **Library:** I generally call/use it when I need its functionality.
> **Framework:** It provides the overall structure of the application and my code works within that structure.

That is the level of understanding you should aim for—not memorizing definitions. The original 20-question list is the basis for this expanded version.

For the **next skills (JavaScript, Java, SQL, React, etc.)**, I would use **this exact style**: every technical term gets a simple meaning, an example where useful, and a natural interview answer.
