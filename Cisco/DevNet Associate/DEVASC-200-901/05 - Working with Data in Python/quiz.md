#   "Do I Know This Already?" Quiz

&nbsp;

<ol>
    <li>When parsing a text file, what determines the end of a line?
        <ol type='a'>
            <li>Return code
            <li>Nothing; Python sees it as one big string
            <li>\n or EoF
            <li>All of the above
        </ol>
        <br />
        <details>
            <summary><strong><i>Answers</i></strong></summary>
            C.  The end-of-line is the last character of a line of text before the text wraps to the next line.  This is identified as \n or as EoF (end of file).
        </details>
    <br />
    <li>What syntax would you use to open a text file to be written to?
        <ol type='a'>
            <li>data = open("text.txt", "w")
            <li>data = load("text.txt", "w")
            <li>load("text.txt", "w")
            <li>open("text.txt", "w")
        </ol>
        <br />
        <details>
            <summary><strong><i>Answers</i></strong></summary>
            A.  In order to open a file for writing, you need to use the <strong>open()</strong> function and assign it to a file handler variable - in this case, data.  In addition, you need to pass the name tof the file and tell Python that you want to allow write access to it (using "w").
        </details>
    <br />
    <li>Which of the following do you use to write to a CSV file in Python?
        <ol type='a'>
            <li>with open("text.csv", "a") as filehandle:
                <br />csv_writer = csv.write(filehandle)
                <br />csv_writer.writerow(data)
            <li>with open("text.csv", "a") as filehandle:
                <br />csv_writer.writerow(data)
            <li>with open("text.csv", "a") as filehandle:
                <br />csv_writer = csv.writer(filehandle)
                <br />csv_writer.writerow(data)
            <li>with open("text.csv", "a") as filehandle:
                <br />csv_writer = csv.writer(f)
                <br />csv_writer.writerow(data)
        </ol>
        <br />
        <details>
            <summary><strong><i>Answers</i></strong></summary>
            C.  Using the <strong>with open</strong> combo to the text.csv file, you map it to the filehandle object.  Map <strong>csv_writer</strong>, which is just another Python object, to the <strong>csv.writer(filehandle)</strong> function.  Next, you write your data to the CSV file by calling the <strong>.writerow</strong> method.
        </details>
    <br />
    <li>Which module is imported to read XML data?
        <ol type='a'>
            <li>xmlm
            <li>xmltodict
            <li>XMLParse
            <li>None of the above
        </ol>
        <br />
        <details>
            <summary><strong><i>Answers</i></strong></summary>
            B.  The xmltodict module reads XML data.
        </details>
    <br />
    <li>Which methods are used for converting a native JSON file to Python and then back to JSON?
        <ol type='a'>
            <li><strong>load()</strong> and <strong>dump()</strong>
            <li><strong>loads()</strong> and <strong>dump()</strong>
            <li><strong>loads()</strong> and <strong>dumps()</strong>
            <li><strong>load()</strong> and <strong>dumps()</strong>
        </ol>
        <br />
        <details>
            <summary><strong><i>Answers</i></strong></summary>
            A.  To load a native JSON file into a Python string object, you use <strong>loads()</strong>, which stands for load string, and to convert a Python string into native JSON, you use <strong>dump()</strong>.
        </details>
    <br />
    <li>What does YAML stand for?
        <ol type='a'>
            <li>Yet Another Markup Language
            <li>YAML Ain't Markup Language
            <li>The name of its creator
            <li>None of the above
        </ol>
        <br />
        <details>
            <summary><strong><i>Answers</i></strong></summary>
            B.  YAML stands for YAML Ain't Markup Language
        </details>
    <br />
    <li>What is the syntax for error handling in Python?
        <ol type='a'>
            <li><strong>try-except-else-finally</strong>
            <li><strong>raise ErrorMessage</strong>
            <li><strong>assertErrorValue</strong>
            <li>All of the above
        </ol>
        <br />
        <details>
            <summary><strong><i>Answers</i></strong></summary>
            A.  Error handling in Python can be conducted by using a <strong>try-except-else-finally</strong> block.
        </details>
    <br />
    <li>When does the <strong>finally</strong> block execute?
        <ol type='a'>
            <li>After the <strong>try</strong> block is successful
            <li>After the <strong>except</strong> block
            <li>At the end of every <strong>try</strong> block
            <li>When are error code stops the <strong>else</strong> block
        </ol>
        <br />
        <details>
            <summary><strong><i>Answers</i></strong></summary>
            C.  <strong>finally</strong> is executed every time the code runs through the <strong>try</strong> block.  It is often used to clean up variables or alert the user to a success or failure event.
        </details>
    <br />
    <li>Test-driven development requires that developers:
        <ol type='a'>
            <li>Create a unit test for every bit of code they write
            <li>Know how to use DevOps tools for automated testing
            <li>Create a simple test that fails and then write code that allows the test to succeed
            <li>Completely unnecessary in an Agile development shop
        </ol>
        <br />
        <details>
            <summary><strong><i>Answers</i></strong></summary>
            C.  Test-driven development focuses on writing code that allows a previously written test (that naturally fails since no code was written) to succeed.
        </details>
    <br />
    <li>What is the difference between a unit test and an integration test?  (Choose two.)
        <ol type='a'>
            <li>An integration test is for validation of how different parts of the application work together.  
            <li>An integration test verifies that the application operates as expected.
            <li>A unit test verified API functionality.
            <li>A unit test is most specific in scope and tests small bits of code.
        </ol>
        <br />
        <details>
            <summary><strong><i>Answers</i></strong></summary>
            A, D.  An integration test is for APi verification, and a function test verified that your application meets the agreed-upon requirements of how it should operate.
        </details>
    <br />
    <li>Which class is inherited as part of a unit test?
        <ol type='a'>
            <li><strong>unittest.testcase</strong>
            <li><strong>unittest.TestCase</strong>
            <li><strong>unittest</strong>
            <li><strong>TestCase</strong>
        </ol>
        <br />
        <details>
            <summary><strong><i>Answers</i></strong></summary>
            B.  unittest.TestCase is a special class that is used to access the unittest module's capabilities.
        </details>
</ol>