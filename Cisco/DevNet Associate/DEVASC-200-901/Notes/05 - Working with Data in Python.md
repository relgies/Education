# Working with Data in Python

## "Do I Know This Already?" Quiz

&nbsp;

-   When parsing a text file, what determines the end of a line?
    -   Return code
    -   Nothing; Python sees it as one big string
    -   \n or EoF
    -   All of the above

&nbsp;

-   What syntax would you use to open a text file to be written to?
    -   data = open("text.txt", "w")
    -   data = load("text.txt", "w")
    -   load("text.txt", "w")
    -   open("text.txt", "w")

&nbsp;

-   Which of the following do you use to write to a CSV file in Python?
    -   ```
        with open("text.csv", "a") as filehandle:  
        csv_write=csv.write(filehandle)
        csv_writerow(data)
    -   ```
        with open("text.csv", "a") as filehandle:
        csv_writer.writerow(data)
    -   ```
        with open("text.csv", "a") as filehandle:
        csv_writer = csv.writer(filehandle)
        csv_writer.writerow(data)
    -   ```
        with open("text.csv", "a") as filehandle:
        csv_writer = csv_writer(f)
        csv_writer.writerow(data)

&nbsp;

-   Which module is imported to read XML data?
    -   xmlm
    -   xmltodict
    -   XMLParse
    -   None of the above

&nbsp;

-   Which methods are used for converting a native JSON file to Python and then back to JSON?
    -   **load()** and **dump()**
    -   **loads()** and **dump()**
    -   **loads()** and **dumps()**
    -   **load()** and **dumps()**

&nbsp;

-   What does YAML stand for?
    -   Yet Another Markup Language
    -   YAML Ain't Markup Language
    -   the name of its creator
    -   None of the above

&nbsp;

-   What is the syntax for error handling in Python?
    -   **try-except-else-finally**
    -   **raise ErrorMessage**
    -   **assertErrorValue**
    -   All of the above

&nbsp;

-   When does the finally block execute
    -   After the **try** block is successful
    -   After the **except** block
    -   At the end of every **try** block
    -   When an error code stops the **else** block

&nbsp;

-   Test-driven development requires that developers:
    -   Create a unit test for every bit of code they write
    -   Know how to use DevOps tools for automated testing
    -   Create a simple test that fails and then write code that allows the test to succeed
    -   Completely unnecessary in an Agile development shop

&nbsp;

-   What is the difference between a unit test and an integration test?  (Choose two.)
    -   An integration test is for validation of how different parts of the application work together.
    -   An integration test verifies that the application operates as expected.
    -   A unit test verifies API functionality.
    -   A unit test is most specific in scope and tests small bits of code.

&nbsp;

-   Which class is inherited as part of a unit test?
    -   **unittest.testcase**
    -   **unittest.TestCase**
    -   **unittest**
    -   **TestCase**

&nbsp;

## File Input and Output

&nbsp;

To extra data from a text file, you can use native Python capabilities.  Binary files, on the other hand, need to be processed by some module or another external program before it is possible to extract the data from them.  The vast majority of your needs will be addressed through text files, so that is what this section focuses on.

&nbsp;

From Python's perspective, a text file can be thought of as a sequence of lines.  Each line, as it is read in to Python, is typically 79 characters long (per PEP 8 convention), with a newline character at the end (**\n** for Python).  There are just two functions that you need to know when working with a text file:  **open()** and **close()**.

&nbsp;

To open a file and read in its contents, you have to first tell Python the name of the file you want to work with.  You do this by using the **open()** function and assigning the output to a PYthon object (the variable **readdata** in this case).  The function returns a file handle, which Python uses to perform various operations on the file.  The code looks as follows:

&nbsp;

```
readdata = open("textfile.txt", "r")
```

&nbsp;

The **open()** function requires two arguments:  the name of the file as a string and the mode that you want to open the file.  In the preceding example, it opens the file in read mode.  There are numerous options you can use when you set mode, and oyu can combine them in some cases to fine-tune how you want Python to handle the file.  The following are some of the options:

-   **r**:  Open for reading (default)
-   **w**:  Open for writing, truncating the file first
-   **x**:  Open for exclusive creation, failing if the file already exists
-   **a**:  Open for writing, appending to the end of the file if it exists
-   **b**:  Open in binary mode
-   **t**:  Open in text mode (default)
-   **+:**  Open for updating (reading and writing)

