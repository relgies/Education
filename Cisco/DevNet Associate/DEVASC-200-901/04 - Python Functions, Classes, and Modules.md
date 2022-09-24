# Python Functions, Classes, and Modules

## Do I Know This Already?

&nbsp;

-   Which of the following is the correct syntax for a Python Function?
    -   define function (arg):
    -   function function(arg):
    -   def function(arg):
    -   func function(arg):

&nbsp;

-   Which of the following is a valid Python function name?
    -   1function
    -   __init__
    -   True
    -   Funct1on

&nbsp;

-   When three single quotation marks are used on the next line directly after defining a function, what does this indicate?
    -   Multi-line text
    -   A docstring
    -   A string value including double or single quotation marks
    -   None of the above

&nbsp;

-   What are key components of object-oriented programming in Python?  (Choose two.)
    -   Functions that can be performed on a data structure
    -   Attributes that are stored in an object
    -   Configuration templates
    -   YAML files

&nbsp;

-   Which of the following are benefits of OOP?  (Choose all that apply.)
    -   Reusable code
    -   Easy to follow
    -   Low coupling/high cohesion
    -   Complex integration

&nbsp;

-   Which of the following are used to define a class in Python?  (Choose two.)
    -   class classname(parent):
    -   class classname:
    -   def class classname(arg):
    -   None of the baove

&nbsp;

-   What is a method?
    -   A variable applied to a class
    -   Syntax notation
    -   A function within a class or an object
    -   Something that is not used in a class

&nbsp;

-   Which of the following describes inheritance?
    -   A hierarchy for functions in Python
    -   Class attributes and methods used as the starting point for another class
    -   A function only applied ot methods being used in another class
    -   None of the above

&nbsp;

-   Which module provides access to the file system and directory structure?
    -   filesystem
    -   open
    -   system
    -   os

&nbsp;

-   Which module is a testing framework for Cisco infrastructure?
    -   pyATST
    -   pyang
    -   devnetats
    -   ncclient

&nbsp;

##  Python Functions

&nbsp;

In Python, a *function* is a named block of code that can take a wide variety of input parameters (or none at all) and return some form of output back to the code that called the function to begin with.  It represents a key concept in programming sometimes referred to as DRY, which stands for Don't Repeat Yourself.  The idea behind DRY is that if you perform some particular operations in your code multiple times, you can simply create a function to reuse that block of code anywhere you need it instead of duplicating effort by typing it each time.

&nbsp;

Python offers two types of functions:  built-in functions that are part of the standard library and functions you create yourself.  The standard library includes a huge number of functions you can use in your program, like **print()**, many of which have already been introduced in Chapter 3.

&nbsp;

Building your own functions is how you construct capabilities that are not already present within Python.

&nbsp;

> ***Key Topic***

&nbsp;

To define a function in Python, you use the keyword **def**, a name for the function, a set of parentheses enclosing any arguments you want to pass to the function, and a color at the end.  The name of the function must follow these rules:

-   Must not start with a number
-   Must not be a reserved Python word, a built-in function (for example, **print()**, **input()**, **type()**), or a name that has already been used as a function or variable Can be any combination of the A-Z, a-z, 0-9 and the underscore (_) and dash (-)

&nbsp;

The following is an example of an incredibly simply function that could be entered into the interactive Python interpreter:

&nbsp;

```
>>> def devnet():
...     '''prints simple function'''
...     print('Simple function')
...

>>> devnet()

Simple function
```

&nbsp;

This function prints out the string "Simple function" any time you call it with **devnet()**.  Notice the indented portion that begins on the next line after the colon.  Python expects this indented portion to contain all the code that makes up the function.  Keep in mind that whitespace matters in Python.  The three single quotation marks that appear on the first line of the indented text of the function are called a ***docstring*** and can be used to describe what the function does.  

&nbsp;

As shown in the following example, you can use the built-in Python function **help()** to learn what a function does and any methods that can be used:

&nbsp;

```
>>> help(devnet)

Help on function devnet in module __main__:

devnet()
    prints simple function
```

&nbsp;

## Using Arguments and Parameters

&nbsp;

An argument is some value (or multiple values) that you pass to a function when you call the function within code.  Arguments allow a function to produce different results and make code reuse possible.  You simply place arguments within the parentheses after a function name.  For example, this example shows how you can pass multiple numeric arguments to the **max()** function to have it return the largest number in the list:

