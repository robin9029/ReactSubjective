## CBA 
- LIST comprehension flat 2*3 array
- how to declare private variable - __
- OOPS concepts
- let str = 'abc_def_001'; increment using 002, 003 etc 
```
let str = 'abc_def_091';
let num= Number(str.substr(8))
let newStr= str.substr(0,8)
console.log(str.lastIndexOf('_'),newStr,num)

num += 1
num<9? num ='00'+num : num<99 ? num ='0'+num :num
console.log(num, typeof(num))

console.log(newStr+num)
```

```markdown
# Python Fundamentals and Basics: Questions and Answers

**Q1: What are the key characteristics of Python?**

**A:** Python is characterized by the following:
    * **Object-Oriented:** Supports object-oriented programming paradigms.
    * **Interpreted:**  Code is executed line by line by an interpreter, not compiled to machine code beforehand.
    * **High-Level:**  Abstracts away many low-level details of computer hardware, making it easier to write and read.
    * **Scripting Language:** Primarily used for scripting, automating tasks, and rapid prototyping.
    * **Case-Sensitive:**  Differentiates between uppercase and lowercase letters (e.g., `variable` and `Variable` are treated as different).

---

# Comments in Python

**Q2: Who created Python and when?**

**A:** Python was created by Guido Van Rossum from the Netherlands in the late 1980s.

**Q3: What are some common uses for Python?**

**A:** Python is versatile and used for:
    * Creating web pages and web applications.
    * Database queries and database management.
    * Scripting and automation.
    * Data analysis and machine learning.
    * And much more!

**Q4: How do you add comments in Python code?**

**A:** Python supports two types of comments:
    * **Single-line comments:** Use the `#` symbol. Anything after `#` on the same line is ignored by the interpreter.

        ```python
        # This is a single-line comment
        ```
    * **Multi-line comments (Paragraph comments):** Use triple quotes `'''` or `"""`.  Everything between the triple quotes is treated as a multi-line string and ignored as a comment if not assigned to a variable.

        ```python
        '''
        This is a
        multi-line comment
        using triple single quotes.
        '''

        """
        This is also a
        multi-line comment
        using triple double quotes.
        """
        ```

---

# Control Flow Statements

**Q5: What does the `break` statement do in a loop?**

**A:** The `break` statement immediately terminates the **entire loop** it is in. Execution jumps to the statement immediately following the loop.

**Q6: What does the `continue` statement do in a loop?**

**A:** The `continue` statement terminates the **current iteration** of the loop.  Execution jumps to the beginning of the loop for the next iteration.

**Q7: How do `break` and `continue` behave in nested loops?**

**A:** If `break` or `continue` is used within an inner loop of nested loops, it **only affects the inner loop**. The outer loop continues to execute as normal.

**Q8: What is the purpose of the `pass` statement?**

**A:** The `pass` statement is a null operation. It is used as a **placeholder** where syntactically some code is required, but you don't want to execute any command.  It's often used in function or class definitions where the implementation will be added later.

    ```python
    def my_function():
        pass  # Placeholder - function implementation will be added later
    ```

---

# Range Function

**Q9: Explain the `range(2, 30, 3)` function.**

**A:** `range(2, 30, 3)` generates a sequence of numbers starting from 2, up to (but not including) 30, incrementing by 3 in each step.
    * It will produce the series: 2, 5, 8, 11, 14, 17, 20, 23, 26, 29.

---

# Global Variables

**Q10: How do you declare a global variable inside a function?**

**A:** To modify a global variable from within a function or to indicate you're working with a global variable (even if not modifying), use the `global` keyword.

    ```python
    global_variable = 10

    def my_function():
        global global_variable
        global_variable = 20  # Modifying the global variable

    my_function()
    print(global_variable) # Output: 20
    ```

---

# `dir()` Function

**Q11: What is the `dir()` function used for?**

**A:** The `dir()` function is used to list the names (modules, functions, variables) in the current scope or within a specified object (like a package or module). It helps in exploring the contents of modules and packages.

---

# pip - Package Installer for Python

**Q12: What are `pip install`, `pip uninstall`, and `pip list` commands used for?**

**A:** `pip` is the package installer for Python.
    * `pip install <package_name>`: Installs a specified Python package from the Python Package Index (PyPI).
    * `pip uninstall <package_name>`: Uninstalls a previously installed package.
    * `pip list`: Lists all packages currently installed in your Python environment.

---

# Command Line Arguments

**Q13: How can you pass parameters to a Python program via the command line?**

**A:** You can access command-line arguments using the `sys` module.

    ```python
    import sys

    print(sys.argv) # sys.argv is a list containing command-line arguments
                     # sys.argv[0] is always the name of the Python script itself
    ```
    **Example:** If you run `python my_script.py arg1 arg2` from the command line, `sys.argv` will be `['my_script.py', 'arg1', 'arg2']`.

---

# User Input

**Q14: How do you get user input in Python?**

**A:** The `input()` function is used to get input from the user. It displays a prompt (optional) and returns the user's input as a string.

    ```python
    user_input = input("Enter some value: ")
    print("You entered:", user_input)
    ```

---

# Data Types in Python

**Q15: What are the built-in data types in Python?**

**A:** Python has several built-in data types:

    * **Numeric Types:**
        * `int`: Integers (whole numbers).
        * `float`: Floating-point numbers (decimal numbers).
        * `complex`: Complex numbers (numbers with a real and imaginary part).
    * **Sequence Types:**
        * `str`: Strings (textual data, immutable sequences of characters).
        * `list`: Lists (ordered, mutable sequences of items, heterogeneous).
        * `tuple`: Tuples (ordered, immutable sequences of items, heterogeneous).
        * `bytes`: Bytes (sequences of single bytes).
    * **Boolean Type:**
        * `bool`: Boolean (represents truth values `True` or `False`).
    * **Set Type:**
        * `set`: Sets (unordered collections of unique items, mutable).
    * **Mapping Type:**
        * `dict`: Dictionaries (unordered collections of key-value pairs, mutable).

---

# List Data Type

**Q16: What are lists in Python?**

**A:** Lists are ordered, mutable (changeable) sequences of items. They can hold items of different data types (heterogeneous).

**Q17: List Manipulation Methods and Operations:**