&nbsp;

With the previous code, you now have a file handling object named **readdata**, and you can use methods to interact with the file methods.  To print the contents of the file, you cna use the following:

&nbsp;

```
print(readdata.read())


Line one of a text file.

Line two of a text file, just like line one, but the second one.

Third line of a text file.
```

&nbsp;

When using the **open()** function, you have to remember to close the file when you are finished reading from it.  If you don't, the file will stay open, and you might run in to file lock issues with the operating system while the Python app is running.  To close the file, you simply use the **close()** method on the **readdata** object:

&nbsp;

```
readdata.close()
```

&nbsp;

Keeping track of the state of the file lock and whether you opened and closed it can be a bit of a chore.  Python provides another way you can use to more easily work with files as well as other Python objects.  The **with** statement (also called ***context manager*** in Python) uses the **open()** function but doesn't require direct assignment to a variable.  It also has better exception handling and automatically closes the file for you when you have finished reading in or writing to the file.  Here's an example:

&nbsp;

```
with open("textfile.txt", "r") as data:
    print(data.read())
```

&nbsp;

This is much simpler code, and you can use all of the same methods to interact with the files as before.  To write to a file, you can use the same structure, but in this case, because you want to append some data to the file, you need to change how you open the file to allow for writing.  

In this example, you can use "**a+**" to allow reading and appending to the end of the file.  Here is what the code would look like:

&nbsp;

```
with open("textfile.txt", "a+") as data:
    data.write('\nFourth line added by Python')
```

&nbsp;

Notice the newline in front of the text you are appending to the file.  It appears here so that it isn't just tacked on at the very end of the text.  Now you can read the file and see what you added.

&nbsp;

```
with open ("textfile.txt", "r") as data:
    print(data.read())


Line one of a text file.

Line two of a text file, just like line one, but the second one.

Third line of a text file.

Fourth line added by Python
```

&nbsp;

##  Parsing Data

&nbsp;

Imagine a world where all the data is in nice, neatly formatted cells, completely structured, and always consistent. Unfortunately, data is not so easily accessible, as there are a multitude of types, structures, and formats. This is why it is essential that you learn how to parse data in some of the more common forms within your Python programs.

&nbsp;

###  **Comma-Separated Values (CSV)**

&nbsp;

A CSV file is just a plaintext spreadsheet or database file.  All of those spreadsheets or databases that you have with infrastructure information can be easily exported as CSV files so that you can use them as source data in Python.  Each line in a CSV file represents a row, and commas are used toe separate the individual data fields to make it easier to parse the data.  Python has a built-in CSV module that you can import that understands the CSV format and simplifies your code.  The following is an example of a typical CSV file (in this case named routerlist.csv):

&nbsp;

```
"router1","192.168.10.1","Nashville"
"router2","192.168.20.1","Tampa"
"router3","192.168.30.1","San Jose"
```

&nbsp;

This example shows a common asset list or device inventory, such as one that you might pull from a network management system or simply keep track of locally.  To start working with this data, you have to import the CSV module, and then you need to create a **reader** object to read your CSV file into.  You first have to read the file into a file handle, and then you run the CSV read function on it and pass the results on to a **reader** object.  From there, you can begin to use the CSV data as you wish.  You can create another variable and pass the **reader** object variable to the built-in **list()** function.  Here is what the code would look like:

&nbsp;

```
>>> import csv

>>> samplefile = open('routerlist.csv')

>>> samplereader = csv.reader(samplefile)

>>> sampledata = list(samplereader)

>>> sampledata

[['router1', '192.168.10.1', 'Nashville'], ['router2',
'192.168.20.1', 'Tampa'], ['router3', '192.168.30.1', 'San Jose ']]
```

&nbsp;

In this example, you now have a list of lists that includes each row of data.  If you want to manipulate this data, you could because it's now in a native format for PYthon.  Using list notation, you can extract individual pieces of information.

&nbsp;

```
>>> sampledata[0]

['router1', '192.168.10.1', 'Nashville']

>>> sampledata[0][1]

'192.168.10.1'
```

&nbsp;

Using **with**, you can iterate through the CSV data and display information in an easier way:

&nbsp;