&nbsp;

```
>>> max(50, 5, 8, 10, 1)

50
```

&nbsp;

Each function must define how it will use arguments, using parameters to identify what gets passed in and how it gets used.  A parameter is simply a variable that is used in a function definition that allows code within the function to use the data passed to it.  To get results back from the function, you use the keyword **return** and the object you want to pass back.  The following example shows how to create a function that subtracts two numbers and stores the result in a local variable called **result** that gets returned when the function is called:

&nbsp;

```
>>> def sub(arg1, arg2):
...     result = arg1 - arg2
...     return result
...

>>> sub(10, 15)

-5
```

&nbsp;

The variable **result** is local, meaning that it is not accessible to the main Python script, and it is used only within the function itself.  If you tried to call **result** directly, Python would produce an error saying that**result** is not defined.  You can, however, access global variables from within the function; you might do this, or example, to set certain constants or key variables that any function can use (for example, IP addresses).  The difference in accessibility between a local variable and a global variable is important, because they allow your code to maintain separation and can keep your function self-contained.

&nbsp;

The previous example uses position arguments, which must be passed to a function in a particular order.  Positional arguments work with a simple set of consistently applied arguments, but if a function needs more flexible alignment to parameters within a function, you can use keyword arguments instead.  A ***keyword argument*** is a name/value pair that you pass to a function.  Instead of using position, you specify the argument that function uses.  It is a lot like assigning a variable to an argument.  In the previous example, *arg1* is subtracted from *arg2*, and if the positions of these arguments were switched, you would get a different result when subtracting the values.  With keyword arguments, it doesn't matter in what order they are passed to the function.  Here is an example:

&nbsp;

```
>>> sub(arg2=15, arg1=10)

-5
```

&nbsp;

What happens if you don't know the total number of arguments that are being passed to a function?  When you read in data, you might not know how many arguments to expect.  Python allows you to use * and ** (often referred to as **\*args** and **\*\*kwargs**) to define any number of arguments or keyword arguments.  * and ** allow you to iterate through a list or other collection of data, as shown in this example:

&nbsp;

```
>>> def hello(*args):
... for arg in args:
...    print("Hello ", arg, "!", sep='')
...

>>> hello('Caleb', 'Sydney', 'Savannah')

Hello Caleb!

Hello Sydney!

Hello Savannah!
```

&nbsp;

By using keyword arguments, you can send a list of key/value pairs to a function, as in the following example:

&nbsp;

```
>>> def hello(**kwargs):
...     for key, value in kwargs.item():
...         print("Hello", value, "1", sep='')
...

>>> hello(kwarg1='Caleb', kwarg2='Sydney', kwarg3='Savannah')

Hello Caleb!

Hello Sydney!

Hello Savannah!
```

&nbsp;

Note the use of the **items()** function in the **for** statement to unpack and iterate through the values.

&nbsp;

You can also supply a default value argument in case you have an empty value to send to a function.  By defining a function with an assigned key value, you can prevent an error.  If the value in the function definition is not supplied, Python uses the default, and if it is supplied, Python uses what is supplied when the function is called and then ignores the default value.  Consider this example:

&nbsp;

```
>>> def greeting(name, message="Good morning!"):
...     print(f"Hello {name}.  {message}")
...

>>> greeting('Caleb')

Hello Caleb.  Good morning!

>>> greeting('Sydney', 'How are you?')

Hello Sydney.  How are you?
```

&nbsp;

 ## Object-Oriented Programming and Python

 &nbsp;

 Python was developed as a modern object-oriented programming (OOP) language.  Object oriented programming is a computer programming paradigm that makes it possible to describe real-world things and their relationships to each other.  If you want to describe a router in the physical world, for example, you would list all its properties, such as ports, software versions, names, and IP addresses.  In addition, you might list different capabilities or functions of the router that you would want to interact with.  OOP was intended to model these types of relationships programmatically, allowing you to create an object that you can use anywhere in your code by just assigning it to a variable in order to instantiate it.

 &nbsp;

 > ***Key Topic***