**A:** Here are some common list methods:
    * `var1.append(value)`: Adds `value` to the end of `var1`.
    * `var1.insert(index, 'new')`: Inserts `'new'` at the given `index` in `var1`.
    * `var1.pop()`: Removes and returns the last item from `var1`.
    * `var1.remove(value)`: Removes the first occurrence of `value` from `var1`.
    * `var1.sort()`: Sorts the items of `var1` in place (modifies the original list).
    * `var1.reverse()`: Reverses the order of items in `var1` in place.
    * `var1.extend(var2)`: Appends all items from list `var2` to the end of `var1` (modifies `var1`).
    * `var1.index(value)`: Returns the index of the first occurrence of `value` in `var1`.
    * `var1.count(value)`: Returns the number of times `value` appears in `var1`.
    * `var1.lower()`: Returns a lowercase version of the list (if list contains strings - *Note: This is generally used for strings, not lists directly. If you intend to lowercase strings inside a list, you would need to iterate through the list.*)
    * `var1.upper()`: Returns an uppercase version of the list (if list contains strings - *Similar note as above*).
    * `var1.split()`: Splits a string into a list of words ( *Note: Again, primarily for strings, not lists directly. To split strings within a list, you'd iterate*).

**Q18: List Built-in Functions and Operations:**

**A:** Here are some built-in functions and operations for lists:
    * `del(var1[index])`: Deletes the item at the specified `index` from `var1`.
    * `id(var1)`: Returns the unique identity (memory address) of `var1`.
    * `len(var1)`: Returns the number of items in `var1`.
    * `type(var1)`: Returns the data type of `var1` (which will be `<class 'list'>`).
    * `max(var1)`: Returns the maximum item in `var1` (works for comparable items).
    * `min(var1)`: Returns the minimum item in `var1` (works for comparable items).
    * `sum(var1)`: Returns the sum of all items in `var1` (works for numeric lists).
    * `abs(number)`: Returns the absolute value of a number (e.g., `abs(-7.25)` returns `7.25`).
    * `pow(base, exponent)`: Returns `base` raised to the power of `exponent` (e.g., `pow(2, 4)` returns `16`).
    * `math.sqrt(number)`: Returns the square root of a number (requires `import math`).
    * `math.ceil(number)`: Returns the ceiling of a number (smallest integer greater than or equal to the number, requires `import math`, e.g., `math.ceil(1.4)` returns `2`).
    * `math.floor(number)`: Returns the floor of a number (largest integer less than or equal to the number, requires `import math`, e.g., `math.floor(1.4)` returns `1`).
    * `math.pi`:  A constant representing the mathematical constant pi (requires `import math`).

**Q19: Shallow Copy vs. Deep Copy of Lists:**

**A:**
    * **Shallow Copy (`var3 = var1.copy()`):** Creates a new list object `var3`, but the elements in `var3` are references to the same objects as in `var1`. If the lists contain mutable objects (like other lists), changes to those inner objects will be reflected in both `var1` and `var3`.
    * **Deep Copy (`var3 = var1.deepcopy()`):** Creates a completely new list object `var3` and recursively copies all objects found in `var1`.  `var3` and `var1` become completely independent; changes in one won't affect the other, even for nested mutable objects. (Requires `import copy`).

**Q20: List Concatenation and Operations:**

**A:**
    * **List Concatenation (`var4 = var1 + var2`):** Creates a new list `var4` by joining the elements of `var1` followed by the elements of `var2`.
    * **List Subtraction, Multiplication, and Division:**  List subtraction, multiplication, and division using operators like `-`, `*`, `/` **do not work directly** in Python like they might in some other languages (e.g., element-wise operations). You would typically use loops or list comprehensions or libraries like NumPy for such operations.

**Q21: Nested Lists and List Slicing:**

**A:**
    * **Nested Lists (`var5 = [var1, var2]`):** Creates a list `var5` where `var1` and `var2` are elements themselves. This results in a list of lists (e.g., `[[a], [b]]`).
    * **List Slicing (`var6 = [1, 2, 3, 4, 5, 6, 7, 8, 9][1:6:2]`):**  Extracts a portion of a list. `[start:stop:step]`  In the example:
        * `1:6`:  Selects items from index 1 up to (but not including) index 6.
        * `2`:  Specifies a step of 2, meaning it takes every second item within the slice.
        * `var6` will be `[2, 4, 6]` (items at index 1, 3, 5 from the original list).

**Q22: Lists with Mixed Data Types:**

**A:** Lists can contain elements of different data types.

    ```python
    list_1 = ["a", 1, np.array([1])] # Requires import numpy as np
    print(list_1) # Output: ['a', 1, array([1])]
    print(type(list_1[2])) # Output: <class 'numpy.ndarray'>
    ```

---

# Set Data Type

**Q23: What are sets in Python?**

**A:** Sets are unordered collections of **unique** items. Sets do not allow duplicate elements. They are mutable.

**Q24: Set Operations and Properties:**

**A:**
    * `s_var1 = {"abc", 1, 2, 3}`: Creating a set.
    * `s3 = s1 - s2`: Set difference - returns elements present in `s1` but not in `s2`.
    * **Set Addition, Multiplication, and Division:** Set addition, multiplication, and division using operators like `+`, `*`, `/` **do not work directly** for set operations like union, intersection, etc. Use set methods like `union()`, `intersection()`, etc.
    * **No Duplicates:** Sets automatically eliminate duplicate elements. If you try to add a duplicate, it will have no effect.

---

# Tuple Data Type

**Q25: What are tuples in Python?**

**A:** Tuples are ordered, **immutable** (unchangeable) sequences of items.  Like lists, they can be heterogeneous. Tuples are defined using parentheses `()`.

**Q26: Immutability of Tuples:**

**A:** Tuples are immutable, meaning you cannot change their contents after they are created.  You cannot add, remove, or modify items in a tuple directly.

**Q27: Tuples Containing Mutable Objects:**

**A:** While tuples themselves are immutable, if a tuple contains mutable objects like lists, the **mutable objects within the tuple can be changed**. The tuple's structure (which lists it contains at which position) remains constant, but the lists themselves can be modified.

    ```python
    new_tup = ([1, 2, 3], "niranjan")
    print(id(new_tup[0])) # Output: Memory address of the list
    vall = new_tup[0]
    vall.append(4) # Modifying the list inside the tuple
    print(vall)      # Output: [1, 2, 3, 4]
    print(new_tup)   # Output: ([1, 2, 3, 4], 'niranjan') - Tuple is changed in terms of list content
    print(id(vall))      # Output: Same memory address as before, list was modified in place
    ```

---

# Dictionary Data Type

**Q28: What are dictionaries in Python?**

**A:** Dictionaries are unordered collections of **key-value pairs**.  Keys must be unique and immutable (strings, numbers, tuples), while values can be of any data type. Dictionaries are mutable. Dictionaries are defined using curly braces `{}`.

**Q29: Accessing Keys and Values in Dictionaries:**

**A:**

    ```python
    thisdict = {"person": [{"name": "Niranjan", "age": 32}, {"name": "Ashwini", "age": 27}]}

    thisdict.keys()       # Returns a view object that displays a list of dictionary keys
    list(thisdict.keys()) # Converts the keys view object to a list
    thisdict.values()     # Returns a view object that displays a list of dictionary values
    thisdict.items()      # Returns a view object that displays a list of dictionary items as tuples (key, value)
    ```

**Q30: Modifying Dictionaries:**

**A:**
    * **Adding a new key-value pair:**

        ```python
        thisdict = {"key3": "value3"} # If "key3" doesn't exist, it's added
        ```
    * **Updating an existing key-value pair:**

        ```python
        thisdict.update({"key3": "new_value3"}) # If "key3" exists, its value is updated
        ```
    * **Removing a specific key-value pair:**

        ```python
        thisdict.pop("key3") # Removes and returns the value associated with "key3". Raises KeyError if "key3" is not found.
        ```
    * **Removing the last inserted key-value pair (Python 3.7+):**

        ```python
        thisdict.popitem() # Removes and returns the last inserted key-value pair as a tuple (key, value).
        ```
    * **Creating a dictionary with default values for keys:**

        ```python
        x = ("key1", "key2", "key3") # Keys as a tuple
        y = 0                         # Default value
        new_dict = dict.fromkeys(x, y) # Creates a dictionary with keys from x and values all set to y.
        ```
    * **Deleting the entire dictionary:**

        ```python
        del thisdict # Removes the dictionary object itself from memory.
        ```
    * **Clearing all items from a dictionary:**

        ```python
        thisdict.clear() # Removes all key-value pairs, making the dictionary empty.
        ```

---

# Conditional and Loop Statements

**Q31: What are the basic conditional statements in Python?**

**A:** Python uses `if`, `elif` (else if), and `else` for conditional execution.

    ```python
    if condition1:
        # code to execute if condition1 is True
    elif condition2:
        # code to execute if condition1 is False AND condition2 is True
    else:
        # code to execute if both condition1 and condition2 are False
    ```

**Q32: What are the loop statements in Python?**

**A:** Python supports `while` and `for` loops.
    * **`while` loop:** Executes a block of code repeatedly as long as a condition is true.

        ```python
        while condition:
            # code to execute repeatedly as long as condition is True
        ```
    * **`for` loop:** Iterates over a sequence (like a list, tuple, string, or range) or other iterable objects.

        ```python
        for i in range(1, 10, 1): # Example using range function
            # code to execute for each item in the sequence
        ```

---

# Functions in Python

**Q33: How do you define a function in Python?**

**A:** Use the `def` keyword followed by the function name, parentheses for parameters (optional), and a colon. The function body is indented.

    ```python
    def new_function():
        return # Optional return statement
    ```

**Q34: How to assign default values to function parameters?**

**A:** You can specify default values in the function definition. If an argument is not provided during a function call, the default value is used.

    ```python
    def new_function(location="Bengaluru"): # "Bengaluru" is the default value for location
        # function body using location
        pass
    ```

**Q35: How to handle a variable number of positional arguments in a function?**

**A:** Use `*args` in the function definition. It collects all positional arguments into a tuple named `args`.

    ```python
    def new_function(*names): # *names collects variable positional arguments
        # function body using names (which is a tuple)
        for name in names:
            print(name)

    new_function("abc", "xyz", "lmn") # Example function call
    ```

**Q36: How to handle a variable number of keyword arguments in a function?**

**A:** Use `**kwargs` in the function definition. It collects all keyword arguments into a dictionary named `person`.

    ```python
    def new_function(**person): #** person collects variable keyword arguments
        # function body using person (which is a dictionary)
        print(person["fname"]) # Accessing a keyword argument 'fname'

    new_function(fname="Niranjan", lname="K") # Example function call
    ```

---

# Lambda Functions

**Q37: What are lambda functions in Python?**

**A:** Lambda functions are small, anonymous (unnamed) functions defined using the `lambda` keyword. They can take any number of arguments but are limited to a single expression.

**Q38: Example of a lambda function:**

**A:**

    ```python
    y = lambda x: x + 2
    print(y(3)) # Output: 5
    ```

---

# Classes and Objects in Python

**Q39: What are classes and objects in Python?**

**A:**
    * **Class:** A blueprint or template for creating objects. It defines the attributes (data) and methods (behavior) that objects of that class will have.
    * **Object:** An instance of a class. Objects are created based on the class blueprint and hold actual data.

**Q40: What is `self` in Python classes?**

**A:** `self` is a convention (though strongly recommended) in Python classes to refer to the **instance of the class** itself. When you call a method on an object, the object itself is automatically passed as the first argument to the method. By convention, we name this first parameter `self`. It's used to access instance variables (attributes) within the class methods.

**Q41: What is the `__init__()` method in a Python class?**

**A:** `__init__()` is a special method (constructor) in Python classes. It is automatically called when an object of the class is created. It's used to initialize the object's attributes (instance variables).

**Q42: Argument Passing Model in Python:**

**A:** Python's argument passing is described as "Pass by Object Reference," which is neither strictly "Pass by Value" nor "Pass by Reference" as in some other languages.

**Q43: Mutable vs. Immutable Objects:**

**A:**
    * **Immutable Objects:** Their value cannot be changed after creation. Examples: `int`, `float`, `bool`, `str`, `tuple`.  When you perform an operation that seems to modify an immutable object, you are actually creating a new object. Immutable variables behave somewhat like "pass by value".
    * **Mutable Objects:** Their value can be changed after creation. Examples: `list`, `dict`, `set`, and generally, custom class objects. Mutable objects behave somewhat like "pass by reference."

**Q44: Example Class `person`:**

**A:**

    ```python
    class person:
        def __init__(self, p_name, p_age):
            self.name = p_name
            self.age = p_age

        def who_person(self):
            print("End User is {}".format(self.name))

    new_employee = person("Sharat", 33) # Creating an object of class person
    new_employee.who_person()        # Calling a method on the object

    del new_employee.name # Deleting an attribute of the object
    del new_employee      # Deleting the object itself
    ```

---

# Inheritance in Python

**Q45: What is inheritance in object-oriented programming?**

**A:** Inheritance is a mechanism where a new class (child class or derived class) inherits properties (attributes and methods) from an existing class (parent class or base class). It promotes code reusability and creates a hierarchy of classes.

**Q46: Single Inheritance Example:**

**A:**

    ```python
    class person:
        def __init__(self, p_name, p_age):
            self.name = p_name
            self.age = p_age

        def who_person(self):
            print("I am {} and I am {} years old".format(self.name, self.age))

    class student(person): # student class inherits from person
        def __init__(self, s_name, s_age):
            person.__init__(self, s_name, s_age) # Calling the parent class's constructor

    s1 = student("Ramesh", 22)
    s1.who_person() # student object can use methods from person class
    # Output: I am Ramesh and I am 22 years old
    ```

**Q47: Multi-Inheritance Example:**

**A:** Python supports inheriting from multiple base classes.

    ```python
    class person():
        def __init__(self, m_name):
            print("person")
            self.m_name = m_name
            print("person-end")

    class parent1(person):
        def __init__(self, p_name):
            print("parent1")
            self.name = p_name
            person.__init__(self, p_name)
            print("end1")

    class parent2(person):
        def __init__(self, p_name):
            print("parent2")
            person.__init__(self, p_name)
            self.name = p_name
            print("end2")

    class parent3(person):
        def __init__(self, p_name):
            print("parent3")
            person.__init__(self, p_name)
            self.name = p_name
            print("end3")

    class kids(parent1, parent2, parent3): # kids inherits from parent1, parent2, parent3
        def __init__(self, p_name):
            print("kid")
            parent1.__init__(self, p_name + "1")
            parent2.__init__(self, p_name + "2")
            parent3.__init__(self, p_name + "3")
            print("end-k")

    k = kids("Raghu")
    print(k.name)   # Output: Raghu3 (due to the order of inheritance in class kids(parent1,parent2,parent3))
    print(k.m_name) # Output: Raghu3 (m_name is initialized in the last parent constructor called - parent3)
    ```
    **Note:** The order of inheritance in the class definition (`class kids(parent1, parent2, parent3)`) matters. If you change the order, the attributes might be initialized based on the method resolution order (MRO).

---

# Try-Except Blocks for Error Handling

**Q48: What are `try`, `except`, `finally`, and `else` blocks in Python error handling?**

**A:** Python's `try-except-finally-else` block is used for handling exceptions (errors).
    * **`try` block:** Encloses the code that might raise an exception.
    * **`except` block:**  Specifies how to handle specific exceptions if they occur in the `try` block. You can have multiple `except` blocks to handle different exception types.
    * **`finally` block:** Contains code that will **always** be executed, regardless of whether an exception occurred in the `try` block or not. Typically used for cleanup actions (like closing files).
    * **`else` block:**  Optional.  Executed **only if no exception** occurs in the `try` block.

**Q49: Common Exception Types mentioned:**

**A:**
    * `RuntimeError`: A base class for exceptions that don't fit into more specific categories.
    * `Exception`: The base class for all built-in exceptions (more general).
    * `NameError`: Raised when a variable is used before it has been assigned a value.
    * `BusinessLogicError`: An example of a user-defined exception (inheriting from `RuntimeError` in this case).
    * `ZeroDivisionError`:  (Implicit in `b = 5/0` example) Raised when you attempt to divide by zero.
    * `TypeError`: (Implicit in `f.write("Lorum Ipsum")` if file is opened in read mode) Raised when an operation or function is applied to an object of inappropriate type. In the `demotry` example, attempting to write to a file opened in read mode would likely raise an `IOError` or similar, but the provided output indicates "not writable" which could be a simplified representation for this context.

**Q50: User-Defined Exception Example:**

**A:**

    ```python
    class BusinessLogicError(RuntimeError): # Creating a custom exception class
        def __init__(self, arg):
            self.args = arg
    ```

**Q51: Example `demotry` function demonstrating error handling:**

**A:**

    ```python
    def demotry(i):
        class BusinessLogicError(RuntimeError):
            def __init__(self, arg):
                self.args = arg
        try:
            f = open("demo_pythonfile.txt", 'r+') # Open in read and write mode for this example, original example might imply read-only open
            if i == 1:
                f.write("Lorum Ipsum") # Will cause error if file is opened in read mode 'r'
            elif i == 2:
                b = bb / 5 # NameError: bb is not defined
            elif i == 3:
                raise Exception("Only integers in range(1 or 2) are allowed. Value passed is {}".format(i)) # Raising a general Exception
            elif i == 4:
                b = 5 / 0 # ZeroDivisionError: division by zero
            elif not type(i) is int:
                raise BusinessLogicError("Only integers are allowed. Value passed is {}".format(i)) # Raising user-defined exception
        except NameError:
            print("Variable is not define")
        except BusinessLogicError as e:
            print("User Defined Error: {}".format(''.join(e.args)))
        #except: # Be cautious with bare except blocks, they catch all exceptions - better to be specific
        #    print("Some Error ")
        except Exception as e:
            print("Raising Expection: {}".format(e.args[0]))
        else:
            print("No Exception was captured")
        finally:
            print("closing file")
            f.close()

    demotry(0)  # No exception
    demotry(1)  # Exception (if file opened in read mode 'r', likely IOError/TypeError based on context) - output shows 'not writable'
    demotry(2)  # NameError
    demotry(3)  # General Exception raised
    demotry(4)  # ZeroDivisionError
    demotry("asdf") # BusinessLogicError (user-defined exception)
    ```
    **Output (as provided, might vary slightly based on file mode and Python version):**

    ```
    >>> demotry(0)
    No Exception was captured
    closing file
    >>> demotry(1)
    Raising Expection: not writable
    closing file
    >>> demotry(2)
    Variable is not define
    closing file
    >>> demotry(3)
    Raising Expection: Only integers in range(1 or 2) are allowed. Value passed is 3
    closing file
    >>> demotry(4)
    Raising Expection: division by zero
    closing file
    >>> demotry("asdf")
    User Defined Error: Only integers are allowed. Value passed is asdf
    closing file
    >>>
    ```

---

# Operators in Python

**Q52: What are the different types of operators in Python?**

**A:** Python supports the following categories of operators:

    1. **Arithmetic Operators:** Perform mathematical operations (+, -, /, *, **, // (floor division), %, etc.).
    2. **Relational Operators (Comparison Operators):** Compare values and return Boolean results (>, <, >=, <=, !=, `<>`, ==, etc.).  `<>` is the same as `!=` (not equals) but less common in modern Python.
    3. **Assignment Operators:** Assign values to variables and can combine assignment with other operations (+=, -=, *=, /=, %=, //=, **=, &=, |=, ^=, >>=, <<=).
    4. **Logical Operators:** Perform logical operations (`and`, `or`, `not`).
    5. **Bitwise Operators (Shift/Bitwise Operators):** Operate on the binary representations of integers (&, |, ^, ~, << (left shift), >> (right shift), etc.).
    6. **Membership Operators:** Test if a value or sequence is present in another sequence (`in`, `not in`).
    7. **Identity Operators:** Compare object identity (memory locations), not just values (`is`, `is not`).

---

# Modules and Packages - Importing Functions

**Q53: How can you add user-defined Python functions to the import library so you can reuse them across different programs?**

**A:** There are a few ways to make your Python functions reusable as modules:

    1. **Modifying `sys.path` at runtime:**
        * Use the `sys.path` list, which contains directories Python searches for modules.
        * Add the directory containing your Python module file to `sys.path`.

        ```python
        from sys import path
        path.append('/path/to/your/module/directory') # Replace with the actual path
        print(path)
        import your_module_name # Now you can import your module
        ```
    2. **Using the `PYTHONPATH` environment variable:**
        * Set the `PYTHONPATH` environment variable to include the directory containing your modules. Python will automatically search these directories for modules when you use `import`. This is a more persistent approach than modifying `sys.path` in your script.
    3. **Placing the Module and Source Program in the Same Directory:**
        * If your module file (`.py` file with your functions) is in the same directory as your main Python program, Python will automatically find it during import.

**Q54: Creating and Using Compiled Python Modules (.pyc):**

**A:**
    1. **Create a Python Module File (.py):**  Write your functions in a `.py` file (e.g., `my_module.py`). Optionally, add a shebang line (`#!/usr/bin/env python3` or similar) at the very top for making it executable on Unix-like systems (if needed).
    2. **Compile to `.pyc` (Bytecode):**
        * **Compile a Directory (Recursively):** Use `compileall.compile_dir('.')` to compile all `.py` files in the current directory and its subdirectories into `.pyc` files.
        * **Compile a Single File:** Use `compileall.compile_file('yourfilename.py')` to compile a single `.py` file.

        ```python
        import compileall

        compileall.compile_dir('.')       # Compile all .py files in current dir recursively
        compileall.compile_file('my_module.py') # Compile a single file
        ```
    3. **Place `.pyc` File in `sys.path` or `PYTHONPATH`:**  Put the generated `.pyc` file in one of the directories that Python searches for modules (like those in `sys.path` or specified by `PYTHONPATH`). When you `import your_module_name`, Python may load the `.pyc` file if it's available (which can sometimes be faster for subsequent imports).
    4. **Creating Package Directories with `__init__.py`:** To organize modules into packages (directories containing modules), create a directory and place your module files (`.py` or `.pyc`) inside it.  Add an `__init__.py` file (can be empty) in the directory to tell Python to treat it as a package. You can then import modules from this package.

---

# File Handling in Python

**Q55: How do you open a file in Python?**

**A:** Use the `open()` function.

    ```python
    fd = open('newfile.txt', 'rt') # or 'r' for read text mode
    ```
    * **Syntax:** `fd = open(filename, mode)`
    * **`filename`**:  The path to the file (string).
    * **`mode`**: A string specifying the mode of operation:
        * `'r'`: Read (default if mode is not specified).
        * `'a'`: Append (writes to the end of the file, creates if it doesn't exist).
        * `'w'`: Write (overwrites the file if it exists, creates if it doesn't exist).
        * `'x'`: Create (creates a new file, but fails if the file already exists).
        * `'t'`: Text mode (default).
        * `'b'`: Binary mode.

    **Combined Modes:**
    * `'rt'` or `'r'`: Read text (default).
    * `'rb'`: Read binary.
    * `'at'` or `'a'`: Append text.
    * `'ab'`: Append binary.
    * `'wt'` or `'w'`: Write text.
    * `'wb'`: Write binary.
    * `'xt'` or `'x'`: Create text (exclusive creation).
    * `'xb'`: Create binary (exclusive creation).
    * `'r+'`: Read and write (updates), file pointer at beginning.
    * `'w+'`: Write and read, overwrites file, creates if not exists.
    * `'a+'`: Append and read, file pointer at the end of the file.
    * `'x+'`: Create and read, exclusive creation.

**Q56: File Pointer Methods:**

**A:**
    * `fd.tell()`: Returns the current position of the file pointer (in bytes from the beginning of the file).
    * `fd.seek(offset, whence)`:  Positions the file pointer to a specific location.
        * `offset`: Number of bytes to move.
        * `whence`: Starting point for the offset:
            * `0`: Beginning of the file (default).
            * `1`: Current position.
            * `2`: End of the file.
        * Examples:
            * `fd.seek(0, 0)`:  Move to the beginning of the file.
            * `fd.seek(1, 0)`: Move 1 byte from the beginning.
            * `fd.seek(-5, 1)`: Move 5 bytes backward from the current position.
            * `fd.seek(-5, 2)`: Move 5 bytes backward from the end of the file.
    * `fd.close()`: Closes the file. It's crucial to close files after you're done to release system resources and ensure data is written to disk.

**Q57: File Reading Methods:**

**A:**
    * `fd.read(size=-1)`: Reads up to `size` characters (in text mode) or bytes (in binary mode) from the file, starting from the current position. If `size` is negative or omitted, it reads the entire file content.
    * `fd.readline()`: Reads one line from the file, including the newline character at the end of the line (if present). Subsequent calls read the next lines.
    * `fd.readlines()`: Reads all lines from the file and returns them as a list of strings. Each string in the list represents a line, including the newline character (if present).

**Q58: File Attributes:**

**A:**
    * `fd.mode`: Returns the mode in which the file was opened (e.g., `'r'`, `'w'`, `'rb'`).
    * `fd.name`: Returns the name of the file associated with the file handle for file operations.

---

# Datetime Module

**Q59: How do you work with dates and times in Python?**

**A:** Use the `datetime` module.

    ```python
    import datetime

    x1 = datetime.datetime.now() # Get the current date and time
    x2 = datetime.datetime(2020, 5, 17) # Create a datetime object for a specific date

    print(x1.year)           # Output: Current year
    print(x1.strftime("%A")) # Output: Current day of the week (e.g., "Sunday", "Monday"...) -  strftime formats datetime objects into strings based on format codes. "%A" is for weekday name.
    print(x2)              # Output: 2020-05-17 00:00:00
    ```

---

# Regular Expressions (RegEx) - `re` Module

**Q60: What are regular expressions and how do you use them in Python?**

**A:** Regular expressions (regex or regexp) are patterns used to match character combinations in strings. Python's `re` module provides support for regular expressions.

**Q61: Example Regex Operations:**

**A:**

    ```python
    import re

    txt = "The rain in Spain country"

    # re.search(pattern, string): Searches for the first match of the pattern in the string. Returns a match object if found, otherwise None.
    x = re.search(r"\bS\w+", txt) # Search for a word starting with 'S' (\b is word boundary, \w+ is one or more word characters)

    if x: # Check if a match was found
        print(x.span())   # Output: (start_index, end_index) of the match
        print(x.start())  # Output: Start index of the match
        print(x.string) # Output: The original string that was searched
        print(x.group())  # Output: The actual matched substring

    # re.findall(pattern, string): Finds all non-overlapping matches of the pattern in the string and returns them as a list of strings.
    y = re.findall("in", txt) # Find all occurrences of "in"
    print(y) # Output: ['in', 'in', 'in']

    # re.sub(pattern, replacement, string, count=0): Replaces occurrences of the pattern in the string with the replacement string.
    z = re.sub("\s", "9", txt) # Replace whitespace (\s) with "9"
    print(z) # Output: The9rain9in9Spain9country

    # re.split(pattern, string, maxsplit=0): Splits the string by occurrences of the pattern.
    ab = re.split("\s", txt, 2) # Split string by whitespace, at most 2 splits
    print(ab) # Output: ['The', 'rain', 'in Spain country']
    ```
    **Output of Regex Examples:**
    ```
    (12, 17)
    12
    The rain in Spain country
    Spain
    ['in', 'in', 'in']
    The9rain9in9Spain9country
    ['The', 'rain', 'in Spain country']
    ```

---

# Encapsulation

**Q62: What is encapsulation in object-oriented programming?**

**A:** Encapsulation is a fundamental OOP concept. It's the bundling of data (attributes) and methods that operate on that data into a single unit (a class). It also involves controlling access to the internal data of an object to prevent accidental modification from outside the object.

**Q63: Access Modifiers in Python (and Encapsulation):**

**A:** Python has a convention (not strict enforcement like in some languages) for access modifiers:
    * **Public (No prefix):** Attributes and methods are public by default and can be accessed from anywhere.

        ```python
        self.name = 'Manjula' # Public attribute
        ```
    * **Protected (`_` prefix):**  Convention is that attributes and methods with a single underscore prefix (`_`) are intended for internal use within the class and its subclasses.  However, they are still technically accessible from outside the class (it's more of a "hint" not to access them directly).

        ```python
        self._middlename = 'md' # Protected - by convention
        ```
    * **Private (`__` prefix):** Attributes and methods with a double underscore prefix (`__`) are intended to be truly private to the class. Python applies name mangling to make them harder to access directly from outside the class.  They are still accessible via name mangling (e.g., `_ClassName__privateAttribute`), but this is generally discouraged.

        ```python
        self.__lastname = 'Dube' # Private - name mangled
        ```

**Q64: Encapsulation Example (`Person` Class):**

**A:**

    ```python
    class Person:
        def __init__(self):
            self.name = 'Manjula'        # Public
            self._middlename = 'md'     # Protected (by convention)
            self.__lastname = 'Dube'     # Private (name mangled)

        def PrintName(self):
            return self.name + ' ' + self.__lastname # Accessing private attribute within the class method

    P = Person()
    print(P.name)         # Output: Manjula (Public - accessible)
    print(P.PrintName())   # Output: Manjula Dube (Accessing private attribute via class method - works)
    print(P._middlename)  # Output: md (Protected - technically accessible, but discouraged)

    try:
        print(P.__lastname) # Attempt to access private attribute directly from outside
    except Exception as e:
        print("Exception {}".format(e)) # Output: Exception 'Person' object has no attribute '__lastname'
    ```

---

# `map()` Function

**Q65: What does the `map()` function do in Python?**

**A:** The `map()` function applies a given function to each item of an iterable (like a list, tuple) and returns a map object (which is an iterator). You typically convert the map object to a list or tuple to see the results.

**Q66: `map()` Function Example:**

**A:**

    ```python
    # Function to double a number
    def addition(n):
        return n + n

    numbers = (1, 2, 3, 4)
    result = map(addition, numbers) # Apply 'addition' function to each number in 'numbers'
    print(list(result)) # Convert the map object to a list to see the results
    # Output: [2, 4, 6, 8]
    ```

---

# NumPy - Numerical Python

**Q67: What is NumPy?**

**A:** NumPy (Numerical Python) is a fundamental Python library for numerical computing. It provides support for:
    * **Arrays:**  Efficient multi-dimensional array objects (especially for numerical data).
    * **Linear Algebra, Fourier Transform, Matrices:**  Functions for these mathematical operations.

**Q68: Key features of NumPy:**

**A:**
    * **Performance:** NumPy is written in C and C++ for performance-critical parts, making it very fast for numerical operations, especially on arrays.
    * **Arrays (ndarrays):**  Provides `ndarray` (N-dimensional array) objects, which are more efficient for numerical data than standard Python lists, especially for large datasets.

**Q69: NumPy Array Creation:**

**A:**

    ```python
    import numpy

    # Create a 1-dimensional NumPy array
    arr = numpy.array([32, 33, 34, 35, 36])
    print(arr) # Output: array([32, 33, 34, 35, 36])

    # Create a 2-dimensional NumPy array (matrix)
    arr2 = numpy.array([[21, 31, 41, 51], [11, 22, 33, 44]])
    print(arr2)
    # Output:
    # array([[21, 31, 41, 51],
    #        [11, 22, 33, 44]])
    ```

**Q70: NumPy Array Reshaping:**

**A:** `reshape()` is used to change the shape (dimensions) of a NumPy array without changing its data.

    ```python
    arr2 = numpy.array([[21, 31, 41, 51], [11, 22, 33, 44]]) # 2x4 array (2 rows, 4 columns)

    arr3d = arr2.reshape(2, 2, 2) # Reshape to a 3D array (2x2x2)
    print(arr3d)
    # Output:
    # array([[[21, 31],
    #         [41, 51]],
    #
    #        [[11, 22],
    #         [33, 44]]])

    arr1d = arr3d.reshape(-1) # Reshape to a 1D array (flattening) using -1 to automatically calculate the dimension
    print(arr1d)
    # Output: array([21, 31, 41, 51, 11, 22, 33, 44])
    ```

**Q71: Creating Higher-Dimensional NumPy Arrays (e.g., 5D):**

**A:** Use the `ndmin` parameter in `numpy.array()` to specify the desired number of dimensions.

    ```python
    import numpy as np

    arr = np.array([1, 2, 3, 4], ndmin=5) # Create a 5-dimensional array
    print(arr) # Output: [[[[[1 2 3 4]]]]]
    print("Array size {}".format(arr.shape)) # Output: Array size (1, 1, 1, 1, 4) - Shape tuple indicating dimensions
    ```

**Q72: Other NumPy Array Operations (Flip, Rotate):**

**A:** NumPy provides functions for array manipulation.

    ```python
    arr2 = np.array([[1, 3, 5, 7],
                     [2, 4, 6, 8]])

    arr3 = np.rot90(arr2) # Rotate array by 90 degrees in the plane specified by axes
    print(arr3)
    # Output:
    # array([[7, 8],
    #        [5, 6],
    #        [3, 4],
    #        [1, 2]])

    arr4 = np.flip(arr2) # Reverse the order of elements along the given axis (default is all axes for multi-dimensional arrays)
    print(arr4)
    # Output:
    # array([[8, 6, 4, 2],
    #        [7, 5, 3, 1]])
    ```

---

# NumPy Iteration

**Q73: How to iterate through elements of a NumPy array?**

**A:** Use `np.nditer()` for efficient multi-dimensional array iteration.

    ```python
    import numpy as np

    arr = np.array([[[1, 2], [3, 4]], [[5, 6], [7, 8]]])
    for x in np.nditer(arr): # Iterating through each element in the array
        print(x)
    # Output: 1 2 3 4 5 6 7 8
    ```

---

# NumPy Enumeration

**Q74: How to get both index and value during NumPy array iteration?**

**A:** Use `np.ndenumerate()` to get both the index (multi-dimensional index tuple) and the value for each element during iteration.

    ```python
    import numpy as np

    arr = np.array([[1, 2, 3, 4], [5, 6, 7, 8]])
    for idx, x in np.ndenumerate(arr): # Enumerate through the array
        print(idx, x)
    # Output:
    # (0, 0) 1
    # (0, 1) 2
    # (0, 2) 3
    # (0, 3) 4
    # (1, 0) 5
    # (1, 1) 6
    # (1, 2) 7
    # (1, 3) 8
    ```

---

# NumPy Splitting Arrays

**Q75: How to split a NumPy array into multiple sub-arrays?**

**A:** Use `np.array_split()` (or `np.split()`, but `array_split` handles cases where the array cannot be split equally).

    ```python
    import numpy as np

    arr = np.array([1, 2, 3, 4, 5, 6])
    newarr = np.array_split(arr, 3) # Split into 3 sub-arrays (might not be equal sizes if not divisible)
    print(newarr)
    # Output:
    # [array([1, 2]), array([3, 4]), array([5, 6])]
    ```

---

# NumPy Joining Arrays

**Q76: How to join or concatenate NumPy arrays?**

**A:** NumPy provides several functions for joining arrays.
    * `np.concatenate()`: General-purpose concatenation along an existing axis.
    * `np.hstack()`: Horizontal stack (column-wise concatenation).
    * `np.vstack()`: Vertical stack (row-wise concatenation).
    * `np.dstack()`: Depth-wise stack (stacking along the 3rd axis - depth).

**Q77: NumPy Array Joining Examples:**

**A:**

    ```python
    import numpy as np

    arr1 = np.array([1, 2, 3])
    arr2 = np.array([4, 5, 6])

    # Concatenate
    arr = np.concatenate((arr1, arr2))
    print(arr) # Output: [1 2 3 4 5 6]

    # Horizontal Stack
    o1 = np.hstack((arr1, arr2))
    print(o1) # Output: [1 2 3 4 5 6] (same as concatenate in 1D case)

    # Vertical Stack (results in a 2D array)
    o2 = np.vstack((arr1, arr2))
    print(o2)
    # Output:
    # [[1 2 3]
    #  [4 5 6]]

    # Depth Stack (results in a 3D array)
    o3 = np.dstack((arr1, arr2))
    print(o3)
    # Output:
    # [[[1 4]
    #   [2 5]
    #   [3 6]]]
    ```

---

# NumPy Searching (Where and Searchsorted)

**Q78: How to find indices of elements that meet a condition in NumPy?**

**A:** Use `np.where()` to find indices where a condition is true.

**Q79: How to perform binary search for insertion points in a sorted NumPy array?**

**A:** Use `np.searchsorted()` for binary search to find indices where values should be inserted to maintain sorted order.

**Q80: NumPy Search Examples:**

**A:**

    ```python
    import numpy as np

    arr1 = np.array([1, 2, 3, 4, 5, 4, 4])
    arr2 = np.array([6, 7, 8, 9])

    # Find indices where arr1 == 4
    x1 = np.where(arr1 == 4)
    print(x1) # Output: (array([3, 5, 6]),) - Indices are returned as a tuple of arrays

    # Find indices where arr1 is odd (arr1 % 2 == 1)
    x2 = np.where(arr1 % 2 == 1)
    print(x2) # Output: (array([0, 2, 4]),) - Indices of odd numbers

    # Binary search in sorted array arr2 to find insertion points
    # for [7, 6, 1, 10] to maintain sorted order (side='right' means rightmost suitable index if value is already present)
    x3 = np.searchsorted(arr2, [7, 6, 1, 10], side='right')
    print(x3) # Output: [2 1 0 4] - Insertion indices
    ```

**Q81: Another `np.where()` Example:**

**A:**

    ```python
    import numpy as np

    arr = np.array([1, 2, 3, 4, 5, 6, 7, 8])
    x = np.where(arr % 2 == 1) # Find indices where arr is odd
    print(x) # Output: (array([0, 2, 4, 6]),)
    ```

---

# NumPy Filters (Boolean Indexing)

**Q82: How to filter elements of a NumPy array based on a condition?**

**A:** Use Boolean indexing (creating a Boolean array based on a condition and using it to index the original array).

    ```python
    import numpy as np

    arr = np.array([1, 2, 3, 4, 5, 6, 7])
    filter_arr = arr % 2 == 0 # Create a Boolean array: True where arr is even, False otherwise
    print(filter_arr) # Output: [False  True False  True False  True False]

    newarr = arr[filter_arr] # Use filter_arr as indices to select elements from arr where filter_arr is True
    print(newarr) # Output: [2 4 6] - Even numbers from arr
    ```

---

# Pandas - Python Data Analysis Library

**Q83: What is Pandas?**

**A:** Pandas is a powerful Python library for data manipulation and analysis. It is especially useful for working with structured data (like tables, spreadsheets, SQL data).

**Q84: Key Features of Pandas:**

**A:**
    * **Data Analysis and Manipulation:** Provides tools for cleaning, exploring, transforming, and analyzing data.
    * **Big Data Handling:** Efficiently handles large datasets.
    * **Data Cleaning:** Tools for dealing with missing data, inconsistencies, etc.
    * **Statistical Analysis:**  Enables statistical operations and insights.
    * **Data Structures:** Core data structures are `Series` (1D labeled array) and `DataFrame` (2D labeled table-like structure).

**Q85: Pandas DataFrame:**

**A:** A `DataFrame` is a 2-dimensional labeled data structure, like a table with rows and columns. It can hold data of different types (numeric, string, boolean, etc.).

    ```python
    import pandas

    mydataset = {
        'cars': ["BMW", "Volvo", "Ford"],
        'passings': [3, 7, 2]
    }

    myvar1 = pandas.DataFrame(mydataset, index=["x", "y", "z"]) # Create DataFrame with data and custom index labels
    myvar2 = pandas.DataFrame(mydataset, index=["x", "y", "z"])

    print(myvar1)
    # Output:
    #       cars  passings
    # x     BMW         3
    # y   Volvo         7
    # z    Ford         2

    print(myvar2) # Will be the same as myvar1
    # Output: (same as above)
    #       cars  passings
    # x     BMW         3
    # y   Volvo         7
    # z    Ford         2
    ```

**Q86: Pandas Series:**

**A:** A `Series` is a 1-dimensional labeled array, like a column in a table.

    ```python
    import pandas as pd # Standard convention to import pandas as pd

    a = [1, 7, 2]
    myvar = pd.Series(a, index=["x", "y", "z"]) # Create Series with data and custom index labels
    print(myvar)
    # Output:
    # x    1
    # y    7
    # z    2
    # dtype: int64
    ```

**Q87: Creating DataFrame from Dictionary (more structured example):**

**A:**

    ```python
    import pandas as pd

    data = {
        "Duration": {"0": 60, "1": 60, "2": 60, "3": 45, "4": 45, "5": 60},
        "Pulse":    {"0": 110, "1": 117, "2": 103, "3": 109, "4": 117, "5": 102},
        "Maxpulse": {"0": 130, "1": 145, "2": 135, "3": 175, "4": 148, "5": 127},
        "Calories": {"0": 409.1, "1": 479.0, "2": 340.0, "3": 282.4, "4": 406.0, "5": 300.5}
    }

    df = pd.DataFrame(data) # Creating DataFrame from a dictionary of dictionaries
    print(df)
    # Output:
    #    Duration  Pulse  Maxpulse  Calories
    # 0        60    110       130     409.1
    # 1        60    117       145     479.0
    # 2        60    103       135     340.0
    # 3        45    109       175     282.4
    # 4        45    117       148     406.0
    # 5        60    102       127     300.5
    ```

**Q88: DataFrame `info()`, `head()`, `tail()` methods:**

**A:**

    ```python
    # Assuming 'myvar' is the DataFrame from Q85 example:
    # myvar = pandas.DataFrame(mydataset, index=["x", "y", "z"])

    myvar.info() # Get concise summary of the DataFrame, including data types, non-null values, memory usage
    # Output (example):
    # <class 'pandas.core.frame.DataFrame'>
    # Index: 3 entries, x to z
    # Data columns (total 2 columns):
    #  #   Column    Non-Null Count  Dtype
    # ---  ------    --------------  -----
    #  0   cars      3 non-null      object
    #  1   passings  3 non-null      int64
    # dtypes: int64(1), object(1)
    # memory usage: 72.0+ bytes

    myvar.head(2) # Display the first 2 rows of the DataFrame
    # Output:
    #       cars  passings
    # x     BMW         3
    # y   Volvo         7

    myvar.tail(2) # Display the last 2 rows of the DataFrame
    # Output:
    #       cars  passings
    # y   Volvo         7
    # z    Ford         2
    ```

**Q89: DataFrame Indexing with `.loc[]`:**

**A:** `.loc[]` is used for label-based indexing in Pandas DataFrames (and Series).

    ```python
    # Assuming 'new_var1' is a DataFrame (not defined explicitly in the provided text - assuming it's similar to myvar from Q85):
    # new_var1 = pandas.DataFrame({'cars': ["BMW", "Ford", "Jaguar"], 'ratings': [5, 4, 3]})

    # Select rows with index labels 0 and 2
    new_var1.loc[[0, 2]]
    # Output (example based on assumed new_var1):
    #       cars  ratings
    # 0     BMW        5
    # 2  Jaguar        3
    ```

**Q90: Converting Pandas Series to String:**

**A:** `to_string()` method converts a Pandas Series (or DataFrame) into a string representation. Useful for printing output.

    ```python
    # Assuming 'myvar' is the DataFrame from Q85 example:
    # myvar = pandas.DataFrame(mydataset, index=["x", "y", "z"])

    myvar.to_string()
    # Output (example):
    # '      cars  passings\nx     BMW         3\ny   Volvo         7\nz    Ford         2'
    ```

**Q91: Appending Rows to a DataFrame:**

**A:** Use `df.append()` to add new rows.  **Note:** In older Pandas versions, `append` often returned a new DataFrame. In more recent versions, it might be deprecated or behave differently for in-place modification.  It's often recommended to use `pd.concat()` for more robust and efficient concatenation in newer Pandas.

    ```python
    # Assuming 'myvar' is the DataFrame from Q85 example:
    # myvar = pandas.DataFrame(mydataset, index=["x", "y", "z"])

    # Append a new row as a dictionary (index '3' will be assigned automatically if not specified in append, 'a' parameter in example is not standard practice for append and likely incorrect)
    myvar2 = myvar.append({"cars": "Maruti", "passings": 3.5}) # 'a' parameter is incorrect usage, removed

    print(myvar2)
    # Output (example):
    #       cars  passings
    # 0     BMW         3.0
    # 1   Volvo         7.0
    # 2    Ford         2.0
    # 3  Maruti         3.5


    myvar3 = myvar.append({"cars": "Tata", "passings": float('nan')}) # Append with NaN for missing 'passings' value
    print(myvar3)
    # Output (example):
    #       cars  passings
    # 0     BMW         3.0
    # 1   Volvo         7.0
    # 2    Ford         2.0
    # 3    Tata         NaN
    ```

**Q92: DataFrame Filtering using `.loc[]` and Boolean Conditions:**

**A:** Filter rows based on column values using Boolean indexing with `.loc[]`.

    ```python
    import pandas as pd

    datatest = {'flight': ['HRR', 'SBC', 'KGI', 'DLH', 'BGM', 'MGL', 'UDP', 'SMG'],
                'seats':  [101, 200, 151, 52, 55, 66, 77, 0],
                'price':  [2500, 2400, 2500, 2000, 5000, 2450, 4400, 6000]}
    flight = pd.DataFrame(datatest)

    # Filter rows where 'price' is greater than 2500
    filtered_flight = flight.loc[flight["price"] > 2500]
    print(filtered_flight)
    # Output:
    #   flight  seats  price
    # 4    BGM     55   5000
    # 6    UDP     77   4400
    # 7    SMG      0   6000
    ```

**Q93: Inserting a New Column into a DataFrame:**

**A:** Use `df.insert()` to insert a column at a specific position. Or simply assign a new Series to a new column name (e.g., `df['new_column'] = values`).

    ```python
    # Assuming 'flight' DataFrame from Q92 example:

    flight.insert(3, "distance", "None") # Insert column 'distance' at index 3, with default value "None"
    print(flight)
    # Output (column 'distance' is inserted at index 3):
    #   flight  seats  price distance
    # 0    HRR    101   2500     None
    # 1    SBC    200   2400     None
    # 2    KGI    151   2500     None
    # 3    DLH     52   2000     None
    # 4    BGM     55   5000     None
    # 5    MGL     66   2450     None
    # 6    UDP     77   4400     None
    # 7    SMG      0   6000     None
    ```

**Q94: Inserting a New Row into a DataFrame:**

**A:** Use `.loc[new_index] = value` to add a new row.  `value` can be a list, NumPy array, or Series.

    ```python
    # Assuming 'flight' DataFrame from Q93 example:

    import numpy

    flight.loc[8] = numpy.array(["MYS", 99, 2200, "None"]) # Add a new row at index 8 with values as a NumPy array
    print(flight)
    # Output (row at index 8 is added):
    #   flight  seats  price distance
    # 0    HRR    101   2500     None
    # 1    SBC    200   2400     None
    # 2    KGI    151   2500     None
    # 3    DLH     52   2000     None
    # 4    BGM     55   5000     None
    # 5    MGL     66   2450     None
    # 6    UDP     77   4400     None
    # 7    SMG      0   6000     None
    # 8    MYS     99   2200     None
    ```

**Q95: Accessing Column Names and Index Labels:**

**A:**

    ```python
    # Assuming 'flight' DataFrame from Q94 example:

    flight.columns # Get column names (returns a Pandas Index object)
    # Output (example): Index(['flight', 'seats', 'price', 'distance'], dtype='object')

    flight.index   # Get index labels (returns a Pandas Int64Index object in this case)
    # Output (example): Int64Index([0, 1, 2, 3, 4, 5, 6, 7, 8], dtype='int64')
    ```

**Q96: Accessing a Specific Value in a DataFrame:**

**A:** Use `.loc[row_label, column_label]` to access a specific value. Or `.at[row_label, column_label]` for faster scalar value access.

    ```python
    # Assuming 'flight' DataFrame from Q95 example:

    flight.loc[7, "seats"] # Access value in row with index 7, column 'seats'
    # Output: 0

    # Update a specific value using .at[] (for scalar access, might be slightly faster than .loc)
    flight.at[7, 'seats'] = 10
    print(flight) # DataFrame with 'seats' at index 7 updated to 10

    flight.loc[7, "price"] = 6500 # Update value using .loc[]
    print(flight) # DataFrame with 'price' at index 7 updated to 6500
    ```

**Q97: Inserting NaN/None into Dataframe:**

**A:** Use `numpy.nan` for NumPy NaN (Not a Number) or Python's `None`.

    ```python
    # Assuming 'flight' DataFrame from Q96 example:

    import numpy

    flight.at[7, 'seats'] = numpy.nan # Insert NumPy NaN
    flight.at[6, 'seats'] = None      # Insert Python None
    print(flight)
    # Output (DataFrame with NaN and None in 'seats' column):
    #   flight  seats  price distance
    # 0    HRR    101   2500     None
    # 1    SBC    200   2400     None
    # 2    KGI    151   2500     None
    # 3    DLH     52   2000     None
    # 4    BGM     55   5000     None
    # 5    MGL     66   2450     None
    # 6    UDP   None   4400     None  # None inserted
    # 7    SMG    NaN   6000     None  # NaN inserted
    # 8    MYS     99   2200     None
    ```

**Q98: How to remove null/none value from dataframe?**

**A:** Use `df.dropna()` to remove rows containing missing values (NaN or None).
    * `df.dropna()` returns a **new DataFrame** with rows removed.
    * `df.dropna(inplace=True)` modifies the **original DataFrame** in place.

    ```python
    # Assuming 'flight' DataFrame from Q97 example:

    new_flight = flight.dropna() # Create a new DataFrame with rows having NaN/None removed
    print(new_flight)
    # Output: DataFrame without rows 6 and 7 (as they had None/NaN in 'seats')
    #   flight  seats  price distance
    # 0    HRR  101.0   2500     None
    # 1    SBC  200.0   2400     None
    # 2    KGI  151.0   2500     None
    # 3    DLH   52.0   2000     None
    # 4    BGM   55.0   5000     None
    # 5    MGL   66.0   2450     None
    # 8    MYS   99.0   2200     None
    ```

**Q99: How to replace null value with other?**

**A:** Use `df.fillna(value)` to replace NaN/None values with a specified `value`.
    * `df.fillna(value)` returns a **new DataFrame** with NaN/None replaced.
    * `df.fillna(value, inplace=True)` modifies the **original DataFrame** in place.

    ```python
    # Assuming 'new_flight' DataFrame from Q98 example (after dropna, re-introducing NaN for demonstration):
    # new_flight.at[8, 'seats'] = numpy.nan

    new_flight.fillna(130, inplace=True) # Fill NaN/None values in-place with 130
    print(new_flight)
    # Output: DataFrame with NaN in 'seats' (if re-introduced) replaced by 130
    #   flight  seats  price distance
    # 0    HRR  101.0   2500     None
    # 1    SBC  200.0   2400     None
    # 2    KGI  151.0   2500     None
    # 3    DLH   52.0   2000     None
    # 4    BGM   55.0   5000     None
    # 5    MGL   66.0   2450     None
    # 8    MYS  130.0   2200     None # NaN at index 8 in 'seats' replaced with 130
    ```

**Q100: How to find null?**

**A:**
    * `df.isnull()`: Returns a DataFrame of the same shape as `df`, where each cell is `True` if the corresponding value in `df` is NaN/None, and `False` otherwise.
    * `df["column_name"].isnull()`: Returns a Pandas Series of Booleans indicating whether each value in the specified column is NaN/None.
    * `df.loc[df['column_name'].isnull()]`: Selects and returns the rows of the DataFrame where the specified column has NaN/None values.

**Q101: Finding Null Value Examples:**

**A:**

    ```python
    # Assuming 'flight' DataFrame from Q97 example (with NaN/None values):

    flight.isnull() # Returns DataFrame of booleans indicating null values
    # Output (example, True where null, False otherwise):
    #   flight  seats  price distance
    # 0   False  False  False    False
    # 1   False  False  False    False
    # 2   False  False  False    False
    # 3   False  False  False    False
    # 4   False  False  False    False
    # 5   False  False  False    False
    # 6   False   True  False    False # True for None in 'seats' at index 6
    # 7   False   True  False    False # True for NaN in 'seats' at index 7
    # 8   False  False  False    False

    flight["seats"].isnull() # Check for null values only in the 'seats' column (returns Series of booleans)
    # Output (example):
    # 0    False
    # 1    False
    # 2    False
    # 3    False
    # 4    False
    # 5    False
    # 6     True # True for None at index 6
    # 7     True # True for NaN at index 7
    # 8    False
    # Name: seats, dtype: bool

    flight.loc[flight['seats'].isnull()] # Select rows where 'seats' column has null values
    # Output (example): Rows 6 and 7 where 'seats' is null
    #   flight  seats  price distance
    # 6    UDP   None   4400     None
    # 7    SMG    NaN   6000     None
    ```

---

# Math in Dataframe

**Q102: How to find duplicate in pandas?**

**A:** Use `df.duplicated()` to find duplicate rows. It returns a Pandas Series of Booleans where `True` indicates a duplicate row (based on all columns by default).

    ```python
    import pandas as pd

    # Assuming 'data.csv' is a CSV file with some data
    df = pd.read_csv('data.csv')
    print(df.duplicated()) # Output: Series of booleans, True for duplicate rows
    ```

**Q103: Math in dataframe.**

**A:** You can perform various mathematical operations directly on DataFrame columns (Series).

    ```python
    # Assuming 'new_flight' DataFrame from Q99 example:
    # new_flight = flight.dropna()  # or any DataFrame with a 'price' column

    price_mean = new_flight["price"].mean() # Calculate mean (average) of 'price' column
    print("Mean price:", price_mean)
    # Output (example): Mean price: 2721.4285714285716

    price_mode = new_flight["price"].mode() # Calculate mode (most frequent value) of 'price' column
    print("Mode price:\n", price_mode)
    # Output (example):
    # Mode price:
    # 0    2500
    # dtype: object

    price_median = new_flight["price"].median() # Calculate median (middle value) of 'price' column
    print("Median price:", price_median)
    # Output (example): Median price: 2450.0

    price_sum = new_flight["price"].sum() # Calculate sum of 'price' column
    print("Sum of prices:", price_sum)
    # Output (example): Sum of prices: 19050
    ```

---

# Python File Types - `.pyc`, `.pyo`, `.pyd`

**Q104: What are the differences between `.pyc`, `.pyo`, and `.pyd` file types in Python?**

**A:** These are different types of files related to Python code:

    * **`.pyc` (Compiled Python file):**
        * Contains bytecode of Python source code (`.py` files).
        * Created when Python imports a module and compiles it to bytecode for faster loading in subsequent imports.
        * Can be used on any operating system.

    * **`.pyo` (Optimized Compiled Python file):**
        * Also contains Python bytecode, but it's **optimized** bytecode.
        * Created when Python is run with optimization flags (e.g., `-O` or `-OO`).
        * Designed to be more compact than `.pyc` due to optimizations.
        * Can be used on any operating system.

    * **`.pyd` (Python Dynamic Module - Windows specific):**
        * A **dynamically-linked library (DLL)** specifically for Windows.
        * Used for extension modules written in languages like C or C++ that can be imported into Python programs on Windows.
        * Not directly related to bytecode compilation of Python code; rather, it's for binary extension modules.
        * Operating system specific (Windows).

**Key Differences Summary:**

| File Type | Description                         | Optimization | Operating System |
| --------- | ----------------------------------- | ------------ | ---------------- |
| `.pyc`    | Compiled Python bytecode          | No           | Cross-platform   |
| `.pyo`    | Optimized compiled Python bytecode | Yes          | Cross-platform   |
| `.pyd`    | Windows Dynamic Link Library (DLL) | N/A          | Windows-specific |

---

# Scripting vs. Programming Languages

**Q105: What is the key difference between scripting languages and programming languages?**

**A:** The main difference lies in their execution model:

    * **Programming Languages (e.g., C++, Java, C#):**
        * Typically use a **compiler**.
        * Compiler translates the entire high-level source code into machine code (executable).
        * Compilation is done **before** execution.
        * Compiled programs usually run faster as they are directly executed by the processor.

    * **Scripting Languages (e.g., Python, JavaScript, Ruby, Perl):**
        * Typically use an **interpreter**.
        * Interpreter executes the source code **line by line at runtime**.
        * No separate compilation step before execution.
        * Scripting languages often prioritize rapid development, flexibility, and ease of use over raw performance compared to compiled languages.

**Execution Flow:**

* **Compiled Language:** Source Code → Compiler → Machine Code → Execution
* **Scripting Language:** Source Code → Interpreter → Execution (line by line)
```
