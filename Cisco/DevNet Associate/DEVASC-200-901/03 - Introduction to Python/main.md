# Introduction to Python

## **Getting Started with Python**

&nbsp;

The 200-901 DevNet Associate DEVASC exam is not a Python test per se.  You will not be asked to answer esoteric questions about techniques and syntax that only a Python wizard would know.  The exam ensures that you are competent enough with PYthon to know how to interact with Cisco hardware through APIs and to use Cisco software development kits and frameworks such as pyATS and Genie.  It is a very good idea to continue learning Python and spend some time in either online courses or self-study via books focused on the Python language itself; you should also spend lots of time working through examples on DevNet at [developer.cisco.com](https://developer.cisco.com).  This chapter and the several that follow provide a crash course in functional Python to get you going with the basics you need for success on the exam.

&nbsp;

> **Note**
> From a community standpoint, the move to version 3 historically was slow to happen because many of the Python extensions (modules) were not updated to the newer version.  If you run across code for a 2.x version, you will find differences in syntax and commands (also known as the Python standard library) that will prevent that code from running under 3.x.  Python is not backward compatible without modifications.  In addition, many Python programs require additional modules that are installed to add functionality to Python that aren't available in the standard library.  If you have a program that was written for a specific module version, but you have the latest version of Python installed on your machine, the program might not work properly.  You will learn more about common Python modules and how to use them in Chapter 4, "Python Functions, Classes, and Modules."

&nbsp;

The use of Python 3 has changed drastically as support for the 2.x version ended in January 2020.  The 3.x version came out in 2008 and is the one that you should be using today.  Of course, this version issue is still a problem even within the 3.x train of Python and the corresponding modules you may want to use.  To address this compatibility conundrum across different versions and modules, Python virtual environments have been created.  Such an environment allows you to install a specific version of Python and packages to a separate directory structure.  This way, you can ensure that the right modules are loaded and your application doesn't break when you upgrade your base Python installation.  As of Python 3.3, there is native support for these virtual environments built into the Python distribution.  You can code in Python without using virtual environments, but the minute you update modules or Python itself, you run the risk of breaking your apps.  A virtual environment allows you to lock in the components and modules you use for your app into a single "package," which is a good practice for building Python apps.

&nbsp;

To use virtual environments, you launch Python 3 with the **-m** argument to run the **venv** module.  You need to supply a name for your virtual environment, which will also become the directory name that will include all the parts of your virtual environment.  Next, you need to activate the virtual environment by using the **source** command in Linux or Mac, as shown in this example.  On Windows, you will need to run the activate batch file.

&nbsp;

```
#  MacOS or Linux

python -m venv myvenv

source myvenv/bin/activate
```

&nbsp;

```
#  Windows

C:\py -3 -m venv myvenv

C:\myvenv\Scripts\activate.bat
```

&nbsp;

At this point, you will see your virtual environment name in parentheses at the beginning of your command prompt:

&nbsp;

```
(myvenv)$
```

&nbsp;

This indicates that you are running Python in your virtual environment.  If you close the terminal, you have to reactive the virtual environment if you want to run the code or add modules via **pip** (the Python module package manager).

&nbsp;

To turn off the virtual environment, just type **deactivate** at the command prompt, and your normal command prompt returns, indicating that you are using your local system Python setup and not the virtual environment.

&nbsp;

To install new modules for Python, you use **pip*, which pulls modules down from the PyPi repository.  The command to load new modules is as follows:

&nbsp;

<pre>
pip install <i>packagename</i>
</pre>

&nbsp;

where *packagename* is the name of the package or module you want to install.  You can go to [pypi.org](https://pypi.org) and search for interesting modules and check to see what others are using.  These modules extend Python functionality and contribute to its flexibility and heavy use today.

&nbsp;

The **pip** command also offers a search function that allows you to query the package index:

&nbsp;

```
pip search "search value"
```

&nbsp;

The output includes the name, version, and a brief description of what the package does.

&nbsp;

To install a specific version of a package, you can specify a version number or a minimum version so that you can get recent bug fixes:

&nbsp;

```
pip install package==1.1.1.     To install a specific version
pip install package>=1.0        To install a version greater than or equal to 1.0
```

&nbsp;

When you download sample code, if there are package dependencies, there is usually a readme file that lists these requirements.

&nbsp;

Using a requirements.txt file included with your code is another essential good practice.  Such a file makes it simpler to get your Python environment ready to go as quickly as possible.  If you have a requirements.txt file included with your code, it will give **pip** a set of packages that need to be installed, and you can issue this one command to get them loaded:

&nbsp;

```
pip install -r requirements.txt
```

&nbsp;

The requirements.txt file is just a list that maps Python package names to versions.  This is an example of what it looks like:

&nbsp;

```
ansible==2.6.3
black==19.3b0
flake8==3.7.7
genie==19.0.1
ipython==6.5.0
napalm==2.4.0
ncclient==0.6.3
netmiko==2.3.3
pyang==1.7.5
pyats==19.0
PyYAML==5.1
requests==2.21.0
urllib3==1.24.1
virlutils==0.8.4
xmltodict==0.12.0
```

&nbsp;

If you are building your own code and want to save the current modules configured in your virtual environment, you can use the **freeze** command and have it automatically populate the requirements.txt file:

&nbsp;

```
pip freeze > requirements.txt
```

&nbsp;

## **Understanding Python Syntax**

&nbsp;

The word *syntax* is often used to describe structure in a language, and in the case of programming syntax, is used in much the same way.  Some programming languages are very strict about how you code, which can make it challenging to get something written.  While Python is a looser language than some, it does have rules that should be followed to keep your code not only readable but functional.  Keep in mind that Python was built as a language to enhance code readability and named after Monty Python (the British comedy troop) because the original architects of PYthon wanted to keep it fun and uncluttered.  Python is best understood through its core philosophy (The Zen of Python):

-   Beautiful is better than ugly.
-   Explicit is better than implicit.
-   Simple is better than complex.
-   Complex is better than complicated.
-   Readability counts.

&nbsp;

Python is a scripted language, which means that any text editor can become a Python programming environment.  The easiest way to get started with some Python code is to just enter **python3** at the command prompt (assuming that Python 3 is installed, of course) and use the interactive interpreter:

&nbsp;

```
$ python 3

>>> print("Savannah rules!")

Savannah rules!
```

&nbsp;

One aspect in which Python is different from other languages is that within Python code, **whitespace matters**.  This can seem really weird and frustrating if you are coming from another language, such as Java or C, that use curly braces or start/stop keywords; instead, **Python uses indention to separate blocks of code**.  This whitespace is not used just to make your code readable; rather, Python will not work without it.  Here is an example of a simple loop that highlights why whitespace is so important:

&nbsp;

```
>>> for kids in ["Caleb", "Sydney", "Savannah"]:

... print("Clean your room,", kids, "!")                                            

    File "<stdin>", line 2

        print("Clean your room,", kids, "1")

        ^

    IndentationError:  expected an indented block
```

&nbsp;

This code will generate a syntax error the minute you try to run it.  Python is expecting to see indentation on the line after the **:**.  If you insert four spaces before the **print()** statement, the code works:

&nbsp;

```
>>> for kids in ["Caleb", "Sydney", "Savannah"]:

...     print("Clean your room," kids, "!")

...

Clean your room, Caleb !

Clean your room, Sydney !

Clean your room, Savannah !
```

&nbsp;

Python allows you to use space sor tabs.  You can use both spaces and tabs in Python 2, but Python 3 will return a syntax error:  however, if you use both tabs and spaces, you might end up with really weird issues that you need to troubleshoot.  The standard for Python from the PEP 8 style guide is to use four spaces or indentation before each block of code.  Why four spaces?  Won't one space work?  Yes, it will, but your code blocks will be hard to align, and you will end up having to do extra work.

The alignment issue becomes especially important when you nest loops and conditional statements, as each loop needs to correspond to another block of code, indented using spaces.  Many text editors allow you to view whitespace, and some even give you a visual indication of what is in a code block.

&nbsp;

Comments in PYthon are created by enter # or a string of three quotation marks (either single or double quotation marks).  One very important good practice when coding is to write a description of what is happening in code that is not obvious.  You probably will not want to write a comment for a simple **print** statement, but describing the output of a nested function would be useful for anyone who needs to make additions to your code in the future or to remind yourself why you did what you did during that late night caffeine-fueled coding session.  The # is used to comment out a single line so the Python interpreter ignores it.  Here is an example:

&nbsp;

```
#get input from user in numeric format
```

&nbsp;

The triple quote method is used to comment multiple lines and can be helpful when you want to provide a bit more context than what you can fit on a single line of text.  Here is an example:

&nbsp;

```
'''  This is 
     line 2
     and line 3 '''
```

&nbsp;

## **Data Types and Variables**

&nbsp;

You can insert various types of data into a variable, and Python supports many types natively.  Python can also be expanded with modules to support even more variables.  A variable is really just a label that maps to a Python object stored somewhere in memory.  Without variables, your program would not be able to easily identify these objects, and your code would be a mess of memory locations.

&nbsp;

### **Variables**

&nbsp;

Python auto types a variable, and you can reassign that same variable to another value of a different type in the future.  You just need to remember the rules for variable names:

-   A variable name must start with a letter or the underscore character.
-   A variable name cannot start with a number.
-   A variable name can only consist of alphanumeric characters and underscore (A-Z, 0-9, and _).
-   A variable name is case sensitive (so Value and value are two different variable names).

&nbsp;

To assign a variable you just set the variable name equal to the value you want, as shown in these examples:

| Variable | Type |
| -- | -- |
| Pip = "cat" | Variable assigned to a string |
| Age = 9 | Variable assigned to an integer |
| Chill = True | Variable assigned to a Boolean |
| Variable1 = Variable2 | Variable assigned to another Variable |

&nbsp;

### **Data Types**

&nbsp;

Everything in Python is an object, and depending on the type of object, there are certain characteristics that you must be aware of when trying to determine the correct action you can perform on them.  In Python, whenever you create an object, you are assigning that object an ID that Python uses to recall what is being stored.  This mechanism is used to point to the memory location of the object in question and allows you to perform actions on it, such as printing its value.  When the object is created, it is assigned a type that does not change.  This type is tied to the object and determines whether it is a string, an integer, or another class.

Within these types, you are allowed to either change the object (mutable) or are not allowed to change the object (immutable) after it has been created.  This doesn't mean that variables are not able to be changed; it means that most of the basic data types are not able to be modified but need to be replaced (or *assigned*, in Python speak) with another value.  You can't just add a character at the end of a string value, for example.  You have to instead reassign the whole string if you want to change it.  This mutable/immutable concept will make more sense as you interact with various data types in programs.  Python treats these two types of objects differently, and each has nuances that you must work around as you build your Python programs.  To make it simple, think of immutable objects as ones that you want to stay the same, such as constants.  Mutable objects, on the other hand, are objects that you will be adding elements to and subtracting from on a regular basis.

Common data are listed below.  The rest of this section covers them in more detail.

&nbsp;

| Name | Type | Mutable | Description |
| -- | -- | -- | -- |
| Integer | int | No | Whole numbers, such as 6,600, and 1589 |
| Boolean | bool | No | Comparison value, either True or False |
| String | str | No | Sequence of characters delimited by quotes, such as "Cisco", 'Piper', and "2000" |
| List | list | Yes | Ordered sequence of objects, such as [10, "DNA, 19.8] |
| Tuple | tup | No | Ordered sequence of immutable objects, such as (10, "DNA", 19.8) |
| Dictionary | dict | Yes | Unordered key:value pairs, such as {"key1":"value1","name":"Pip"} |
| Set | set | Yes | Unordered collection of unique objects, such as {"a","b"} |

&nbsp;

### **Integers, Floating Point, and Complex Numbers**

&nbsp;

The integers and floating point number are the simplest of data types:

-   **Integers**:  Whole numbers without decimal points
-   **Floating point**:  Numbers with decimal points or exponents (such as 10e5, which indicates 10 to the fifth power)

&nbsp;

Python can perform advanced calculations, so it is used heavily in data science, and many features are built into the language and can be easily added with modules.  For our purposes, though, the basic building blocks will suffice.  Python has a simple set of built-in operators for working with numbers, much like the operators on a regular calculator.  Below is a list of Python's numeric operators.

&nbsp;

| Operator | Description | Example | Evaluates to |
| -- | -- | -- | -- |
| + | Adds two expressions together | 5 + 5 | 10 |
| - | Subtracts one expression from another | 35 - 15 | 20 |
| * | Multiplies two expressions | 10 * 10 | 100 |
| / | Divides one expression by another | 20 / 5 | 4 |
| // | Performs integer division (leaving off the remainder) | 30 // 7 | 4 |
| % | Performs modulus division (printing the remainder only) | 30 % 7 | 2 |
| ** | indicates an exponent | 2 ** 8 | 256 |

&nbsp;

When working with numbers in Python, a defined order of precedence must be observed in calculations.  Python uses the following order (also known as PEMDAS):

-   **Parentheses**:  Parentheses are always evaluated first.
-   **Power**:  The exponent is evaluated.
-   **Multiplication**:  Any multiplication is performed.
-   **Division**:  Division is evaluated.
-   **Addition**:  Addition is performed.
-   **Subtraction**:  Subtraction is performed.
-   **Left to right**:  After PEMDAS, anything else (such as **sqrt()** or other math functions) is evaluated from left to right.

&nbsp;

In most languages, the parenthesis are preferred over anything else.  Most Python programmers use them liberally in their math formulas to make them simpler to construct without being so strict with the rules.  Take the following example:

&nbsp;

```
>>> 5 * 6 - 1

29
```

&nbsp;

Python evaluates the multiplication first and then subtracts 1 from the result.  If you wanted the subtraction to happen first, you could simply add parentheses around the parts you want evaluated:

&nbsp;

```
>>> 5 * (6 - 1)

25
```

&nbsp;

A floating point number is just a whole number with a decimal point.  When you divide in Python, you often get a remainder that is displayed as a floating point number, as in this example:

&nbsp;

```
>>> 10 / 7 

1.4285714285714286
```

&nbsp;

If you just want to see whole numbers, you can use integer division and lop off the remainder, as shown here:

&nbsp;

```
>>> 10 // 7 

1
```

&nbsp;

Likewise, if you are only interested in the remainder, you can have modulus division show you what is left over:

&nbsp;

```
>>> 10 % 7

3
```

&nbsp;

You have the option to use other base systems instead of just the default base 10.  You have three choices in addition to base 10: binary (base 2), octal (base 8), and hex (base 16).  You need to use prefixes before integers in order for Python to understand that you are using a different base:

-   0b or 0B for binary
-   0o or 0O for octal
-   0x or 0X for hex

&nbsp;

From Python's perspective, these are still just integers, and if you type any of them into the interpreter, it will return the decimal value by default, as shown in this example:

&nbsp;

```
>>> 0xbadbeef

195935983
```

&nbsp;

You can also convert back and forth by using the base keyword in front of the value you want to exchange, as in these examples:

&nbsp;

```
>>> hex(195935983)

'0xbadbeef'
```

&nbsp;

```
>>> bin(195935983)

'0b1011101011011011111011101111'
```

&nbsp;

### **Booleans**

&nbsp;

A Boolean has only two possible values, **True** and **False**.  You use comparison operators to evaluate between two Boolean objects in PYthon.  This data type is the foundation for constructing condition steps and decisions within programs.  Below shows the various Boolean comparison operators and some examples of how to use them.

&nbsp;

| Operator | What It Does | Example | Evaluates to |
| -- | -- | -- | -- |
| < | Less than | 5 < 10 | True |
| > | Greater than | 6.5 > 3.5 | True |
| <= | Less than or equal to | 0 <= -5 | False |
| >= | Greater than or equal to | 6 >= 6 | True |
| == | Equal to | 5 == "5 | False |
| != | Not equal to | 5 != "5 | True |

&nbsp;

### **Strings** 

&nbsp;

The string data type is a sequence of characters and use quotes to determine which characters are included.  The string '**Hello**' is just a set of characters that Python stores in order from left to right.  Even if a string containers a series of numbers, it can still be a string data type.  IF you try to add a 1 to a string value, Python gives you an error as show in this example:

&nbsp;

```
>>> '10' + 1

Traceback (most recent call last):

    File "<stdin>", line 1, in <module>

TypeError:  can only concatenate str (not "int") to str
```

&nbsp;

This error tells you that you have to convert the string to an integer or another data type to be able to use it as a number (in a math formula, for example).

&nbsp;

The **int()** function can convert a string value into an integer for you, as shown in this example:

&nbsp;

```
>>> int('10)' + 1

11
```

&nbsp;

A string is just a list of characters in a certain order that Python keeps track of.  In fact, this aspect of strings makes them easy to manipulate.  If you use the string '**DevNet**', you can pull out any individual characters of the string by knowing where it sits in the string index.  One thing to keep in mind is that indexes in Python always start with 0, so if you want the very first character in a string, your index value would be 0 and not 1.  

&nbsp;

If you assign the string DevNet to a variable, you can separate and manipulate the component values of the string by using the index value.  You can use brackets to specific the index number.  The following example prints a capitol **D** from **DevNet**:

&nbsp;

```
>>> a = 'DevNet'

>>> a[0]

'D'
```

&nbsp;

You can also specify ranges to print.  The colon operator gives you control over whole sections of a string.  The first number is the beginning of the slice, and the second number determines the end.  The second number may be confusing at first because it is intended to identify "up to but not including" thte last character.  Consider this example:

&nbsp;


```
>>> a[0:3]

'Dev'
```

&nbsp;

This example shows a **3** at the end, but this is technically four characters since the index starts at 0, but Python doesn't print the last character and instead stops right before it.  For new Python programmers, this can be confusing, but remember that Python is literal.  If you think of an index value as a box, you want to stop at box 3 (but don't want to open the box).  If you want to print the whole string, just pick a number beyond the index value and Python will print everything, as in this example:

&nbsp;

```
>>> a[0:6]

'DevNet'
```

&nbsp;

If you omit a value for the first number, Python starts at 0, as in this example:

&nbsp;

```
>>> a[:2]

'De'
```

&nbsp;

If you omit hte second value, Python prints to the end of the string, as in this example:

&nbsp;

```
>>> a[2:]

'vNet'
```

&nbsp;

You can also reverse directions by using negative numbers.  If you put a negative first number, you start from the end of the string, as in this example:

&nbsp;

```
>>> a[-2:]

'et'
```

&nbsp;

A negative value on the other side of the colon causes Python to print using the end as a reference point, as in this example:

&nbsp;

```
>>> a[:-2]

'DevN'
```

&nbsp;

You can perform math operations on strings as well.  The + is used to add or concatenate two strings together, as in this example:

&nbsp;

```
>>> 'DevNet' + 'Rocks'

'DevNetRocks'
```

&nbsp;

Multiplication works as we, as in this example:

&nbsp;

```
>>> 'DevNet Rocks ' * 5

'DevNet Rocks DevNet Rocks DevNet Rocks DevNet Rocks DevNet Rocks '
```

&nbsp;

There is a tremendous amount of string manipulation you can do with Python, and there are a number of built-in methods in the standard string library.  These methods are called with a dot after the variable name for a string.  Below lists some commonly used string manipulation methods, including the syntax used for each and what each method does.

&nbsp;

| Method | What It Does |
| -- | -- |
| **str.capitalize()** | Capitalize the string |
| **str.center(width[, fillchar])** | Center justify the string |
| **str.endwith(suffix[, start[, end]])** | Add an ending string to the string |
| **str.find(sub[, start[, end]])** | Find the index position of the characters in a string |
| **str.lstrip([chars])** | Remove whitespace characters from the end of the string |
| **str.replace(old, new[, count])** | Replace characters in the string |
| **str.lower()** | Make the string all lowercase |
| **str.rstrip([chars])** | Strip whitespace characters from the front of the string |
| **str.strip([chars])** | Remove whitespace characters from the beginning and end of the string |
| **str.upper()** | Make the string all uppercase |

&nbsp;

### **Lists**

&nbsp;

Python, unlike other programming languages, such as C++ and Java, doesn't have arrays.  If you want to store a bunch of values, you can use a list.  You can use a variable to store a collection of lists in a list.  To create a list, you assigned the contents of the list to a variable with the **=** and **[]** and separate the items with commas, as in this example:

&nbsp;

```
>>> kids = ['Caleb', 'Sydney', 'Savannah']

>>> kids

['Caleb', 'Sydney', 'Savannah']
```

&nbsp;

A list can contain a Python object, such as integers, strings, and even other lists.  A list can also be empty and is often initialized in an empty state for programs that pull data from other sources.  To initialize a list in an empty state, you just assign two brackets with nothing in them or you can use the built-in **list()** function:

&nbsp;

```
emptylist = []
emptylist = list()
```

&nbsp;

Lists are similar to strings in that each is a set of items indexed by Python that you can interact with and slice and dice.  To pull out values, you just use the variable name with brackets and the index number, which starts at 0, as in this example:

&nbsp;

```
>>> print(kids[1])

Sydney
```

&nbsp;

Unlike strings, lists are mutable objects, which means you can change parts of the list at will.  With a string, you can't change parts of the string without creating a new string.  This is not the case with lists, where you have a number of ways to make changes.  If you have a misspelling, for example, you can change just one element of the list, leaving the rest untouched, as in this example:

&nbsp;

```
>>> kids

['Caleb', Sidney', 'Savannah']

>>> kids[1]='Sydney'

>>> kids

['Caleb', 'Sydney', 'Savannah']
>>>
```

&nbsp;

You can concatenate lists as well by using the + operator to join two lists together.  The list items do not need to be unique.  Python just connects the two together into a new list, as shown in the following example:

&nbsp;

```
>>> a = [1, 2, 4]

>>> b = [4, 5, 6]

>>> c = a + b

>>> print(c)

[1, 2, 4, 4, 5, 6]
```

&nbsp;

Remember all of the slicing you saw with the strings?  The same principles apply here, but instead of having a single string with each letter being in a bucket, the elements in the list are the items in the bucket.  Don't forget the rule about the second number after hte colon, which means "up to but not including."  Here is an example:

&nbsp;

```
>>> c = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

>>> c[1:4]

[2, 3, 4]

>>> c[:-4]

[1, 2, 3, 4, 5, 6]

>>> c[:]

[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```

&nbsp;

Below describes some of the most common list methods.

*Note:  Below you replace the word **list** before the **.** with the name of your list.*

&nbsp;

| Method | What It Does |
| -- | -- |
| list.append(element)  | Adds an element to the end of the list |
| list.clear() | Removes everything from the list |
| list.copy(alist) | Returns a copy of the list |
| list.count(element) | Shows the number of elements with the specified value |
| list.extend(alist) | Adds the elements of a list to the end of the current list |
| list.index() | Returns the index number of the first element with a specified value |
| list.insert(index, element) | Adds an element tat a specified index value |
| list.pop(index) | Remove an element at a specific index position, or if no index position is provided, removes the last item from the list |
| list.remove() | Removes a list item with a specified value |
| list.reverse() | Reverses the list order |
| list.sort() | Sorts the list alphabetically and/or numerically |

&nbsp;

### **Tuples**

&nbsp;

Tuples and lists are very similar.  The biggest difference between the two comes down to mutability.  As discussed earlier, Python data types are either mutable ro immutable.  Lists are mutable, and tuples are immutable.  So why would you need these two types if they are so similar?  It all comes down to how Python accesses objects and data in memory.  When you have a lot of changes occurring, a mutable data structure is preferred because you don't have to create a new object every time you need to store different values.  When you have a value that is constant and referenced in multiple parts of a program, an immutable data type (such as a tuple), is more memory efficient and easier to debug.  You don't want some other part of your program to make changes to a crucial piece of data stored in a mutable data type.

&nbsp;

To create a tuple, you use parentheses instead of brackets.  You can use the **type()** function to identify a Python data type you have created.  Here is an example.

&nbsp;

```
>>> person = (2012, 'Mike', 'CCNA')

>>> person

(2012, 'Mike', 'CCNA')

>>> type(person)

<class 'tuple'>
```

&nbsp;

You access data in a tuple the same way as in a list - by using brackets and the index value of the item in the tuple that you want to return:

&nbsp;

```
>>> person[0]

2012
```

&nbsp;

What you can't do with a tuple is make an assignment to the values:

&nbsp;

```
>>> person[0]=15

Traceback (most recent call last):

    File "<stdin>" ,line 1, in <module>

TypeError:  'tuple' object does not support item assignment
```

&nbsp;

Tuples can, however, be used to assign a set of variables quickly:

&nbsp;

```
>>> (a, b, c) = (12, 'Fred', 18)

>>> c

18
```

&nbsp;

### **Dictionaries**

&nbsp;

A dictionary provides another way of creating a collection of items.  Why do you need another way of storing data when you already have lists and tuples?  A list is an ordered set of items tracked by an index.  What if you need to access data that is tied to a certain value, such as a person's name?  This capability is exactly why you need dictionaries in Python.  A dictionary saves a ton of effort by giving you a built-in system for storing data in a key:value pair.  Dictionaries don't have any defined order; all you need is the key - and not some index number - to get access to your data.  There are some rules regarding dictionaries.

-   **Keys**:  A dictionary's keys are limited to only using immutable values (int, float, bool, str, tuple, and so on).  No, you can't use a list as a key, but you can use a tuple, which means you could use a tuple as a key (immutable) but you can't use a list as a key (mutable).
-   **Values**:  A value can be any Python object or any combination of objects.

&nbsp;

To create a dictionary, you use braces and your key and value separated by a colon.  You separate multiple items with commas.  Here's an example:

&nbsp;

```
>>> cabinet = { "scores": (98, 76, 95), "name":"Chris", "company":"Cisco" }

>>> type(cabinet)

<class 'dict'>
```

&nbsp;

Instead of using an index, you use the key, as shown in this example:

&nbsp;

```
>>> cabinet["scores"]

(98, 76, 95)

>>> cabinet["company"]

'Cisco'
```

&nbsp;

To add more items to a dictionary, you can assign them with a new key.  You can even add another dictionary to your existing dictionary, as shown in this example:

&nbsp;

```
>>> cabinet["address"] = {"street":"123 Anywhere Dr", "city":"Franklin", "state":"TN"}

>>> cabinet["address"]

{'street': '123 Anywhere Dr', 'city':'Franklin', 'state':'TN'}
```

&nbsp;

### **Sets**

&nbsp;

A set in Python consists of an unordered grouping of data and is defined by using the curly braces of a dictionary, without the key:value pairs.  Sets are mutable, and you can add and remove items from the set.  You can create a special case of sets called a frozen set that makes the set immutable.  A frozen set is often used as the source of keys in a dictionary (which have to be immutable); it basically creates a template for the dictionary structure.  If you are familiar with how sets work in mathematics, the various operations you can perform on mutable sets in Python will make logical sense.  To define a set, do the following:

&nbsp;

```
>>> numbs = {1, 2, 4, 5, 6, 8, 10}

>>> odds = {1, 3, 5, 7, 9}
```

&nbsp;

To check that these are indeed sets, use the **type()** function:

&nbsp;

```
>>> type(odds)

<class 'set'>
```

&nbsp;

To join two sets (just as in a mathematical join), you can use the | operator to show a combined set with no duplicates:

&nbsp;

```
>>> numbs | odds

{1, 2, 3, 4, 5, 6, 7, 8, 9, 10}
```

&nbsp;

You can get an intersection of two sets and show what numbers are in both by using the **&** operator:

&nbsp;

```
>>> numbers & odds

{1, 5}
```

&nbsp;

There are many ways to evaluate sets, and the Python documentation can be used to explore them all.  In addition, Python has library collections that give even more options for ways to store data.  Search the Python documentation for "collections" and take a look at ordered dictionaries, named tuples, and other variations that may suit your data collecting needs.  For the purpose of the DEVASC exam, though, you do not need to know data structures beyond the basic types discussed here.

&nbsp;

## **Input and Output**

&nbsp;

Input and output pretty much defines what a computer does for you.  In Python, the **input()** function and the **print()** function are two essential components that allow you to create interactive applications.  In this section, you will learn how to leverage these powerful functions in your applications.

&nbsp;

### **Getting Input from the User**

&nbsp;

Python has the **input()** function to get information from a user running your Python code.  The user is asked a question, and the program waits until the user types a response.  It really is as simple as that.  The **input()** function takes the characters that are entered and automatically stores them as a string data type, regardless of what the user enters.  Here is an example:

&nbsp;

```
>>> inpt = input('Type your name: ')

Type your name:  Chris Jackson

>>> inpt

'Chris Jackson'
```

&nbsp;

You assign a variable (in this case, **inpt**) to the **input()** function with a text prompt so that the user knows what is expected.  That variable now holds the string the user typed.  What if you need to get an integer or a floating point number?  Since Python stores every input as a string, you need to do a conversion on the data supplied.  Here is an example:

&nbsp;

```
>>> inpt = float(input('What is the Temperature in F: '))

What is the Temperature in F: 83.5

>>> inpt

83.5
```

&nbsp;

To make sure the variable holds the correct type, you used the **input()** function inside the **float()** function to convert the string into a floating point number.

&nbsp;

### **The Mighty print() Function**

&nbsp;

The **print()** function provides output that can be displayed in the user's terminal.  Just like every other function in Python, it is called with parentheses.  This function is usually the gateway into writing your first code in Python, as in this example:

&nbsp;

```
>>> print('Hello World')

Hello World
```

&nbsp;

Every line printed with the **print()** function includes a newline character (**\\n**) at the end, which is a special character that tells the terminal to advance one line.  If you use the **\\n** sequence within the **print()** string, it is interpreted as a new line, as shown in this example:

&nbsp;

```
>>> print('Hello\nWorld')

Hello

World
```

&nbsp;

There are numerous codes like this that can control how text is displayed in a string and how Python interprets the output.  Without them, you would not be able to use, for example, a backslash in your text output.  Here are a few of the most common ones:

-   \\\\:  Backslash
-   \b:  Backspace
-   \\':  Single quote
-   \\":  Double quote
-   \t:  Tab
-   \r:  Carriage return

&nbsp;

You can add multiple arguments to the **print*()** function by using commas between elements.  This is very useful in creating meaningful text, and the **print()** function also handles concatenation for the different data types automatically.  Consider this example:

&nbsp;

```
>>> print('Numbers in set', 1, ':', numbs)

Numbers in set 1 : {1, 2, 4, 5, 6, 8, 10}
```

&nbsp;

By default, the **print()** function uses a separator between elements.  This is normally not an issue if you want spaces to appear between words or elements.  In the previous example, you can see a space between the **1** and the **:** that just doesn't look good.  You can fix it by changing the separator that the **print()** function uses with the **sep=''** attribute (using single quotes with nothing between them).  Since you will be removing all automatic spacing, you have to compensate for this by adding spaces in your actual text if you need them.  Remember that separators come between elements and don't add anything to the start or end of the **print()** function.  Consider this example:

&nbsp;

```
>>> print('NUmbers in set ', 1, ': ', numbs, sep='')

Numbers in set 1: {1, 2, 4, 5, 6, 8, 10}
```

&nbsp;

One capability added to Python 3.6 and up is the addition of f-string formatting.  Not only are these strings easier to read and less prone to syntax errors, but they allow you to write formatting code a lot faster.  To create an f-string, you put an **f** at the beginning of a string, within the **print()** function, to let Python know what you are doing, and then you can use **{}** within your string to insert values or other functions.  Here is an example:

&nbsp;

```
>>> name = 'Piper'

>>> name2 = 'Chris'

>>> print(f'{name2} says Hi to {name}!')

Chris says Hi to Piper!
```

&nbsp;

##  **Flow Control with Conditionals and Loops**

&nbsp;

So far you have been exposed to many of the building blocks of the Python language.  The real power of a programming language is in the mechanisms you can use to embed logic and respond to different conditions by changing the flow of operation.  Python has three primary control statements:

-   **if**:  Any **if** statement is a conditional statement that can compare values and make branching decisions.
-   **for**:  A **for** loop is a counting loop that can iterate through data a specific number of times.
-   **while**:  The **while** loop can iterate forever when certain conditions are met.

&nbsp;

### **If Statements**

&nbsp;

An **if** statement starts with an **if** and then sets up a comparison to determine the truth of the statement it is evaluating and ending with a **:** to tell PYthon to expect the clause (the action if the the condition is true) block of code next.  As mentioned earlier in this chapter, whitespace indenting matters very much in Python.  The clause of an **if** statement must be indented (four spaces is the standard) from the beginning of the **if** statement.  The following example looks for a condition where the variable **n** is equal to **20** and prints a message to the console indicating that the number is indeed a 20:

&nbsp;

```
>>> n = 20
>>> if n == 20:
...     print('The number is 20')
...
The number is 20
```

&nbsp;

The Python interpreter uses three dots to let you continue the clause for the **if** statement.  Notice that there is a space between the start of the dots and the **print()** statement.  Without these four spaces, Python would spit back a syntax error like this:

&nbsp;

```
>>> if n == 20:
... print('oops')

    File "<stdin>", line 2
        print('oops')
        ^
    IndentationError:  expected an indented block
```

&nbsp;

The goal of an **if** statement is to determine the "truth" of the element under evaluation.  This is a Boolean logic, meaning that the operators evaluate True or False.  The previous example is determining whether a variable is equal to a specific integer.  What if the number is different?  You might want to apply other logic by asking more questions.  This is where else if (**elif** in Python) comes into play.

An **if** statement can have as many **elif** conditions as you want to add to the condition check.  Good coding practices recommend simplification, but there is no real limit to how many you add.  Here is an example that uses two **elif** conditionals:

&nbsp;

```
>>> n = 3

>>> if n == 17:
...     print('Number is 17')
... elif n < 10:
...     print('Number is less than 10')
... elif n > 10:
...     print('Number is greater than 10')
...

Number is less than 10
```

&nbsp;

Since each **if** and **elif** statement does something only if the condition identified is true, it may be helpful to have a default condition that handles situations where none of the **if** or **elif** statements are true.  For this purpose, you can assign a single **else** statement at the end, as shown below:

&nbsp;

```
score = int(input('What was your test score?:'))

if score >= 90:
    print('Grade is A')
elif score >= 80:
    print('Grade is B')
elif score >= 70:
    print('Grade is C')
elif score >= 60:
    print('Grade is D')
else:
    print('Grade is F')

What was your test score?:53
Grade is F
```

&nbsp;

###  **For Loops**

&nbsp;

The **for** statement allows you to create a loop that continues to iterate through the code a specific number of times.  It is also referred to as a counting loop and can work through a sequence of items, such as a list or other data object.  The **for** loop is heavily used to parse through data and is likely to be your go-to tool for working with data sets.  A **for** loop starts with the **for** statement, followed by a variable name (which is a placeholder used to hold each sequence of data), the **in** keyword, some data set to iterate through, and then finally a closing colon, as shown in this example:

&nbsp;

```
>>> dataset = (1,2,3,4,5)

>>> for variable in dataset:
...     print(Variable)
...
1
2
3
4
5
```

&nbsp;

The **for** loop continues through each item in the data set, and in this example, it prints each item.  You can also use the **range()** function to iterate a specific number of times.  The **range** function can take arguments that let you choose what number it starts with or stops on and how it steps through each one.  Here is an example:

&nbsp;

```
>>> for x in range(3):
...     print(x)
...
0
1
2
```

&nbsp;

By default, if you just give **range()** a number, it starts at 0 and goes by 1s until it reaches the number you provided.  Zero is a valid iteration, but if you don't want it, you can start at 1.  Consider this example:

&nbsp;

```
>>> for x in range(1,3):
...     print(x)
...
1
2
```

&nbsp;

To change the increment from the default to 1, you can add a third attribute to the **range()** statement.  In the follow example, you start at 1 and increment by 3 until you reach 10:

&nbsp;

```
>>> for x in range(1,11,3):
...     print(x)
...
1
4
7
10
```

&nbsp;

Remember that these ranges are up to and not including the final number you specify.  If you want to go all the way to the 10 in this example, you still need to set your range to 11.

&nbsp;

### **While Loops**

&nbsp;

Whereas the **for** loop counts through data, the **while** loop is a conditional loop, and the evaluation of the condition (as in **if** statements) being true is what determines how many times the loop executes.  This difference is huge in that it means you can specify a loop that could conceivably go on forever, as long as the loop condition is still true.  You can use **else** with a **while** loop.  An **else** statement after a **while** loop executes when the condition for the **while** loop to continue is no longer met.  Below shows a **count** and an **else** statement.

&nbsp;

```
>>> count = 1
>>> while (count < 5):
...     print("Loop count is:", count)
...     count = count +1
... else:
...     print("loop is finished")
...
Loop count is: 1
Loop count is: 2
Loop count is: 3
Loop count is: 4
Loop count is finished
```

&nbsp;

You can probably see similarities between this and the **for** loop.  The difference is that the **for** loop was built to count, whereas this example uses an external variable to determine how many times the loop iterates.  In order to build some logic into the **while** loop, you can use the **break** statement to exit the loop.  Below shows a **break** with **if** statements in an infinite **while** loop.

&nbsp;

```
while True:
    string = input('Enter some text to print.  \nType "done" to quite')
    if string == 'done':
        break
    print(string)
print('Done!')

Enter some text to print.
Type "done" to quite>  Good luck on the test!
Good luck on the test!
Enter some text to print
Type "done to quite> done
Done!
```

&nbsp;

Notice the condition this example is checking with the **while** statement.  Because **True** will always be **True** from an evaluation perspective, the **while** condition is automatically met.  Without that **if** statement looking for the string **'done'**, your loop would keep asking for input and printing what you typed forever.

&nbsp;

This chapter provides an overview of some of the key concepts and capabilities in Python.  The goal is to prepare you to be able to read and understand code snippets that you might see on the DEVASC exam.  The next two chapters dive into other aspects of working with Python and Cisco APIs that are considered essential skills.  Make sure you have followed along with the code examples here and that you are familiar with how to construct these basic examples.  The following chapters build on these skills.