&nbsp;

 Objects are central to Python; in fact, Python really is just a collection of objects interacting with each other.  An object is self-contained code or data and the idea of OOP is to break up a program into smaller, easier-to-understand components.  Up until now, you have mainly seen procedural programming techniques, which take a top-down approach and follow predefined sets of instructions.  While this approach works well for simple programs, to write more sophisticated applications with better scalability, OOP is often the preferred method used by professional programmers.  However, Python is very flexible in that you can mix and match these two approaches as you build applications.

 &nbsp;

 Functions are an important part of the OOP principles of reusability and object-oriented structure.  For the 200-901 DevNet Associate DEVASC exam, you need to be able to describe the benefits and techniques used in Python to build modular programs.  Therefore, you need to know how to use Python classes and methods, which are covered next.
 
 &nbsp;

 ## Python Classes

 &nbsp;

 In Python, you can use classes to describe objects.  Think of a class as a tool you use to create your own data structures that contain information about something; you can then use functions (methods) to perform operations on the data you describe.  A class models how something should be defined and represents an idea or a blueprint for creating objects in Python.

&nbsp;

 ### **Creating a Class**

 &nbsp;

 > ***Key Topic***

 &nbsp;

 Say that you want to create a class to describe a router.  The first thing you have to do is define it.  In Python, you define a class by using the **class** keyword, giving the class a name, and then closing with a colon.  Pep8 (introduced in Chapter 3) recommends capitalizing a class name to differentiate it from a variable.  Here is a simple example of creating a class in Python:

 &nbsp;

 ```
 >>> class Router:
 ...    pass
 ```

&nbsp;

 This example uses **pass** as a sort of placeholder that allows the class to be defined and set up to be used as an object.  To make the class more useful, you can add some attributes to it.  In the case of a router, you typically have some values that you want to have when you instantiate the class.  Every router has a model name, a software version, and an IP address for management.  You also need to pass some values to get started.  The first value is always **self**.  The reason for this will become obvious when you instantiate the class:  *The **self** value passes the object name that you select to instantiate the class*.  In the following example, the object you will create is **rtr1**:

 &nbsp;

 ```
 class Router:
    '''Router Class'''
    def __init__(self, model, swversion, ip_add):
        '''initialize values'''
        self.model = model
        self.swversion = swversion
        self.ip_add = ip_add

rtr1 = Router('iosV', 15.6.7', '10.10.10.1')
```

&nbsp;

After defining the class, you add a docstring to document what the class is for and then you create a function that calls **__init__**, which is a special case that is used for the setup of the class.  (In **__init__**, the double underscores are called *dunder* or *magic methods*.)  Functions that are within that are within the class are called *methods* and become actions that you can perform on the object you are creating.  To store attributes, you map the name **self** and the values you pass to it become variables inside the object, which then store those values as attributes.  The last bit of code instantiates the object itself.  Up until now, you have been creating a template, and by assigning data to the variables within the class, you have been telling Python to build the object.  Now you can access any of the stored attributes of the class by using dot notation, as show here:

&nbsp;

```
>>> rtr1.model

'iosV'
```

&nbsp;

When you call **rtr1.model**, the interpreter displays the value assigned to the variable model within the object.  You can also create more attributes that aren't defined during initialization, as shown in this example:

&nbsp;

```
>>> rtr1.desc = 'virtual router'

>>> rtr1.desc

'virtual router'
```

&nbsp;

This example shows how flexible objects area, but you typically want to define any attributes as part of the class to automate object creation instead of manually assigning values.  When building a class, you can instantiate as many objects as you want by just providing a new variable and passing over some data.  Here is another example of creating a second router object **rtr2**:

&nbsp;

```
>>> rtr2 = Router('isr4221', '16.9.5', '10.10.10.5')

>>> rtr2.model

'isr4221'
```

&nbsp;

### **Methods**

&nbsp;

Attributes describe an object, and methods allow you to interact with an object.  Methods are functions you define as part of a class.  In the previous section, you created an object and applied some attributes to it.  The example below shows how you can work with an object by using methods.  A method that allows you to see the details hidden within an object without typing a bunch of commands over and over would be a useful method to add to a class.  Building on the previous example, below we add a new function called **getdesc()** to format and print the key attributes on your router.  Notice that you pass **self** to this function only, as **self** can access the attributes applied during initialization.

&nbsp;

```
class Router:

    '''Router Class'''

    def __init__(self, model, swversion, ip_add):

        '''Initialize Values'''

        self.model = model
        self.swversion = swversion
        self.ip_add = ip_add

    def getdesc(self):

        '''Return a formatted description of the router'''

        desc = f'Router Model               :{self.model}\n'\
               f'Router Version             :{self.swversion}\n'\
               f'Router Management Address: :{self.ip_add}\n'\

        return desc

rtr1 = Router('iosV', '15.6.7', '10.10.10.1')

rtr2 = Router('isr4221', '16.9.5', '10.10.10.5')

print('Rtr1\n', rtr1.getdesc(), '\n', sep='')
print('Rtr2\n', rtr2.getdesc(), set='')
```

