#   "Do I Know This Already?" Quiz

&nbsp;

<ol>
    <li>What is the appropriate way to create a virtual environment for Python 3?
        <ol type='a'>
            <li><strong>python3 -virtual myvenv</strong>
            <li><strong>python3 virtual myvenv</strong>
            <li><strong>python3 -m vrt myvenv</strong>
            <li><strong>python3 -m venv myvenv</strong>
        </ol>
        <br />
        <details>
            <summary><strong><i>Answers</i></strong></summary>
            D.  The correct command is <strong>python3 -m (for module) venv myvenv</strong> (which can be whatever you choose to name your virtual environment)
        </details>
    <br />
    <li>What command is used to install Python modules from PyPI?
        <ol type='a'>
            <li><strong>pip load</strong> packagename
            <li><strong>pip install</strong> packagename
            <li><strong>python3 -m pip install</strong> packagename
            <li><strong>python3 -t pip install</strong> packagename
        </ol>
        <br />
        <details>
            <summary><strong><i>Answers</i></strong></summary>
            B, C.  PyPI is a repository that holds thousands of Python modules that you can import.  To install it, you can use python3 -m (module) pip install and the name of the package you want.  You can also directly install it with the pip command.
        </details>
    <br />
    <li>What is the standard for indention in Python?
        <ol type='a'>
            <li>One space for each block of code
            <li>Four spaces for each block of code
            <li>One tab for each block of code
            <li>One tab and one space per block of code
        </ol>
        <br />
        <details>
            <summary><strong><i>Answers</i></strong></summary>
            B.  PEP 8 is the style guide for Python syntax, and it specifies four spaces for each block of code.  Tabs will work, and your editor may actually convert them automatically for you, but it is a good practice to follow the standard.
        </details>
    <br />
    <li>How are comments in Python denoted?
        <ol type='a'>
            <li>// on each line you want to make a comment
            <li># or '" quotation marks encompassing multiline comments
            <li>/* comment */
            <li>@$ comment %@
        </ol>
        <br />
        <details>
            <summary><strong><i>Answers</i></strong></summary>
            B.  Comments are specified by the # or three single quotes '''.  The benefit of using the single quotes is that you can write multiline text.
        </details>
    <br />
    <li>Which of the following are mutable data types?  (Choose two.)
        <ol type='a'>
            <li>Lists
            <li>Dictionary
            <li>Integers
            <li>Tuples
        </ol>
        <br />
        <details>
            <summary><strong><i>Answers</i></strong></summary>
            A, B.  Lists and dictionaries are both mutable, or changeable, data types.  Integers and tuples must be replaced and can't be edited, which makes them immutable.
        </details>
    <br />
    <li>Which of the following would create a dictionary?
        <ol type='a'>
            <li>a= (" name","chris","age",45)
            <li>a= dict()
            <li>a= [name, chris, age, 45]
            <li>a= {" name":"chris", "age": 45}
        </ol>
        <br />
        <details>
            <summary><strong><i>Answers</i></strong></summary>
            B, D.  You can create an empty dictionary object by assigning the function <strong>dict()</strong> to a Python object (in this example, <strong>a</strong>).  you can insert dictionary values as well by using braces, <strong>{}</strong>, and key:value pairs that you assign to an object.
        </details>
    <br />
    <li>What data type does the <strong>input()</strong> function create when assigned to a variable?
        <ol type='a'>
            <li>List
            <li>Raw
            <li>String
            <li>An auto typed one
        </ol>
        <br />
        <details>
            <summary><strong><i>Answers</i></strong></summary>
            C.  The <strong>input()</strong> function by default creates a string data type.
        </details>
    <br />
    <li>Which print statement is valid for Python 3?
        <ol type='a'>
            <li>print 'hello world'
            <li>print(‘hello world”)
            <li>print(hello, world)
            <li>print(‘‘‘hello world’’’)
        </ol>
        <br />
        <details>
            <summary><strong><i>Answers</i></strong></summary>
            D.  the only one that is valid as is would be <strong>print('''hello world''')</strong>.  <strong>print(hello, world)</strong> would be valid only if there were two variables named <strong>hello</strong> and <strong>world</strong>; otherwise, it would produce an error.  Since you don't know in this case whether these variables exist, <strong>print('''hello world''')</strong> is the correct answer.
        </details>
    <br />
    <li>How do <strong>if</strong> statements operate?
        <ol type='a'>
            <li><strong>If</strong> evaluates a variable against a condition to determine whether the condition is true.
            <li><strong>If</strong> uses Boolean operators.
            <li>An <strong>if</strong> statement needs to end with :.
            <li>All of the above are correct.
        </ol>
        <br />
        <details>
            <summary><strong><i>Answers</i></strong></summary>
            D.  All of the statements are correct regarding how an <strong>If</strong> statement operates in Python.
        </details>
    <br />
    <li>Which statements are true about the <strong>range()</strong> function?  (Choose two.)
        <ol type='a'>
            <li>The <strong>range()</strong> function iterates by one, starting at 0, up to but not including the number specified.
            <li>The <strong>range()</strong> function iterates by one, starting at 1, up to the number specified.
            <li>A <strong>range()</strong> function cannot count down, only up.
            <li>A <strong>range()</strong> function can count up or down, based on a positive or negative step value.
        </ol>
        <br />
        <details>
            <summary><strong><i>Answers</i></strong></summary>
            A, D.  The <strong>range()</strong> function in Python allows you to set a range that is up to but not including the number specified.  If you want to increment to 10, for example, you need to provide the number 11.  A range can also count up or down based on the sign of the number provided.
        </details>
</ol>