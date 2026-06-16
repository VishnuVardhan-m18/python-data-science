## 📚Table of Contents

* [Input Function](#input--function)

* [Print Function](#print--function)

  * [Sep Parameter](#sep-parameter-in-print-)

  * [End Parameter](#end-parameter-in-print-)

  * [Escape Sequence Characters](#escape-sequence-characters)

* [Python Data Types](#python-data-types)

  * [Numeric Types](#1-numeric-types)

  * [Text Type](#2-text-type)

  * [Sequence Types](#3-sequence-types)

  * [Set Types](#4-set-types)

  * [Mapping Type](#5-mapping-type)

  * [Boolean Type](#6-boolean-type)

  * [Binary Types](#7-binary-types)

    * [bytes](#bytes)

    * [bytearray](#bytearray)

    * [memoryview](#memoryview)

  * [None Type](#8-none-type)

* [Type Conversions](#type-conversions)

  * [Implicit Type Conversion](#1-implicit-type-conversion)

  * [Explicit Type Conversion](#2-explicit-type-conversion)

* [Type Function](#type--function)

* [ID Function](#id--function)

* [isinstance Function](#isinstance--function)

* [Key Takeaways](#key-takeaways)

# input( ) Function
 
*The function which is used to take input from the user is called the `input()` function in Python.*  
### Syntax  
```python  
variable = input("Enter a value: ")
```  
### Example  
```python  
x = input("Enter the Number:")

print(x)       #25
print(type(x)) #<class 'str'>
``` 

> *Note: `input()` returns data as a string (`str`) by default.*  

### Custom input( ) Function
```Python
x=int(input("Enter x:"))
y=float(input("Enter y:"))
print(type(x)) #<class 'int'>
print(type(y)) #<class 'float'>
```

---
# print( ) Function

- *The function which is used to display output on the screen is called the  `print()` function.*
### Syntax  
```Python
#For single value
print(object)
#For mulptiple values
print(object1,object2)
```

### Example 
```Python
name="Hello"
age=19
print(name)    #Hello
print(name,age)#Hello 19 (Python automatically inserts a space between the values)
```

### Sep parameter in print( )

- *The sep parameter specifies the separator between multiple values. By default, it is a space.*
### Example 
```Python
print("16","06","2026",sep="-") #16-06-2026
```

### End parameter in print( )

- *The end parameter is used to specify what to print at end of the execution of the print() function . By default it is set to a new line character(\n).*
### Example 
```Python
print("Welcome",end=" ")
print("to Kaggle")

#output: Welcome to Kaggle
```

### Escape Sequence Characters
```Python
print("Hello World")  #Hello World
print('Hello\nWorld')  #Hello
                       #World
print("Hello\tWorld")  #Hello	World
print("Hello\aWorld")  #Bell Sound
print("Hello\\World")  #Hello\World
print("\"Hello World\"")  #"Hello World"
print("Hello\bWorld")  #HellWorld (Backspace Character)
print("Hello\vWorld")  #Vertical Tab
print("\'Hello World\'") #'Hello World'
```
---
# Python Data Types  
  
*In Python, data types define the kind of value a variable can hold.*  
  
## 1. Numeric Types  

*Used for storing numeric values.*  
### `int`  
*Integers without decimal points.* 
  
```python  
x = 10  
```  

### `float`  
*Numbers with decimal points.*  
  
```python  
y = 3.14  
```  

### `complex`  
*Numbers with a real and imaginary part.*  

```python  
z = 2 + 3j  
```  
  
---  
## 2. Text Type  

*Used for handling textual data.*  
### `str`  
A sequence of Unicode characters.  
  
```python  
name = "Alice"  
```  
  
---   
## 3. Sequence Types 

*Used for storing ordered collections of items.*  
### `list`  
*Mutable, ordered collection.* 
  
```python  
numbers = [1, 2, 3, 4]  
```  
  
You can change, add, or remove elements.  

### `tuple`  
Immutable, ordered collection.  
  
```python  
coordinates = (10, 20)  
```  
  
### `range`  
*Sequence of numbers. *
  
```python  
r = range(stop) -> range(5)   # 0 to 4
r = range(start,stop) -> range(2,8) # 2 to 7  by default start is 0
r = range(start,stop,step) -> range(1,10,2) # 1,3,5,7,9  by default step is 1
```  
  
---  
## 4. Set Types  
  
*Used for storing unordered collections of unique items. *
### `set`  
Mutable, unordered collection with no duplicates.  
  
```python  
s = {1, 3, 2}  
```  

### `frozenset`  
*Immutable version of a set. *
  
```python  
s = frozenset({1, 3, 2})  
```  
  
---   
## 5. Mapping Type  
  
*Used for key-value pairs.*
### `dict`  
Stores data in key-value pairs.  
  
```python  
student = {  
    "name": "John",  
    "age": 20  
}  
```  
  
---  
## 6. Boolean Type  
  
*Used for logical values. *
### `bool`  
Represents `True` or `False`.  
  
```python  
x = True  
```  
  
---  
## 7. Binary Types  
  
*Used for handling binary data.*(`Data Handling`)
### `bytes`  
- *bytes is an **immutable** sequence of integers in the range **0 to 255**.* 
- *A binary version of a string, but each element is a number not a character* .
  
```python  
b = b"hello"
print(b[0])       #104
print(b[0:4])     #b'hell'
print(type(b[0:4])) #<class 'bytes'>
```  

**Note: **** 
- *Slicing returns bytes.*
- *Creates a copy.(`Python creates a new object in memory`)*

**`bytes Methods`**
- *Since byte is immutable, its methods return a new bytes object.*
- *byte methods works with bytes values, not regular strings.*
```Python
b = b"python"

print(b.upper())      # b'PYTHON'
print(b.lower())      # b'python'
print(b.replace(b"py", b"my"))   # b"mython"
print(b.split(b"t"))   # [b'py', b'hon']
# b.replace("p", "P")   # Error
b.replace(b"p", b"P")   # Correct
```

### `bytearray`  
- *Mutable(Editable) version of bytes.*
- *bytearray is a sequence of integers where each integer must be in the range 0 t0 255.*

```Python
ba= bytearray(b"hello")  #[104, 101, 108, 108, 111]
ba[0] = 72  # In ASCII value 72=H

print(ba) #bytearray(b'Hello')
print(ba[0:3])  #bytearray(b'Hel')
print(type(ba[0:3])) #<class 'bytearray'>
```

**Note: **
- Slicing returns bytearray.
- Creates a copy.(`Python creates a new object in memory`)*

**`bytearray Methods`**
- bytearray has many methods similar to bytes.
```Python
ba = bytearray(b"python")

ba.append(33)        # adds !
print(ba)            # bytearray(b'python!')

ba.extend(b"123")
print(ba)           # bytearray(b'python!123')

ba.remove(49)       # removes byte value 49 -> ASCII '1'
print(ba)

ba[1:4]=b"143"
print(ba)          #bytearray(b'p143on!23')
```
### `memoryview`  
- *memoryview gives a **view of the memory** of another binary object without copying it.*
- *It is a powerful tool for working with large binary data efficiently.*
- `memoryview` can wrap:
     - `bytes`
     - `bytearray`
    - some other buffer-compatible objects
```Python
ba = bytearray(b"hello")
mv = memoryview(ba)
print(mv)        # <memory at 0x7c7d11275f00>(Does not copy the object)
print(mv[0])     # 104 (ASCII of 'h')
mv[0] = 72
print(ba)        # bytearray(b'Hello')
print(type(mv))  # <class 'memoryview'>

#A slice of a memoryview returns another **memoryview**.
print(mv[0:3])  # <memory at 0x7f2207306380>
#To see the actual data
print(mv[0:3].tobytes()) # b'hel'
```

**Note: **
- *Slicing returns memoryview.*
- *Doesn't creates a copy(No new binary data is created.)*
- *Only a new "window" into the same memory is created.*

`memoryview Methods`
- mv.tobytes()
- mv.tolist()
- mv.release()
---  
## 8. None Type  
  
*Represents the absence of a value or a null value. *
  
```python  
x = None  
```  
  
---  

# Type Conversions  
  
*Changing from one data type to another data type is called Type Casting `or` Type Conversion.*  

*Python supports two types of type conversions:*  
## 1. Implicit Type Conversion  
  
*Python automatically converts a smaller data type to a larger one during operations.*  
  
  ### *Example*  
  
```python  
a = 5  
b = 2.0  
  
result = a + b  
  
print(result)  
print(type(result))  
```  
  
*Output:*  
  
```python  
7.0  
<class 'float'>  
```  
  
*Because:*  
  
```python  
int + float = float  
```  
  
## 2. Explicit Type Conversion  
  
*Manually converting data types using built-in functions.*  

| Function  | Description              | Example                                       |     |
| --------- | ------------------------ | --------------------------------------------- | --- |
| `int()`   | *Converts to integer*    | `int(3.6) -> 3`                             |     |
| `float()` | *Converts to float*      | `float(5) -> 5.0`                           |     |
| `str()`   | *Converts to string*     | `str(143) -> "143"`                         |     |
| `bool()`  | *Converts to boolean*    | `bool(0) -> False`                          |     |
| `list()`  | *Converts to list*       | `list("abc") -> ['a','b','c']`              |     |
| `tuple()` | *Converts to tuple*      | `tuple([1,2]) -> (1,2)`                     |     |
| `set()`   | *Converts to set*        | `set([1,2,2]) -> {1,2}`                     |     |
| `dict()`  | *Converts to dictionary* | `dict([(1,'a'),(2,'b')]) -> {1:'a', 2:'b'}` |     |
  
### Example  
  
```python  
x = "143"  
  
y = int(x)  
z = float(y)  
  
print(z)  
```  
### Number Representation Functions  
  
```python  
a = 20  
  
print(bin(a))   # 0b10100  
print(hex(a))   # 0x14  
print(oct(a))   # 0o24  
```

### Additional Examples  
  
```python  
a = "1001"  
print(int(a, 2))     # Binary to Decimal  
  
b = "12"  
print(int(b))        # String to Integer  
  
c = "A1"  
print(int(c, 16))    # Hexadecimal to Decimal  
```  
  
---  

# type( ) Function

- *A built-in function which is used to know the data type of a variable is called `type` function.*
- Tells **what type** an object is.
**`Syntax`**

`type(variable_name)`

**Example**
```Python
x=143
y="Greetings"
print(type(x)) # <class 'int'>
print(type(y)) # <class 'str'>
```

---
# id( ) Function

- *A built-in function that returns a unique identifier for every  object in memory.*
- *This identifier helps in understanding how objects are stored and referenced in memory.*
- *Tells **which object** it is (its identity in memory).*
- *Returns an integer representing the unique identity of the object.*
`Syntax`

`id(object)`

**Example**
```Python
a=10
b=5
print(id(a)) # 140701137235792
print(id(b)) # 140701137234382
```

> Note: *The output values may differ from system to system.*

---
# isinstance( ) Function

- *A built-in function which is  used to check if an object (variable) belongs to a specific data type or class.*
- *It is highly recommended for type-checking in Python because it supports **inheritance**—meaning it will return `True` if the object is an instance of a subclass as well.*
- *Returns **`True`** if the object is an instance of the specified type(s).*
- *Returns **`False`** otherwise.*
**`Syntax`**

`isinstance(object, classinfo)`

**Example**
```Python
x="Hello"
print(isinstance(x,str)) # True

account_balance=12
print(isinstance(account_balance, int)) # True 
print(isinstance(account_balance, str)) # False
```

- *The `isinstance()` function also allows us to check for multiple types at once.*
- *If you pass a tuple of types to `classinfo`, `isinstance()` will return `True` if the object matches **any** of the types in that tuple.*
- Here is an example checking if `account_balance` is an `int` or `float`:

```python
account_balance = 12
isinstance(account_balance, (int, float)) # True
```

# Key Takeaways

- *input() always returns a string.*
- *print() is used for output.*
- *bytes → immutable.*
- *bytearray → mutable.*
- *memoryview → no copy.*
- *type() tells what type an object is.*
- *id() tells which object it is.*
- *isinstance() checks object type.*
- *Type conversion can be implicit or explicit.*