&nbsp;

There are two routers instantiated in this example: **rtr1** and **rtr2**.  Using the **print** function, you can call the **getdesc()** method to return formatted text about the object's attributes.  The following output would be displayed:

&nbsp;

```
Rtr1
Router Model             :iosV
Software Version         :15.6.7
Router Management Address:10.10.10.1

Rtr2
Router Model             :isr4221
Software Version         :16.9.5
Router Management Address:10.10.10.5
```

&nbsp;

### **Inheritance**

&nbsp;

> ***Key Topic***

&nbsp;

Inheritance in Python classes allows a child class to take on attributes and methods of another class.  In the previous section, we created a class for routers, but what about switches?  If you look at the **Router** class, you see that all of the attributes apply to switches as well, so why not reuse the code already written for a new Switch class?  The only part of the previous example that wouldn't work for a switch is the **getdesc()** method, which prints information about a router.  When you use the inheritance, you can replace methods and attributes that need to be different.  To inherit a class, you can create the class as shown earlier in this chapter, but before the colon, you add parentheses that include the class from which you want to pull attributes and methods.  It is important to note that the parent class must come before the child class in the Python code.  Below shows how this works, creating a second class named **Switch**, using the **Router** class as a parent.  In addition, it creates a different **getdesc()** method that prints text about a switch rather than about a router.

&nbsp;

```
class Router:

    '''Router Class'''

    def __init__(self, model, swversion, ip_add):

        '''Initialize Values'''

        self.model = model
        self.swversion = swversion
        self.ip_add = ip_add

    def getdesc(self):

        '''return a formatted description of the router'''

        desc = f'Router Model               :{self.model}\n'\
               f'Router Version             :{self.swversion}\n'\
               f'Router Management Address: :{self.ip_add}\n'\

        return desc


class Switch(Router):

    def getdesc(self)

        '''return a formatted description for a the switch'''

        desc = f'Switch Model               :{self.model}\n'\
               f'Switch Version             :{self.swversion}\n'\
               f'Switch Management Address: :{self.ip_add}\n'\

        return desc


rtr1 = Router('iosV', '15.6.7', '10.10.10.1')

rtr2 = Router('isr4221', 16.9.5', '10.10.10.5')

sw1 = Switch('Cat9300', '16.9.5', '10.10.10.8')


print('Rtr1\n', rtr1.getdesc(), '\n', sep='')

print('Rtr2\n', rtr2.getdesc(), '\n', sep='')

print('Sw1\n', sw1.getdesc(), '\n', sep='')
```

&nbsp;

You can add another variable named **Sw1** and instantiate the **Switch** class just as you did the **Router** class, by passing in attributes.  If you create another **print** statement using the newly created **Sw1** object, you see the output shown below:

&nbsp;

```
Rtr1
Router Model             :iosV
Software Version         :15.6.7
Router Management Address:10.10.10.1

Rtr2
Router Model             :isr4221
Software Version         :16.9.5
Router Management Address:10.10.10.5

Sw1
Switch Model             :Cat9300
Software Version         :16.9.5
Switch Management Address:10.10.10.8
```

&nbsp;

To learn more about classes, methods, and inheritance, you can refer to the Python documentation.  https://docs.python.org/3/tutorial/classes.html

&nbsp;

## Working with Python Modules

&nbsp;

>  ***Key Topic***

&nbsp;

A central goal of OOP is to allow you to build modular software that breaks code into smaller, easier-to-understand pieces.  One big file with thousands of lines of code would be extremely difficult to maintain and work with.  If you are going to break up your code into functions and classes, you can also separate that code into smaller chunks that hold key structures and classes and allow them to be physically moved into other files, called *modules*, that can be included in your main Python code with the **import** statement.  Creating modular code provides the following benefits:

