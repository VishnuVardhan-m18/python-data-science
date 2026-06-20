
# 📚Table of Contents

- *[Strings](#strings)*
- *[in Operator](#in-operator)*
- *[len( ) Function](#len--function)*
- *[String Operations](#string-operations)*
  - *[Concatenation(`+`)](#concatenation)*
    - *[str( ) Function](#str--function)*
    - *[repr( ) Function](#repr--function)*
    - *[eval( ) Function](#eval--function)*
  - *[Repetition(`*`)](#repetition)*
- *[String Interpolation](#string-interpolation)*
  - *[String Format](#string-format)*
    - *[f-strings](#f-strings)*
    - *[format( ) Method](#format--method)*
    - *[% formatting](#-formatting)*
- *[String Indexing](#string-indexing)*
- *[String Slicing](#string-slicing)*
- *[String Methods](#string-methods)*
  - *[Essential and Frequently used methods](#essential-and-frequently-used-methods)*
    - *[lower( ) Method](#lower--method)*
    - *[upper( ) Method](#upper--method)*
    - *[capitalize( ) Method](#capitalize--method)*
    - *[title( ) Method](#title--method)*
    - *[swapcase( ) Method](#swapcase--method)*
    - *[strip( ) Method](#strip--method)*
    - *[lstrip( ) Method](#lstrip--method)*
    - *[rstrip( ) Method](#rstrip--method)*
    - *[split( ) Method](#split--method)*
    - *[join( ) Method](#join--method)*
    - *[replace( ) Method](#replace--method)*
    - *[find( ) Method](#find--method)*
    - *[rfind( ) Method](#rfind--method)*
    - *[index( ) Method](#index--method)*
    - *[rindex( ) Method](#rindex--method)*
    - *[startswith( ) Method](#startswith--method)*
    - *[endswith( ) Method](#endswith--method)*
    - *[count( ) Method](#count--method)*
  - *[Useful for Conditions and Validations](#useful-for-conditions-and-validations)*
    - *[isalnum( ) Method](#isalnum--method)*
    - *[isalpha( ) Method](#isalpha--method)*
    - *[isdigit( ) Method](#isdigit--method)*
    - *[isnumeric( ) Method](#isnumeric--method)*
    - *[isdecimal( ) Method](#isdecimal--method)*
    - *[islower( ) Method](#islower--method)*
    - *[isupper( ) Method](#isupper--method)*
    - *[isspace( ) Method](#isspace--method)*
    - *[istitle( ) Method](#istitle--method)*
    - *[isascii( ) Method](#isascii--method)*
    - *[isidentifier( ) Method](#isidentifier--method)*
    - *[isprintable( ) Method](#isprintable--method)*
  - *[Helpful in Special Cases](#helpful-in-special-cases)*
    - *[center( ) Method](#center--method)*
    - *[ljust( ) Method](#ljust--method)*
    - *[rjust( ) Method](#rjust--method)*
    - *[partition( ) Method](#partition--method)*
    - *[rpartition( ) Method](#rpartition--method)*
    - *[splitlines( ) Method](#splitlines--method)*
    - *[zfill( ) Method](#zfill--method)*
    - *[encode( ) Method](#encode--method)*
    - *[maketrans( ) Method](#maketrans--method)*
    - *[translate( ) Method](#translate--method)*
    - *[expandtabs( ) Method](#expandtabs--method)*
  - *[Rarely used methods](#rarely-used-methods)*
    - *[casefold( ) Method](#casefold--method)*
    - *[format_map( ) Method](#format_map--method)*
- *[String Methods Quick Access Table](#string-methods-quick-access-table)*

  
# Strings

- *A string in python is a sequence of characters enclosed in quotes. It can include letters, numbers, symbols and spaces.*
- *Python allows us to create strings using*
     1. *Single Quotes -> `'.....'`   
     **Example:**
     `my_str1 = 'Hello'`
     2. *Double Quotes-> `"....."`   
     **Example:**
     `my_str2 = "Hello"`
     3. *Triple Quotes   -> `'''.....'''`  or `"""....."""`    (For multiline strings)*
     **Example:**
     `my_str3 = '''multiline string'''`
- *If the string contains either single or double quotation marks, then: *
     - *If the string contains single quotes, use double quotes to wrap the string and vice versa.*
     **Example:**
     `my_str1 = "It's Mine"`
     `my_str2 = 'I said, "Hello!"'`
     - *Escape the single or double quotation mark in the string with a backslash (`\`).*
     **Example:**
     `my_str1 = 'It\'s Mine'`
     `my_str2 = "I said, \"Hello!\""`
- *Strings in python are immutable, meaning you cannot change characters in place.*
**Example:**
  ```Python
  s = "Hello"
  s[0]="h" # This will raise an error
  s = "hello"
  print(s) # hello
  ```

---
# in Operator

*A boolean operator that specifies whether the character or characters exist in string or not.*
**Example:**
```Python
greeting = "Hello World!"  
print("Hello" in greeting) # True
print('Hello' in greeting) # True
print("hi" in greeting)    # False
print("wood" in greeting)  # False
print("!" in greeting)     # True
```

---
# len( ) Function

*A built-in function which is used to get the length of a string is called len( ) function.*
**Example:**
```Python
msg1 = "HelloWorld"
print(len(msg1)) # 10
msg2 = "Hello World!"
print(len(msg2)) # 12
msg3 = " Hello World!"
print(len(msg3)) # 13
```

--- 
# String Operations

### Concatenation(`+`):
*The Process of combing multiple strings together with the plus (`+`) operator is called string concatenation.*
**Example:**
```Python

#msg1 and msg2 are string data types. This + works with string data types only.
msg1 = "Hello"
msg2 = "my❤️world!"
print(msg1+' '+msg2) # Hello my❤️world!
```

> [!NOTE] 
> *Trying to concatenate a string with a number, result in `TypeError'.*
> **Example:**
> ```Python
> name = "Marcus"
> age = 31
> print(name+age) # TypeError: can only concatenate str (not "int") to str
> ```

#### str( ) Function:
*A built-in function which returns the string representation of the given object without modifying the original object.*(Readable output)
**Syntax**
`str(variable_name)`
**Example:**
```Python
name = "Marcus"
age = 31
print(name+str(age)) # Marcus31
greeting = "Hello\nWorld"
print(str(greeting))   #Hello
                       #World
print(type(str(greeting))) # <class 'str'>
```

*`str()` returns the **readable / user-friendly string representation** of an object.*

#### repr( ) Function:

*A built-in function which returns the exact(``Developer``) string representation of the given object.*
**Syntax**
`repr(variable_name)`

**Example:**
```Python
greeting = "Hello\nWorld"
print(repr(greeting)) # 'Hello\nWorld'
print(type(repr(greeting))) # <class 'str'>
```

*`repr()` is very useful for debugging the strings.*

#### eval( ) Function:

*A built-in function that is used to evaluate  a string as a python expression and return the result.*
i.e
- *If a string contains a **number**, `eval()` can convert it into a number.*
- *If a string contains a **mathematical expression**, `eval()` can calculate it.*
- *If a string contains a valid **Python expression**, `eval()` will execute/evaluate it and give the result.*
**Syntax**
`eval(expression)`

**Example:**
```Python
s="10+20"
ans=eval(s)
print(ans,type(ans)) # 30 <class 'int'>
H1=input()       # 12
H2=eval(input()) # 12
print(type(H1),type(H2)) # <class 'str'> <class 'int'>
```

***`eval()` is generally avoided for user input.***
### Repetition(`*`):
*The process of repeating a string multiple times with the mutlipy(`*`) operator is called string repetition.*
**Example**:
```Python
msg = "I Love You"
print(msg*3) # I Love YouI Love YouI Love You
print(' '.join(msg*3)) # I   L o v e   Y o u I   L o v e   Y o u I   L o v e   Y o u (this joins characters)
print(' '.join([msg]*3)) # I Love You I Love You I Love You
print(' '.join([msg*3])) # I Love YouI Love YouI Love You
```

---
# String Interpolation 

- *The process of inserting variables and expressions into a string is called string interpolation.*
- *Python has a category of string called **f-strings** (short for formatted string literals), which allows you to handle interpolation with a compact and readable syntax.*
#### String Format:
- *Strings, numbers and symbols are combined by using `f-strings` or `format()` method.*
##### f-strings:
 *F-strings start with `f` (either lowercase or uppercase) before the quotes, and allow you to embed variables or expressions inside replacement fields indicated by curly braces or placeholders(`{}`).*

**Example:**
```Python
name = "Alice"
age = 21
print(f"My name is {name} and I am {age} years old") #my name is Alice and I am 21 years old
```

##### format( ) Method:
*Variable names are passed in format() method at end.*

**Example:**
```Python
name = 'Alice'
age = 21
print("My name is {} and I am {} years old".format(name,age)) # My name is Alice and I am 21 years old
```

##### `%` formatting:
*String formatting is done by using format specifiers.*

**Example:**
```Python
name = "Alice"
age = 21
print("My name is %s and I am %d years old"%(name,age)) # My name is Alice and I am 21 years old
```

---
# String Indexing

1.*String indexing in Python is the process of accessing individual characters of a string using index numbers.*
2.*Indexing starts from 0.*
3.*Negative indexing starts from -1(from an end).*
**Example:**
```Python
s = 'Python'
```
*This string contains 6 characters*

| **Character**         | **P** | **y** | **t** | **h** | **o** | **n** |
| --------------------- | ----- | ----- | ----- | ----- | ----- | ----- |
| **Positive<br>Index** | 0     | 1     | 2     | 3     | 4     | 5     |
| **Negative<br>Index** | -6    | -5    | -4    | -3    | -2    | -1    |
4.*Individual characters from a string can be accessed using `[ ]`.*

**Syntax**
`String_name[index/position]`

**Example:**
```Python
s = 'Python'
print(s[0]) # first character : P 
print(s[1]) # second character : y 
print(s[2]) # third character : t
print(s[3]) # fourth character : h
print(s[-1]) # last character : n
print(s[-2]) # second last : o
print(s[10]) # IndexError
```

> [!NOTE] 
> *Indexing a string does not modify the original string.*
> ```Python
> s = 'Python'
> print(s[4]) # o
> print(s) # Python
> ```

---
# String Slicing

1.*String slicing in python is the process of the extracting a portion of string/range of characters or work with only specific part of the string.*
**Syntax**
`String_name[start:stop:step]`
Where
- *start -> index where slicing begins (start is included)*
- *end -> index where slicing stops (stop is excluded)*
- step -> to specify the increment between each index in the slice

**Example:**
```Python
my_str = "Hello World"
print(my_str[1:4]) # ell
print(my_str[:7])  # Python assumes start as 0 : Hello W
print(my_str[8:])  # Python assumes end as end of the string : rld
print(my_str[:])  # Hello world
print(my_str[0:11:2]) # Hlowrd
print(my_str[::-1]) # dlrow olleH
```

> [!NOTE] 
> *Slicing a string does not modify the original string.*
> ```Python
my_str = 'Hello world'
print(my_str[8:])  # rld
print(my_str)  # Hello world
> ```

---
# String Methods

### Essential and Frequently used methods
#### `lower( )` Method:

_Returns a new string by converting all uppercase characters of the string into lowercase._
**Syntax**  
`string_name.lower()`

**Example:**
```Python
text = "HELLO World"
print(text.lower()) # hello world
```
---
#### `upper( )` Method:

_Returns a new string by converting all lowercase characters of the string into uppercase._
**Syntax**  
`string_name.upper()`

**Example:**
```Python
text = "hello World"
print(text.upper()) # HELLO WORLD
```
---
#### `capitalize( )` Method:

_Returns a new string by converting only the first character of the string into uppercase and the remaining characters into lowercase._
**Syntax**  
`string_name.capitalize()`

**Example:**
```Python
text = "python PROGRAMMING"
print(text.capitalize()) # Python programming
```
---
#### `title( )` Method:

_Returns a new string by converting the first character of each word into uppercase._
**Syntax**  
`string_name.title()`

**Example:**
```Python
text = "python programming language"
print(text.title()) # Python Programming Language
```
---
#### `swapcase( )` Method:

_Returns a new string by converting uppercase letters into lowercase and lowercase letters into uppercase._
**Syntax**  
`string_name.swapcase()`

**Example:**
```Python
text = "PyThOn"
print(text.swapcase()) # pYtHoN
```
---
#### `strip( )` Method:

_Returns a new string after removing leading and trailing whitespaces._
**Syntax**  
`string_name.strip()`

**Example:**
```Python
text = "   Hello World   "
print(text.strip()) # Hello World
```
---
#### `lstrip( )` Method:

_Returns a new string after removing leading (left side) whitespaces._
**Syntax**  
`string_name.lstrip()`

**Example:**
```Python
text = "   Hello"
print(text.lstrip()) # Hello
```
---
#### `rstrip( )` Method:

_Returns a new string after removing trailing (right side) whitespaces._
**Syntax**  
`string_name.rstrip()`

**Example:**
```Python
text = "Hello   "
print(text.rstrip()) # Hello
```
---
#### `split( )` Method:

_Splits the string at the specified separator and returns a list of substrings._
**Syntax**  
`string_name.split("separator")`

**Example:**
```Python
text = "apple,banana,mango"
print(text.split(",")) # ['apple', 'banana', 'mango']
```

**Example with default separator (space):**
```Python
text = "I love Python"
print(text.split()) # ['I', 'love', 'Python']
```
---
#### `join( )` Method:

_Joins elements of an iterable (like list or tuple) into a single string using the given separator._
**Syntax**  
`separator.join(iterable)`

**Example:**
```Python
words = ["I", "love", "Python"]
print(" ".join(words)) # I love Python
print("-".join(words)) # I-love-Python
```
---
#### `replace( )` Method:

_Returns a new string in which all occurrences of the specified old value are replaced with the new value._
**Syntax**  
`string_name.replace(old, new)`

**Example:**
```Python
text = "I like Java"
print(text.replace("Java", "Python")) # I like Python
```
---
#### `find( )` Method:

_Returns the index of the first occurrence of the specified substring. If the substring is not found, it returns `-1`._
**Syntax**  
`string_name.find(substring)`

**Example:**
```Python
text = "Hello World"
print(text.find("World")) # 6
print(text.find("Python")) # -1
```
---
#### `rfind( )` Method:

_Returns the index of the last occurrence of the specified substring. If the substring is not found, it returns `-1`._

**Syntax**  
`string_name.rfind(substring)`

**Example:**
```Python
text = "one two one three"
print(text.rfind("one")) # 8
print(text.rfind("four")) # -1
```
---
#### `index( )` Method:

_Returns the index of the first occurrence of the specified substring. If the substring is not found, it raises a `ValueError`._
**Syntax**  
`string_name.index(substring)`

**Example:**
```Python
text = "Hello World"
print(text.index("World")) # 6
```

**Example if substring is not found:**
```Python
text = "Hello"
print(text.index("z")) # ValueError
```
---
#### `rindex( )` Method:

_Returns the index of the last occurrence of the specified substring. If the substring is not found, it raises a `ValueError`._
**Syntax**  
`string_name.rindex(substring)`

**Example:**
```Python
text = "one two one"
print(text.rindex("one")) # 8
```

**Example if substring is not found:**
```Python
text = "Hello" 
print(text.rindex("z")) # ValueError
```
---
#### `startswith( )` Method:

_Returns `True` if the string starts with the specified substring, otherwise returns `False`._
**Syntax**  
`string_name.startswith(substring)`

**Example:**
```Python
text = "Python is easy"
print(text.startswith("Python")) # True
print(text.startswith("Java")) # False
```
---
#### `endswith( )` Method:

_Returns `True` if the string ends with the specified substring, otherwise returns `False`._

**Syntax**  
`string_name.endswith(substring)`

**Example:**
```Python
text = "notes.txt"
print(text.endswith(".txt")) # True
print(text.endswith(".pdf")) # False
```
---
#### `count( )` Method:

_Returns the number of times the specified substring occurs in the string._
**Syntax**  
`string_name.count(substring)`

**Example:**
```Python
text = "apple apple banana apple"
print(text.count("apple")) # 3
```


---

### Useful for Conditions and Validations

#### `isalnum( )` Method:

_Returns `True` if all characters in the string are alphanumeric (letters or digits) and the string is not empty._
**Syntax**  
`string_name.isalnum()`

**Example:**
```Python
print("Python123".isalnum()) # True
print("Python 123".isalnum()) # False
print("abc@123".isalnum()) # False
```
---
#### `isalpha( )` Method:

_Returns `True` if all characters in the string are alphabetic letters and the string is not empty._
**Syntax**  
`string_name.isalpha()`

**Example:**
```Python
print("Python".isalpha()) # True
print("Python123".isalpha()) # False
print("Hello World".isalpha()) # False
```
---
#### `isdigit( )` Method:

_Returns `True` if all characters in the string are digits and the string is not empty._
**Syntax**  
`string_name.isdigit()`

**Example:**
```Python
print("12345".isdigit()) # True
print("12a45".isdigit()) # False
print("12.5".isdigit()) # False
```
---
#### `isnumeric( )` Method:

_Returns `True` if all characters in the string are numeric characters and the string is not empty._
**Syntax**  
`string_name.isnumeric()`

**Example:**
```Python
print("123".isnumeric()) # True
print("12.5".isnumeric()) # False
print("abc".isnumeric()) # False
```

> [!NOTE]  
> _`isnumeric()` is similar to `isdigit()`, but it can also recognize some special numeric Unicode characters._

---
#### `isdecimal( )` Method:

_Returns `True` if all characters in the string are decimal characters and the string is not empty._
**Syntax**  
`string_name.isdecimal()`

**Example:**
```Python
print("123".isdecimal()) # True
print("12.5".isdecimal()) # False
print("abc".isdecimal()) # False
```
---
#### `islower( )` Method:

_Returns `True` if all alphabetic characters in the string are lowercase and the string contains at least one alphabetic character._
**Syntax**  
`string_name.islower()`

**Example:**
```Python
print("hello".islower()) # True
print("Hello".islower()) # False
print("hello123".islower()) # True
```
---
#### `isupper( )` Method:

_Returns `True` if all alphabetic characters in the string are uppercase and the string contains at least one alphabetic character._
**Syntax**  
`string_name.isupper()`

**Example:**
```Python
print("HELLO".isupper()) # True
print("Hello".isupper()) # False
print("HELLO123".isupper()) # True
```
---
#### `isspace( )` Method:

_Returns `True` if all characters in the string are whitespace characters and the string is not empty._

**Syntax**  
`string_name.isspace()`

**Example:**
```Python
print("   ".isspace()) # True
print("\n\t".isspace()) # True
print(" a ".isspace()) # False
```
---
#### `istitle( )` Method:

_Returns `True` if the string follows title case rules, i.e., the first character of each word is uppercase and the remaining characters are lowercase._
**Syntax**  
`string_name.istitle()`

**Example:**
```Python
print("Python Programming".istitle()) # True
print("python Programming".istitle()) # False
```
---
#### `isascii( )` Method:

_Returns `True` if all characters in the string are ASCII characters._
**Syntax**  
`string.isascii()`

**Example:**
```Python
print("Hello123".isascii()) # True
print("😊".isascii()) # False
```
---
#### `isidentifier( )` Method:

_Returns `True` if the string is a valid Python identifier (valid variable name), otherwise returns `False`._
**Syntax**  
`string_name.isidentifier()`

**Example:**
```Python
print("student_name".isidentifier()) # True
print("_value1".isidentifier()) # True
print("123name".isidentifier()) # False
print("my name".isidentifier()) # False
```
---
#### `isprintable( )` Method:

_Returns `True` if all characters in the string are printable characters._
**Syntax**  
`string_name.isprintable()`

**Example:**
```Python
print("Hello123".isprintable()) # True
print("Hello\nWorld".isprintable()) # False
```

---

### Helpful in Special Cases

#### `center( )` Method:

_Returns a centered string of the specified width. By default, spaces are used for padding._

**Syntax**  
`string_name.center(width, fillchar)`

**Example:**
```Python
text = "Python"print(text.center(12)) #    Python   
print(text.center(12, "-")) # ---Python---
```
---
#### `ljust( )` Method:

_Returns a left-justified string of the specified width. Extra spaces or given fill character are added on the right side._
**Syntax**  
`string_name.ljust(width, fillchar)`

**Example:**
```Python
text = "Hi"
print(text.ljust(6)) # Hi      .    
print(text.ljust(6, "*")) # Hi****
```
---
#### `rjust( )` Method:

_Returns a right-justified string of the specified width. Extra spaces or given fill character are added on the left side._
**Syntax**  
`string_name.rjust(width, fillchar)`

**Example:**
```Python
text = "Hi"
print(text.rjust(6)) #     Hi
print(text.rjust(6, "*")) # ****Hi
```
---
#### `partition( )` Method:

_Splits the string into 3 parts using the first occurrence of the given separator and returns a tuple: `(before_separator, separator, after_separator)`._
**Syntax**  
`string_name.partition(separator)`

**Example:**
```Python
text = "apple-banana-mango"
print(text.partition("-")) # ('apple', '-', 'banana-mango')
```
---
#### `rpartition( )` Method:

_Splits the string into 3 parts using the last occurrence of the given separator and returns a tuple._
**Syntax**  
`string_name.rpartition(separator)`

**Example:**
```Python
text = "apple-banana-mango"
print(text.rpartition("-")) # ('apple-banana', '-', 'mango')
```
---
#### `splitlines( )` Method:

_Splits the string at line breaks and returns a list of lines._
**Syntax**  
`string_name.splitlines()`

**Example:**
```Python
text = "Hello\nWorld\nPython"
print(text.splitlines()) # ['Hello', 'World', 'Python']
```
---
#### `zfill( )` Method:

_Returns a new string by adding zeros (`0`) at the beginning until the string reaches the specified width._
**Syntax**  
`string_name.zfill(width)`

**Example:**
```Python
num = "45"
print(num.zfill(5)) # 00045
```
---
#### `encode( )` Method:

_Returns an encoded version of the string in bytes format using the specified encoding._
**Syntax**  
`string_name.encode(encoding)`

**Example:**
```Python
text = "Hello"
print(text.encode()) # b'Hello'
print(text.encode("utf-8")) # b'Hello'
```
---
#### `maketrans( )` Method:

_Returns a translation table that can be used with the `translate()` method._
**Syntax**  
`str.maketrans(x, y)`

**Example:**
```Python
table = str.maketrans("abc", "123")
print(table) # {97: 49, 98: 50, 99: 51}
```
---
#### `translate( )` Method:

_Returns a new string where characters are replaced according to the translation table created by `maketrans()`._
**Syntax**  
`string_name.translate(table)`

**Example:**
```Python
table = str.maketrans("abc", "123")
text = "apple cab"
print(text.translate(table)) # 1pple 312
```
---
#### `expandtabs( )` Method:

_Returns a new string by replacing each tab character (`\t`) with spaces. By default, one tab is replaced with 8 spaces, but we can change it using `tabsize`._
**Syntax**  
`string_name.expandtabs(tabsize)`

**Example:**
```Python
text = "A\tB\tC"
print(text.expandtabs())    # A       B       C
print(text.expandtabs(4))   # A   B   C
```

---

### Rarely used methods

#### `casefold( )` Method:

_Returns a more aggressive lowercase version of the string than `lower()`. It is mainly used for case-insensitive comparisons._
**Syntax**  
`string_name.casefold()`

**Example:**
```Python
text1 = "HELLO"
text2 = "hello"
print(text1.casefold() == text2.casefold()) # True
```
---
#### `format_map( )` Method:

_Works like `format()` but takes a dictionary directly and replaces placeholders with values from that dictionary._

**Syntax**  
`string_name.format_map(mapping)`

**Example:**
```Python
data = {"name": "Alice", "age": 21}
text = "My name is {name} and I am {age} years old"
print(text.format_map(data)) # My name is Alice and I am 21 years old
```

---
# String Methods Quick Access Table

| Method           | Purpose / What it does                                  | Example                                     | Output                 |
| ---------------- | ------------------------------------------------------- | ------------------------------------------- | ---------------------- |
| `lower()`        | Converts all characters to lowercase                    | `"HELLO".lower()`                           | `'hello'`              |
| `upper()`        | Converts all characters to uppercase                    | `"hello".upper()`                           | `'HELLO'`              |
| `capitalize()`   | Makes first character uppercase and rest lowercase      | `"python programming".capitalize()`         | `'Python programming'` |
| `title()`        | Makes first letter of each word uppercase               | `"python programming".title()`              | `'Python Programming'` |
| `swapcase()`     | Swaps uppercase to lowercase and lowercase to uppercase | `"PyThOn".swapcase()`                       | `'pYtHoN'`             |
| `strip()`        | Removes spaces from both ends                           | `" hello ".strip()`                         | `'hello'`              |
| `lstrip()`       | Removes spaces from left side                           | `" hello".lstrip()`                         | `'hello'`              |
| `rstrip()`       | Removes spaces from right side                          | `"hello ".rstrip()`                         | `'hello'`              |
| `split()`        | Splits string into a list using separator               | `"a,b,c".split(",")`                        | `['a', 'b', 'c']`      |
| `join()`         | Joins iterable items into one string                    | `"-".join(["a","b","c"])`                   | `'a-b-c'`              |
| `replace()`      | Replaces old substring with new substring               | `"I like Java".replace("Java","Python")`    | `'I like Python'`      |
| `find()`         | Returns first index of substring, `-1` if not found     | `"Hello World".find("World")`               | `6`                    |
| `rfind()`        | Returns last index of substring, `-1` if not found      | `"one two one".rfind("one")`                | `8`                    |
| `index()`        | Returns first index of substring, error if not found    | `"Hello World".index("World")`              | `6`                    |
| `rindex()`       | Returns last index of substring, error if not found     | `"one two one".rindex("one")`               | `8`                    |
| `startswith()`   | Checks whether string starts with given substring       | `"Python".startswith("Py")`                 | `True`                 |
| `endswith()`     | Checks whether string ends with given substring         | `"notes.txt".endswith(".txt")`              | `True`                 |
| `count()`        | Counts occurrences of substring                         | `"apple apple".count("apple")`              | `2`                    |
| `isalnum()`      | Checks if all characters are letters or digits          | `"Python123".isalnum()`                     | `True`                 |
| `isalpha()`      | Checks if all characters are alphabets only             | `"Python".isalpha()`                        | `True`                 |
| `isdigit()`      | Checks if all characters are digits                     | `"12345".isdigit()`                         | `True`                 |
| `isnumeric()`    | Checks if all characters are numeric                    | `"123".isnumeric()`                         | `True`                 |
| `isdecimal()`    | Checks if all characters are decimal characters         | `"123".isdecimal()`                         | `True`                 |
| `islower()`      | Checks if all letters are lowercase                     | `"hello".islower()`                         | `True`                 |
| `isupper()`      | Checks if all letters are uppercase                     | `"HELLO".isupper()`                         | `True`                 |
| `isspace()`      | Checks if all characters are whitespace                 | `" ".isspace()`                             | `True`                 |
| `istitle()`      | Checks if string is in title case                       | `"Python Programming".istitle()`            | `True`                 |
| `isascii()`      | Checks if all characters are ASCII                      | `"Hello123".isascii()`                      | `True`                 |
| `isidentifier()` | Checks if string is a valid Python identifier           | `"student_name".isidentifier()`             | `True`                 |
| `isprintable()`  | Checks if all characters are printable                  | `"Hello123".isprintable()`                  | `True`                 |
| `center()`       | Centers string in given width                           | `"Python".center(10, "-")`                  | `'--Python--'`         |
| `ljust()`        | Left aligns string in given width                       | `"Hi".ljust(5, "*")`                        | `'Hi***'`              |
| `rjust()`        | Right aligns string in given width                      | `"Hi".rjust(5, "*")`                        | `'***Hi'`              |
| `partition()`    | Splits into 3 parts using first separator               | `"a-b-c".partition("-")`                    | `('a', '-', 'b-c')`    |
| `rpartition()`   | Splits into 3 parts using last separator                | `"a-b-c".rpartition("-")`                   | `('a-b', '-', 'c')`    |
| `splitlines()`   | Splits string at line breaks                            | `"a\nb\nc".splitlines()`                    | `['a', 'b', 'c']`      |
| `zfill()`        | Adds zeros at beginning until width is reached          | `"45".zfill(5)`                             | `'00045'`              |
| `encode()`       | Converts string to bytes                                | `"Hello".encode()`                          | `b'Hello'`             |
| `maketrans()`    | Creates translation table for `translate()`             | `str.maketrans("abc","123")`                | translation table      |
| `translate()`    | Replaces characters using translation table             | `"apple".translate(str.maketrans("a","1"))` | `'1pple'`              |
| `expandtabs()`   | Replaces tab `\t` with spaces                           | `"A\tB".expandtabs(4)`                      | `'A B'`                |
| `casefold()`     | Strong lowercase conversion for comparison              | `"HELLO".casefold()`                        | `'hello'`              |
| `format_map()`   | Formats string using dictionary values                  | `"{name}".format_map({"name":"Alice"})`     | `'Alice'`              |