```
import csv

with open("routerlist.csv") as data:

    csv_list = csv.reader(data)

    for row in csv_list:

        device = row[0]

        location = row[2]

        ip = row[1]

        print(f"{device} is in {location.rstrip()} and has IP {ip}.")
```

&nbsp;

> ***Personal Note**:  Why is list not needed?  **data** is the file handler, **csv_list** is the reader, but why do we not need the list function?*  After testing it seems to work with or without **list()**, not sure why.

> This was answered [here](https://www.reddit.com/r/learnpython/comments/wywuh5/no_list_needed_when_using_with_for_csv/).  Essentially though, list() works by essentially iterating over the items and building the list, similar to how a for loop iterates, so you can skip the list in the previous example and for loop over it as well. 

&nbsp;

Notice the **rstrip** function used to format the **location** variable?  You use it because the last entry in your CSV file will have a whitespace character at the very end when it is read into Python because it is at the very end of the file.  If you don't get rid of it (by using **rstrip**), your formatting will be off.

The output of this code is as follows:

```
router1 is in Nashville and has IP 192.168.10.1.
router2 is in Tampa and has IP 192.168.20.1.
router3 is in San Jose and has IP 192.168.30.1.
```

&nbsp;

If you want to add a fourth device to the CSV file, you can follow a process very similar to what you did with text files.  Below shows how to add a little interaction from the command line to fill in the fields and create a Python list with details on the new router.  Instead of using a **reader** object, this example uses a **writer** object to store the formatted CSV data and then write it to the file.

&nbsp;

```
import csv

print("Please add a new router to the list")

hostname = input("What is the hostname? ")

ip = input("What is the ip address? ")

location = input("What is the location? ")


router = [hostname, ip, location]


with open("routerlist.csv", "a") as data:

    csv_writer = csv.writer(data)

    csv_wrtier.writerow(router)


<Below is interactive from the terminal after running the above code>

Please add a new router to the list

What is the hostname? router4

What is the ip address? 192.168.40.1

What is the location? London
```

&nbsp;

If you run the code show above and input details for router 4, now when you display the router list, you will have the new router included as well:

&nbsp;

```
router1 is in Nashville and has IP 192.168.10.1.
router2 is in Tampa and has IP 192.168.20.1.
router3 is in San Jose and has IP 192.168.30.1.
router4 is in London and has IP 192.168.40.1.
```

&nbsp;

### JavaScript Object Notation (JSON)

&nbsp;

> ***Key Topic***

&nbsp;

JavaScript Object Notation (JSON) is a data structure that is derived from the JavaScript programming language, but it can be used as a portable data structure for any programming language.  It was built to be an easily readable and standard way for transporting data back and forth between applications.  JSON is heavily used in web services and is one of the core data formats you need to know how to use in order to interact with Cisco infrastructure.  The data structure is built around key/value pairs that simplify mapping of data and its retrieval.  Below shows an example of JSON.

&nbsp;

```
{   
    "interface": {
        "name": "GigabitEthernet1",
        "description": "Router Uplink",
        "enabled": true,
        "ipv4" {
            "address": {
                "ip": "192.168.1.1",
                "netmask": "255.255.255.0"
            }
        }
    }
}
```

&nbsp;

Above, you see the structure that JSON provides.  **interface** is the main data object, and you can see that its value is multiple key/value pairs.  This nesting capability allows you to structure very sophisticated data models.  Notice how similar to a Python dictionary the data looks.  You can easily convert JSON to lists (for a JSON array) and dictionaries (for JSON objects) with the built-in JSON module.  There are four functions that you work with to perform the conversion of JSON data into Python objects and back.

-   **load()**:  This allows you to import native JSON and convert it to a Python dictionary from a file.
-   **loads()**:  This will import JSON data from a string for parsing and manipulating within your program.
-   **dump()**:  This is used to write JSON data from Python objects to a file.
-   **dumps()**:  This allows you to take JSON dictionary data and convert it into serialized string for parsing and manipulating within Python.

&nbsp;

The **s** at the end of **dump** and **load** refers to a string, as in *dump string*.  To see this in action, you load the JSON file and map the file handle to a Python object (data) like so:

&nbsp;

```
import json

with open("json_sample.json") as data:
    json_data = data.read()


json_dict = json_loads(json_data)
```

&nbsp;

The object **json_dict** has taken the output of **json.loads(json_data)** and now holds the **json** object as a Python dictionary:

&nbsp;

```
>>> type(json_dict)

<class 'dict'>

>>> print(json_dict)

{'interface': {'name': 'GigabitEthernet1', 'description':
'Router Uplink', 'enabled': True, 'ipv4': {'address':
[{'ip': '192.168.0.2', 'netmask': '255.255.255.0'}]}}}
```

&nbsp;

You can now modify any of the key/value pairs, as in this example where the description is changed:

&nbsp;

```
>>> json_dict["interface"]["description"] = "Backup Link"

>>> print(json_dict)

{'interface': {'name': 'GigabitEthernet1', 'description': 'Backup
Link', 'enabled': True, 'ipv4': {'address': [{'ip': '192.168.0.2',
'netmask': '255.255.255.0'}]}}}
```

&nbsp;

In order to save the new **json** object back to a file, you have to use the **dump()** function (without the **s**) to convert the Python dictionary back into a JSON file object.  To make it easier to read, you can use the **indent keyword:

&nbsp;

```
with open("json_sample.json", "w") as fh:

    json.dump(json_dict, fh, indent = 4)
```

&nbsp;

Now if you load the file again and print, you can see the stored changes, as shown below:

&nbsp;

```
>>> with open ("json_sample.json") as data:
    json_data = data.read()
    print(json_data)
{
    "interface": {
        "name": "GigabitEthernet1",
        "description": "Backup Link",
        "enabled": true,
        "ipv4": {
            "address": [
                {
                    "ip": "192.168.0.2",
                    "netmask": "255.255.255.0"
                }
            ]
        }
     }
}
>>>
```

&nbsp;

> ***Key Topic***

&nbsp;

### **Extensible Markup Language (XML)**

&nbsp;

Extensible Markup Language (XML) is a very common data format that is used heavily in configuration automation.  Parsing XML is similar to using other data formats, in that Python natively understands and can support XML encoding and decoding.  The following is a very simple example of what XML structure looks like.

&nbsp;

```
<device>
    <Hostname>Rtr01</Hostname>
    <IPv4<192.168.1.5</IPv4>
    <IPv6></IPv6>
</device>
```

&nbsp;

It should come as no surprise that XML looks a bit like HTML syntax; it was designed to work hand-in-hand with HTML for data transport and storage between web services and APIs.  XML has a tree structure, with the root element being at the very top.  There is a parent/child relationship between elements.  In the preceding example, **device** is the root element that has **Hostname**, **IPv4**, and **IPv6** as child elements.  Just like with HTML, as tag has meaning and is used to enclose the relationships of the elements with a start tag (<>) and a closing tag (</>).  It's not all that different from JSON in that a tag acts as a key with a value.  You can also assign attributes to a tag by using the following syntax:

&nbsp;

```
attribute name="some value"
```

&nbsp;

This works the same as an element in that it can provide a way to represent data.  Below shows an example of the IETF interface YANG model in XML.

&nbsp;

```
 <?xml version="1.0" encoding="UTF-8" ?>
<interface xmlns="ietf-interfaces">
  <name>GigabitEthernet2</name>
  <description>Wide Area Network</description>
  <enabled>true</enabled>
  <ipv4>
    <address>
      <ip>192.168.1.5</ip>
      <netmask>255.255.255.0</netmask>
    </address>
  </ipv4>
</interface>
```

&nbsp;

To work with this, you can use the native XML library, but it has a bit of a learning curve and can be a little hard to use if you just want to convert XML into something you can work with in Python.  To make it easier, you can use a module called xmltodict to convert XML into an ordered dictionary in Python.  This is a special class of dictionary that does not allow elements to change order.  Since dictionaries use key/value pairs, where the key/value pairs are stored is normally not a problem, but in the case of XML, order matters.  Below reads in the XML from the previous example and converts it to an ordered dictionary.

&nbsp;

```
import xmltodict

with open("xml_sample.xml") as data:

    xml_example = data.read()

xml_dict = xmltodict.parse(xml_example)

>>> print(xml_dict)

OrderedDict([('interface', OrderedDict([('@xmlns', 'ietf-interfaces'), ('name',
'GigabitEthernet2'), ('description', 'Wide Area Network'), ('enabled', 'true'),
('ipv4', OrderedDict([('address', OrderedDict([('ip', '192.168.0.2'), ('netmask',
'255.255.255.0')]))]))]))])
```

&nbsp;

Now that you have the XML in a Python dictionary, you can modify an element, as shown here:

&nbsp;

```
xml_dict["interface"]["ipv4"]["address"]["ip"] = "192.168.55.3"
```

&nbsp;

You can see your changes in XML format by using the **unparse** function shown below.  You can use the **pretty=True** argument to format the XML to make it a bit easier to read.  XML doesn't care about whitespace, but humans do for readability.

&nbsp;

```
>>> print(xmltodict.unparse(xml_dict, pretty=True))

<?xml version="1.0" encoding="utf-8"?>
<interface xmlns="ietf-interfaces">
     <name>GigabitEthernet2</name>
     <description>Wide Area Network</description>
     <enabled>true</enabled>
     <ipv4>
         <address>
              <ip>192.168.55.3</ip>
              <netmask>255.255.255.0</netmask>
         </address>
     </ipv4>
</interface>
```

&nbsp;

To write these changes back to your original file, you can use the following code:

&nbsp;

```
with open("xml_sample.xml", "w") as data:

    data.write(xmltodict.unparse(xml_dict, pretty=True))
```

&nbsp;

### YAML Ain't Markup Language (YAML)

&nbsp;

YAML is an extremely popular human-readable format for constructing configuration files and storing data.  It was built for the same use cases as XML but has a much simpler syntax and structure.  It uses Python-like indentation to differentiate blocks of information and waste actually built based on JSON syntax but with a whole host of features that are unavailable in JSON (such as comments).  If you have ever used Docker or Kubernetes, you have undoubtedly run into YAML files.  The follow is an example of YAML:

&nbsp;

```
---
interface:
    name: GigabitEthernet2
    description: Wide Area Network
    enabled: true
    ipv4:
        address:
        -   ip: 172.16.0.2
            netmask: 255.255.255.0
```

&nbsp;

Notice that a YAML object has minimal syntax, all data that is related has the same indentation level, and key/value pairs are used to store data.  YAML can also represent a list by using the **-** character to identify elements, as in the following example of IP addresses:

&nbsp;

```
---
addresses:
    -   ip: 172.16.0.2
        netmask: 255.255.255.0
    -   ip: 172.16.0.3
        netmask: 255.255.255.0
    -   ip: 172.16.0.4
        netmask: 255.255.255.0
```

&nbsp;

To work with YAML in Python, you need to install and import the PyYAML module.  Once you import it into your code, you can convert YAML to Python objects and back again.  YAML objects are converted to dictionaries, and YAML lists automatically become Python lists.  The two functions that perform this magic are **yaml.load** to convert from YAML objects into Python and **yaml.dump** to convert Python objects back to YAML.  Just as in the other data examples, you can load a YAML file and then pass it to **yaml.load** to work its magic.  The latest PyYAML module requires that you add an argument to tell it which loader you want to use.  This is a security precaution so that your code will not be vulnerable to arbitrary code execution from a bad YAML file.  Here is what the code looks like.

&nbsp;

```
import yaml

with open("yaml_sample.yaml") as data:

    yaml_sample = data.read()

yaml_dict = yaml.load(yaml_sample, Loader=yaml.FullLoader)
```

&nbsp;

The variable **yaml_dict** is now a dictionary object containing your YAML file.  Had this key/value been a YAML list, it would have created a list instead, like this:

&nbsp;

```
>>> type(yaml_dct)

<class 'dict'>

>>> yaml_dict

{'interface': {'name': 'GigabitEthernet2', 'description': 'Wide
Area Network', 'enabled': True, 'ipv4': {'address': [{'ip':
'192.168.0.2', 'netmask': '255.255.255.0'}]}}}
```

&nbsp;

As before, you can modify this object to your liking.  For example, you can change the interface name to **GigabitEthernet1**, as shown below.

&nbsp;

```
>>> yaml_dict["interface"]["name"] = "GigabitEthernet1"

>>> print(yaml.dump(yaml_dict, default_flow_style=False))

interface:
    description:  Wide Area Network
    enabled:    true
    ipv4:
        address:
        -   ip: 192.168.0.2
            netmask: 255.255.255.0
    name: GigabitEthernet1
```

&nbsp;

To write these changes back to your file, use the following code.

&nbsp;

```
with open("yaml_sample.yaml", "w") as data:
    data.write(yaml.dump(yaml_dict, default_flow_style=False))
```

&nbsp;

> ***Key Topic***

&nbsp;

## Error Handling in Python

&nbsp;

Whenever you are working with code, errors are bound to happen.  In Python, errors often half the execution of code, and the interpreter spits out some type of cryptic message.  What if you wanted Python to tell the users what they did wrong and let them try again or perform some other task to recover from the error?  That's where the **try-except-else-finally** code blocks come into play.

&nbsp;

You have seen quite a bit of file access in this chapter.  What happens if you ask the user for the filename instead of hard-coding it?  If you did this, you would run the risk of a typo halting your program.  In order to add some error handling to your code, you can use the **try** statement.  Below shows an example of how this works.

&nbsp;

```
x = 0

while True:

    try:

        filename = input("Which file would you like to open? :")

        with open(filename, "r") as fh:

            file_data = fh.read()

    except FileNotFoundError:

        print(f'Sorry, {filename} doesn't exist!  Please try again.')

    else:

        print(file_data)

        x = 0

        break

    finally:

        x += 1

        if x == 3:

            print('Wrong filename 3 times.\nCheck name and return.')

            break
```

&nbsp;

In this example, a variable keeps track of the number of times the **while** loop will be run.  This is useful for building in some logic to make sure the program doesn't drive the uers crazy by constantly asking them to enter a filename.  Next is an infinite **while** loop that uses the fact that the Boolean True will always result in continuing looping through the code.  Next is the **try** statement, which contains the block of code you want to subject to error handling.  You ask the user to enter a filename to open, and it is stored in the **filename** variable.  This variable is used with **open()** to open a read-only text file and use the file handle object **fh**.  The file handle object uses **read()** to store the text file in the **file_data** variable.  If Python can't find the file specified, the **except FileNotFoundError** block of code is executed, printing an error message with the file's name and informing the user to try again.  The **else** block runs only if an exception does not occur and the filename can be found.  THe **file_data** is printed, **x** is set to 0 (to empty the counter), the loop is stopped, and the **finally** block is run.  The **finally** block runs regards of whether an exception occurs each time through the loop.  The **x** variable is incremented each time through the loop, and if the user gets the wrong filename three times, a message is printed, saying the user tried three times and to check the file.  At this point, the loop is broken and the script is halted.

Here is what the program output would look like with a valid **text.txt** file in the script directory:

&nbsp;

```
Which file would you like to open? :test
Sorry, test doesn't exist! Please try again.
Which file would you like to open? :test.txt
Test file with some text.
Two lines long.
```

&nbsp;

Here is what the output would look like with three wrong choices:

&nbsp;

```
Which file would you like to open? :test
Sorry, test doesn't exist! Please try again.
Which file would you like to open? :test2
Sorry, test2 doesn't exist! Please try again.
Which file would you like to open? :test3
Sorry, test3 doesn't exist! Please try again.
Wrong filename 3 times.
Check name and Rerun.
```

&nbsp;

There are quite a few other error-handling capabilities available in Python, and if you want to try and to make your applications more user friendly, it would be worth your time to explore them.  The latest documentation can be found at https://docs.python.org/3/tutorial/errors.html.  This documentation discusses custom errors and provides more examples of types of errors you can use with the previous sample code.

&nbsp;

## Test-Drive Development

&nbsp;

Test-drive development (TDD) is an interesting concept that at first glance may seem completely backward.  The idea is that you build a test case first, before any software has been created or modified.  The goal is to streamline the development process by focusing on only making changes or adding code that satisfies the goal of the test.  In normal testing, you test after the software is written, which means you spend your time chasing errors and bugs more than writing code.  By writing the test first, you spend your time focused on writing only what is needed and making sure your code simple, easier to understand, and hopefully bug free.  Below shows the TDD process in action.

1. Write Test
2. Test Fails
3. Write Code
4. Test Passes
5. Refactor

The above is circular, meaning you repeat after step 6.

&nbsp;

> ***Key Topic***

&nbsp;

The following are the five steps of TDD:

-   **Step 1.  Write a test**:  Write a test that tests for the new class or function that you want to add to your code.  Think about the class name and structure you will need in order to call the new capability that doesn't exist yet - and nothing more.
-   **Step 2.  Test fails**:  Of course, the test fails because you haven't written the part that works yet.  The idea here is to think about the class or function you want and test for its intended output.  This initial test failure shows you exactly where you should focus your code writing to get it to pass.  This is like starting with your end state in mind, which is the most effective way to accomplish a goal.
-   **Step 3.  Write some code**:  Write only the code needed to make the new function or class successfully pass.  This is about efficiency and focus.
-   **Step 4.  Test passes**:  The test now passes, and the code works.
-   **Step 5.  Refactor**:  Clean up the code as necessary, removing any test stubs or hard-coded variables used in testing.  Refine the code, if needed, for speed.

&nbsp;

TDD may seem like a waste of time initially.  Why write tests for stuff you know isn't going to pass?  Isn't all of this testing just wasted effort?  The benefit of this style of development is it starts with the end goal in mind, by defining success right away.  The test you create is laser focused on the application's purpose and a clear outcome.  Many programmers add too much to their code by trying to anticipate future needs or building in too much complexity for an otherwise simple problem.  ***TDD works extremely well with the iterative nature of Agile development, with the side benefit of having plenty of test cases to show that the software works.***

&nbsp;

## Unit Testing

&nbsp;

Testing your software is not optional.  Every script and application that you create have to go through testing of some sort.  Maybe it's just testing your syntax in the interactive interpreter or using an IDE and trying your code as you write it.  While this is software testing, it's not structured and often is not repeatable.  Did you test all options?  Did you validate your expectations?  What happens if you send unexpected input to a function?  These are some of the reasons using a structured and automated testing methodology is crucial to creating resilient software.

&nbsp;

***A unit test is a type of test that is conducted on small, functional aspects of code.  It's the lowest level of software testing and is interested in the logic and operation of only a single function in your code.*** That's not to say you can't perform multiple tests at the same time.  Computers are great at performing repetitive tasks, but the goal is for each test to be on one function at a time so that the testing is specific and consistent.  ***Remember that a unit is the smallest testable part of your software.***

&nbsp;

There are other types of testing that you may hear about, such as ***integration testing*** and ***functional testing***.  ***The differences between these types of testing and unit testing come down to the scope of the test***.  ***As mentioned, a unit test is testing a small piece of code, such as a method or function.  An integration test, on the other hand, tests how one software component works with the rest of the application.***  It is often used when the modules of an application are developed by separate teams or when a distributed application has multiple components working together.  ***A function test(also called an end-to-end test) is the broadest in scope from a testing perspective.  This is where the entire system is tested against the function specification and requirements of the software application.***

&nbsp;

> ***Key Topic***

&nbsp;

Python has a built-in unit test module, named unittest.  This module is quite full featured and can support a tremendous number of test cases.  There are other testing modules that you can use, such as Nose and PyTest, but for the purpose of the 200-901 DevNet Associate DEVASC exam, you need to know how unittest works.  In order to use unittest, you need a bit of code to test.  Here is a simple function that computers the are of a circle:

&nbsp;

```
from math import pi

def area_of_circle(r):

    return pi*(r**2)
```

&nbsp;

You import from the math module the **pi** method to make it a little easier.  A function is defined with the name **area_of_circle** that takes the argument **r**.  The function computers the radius of a circle and returns the value.  This is very simple, but what happens if the function is called, and odd values are passed to it?  You guessed it: lots of errors.  So in order to test his function, you can create a unit test.

&nbsp;

Certain conventions must be followed for a unit test.  While you can create a unit test that has the code that you want to test all in the same file, it's a better idea to use object-oriented principles when building tests.  In this case, the function you want to test is saved as areacircle.py, so following good practices you should name your unit test file test_areacircle.py.  This makes it easy to differentiate the two.  You should also import the unittest module, and from areacircle you can import the **area_of_circle** function.  Import the **pi** method from math so that you can test your results.  The **import** statements would look as follows:

&nbsp;

```
import unittest
from areacircle import area_of_circle
from math import pi
```

&nbsp;

Next, you need to create a class for your test.  You can name it whatever you want, but you need to inherit **unittest.TestCase** from the unittest module.  This is what enables the test function methods to be assigned to your **test** class.  Next, you can define your first test function.  In this case, you can test various inputs to validate that the math in your function under **test** is working as it should.  You will notice a new method called **assertAlmostEqual()**, which takes the function you are testing, passes a value to it, and checks the returned value against an expected value.  You can add a number of tests to this function.  This is what the test now looks like with the additional code:

&nbsp;

```
class Test_Area_of_Circle_input(unittest.TestCase):

    def test_area(self):

        # Test radius >= 0

        self.assertAlmostEqual(area_of_circle(1), pi)
        self.assertAlmostEqual(area_of_circle(0), 0)
        self.assertAlmostEqual(area_of_circle(3.5), pi * 3.5**2)
```

&nbsp;

You can go to the directory where these two scripts reside and enter **python -m unittest test_areacircle.py** to run the test.  If you don't want to type all that, you can add the following to the bottom of the **test_areacircle.py** script to allow the unittest module to be launched when you run the test script:

&nbsp;

```
if __name__ == '__main__':

    unittest.main()
```

&nbsp;

All this does is check to see if the script is being run directly (because the **__main__** special case is an attribute for all Python scripts run from the command line) and call the **unittest.main()** function.  After executing the function, you should see the following results:

&nbsp;

```
.
-------------------------------------------------------------------
Ran 1 test in 0.000s

OK
```

&nbsp;

The dot at the top shows that 1 test ran (even though you had multiple checks in the same function) to determine whether the values submitted produced an error.  Since all are valid for the function, teh unit test came back successful. 

&nbsp;

Now you can check to see if a negative number causes a problem.  Create a new function under your previous **test_area** function.  Name this function **test_values**.  (The test at the beginning is required, or unittest will ignore the function and not check it.)  You can use the **assertRaises** check, which will look for a **ValueError** exception for the function **area_of_circle**, and pass it a value of **-1**.  The following function can be added to your code:

&nbsp;

```
def test_values(self):

    # Test that bad values are caught

    self.assertRaises(ValueError, area_of_circle, -1)
```

&nbsp;

Below shows the output of the test with this additional check.

&nbsp;

> ***Key Topic***

&nbsp;

```
.F
=========================================
FAIL: test_values (__main__.Test_Area_of_Circle_input)
----------------------------------------------------------------------
Traceback (most recent call last):
  File "/Users/chrijack/Documents/ccnadevnet/test_areacircle.py", line 14, in
  test_values
    self.assertRaises(ValueError, area_of_circle, -1)
AssertionError: ValueError not raised by area_of_circle

----------------------------------------------------------------------
Ran 2 tests in 0.001s

FAILED (failures=1)
```

&nbsp;

The first check is still good, so you can see one dot  at the top, but next to it is a big **F** for fail.  You get a message saying that the **test_value** function is where it failed, and see that your original function did not catch this error.  This means that the code is giving back results.  A radius of **-1** is not possible, but the function gives you the following output:

&nbsp;

```
>>> area_of_circle(-1)
3.141592653589793
```

&nbsp;

> ***Key Topic***

&nbsp;

To fix this, you go back to your original function and add some error-checking code.  You use a simple **if** statement to check for a negative number, and you raise a **ValueError** with a message to the user about invalid input:

&nbsp;

```
from math import pi

def area_of_circle(r):

    if r < 0:

        raise ValueError('Negative radius value error')

    return pi*(r**2)
```

&nbsp;

Now when you try the test from the interpreter, you see an error raised:

&nbsp;

```
>>> area_of_circle(-1)

Traceback (most recent call last):

  File "<pyshell>", line 1, in <module>

  File "/Users/chrijack/Documents/ccnadevnet/areacircle.py",
  line 5, in area_of_circle

    raise ValueError('Negative radius value error')

ValueError: Negative radius value error
```

&nbsp;

If you rerun the unit test, you see that it now passes the new check because an error is raised:

&nbsp;

```
..
-------------------------------------------------------------------
Ran 2 tests in 0.000s
```

&nbsp;

This simple example barely scratches the surface of how you can use unit testing to check your software, but it does show you how a unit test is constructed and, more importantly, what it does to help you construct resilient code.  Many more tests can be conducted; see the documentation at https://docs.python.org/3/library/unittest.html.