-   **Easier readability/maintainability**:  Code written in a modular fashion is inherently easier to read and follow.  It's like chapters in a book providing groupings of similar concepts and topics.  Even the best programmers struggle to understand line after line of code, and modularity makes maintaining and modifying code much easier.
-   **Low coupling/high cohesion**:  Modular code should be written in such a way that modules do not have interdependencies.  Each module should be self-contained so that changes to one module do not affect other modules or code.  In addition, a module should only include functions and capabilities related to what the module is supposed to do.  When you spread your code around multiple modules, bouncing back and forth, it is really difficult to follow.  This paradigm is called low coupling/high cohesion modular design.
-   **Code reusability**:  Modules allow for easy reusability of your code, which saves you time and makes it possible to share useful code.
-   **Collaboration**:  You often need to work with others as you build functional code for an organization.  Being able to split up the work and have different people work on different modules speeds up the code-production process.

&nbsp;

There are a few different ways you can use modules in Python.  
-   The first and easiest way is to use one of the many modules that are included in the Python standard library or install one of thousands of third-party modules by using **pip**.  Much of the functionality you might need or think of has probably already been written, and using modules that are already available can save you a lot of time.  
-   Another way to use modules is to build them in Python language by simply writing some code in your editor, giving the file a name, and appending a .py extension.  Using your own custom modules does add a bit of processing overhead to your application, as Python is an interpreted language and has to convert your text into machine-readable instructions on the fly.  
-   Finally, you can program a module in the C language, compile it, and then add its capabilities to your Python program.  Compared to writing your own modules in Python, this method results in faster runtime for your code, but it is a lot more work.  Many third-party modules and those included as part of the standard library in Python are built this way.

&nbsp;

### **Importing a Module**

&nbsp;

All modules are accessed the same way in Python: by using the **import** command.  Within a program - by convention at the very beginning of the code - you type **import** followed by the module name you want to use.  The following example uses the **math** module from the standard library:

&nbsp;

```
>>> import math

>>> dir(math)

['__doc__', '__file__', '__loader__', '__name__', '__package__',
'__spec__', 'acos', 'acosh', 'asin', 'asinh', 'atan', 'atan2',
'atanh', 'ceil', 'comb', 'copysign', 'cos', 'cosh', 'degrees',
'dist', 'e', 'erf', 'erfc', 'exp', 'expm1', 'fabs', 'factorial',
'floor', 'fmod', 'frexp', 'fsum', 'gamma', 'gcd', 'hypot', 'inf',
'isclose', 'isfinite', 'isinf', 'isnan', 'isqrt', 'ldexp', 'lgam-
ma', 'log', 'log10', 'log1p', 'log2', 'modf', 'nan', 'perm', 'pi',
'pow', 'prod', 'radians', 'remainder', 'sin', 'sinh', 'sqrt',
'tan', 'tanh', 'tau', 'trunc']
```

&nbsp;

After you import a module, you can use the **dir()** function to get a list of all the methods available as part of the module.  The ones in the beginning with the **__** are internal to Python and are not generally useful in your programs.  All the others, however, are functions that are now available for your program to access.  As shown below, you can use the **help()** function to get more details and read the documentation on the **math** module.

&nbsp;

```
>>> help(math)
Help on module math:

NAME
    math

MODULE REFERENCE
    https://docs.python.org/3.8/library/math

    The following documentation is automatically generated from the Python
    source files.  It may be incomplete, incorrect or include features that
    are considered implementation detail and may vary between Python
    implementations.  When in doubt, consult the module reference at the
    location listed above.

 
DESCRIPTION
    This module provides access to the mathematical functions
    defined by the C standard.

FUNCTIONS
    acos(x, /)
        Return the arc cosine (measured in radians) of x.

    acosh(x, /)
        Return the inverse hyperbolic cosine of x.

    asin(x, /)
        Return the arc sine (measured in radians) of x.
-Snip for brevity-
```

&nbsp;

You can also use **help()** to look at the documentation on a specific function, as in this example:

&nbsp;

```
>>> help(math.sqrt)
Help on built-in function sqrt in module math:

sqrt(x, /)
    Return the square root of x.
```

&nbsp;

If you want to get a square root of a number, you can use the **sqrt()** method by calling **math.sqrt** and passing a value to it as show here:

&nbsp;

```
>>> math.sqrt(15)

3.872983346207417
```

&nbsp;

You have to type a module's name each time you want to use one of its capabilities.  This isn't too painful if you're using a module with a short name, such as **math**, but if you use a module with a longer name, such as the **calendar** module, you might wish you could shorten the module name.  Python lets you do this by adding **as** and a short version of the module name to the end of the import command.  For example you can use this command to shorten the name of **calendar** module to **cal**.

