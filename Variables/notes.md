## 📚 Table of Contents

- [Why Variables?](#why-variables)
- [Variables in Python](#variables-in-python)
  - [Declaration and Assignment](#declaration-and-assignment)
  - [Rules for Naming Variables](#rules-for-naming-variables)
  - [Multi-Word Variable Names](#multi-word-variable-names)
  - [Many Values to Multiple Variables](#many-values-to-multiple-variables)
- [Scope of Variables](#scope-of-variables)
  - [The LEGB Rule](#the-legb-rule)
    - [Local Scope](#1local-scope)
    - [Enclosing Scope](#2enclosing-scope)
    - [Global Scope](#3global-scope)
    - [Built-in Scope](#4built-in-scope)
- [Key Takeaways](#key-takeaways)
#### Why Variables


*Variables help us:*
- *Store data for later use.*
- *Avoid repeating values.*
- *Make programs dynamic and reusable.*
- *Perform calculations and data manipulation.*

# Variables in Python

*A variable is a name that refers to a value stored in memory. It acts as a container for data.*

## Declaration and Assignment

*Syntax:* variable_name=value
ex: *x=5*
*y=143*
*name="Python"*

**[!NOTE]**
*Python automatically detects the data type when a value is assigned(as it is dynamically typed language).*
## Rules for naming variables

- *can contain letters, numbers, and underscores(_).*
- *Must start with a letter or underscore, but not with a digit.*
- *Variables are case-sensitive.*
- *Keywords are not allowed to use as variable names.*
### Valid Variable Names

```
name = "Alice"
_age = 19
student1 = "Kishore"
```

### Invalid Variable Names

```
1name = "Alice"     # Starts with a digit
class = "CSE"        # Keyword
student-name = "A"   # Hyphen not allowed
```
## Multi-Word variable names

*Variable names with more than one word can be difficult to read. There are several techniques used to make them more readable.*
#### 1.Camel Case
- *Each word(Except the 1st word),starts with a capital letter.*
- *Ex: myVariableName="Hello"*
#### 2.Pascal Case
- *Each word starts with a capital letter.*
- *Ex: MyVariableName="Hello*"
#### 3.Snake Case
- *Each word is separated by an undescore.*
- *Ex: my_variable_name="Hello"*

## Many values to multiple variables

 - *Python allows to assign values to multiple variables in one line.*
    *Ex: x, y, z=1, 4, 3*
- *Can assign the same value to multiple variables in one line.* 
	*Ex: x=y=z=1432*

**Note(Unpacking of Variables)**

*If you have a collection of values in a data structures like list, tuple etc. Python allows you to extract the values into variables. This is called Unpacking.*
Ex:
```
fruits=["apple", "Banana", "Cherry"]
x, y, z=fruits
print(x) #apple
print(y)  #Banana
print(z)  #Cherry

```
# Scope of Variables

- *Scope determines where in your program, a variable can be accessed or modified.*
- *Variables defined in one scope may not be visible in other scope.*
- *Python uses lexical scoping based on the source code structure.*

## The LEGB Rule

- *Understanding this rule is essential for debugging and writing maintainable code where variables can be accessed and how they are assigned.*
- *Python resolves variable names in this specific order:*
   1. Local Scope
   2. Enclosing Scope
   3. Global Scope
   4. Built-in Scope

#### 1.Local Scope
- *Variables that are declared inside a function.*
- *Can only be used within that function.*
- *Exists only while the function runs.*
Ex: 
```
 def greet():
	 name="Alice" #Variable inside a greet function
	 print("Hello",name)
 greet()    
```

#### 2.Enclosing Scope
- *Enclosing scope refers to variables defined in outer functions that contains nested functions.*
- *Inner functions can access varaibles from their enclosing(outer) functions.*
- *Enclosing is checked after local scope but before global scope.*
 Ex:
```
def outer():
    x=10 #x is in enclosing scope
    def inner():
        print("Inner:",x) #inner function can access 10
    
    inner()
    print("Outer:",x) #10
outer()
```

**[!NOTE]**
- *nonlocal keyword allows a nested (inner) function to update and modify a variable that belongs to its outer (enclosing) function.*
- *Without nonlocal keyword, assigning a value inside an inner function automatically creates a brand-new local variable, leaving the outer function's variable unchanged.*
Ex: 
```
def outer():
    x=10 #x is in enclosing scope
    def inner():
        nonlocal x #Declare x as nonlocal 
        x=20       #Assign new value on a seperate line
        print("Inner:",x) #20
    
    inner()
    print("Outer:",x) #20
outer()
```

#### 3.Global Scope
- *Declared outside any function.*
- *Can be used anywhere in the program(inside and outside functions).*
Ex: 
```
x=10  #global variable
def show():
    print("x inside function:",x) #10
show()
print("x outside function:",x) #10
```
- *Excessive use of global variables can make code harder to debug and maintain.*
**[!NOTE]**
*Use the global keyword to modify a global variable inside a function.*
Ex:
```
x=10
def show():
    global x
    x=5
    print("x inside function:",x) #5
show()
print("x outside function:",x) #5
```

#### 4.Built-in Scope
- *The built-in scope contains names that are pre-defined in python.*
```
#gives list of built-in functions  
import builtins  
print(dir(builtins)) #['ArithmeticError', 'AssertionError', 'AttributeError', 'BaseException', 'BaseExceptionGroup', 'BlockingIOError', 'BrokenPipeError', 'BufferError', 'BytesWarning', 'ChildProcessError', 'ConnectionAbortedError', 'ConnectionError', 'ConnectionRefusedError', 'ConnectionResetError', 'DeprecationWarning', 'EOFError', 'Ellipsis', 'EncodingWarning', 'EnvironmentError', 'Exception', 'ExceptionGroup', 'False', 'FileExistsError', 'FileNotFoundError', 'FloatingPointError', 'FutureWarning', 'GeneratorExit', 'IOError', 'ImportError', 'ImportWarning', 'IndentationError', 'IndexError', 'InterruptedError', 'IsADirectoryError', 'KeyError', 'KeyboardInterrupt', 'LookupError', 'MemoryError', 'ModuleNotFoundError', 'NameError', 'None', 'NotADirectoryError', 'NotImplemented', 'NotImplementedError', 'OSError', 'OverflowError', 'PendingDeprecationWarning', 'PermissionError', 'ProcessLookupError', 'PythonFinalizationError', 'RecursionError', 'ReferenceError', 'ResourceWarning', 'RuntimeError', 'RuntimeWarning', 'StopAsyncIteration', 'StopIteration', 'SyntaxError', 'SyntaxWarning', 'SystemError', 'SystemExit', 'TabError', 'TimeoutError', 'True', 'TypeError', 'UnboundLocalError', 'UnicodeDecodeError', 'UnicodeEncodeError', 'UnicodeError', 'UnicodeTranslateError', 'UnicodeWarning', 'UserWarning', 'ValueError', 'Warning', 'WindowsError', 'ZeroDivisionError', '_IncompleteInputError', '__build_class__', '__debug__', '__doc__', '__import__', '__loader__', '__name__', '__package__', '__spec__', 'abs', 'aiter', 'all', 'anext', 'any', 'ascii', 'bin', 'bool', 'breakpoint', 'bytearray', 'bytes', 'callable', 'chr', 'classmethod', 'compile', 'complex', 'copyright', 'credits', 'delattr', 'dict', 'dir', 'divmod', 'enumerate', 'eval', 'exec', 'exit', 'filter', 'float', 'format', 'frozenset', 'getattr', 'globals', 'hasattr', 'hash', 'help', 'hex', 'id', 'input', 'int', 'isinstance', 'issubclass', 'iter', 'len', 'license', 'list', 'locals', 'map', 'max', 'memoryview', 'min', 'next', 'object', 'oct', 'open', 'ord', 'pow', 'print', 'property', 'quit', 'range', 'repr', 'reversed', 'round', 'set', 'setattr', 'slice', 'sorted', 'staticmethod', 'str', 'sum', 'super', 'tuple', 'type', 'vars', 'zip']
```

## Key Takeaways

- *Variables store data in memory.*
- *Python is dynamically typed.*
- *Follow proper naming conventions.*
- *Prefer snake_case in Python.*
- *Multiple assignment and unpacking are supported.*
- *Scope determines where variables can be accessed.*
- *Python follows the LEGB Rule.*
- *Use `global` and `nonlocal` carefully.*