&nbsp;

```
>>> import calendar as cal
```

&nbsp;

Now you can use **cal** as an alias for **calendar** in your code, as shown in this example:

&nbsp;

```
>>> print(cal.month(2020, 2, 2, 1))
```

&nbsp;

Importing a whole module when you need only a specific method or function adds unneeded overhead.  To help with this, PYthon allows you to important specific methods by using the **from** syntax.  Here is an example of importing the **sqrt()** and **tan()** methods:

&nbsp;

```
>>> from math import sqrt, tan

>>> sqrt(15)

3.872983346207417
```

&nbsp;

As you can see here, you can import more than one method by separating the methods you want with commas.

&nbsp;

Notice that you no longer have to use **math.sqrt** and can just call **sqrt()** as a function, since you imported only the module functions you needed.  Less typing is always a nice side benefit.

&nbsp;

###  **The Python Standard Library**

&nbsp;

The Python standard library, which is automatically installed when you load Python, has an extensive range of prebuilt modules you can use in your applications.  Many are built in C and make life easier for programmers looking to solve common problems quickly.  Throughout this book, you will see many of these modules used to interact programmatically with Cisco infrastructure.  To get a complete list of the modules in the standard library, go to https://docs.python.org/3/library/.  This documentation lists the modules you can use and also describes how to use them.

&nbsp;

###  **Importing Your Own Modules**

&nbsp;

As discussed in this chapter, modules are Python files that save you time and make your code readable.  To save the class example from earlier in this chapter as a module, you just need to save all of the code for defining the class and the attributes and functions as a separate file with the .py extension.  You can import your own modules by using the same methods shown previously with standard library modules.  By default, Python looks for a module in the same directory as the Python program you are importing into.  If it doesn't find the file there, it looks through your operating system's **path** statements.  To print out the path your OS will search through, consider this example of importing the **sys** module and using the **sys.path** method:

&nbsp;

```
>>> import sys

>>> sys.path

['', '/Users/chrijack/Documents', '/Library/Frameworks/Python.
framework/Versions/3.8/lib/python38.zip', '/Library/Frameworks/
Python.framework/Versions/3.8/lib/python3.8', '/Library/Frameworks/
Python.framework/Versions/3.8/lib/python3.8/lib-dynload', '/
Library/Frameworks/Python.framework/Versions/3.8/lib/python3.8/
site-packages']
```

&nbsp;

Depending on your OS (this output is from a Mac), the previous code might look different from what you see here, but it should still show you what Python sees, so it is useful if you are having trouble importing a module.

&nbsp;

If you remove the class from the code shown previously and store it in a separate file named device.py, you can import the class rom your new module and end up with the following program, which is a lot more readable while still operating example the same:

&nbsp;

```
from device import Router, Switch

rtr1 = Router('iosV', '15.6.7', '10.10.10.1')
rtr2 = Router('isr4221', '16.9.5', '10.10.10.5')
sw1 = Switch('Cat9300', '16.9.5', '10.10.10.8')

print('Rtr1\n', rtr1.getdesc(), '\n', sep='')
print('Rtr2\n', rtr2.getdesc(), '\n', sep='')

print('Sw1\n', sw1.getdesc(), '\n', sep='')
```

&nbsp;

When you execute this program, you get the output shown below.  If you compare these results with the results shown previously, you see they are exactly the same.  Therefore, the device module is just Python code that is stored in another file but used in your program.

&nbsp;

```
Rtr1
Router Model             :iosV
Software Version         :15.6.7
Router Management Address:10.10.10.1

 
Rtr2
Router Model             :isr4221
Software Version         :16.9.5
Router Management Address:10.10.10.5

Sw1
Switch Model             :Cat9300
Software Version         :16.9.5
Router Management Address:10.10.10.8
```

&nbsp;

### **Useful Python Modules for Cisco Infrastructure**

&nbsp;

This chapter cannot cover every single module that you might find valuable when writing Python code to interact with Cisco infrastructure.  As you become familiar with Python, you will come to love and trust a wide range of standard library and third-party modules.  The following list includes many that are widely used to automate network infrastructure.  Many of these modules are used throughout this book, so you will be able to see them in action.  The following list provides a description of each, how to install it (if it is not part of the standard library), and the syntax to use in your Python **import** statement:

&nbsp;

> ***Key Topic***

&nbsp;

-   General purpose standard library modules:
    -   pprint:  The pretty print module is a more intelligent print function that makes it much easier to display text and ata by, for example, aligning data for better readability.  Use the following command to import this module:
        -   ```from pprint import pprint```
    -   sys:  This module allows you to interact with the Python interpreter and manipulate and view values.  Use the following command to import this module:
        -   ```import sys```
    -   os:  This module gives you access to the underlying operating system environment and file system.  It allows you to open files and interact with OS variables.  Use the following command to import this module:
        -   ```import os```
    -   datetime:  This module allows you to create, format, and work with calendar dates and time.  It also enables timestamps and other useful additions to logging and data.  Use the following command to import this module:
        -   ```import datetime```
    -   time:  This module allows you to add time-based delays and clock capabilities to your Python apps.  Use the following command to import this module:
        -   ```import time```
-   Modules for working with data:
    -   xmltodict:  This module translates XML-formatted files into native Python dictionaries (key/value pairs) and back to XML, if needed.  Use the following commands to install and import this module:
        -   ```pip install xmltodict```
        -   ```import xmltodict```
    -   csv:  This is a standard library module for understanding CSV files.  It is useful for exporting Excel spreadsheets into a format that you can then import into Python as a data source.  It can, for example, read in a CSV file and use it as a Python list data type.  Use the following command to import this module:
        -   ```import csv```
    -   json:  This is a standard library module for reading JSON-formatted data sources and easily converting them to dictionaries.  Use the following command to import this module:
        -   ```import json```
    -   PyYAML:  This module converts YAML files to Python objects that can be converted to Python dictionaries or lists.  Use the following commands to install and import this module:
        -   ```pip install PyYAML```
        -   ```import yaml```
    -   pyang:  This isn't a typical module you import into a Python program.  It's a utility written in Python that you can use to verify your YANG models, create YANG code, and transform YANG models into other data structures, such as XSD (XML Schema Definitions).  Use the following command to install this module:
        -   ```pip install pyang```
-   **Tools for API interaction**:
    -   requests:  This is a full library to interact with HTTP services and used extensively to interact with REST APIs.  Use the following commands to install and import this module:
        -   ```pip install requests```
        -   ```import requests```
    -   ncclient:  This Python library helps with client-side scripting and application integration for the NETCONF protocol.  Use the following commands to install and import this module:
        -   ```pip install ncclient```
        -   ```from ncclient import manager```
    -   netmiko:  This connection-handling library makes it easier to initiate SSH conncetions to network devices.  This module is intended to help bridge the programmability gap between devices with APIs and those without APIs that still rely on command-line interfaces and commands.  It relies on the paramiko module and works with multiple vendor platforms.  Use the following commands to install and import this module:
        -   ```pip install netmiko```
        -   ```from netmiko import ConnectHandler```
    -   pysnmp:  This is a Python implementation of an SNMP engine for network management.  It allows you to interact with older infrastructure components without APIs but that do support SNMP for management.  Use the following commands to install and import this module:
        -   ```pip install pysnmp```
        -   ```import pysnmp```
-   **Automation tools**
    -   napalm:  napalm (Network Automation and Programmability Abstraction Layer with Multivendor Support) is a Python module that provides functionality that works in a multivendor fashion.  Use the following commands to install and import this module:
        -   ```pip install napalm```
        -   ```import napalm```
    -   nornir:  This is an extendable, multithreaded framework with inventory management to work with large numbers of network devices.  Use the following commands to install and import this module:
        -   ```pip install nornir```
        -   ```from nornir.core import InitNornir```
-   Testing tools:
    -   unittest:  This standard library testing module is used to test the functionality of Python code.  It is often used for automated code testing and as part of test-driven development methodologies.  Use the following command to import this module:
        -   ```import unittest```
    -   pyats:  This module was a gift from Cisco to the development community.  Originally named Genie, it was an internal testing framework used by Cisco developers to validate their code for Cisco products.  pyats is an incredible framework for constructing automated testing for infrastructure as code.  Use the following command to install this module:
        -   ```pip install pyats (just install the core framework, check documentation for more options)```
        -   Many parts of the **pyats** framework can be imported.  Check the documentation on how to use it.  

&nbsp;

Chapter 5, "Working with Data in Python," places more focus on techniques and tools used to interact with data in Python.  This will round out the key Python knowledge needed to follow along with the examples in the rest of the book.