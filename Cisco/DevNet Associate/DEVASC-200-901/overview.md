#   01 - Introduction to Cisco DevNet Associate Certification

Reasons for certification:

-   Highlighting skills to employers
-   Highlighting skills to industry peers
-   Providing value to employers
-   Providing credibility
-   Providing a baseline of understanding
-   Building confidence
-   Enabling career advancement
-   Increasing salary

&nbsp;

Five levels of accreditation for Cisco career certifications:

1.  Architect
2.  Expert
3.  Professional
4.  Associate
5.  Entry

&nbsp;

DevNet menu options (https://developer.cisco.com):

-   Discover
-   Technologies
-   Community
-   Support
-   Events

&nbsp;

#   02 - Software Development and Design

##  **Software Development Lifecycle (SDLC)**

&nbsp;

Stages of ***Software Development Lifecycle (SDLC)***:

-   Stage 1 - Planning
-   Stage 2 - Defining
-   Stage 3 - Designing
-   Stage 4 - Building
-   Stage 5 - Testing
-   Stage 6 - Deployment

&nbsp;

Some of the most popular SDLC models:

-   Waterfall
-   Lean
-   Agile
-   Interactive model
-   Spiral model
-   V model
-   Big Bang model
-   Prototyping models

*For the DEVASC exam you only need to know about **Waterfall**, **Lean**, and **Agile**.*

&nbsp;

### ***Waterfall***

Waterfall is based on the construction industry approach and is one of the most popular SDLC approaches.

Waterfall is a serial approach to software development that is divided into phases:

-   Requirements / analysis
-   Design
-   Coding
-   Testing
-   Maintenance

Shortcomings:

-   Fixed design means changes cannot be made after the analysis and design phase.
-   Value is not achieved until 00% of the project is complete.
-   Quality suffers in order to complete the project in time.

&nbsp;

### ***Lean***

From the ***Toyota Production System (TPS)*** which is based on the following concepts:

-   **Elimination of waste**:  If something doesn't add value to the final product, get rid of it.  There is no room for waste.
-   **Just-in-time**:  Don't build something until the customer is ready to buy it.  Excessive inventory wastes resources.
-   **Continuous improvement (Kizan)**:  Always improve your process with lessons learned and communication.

*Lean led to Agile*

&nbsp;

### ***Agile***

Agile is an application of Lean principles to software development.

"Manifesto for Agile Software Development".

With Waterfall a project is not "finished" and deployable until the very end.  With Agile, the time frame is changed: Agile uses smaller time increments (often 2 weeks), or "***sprints***," that encompass the full process of but on a much smaller aspect of an application.

With Agile you can keep adding value immediately and adapt to change.  

&nbsp;

##  **Common Design Patterns**

&nbsp;

Design patterns to know for DEVASC:

-   ***Model-View-Controller (MVC)***
-   ***Observer patterns***

&nbsp;

### ***Model-View-Controller (MVC) Pattern***

Model-View-Controller (MVC) pattern was one of the first design patterns to leverage the ***separation of concerns (SoC) principle***.

The SoC principle is used to decouple an applications' interdependencies and functions from its other parts.  The goal is to make the various layer sof the application - such as data access, business logic, and presentation (to the end user) - modular.

The classic MVC pattern has three main parts:

-   **Model**:  Responsible for retrieving and manipulating data.  Conducts all data operations such as select, insert, update, an delete operations.  Receives instructions from the controller.
-   **View**:  What end users see.  Communicates with controller by sending data or receiving output from the model through the controller.  Primary function is to render data.
-   **Controller**:  Intermediary between what the user sees and the backend logic that manipulates the data.  Receive requests from the user via the view and pass those requests on to the model.

&nbsp;

### ***Observer Pattern***

*The Observer pattern was created to address the problem of sharing information between one object to many other objects*.

The Observer Pattern consists of only two logical components:

-   **Subject**:  Subject refers to the object state being observed - i.e., the data that is to be synchronized.  Subject has a registration process that allows other components of an application or remote system to subscribe to the process.  
-   **Observer**:  Observer is the component that registers with the subject to allow the subject to be aware of the observer and how to communicate to it.  The only function of the observer is to synchronize its data with the subject when called.  The observer **does not** use a polling process, which can be very inefficient with a large number of observers registered to a subject.  Updates are **push only**.

*In short:  A single Subject can have multiple Observers.  When an Event Happens on the Subject, it will push a notify() to the Observers.*

***Observer pattern is often used for communications between the model and the view in the MVC pattern.***

&nbsp;

##  **Linux Bash**

&nbsp;

BASH stands for Bourne Again Shell

BASH supports ***piping*** (which involves feeding output from one command as the input of another command), ***variables***, ***evaluation of conditions***, and ***interation*** (repeating processing of a command with **if** statements).  You also have a ***command history*** as part of the shell.

To access help for any command, type **man** (short for manual) and then the command.

Temporarily upgrade your privileges by prepending the **sudo** command before you execute a command.

**piping** allows you to string together commands.  The **cat** command displays the contents of a file to the screen.  If it can't fit on a single screen, you can pipe the output to the **more** command.

```bash
$ cat weather.py | more
```

&nbsp;

### ***Directory Navigation***

UNIX-based file system has a directory tree (upside down tree) structure.  The top of the tree is the **root**, and you use the forward slash (/) to refer to root.

Everything executed in UNIX is in relationship to root.  

To execute a file in the directory you are in, you use **./filename.sh**, where the leading **.** is an alias for the current directory.

&nbsp;

**cd**

The **cd** command is used to change directories and move around the file system.

| Command | Use |
| -- | -- |
| **$ cd /** | Changes directory to the root directory |
| **$ cd /home/username** | Changes directory to the /home/username directory |
| **$ cd test** | Changes directory to the test folder |
| **$ cd ..** | Moves up one directory |

&nbsp;

**ls**

The **ls** command gives you a list of the current directory.  

Without parameters it doesn't show hidden files.  Anything starting with **.** does not show up in a standard directory listing, and you need to use the **-a** flag to see all files, including hidden files.

The **-l** flag shows the permissions and the user and group that own the file or directory.

You can use the wildcard * to list specific filename values (ex **ls \*test\***, would match both 1test and test1).

| Command | Use |
| -- | -- |
| **$ ls** | Lists files and directories in current working directory |
| **$ ls -a** | Lists everything in the current directory, including hidden files |
| **$ ls /home/username** | Lists everything in the /home/username directory |
| **$ ls -l** | Lists permissions and user and group ownership |
| **$ ls -F** | Displays files and directories and detonates which are which |

&nbsp; 

**mkdir**

Create a directory with the **mkdir** command.

| Command | Use |
| -- | -- |
| **$ mkdir test** | Makes a new directory called test in the current working directory if you have permission |
| **$ mkdir /home/username/test** | Makes a new directory called test at /home/username/test |

&nbsp;

### ***File Management***

**cp**
The **cp** command is to copy a file or folder someplace.  Makes an identical duplicate - does not delete the source file.  

When copying the contents of a folder, you need to use the **-r**, or recursive, flag.

| Command | Use |
| -- | -- |
| **$ cp sydney.txt sydney2.txt** | Copies a file called sydney.txt from the current directory and names the copy sydney2.txt |
| **$ cp /home/username/sydney.txt ~/sydney2.txt** | Copies a file as described above but using the full path and the home directory path |
| **$ cp -r folder folder.old** | Copies a folder |

&nbsp;

**mv**

The **mv** command moves a file or folder from one directory to another or to rename files or folders from the command line (there is no dedicated renaming function).

The **mv** command takes a source and destination, just as **cp**.

The **-i** flag creates an interactive option prompt when moving files that exist at the destination.

The **-f** flag forces the move and overwrites any files at the destination.

Wildcards also work to select multiple source files or directories.

| Command | Use |
| -- | -- |
| **$ mv caleb.txt calebfinal.txt** | Renames a file called caleb.txt to calebfinal.txt |
| **$ mv /home/username/caleb.txt ~calebfinal.txt** | Renames a file as described above but using full paths |
| **$ mv -i \* /home/username/new/** | Moves all files and directories in the current folder to a directory called new |

&nbsp;

**rm**

To delete a file or directory, use the **rm** command.  

If you want to delete a folder that is not empty, you can use the **-rf** flag to force deletion.

| Command | Use |
| -- | -- |
| **$ rm test.txt** | Deletes the file test.txt in the current working directory |
| **$ rm -rf test** | Forces the deletion of the folder test and everything in it |

&nbsp;

**touch**

The **touch** command creates a file and/or changes the timestamps on a file's access without opening it.

Used for when you want to create a file but don't want to put any content in it.

| Command | Use |
| -- | -- |
| **$ touch emptyfile.txt** | Creates an empty file named emptyfile.txt | 
| **$ touch file{1..20}.txt** | Bulk creates files from file1.txt to file20.txt |

&nbsp;

**cat**

The **cat** command, which stands for ***concatenate***, allows you to view or create files and also pipe to other commands.

| Command | Use |
| -- | -- |
| **$ cat file1.txt** | Displays the contents of file1.txt |
| **$ cat file1.txt \| more** | Displays the contents of file1.txt and pipes the output to **more** to add page breaks |
| **$ cat >file2.txt** | Sends a user's typed or copied contents from the command line to file2.txt |

>   **Note**
>   Research **cat** more.

&nbsp;

### ***Environment Variables***

You can view all currently set environment variables by entering the **env** command.

Since there are more entries than room to display on a single terminal page, you can pipe the results to the **more** command.

| Command | Use |
| -- | -- |
| **$ env \| more** | Shows all environment variables with page breaks |

When viewing environment variables a lot of keywords will have the = sign tied to values.  One environment variable that you use every time you execute a command is the PATH variable.  This is where your shell looks for executable files.  If you can't execute a newly added command, it's more than likely the place where the command was copied is not listed in your PATH.

To view any variable value, you can use the **echo** command and the variable you want to view.  You also need to tell BASH it's a variable by using the **$** in front of it:

```bash
echo $PATH

/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin:/Applications/VMware
Fusion.app/Contents/Public:/opt/X11/bin
```

To add a new value to the PATH variable, you can't just type **$PATH=/new_directory** because the OS reads the environment variables only when the terminal session starts.  To update the environment variables, you need to use the **export** command.  This command appends additional paths to BASH and exists for the duration of the session.  Must have **:** or **,** in front of your new value, depending on operating system.

```bash
$ export PATH=$PATH:/Home/chrijack/bin
```

When the terminal session ends, changes are not saved.  To retain changes, write the path to **.bashrc** (or **.zshrc** if using Z shell) profile settings.

```bash
$ echo "export PATH=$PATH:/Home/chrijack/bin" >> .bashrc
```

This becomes active once you close the current session or force reload the variable.  The **source** command can be used to reload the variables from the hidden configuration file **.bashrc**.

```bash
$ . ~/.bashrc
```

&nbsp;

##  **Software Version Control (SVC)**

&nbsp;

The term ***version control*** is used to describe the process of saving various copies of a file or set of files in order to track changes made to those files.

Also called ***revision control*** or ***source control***, but it all falls under the topic of ***software configuration management***.

&nbsp;

### ***Git***

Git was created by Linus Torvalds as an alternative to the SCM system BitKeeper.

&nbsp;

### ***Understanding Git***

Git is a distributed version control system with a multi-tree structure.  Git keeps track of three main structures or trees:

-   **Local workspace**:  this is where you store source code, files, binaries, images, documentation, and whatever else you need.
-   **Staging area**:   This is an intermediary storage area for items to be synchronized (changes and new items).
-   **Head** or **local repository**:   This is where you store all committed items.

Git file status lifecycle includes the following statuses:

-   **Untracked**:  When you first create a file in a directory that Git is managing, it gets the untracked status.  Git sees the file but does not perform any type of version control operation on nit.  If you want Git to start tracking a file, you have to explicitly tell it to with the **git add** command; the status of the file then changes to tracked.
-   **Unmodified**:  A tracked file in Git is included as part of the repository, and changes are watched.  This status means Git is watching for any file changes that are made, but it doesn't see any yet.
-   **Modified**:   Whenever you add some code or make a change to the file, Git changes the status of the file to modified.  You tell Git that you are ready to add a change (modified) file to the index or staging area by issuing the **git add** command again.
-   **Staged**:  Once a file is added to the index, Git needs to bundle the changes and update the local repository.  This process is called staging, and done through **git commit**.  The file is then moved back to the track status, and the process starts over again.

*Untracked (use 'git add') => Unmodified (modify it) => Modified ('git add' again) => Staged ('git commit')*

**git status** will show the file status.

&nbsp;

### ***Using Git***

Git commands have two different flavors:

-   The standard user-friendly commands are called ***"porcelain"***.
-   The more complicated inner workings of Git manipulating commands care called ***"plumbing"***.

At its core, Git is a ***content-addressable file system*** with a version control system layered on top.  For DEVASC you need to know Git at a functional level (porcelain).

&nbsp;

### ***Cloning/Initiating Repositories***

Git operates on a number of processes.  The first of these processes is defining a local repository with either **git clone** or **git init**.  

```git clone (url to repository) (directory to clone to)```

If there is an existing repository to work on, you use **git clone**.  

To create a new repository, you need to create a directory.  **git init** can be supplied with a directory name as an option to create one for you.

```git init newrepo```

This creates an empty repo.

&nbsp;

### ***Adding and Removing Files***

The following commands add files to an index:

-   **git add .** or **-A**:  Adds everything in the entire local workspace.
-   **git add (filename)**:  Adds a single file

The best way to remove a file or directory from Git is to use the **git rm** command:

```git rm (-r) (-f) (folder/file.py)```

This command removes a file or directory and syncs it with the index in one step.  **-r** option to remove recursively (to remove directory that is not empty).  If you add a file to Git and later want to remove it, you use the **-f** option to force removal from the index.  This is only required if you haven't committed the changes to the local repository.

&nbsp;

**git mv** command to move or rename a file, directory, or symbolic link:

```git mv (-f) (source) (destination)```

This updates the index at the same time, so there is no need to issue **git add**.  You can use the **-f** argument if you are trying to overwrite an existing file or directory where the same target exists.

&nbsp;

### ***Committing Files***

Committing a file moves it from the index or staging area to the local copy of the repository.  Git doesn't send entire updates; just changes.

```git commit [-a] [-m] <"your commit message">```

**-a** option adds any changes you make to your files to the index.  It's a shortcut instead of using **git add -A**, *it works only for files already added at some point before in their history; new files need to be explicitly added to Git tracking*.

&nbsp;

### ***Pushing and Pulling Files***

To allow Git to use a remote repository, you have to configure Git with some information.

When you use the command **git clone** on a repository, it automatically adds the remote repository connection information via the URL entered with the command.

When using **git init**, you need to enter information to find the remote location for the server with the **git remote add** command:

```git remote add (name) (url)```

**git remote -v** shows which remote repository is configured.

```
# git remote add origin https://github.com/chrijack/devnetccna.git

# git remote -v

origin  https://github.com/chrijack/devnetccna.git  (fetch)
origin  https://github.com/chrijack/devnetccna.git  (push)
```

&nbsp;

**git remote rm** command removes remote tracking:

```git remote rm (name)```

&nbsp;

**git push** syncs your local repository with the remote repository:

```git push (remotename) (branchname)```

&nbsp;

**git pull** syncs any changes made on the remote repository and brings your local repository up to date:

```git pull (remotename) (branchname)```

**git pull** does two things:

-   fetches the latest version of the remote master repository
-   merges it into the local repository

Conflicts are handled just like **git merge** conflicts are (shown later).

&nbsp;

### ***Working with Branches***

Git keeps a history of every commit, called a ***snapshot***.

Integrity is ensured with SHA-1 hash.  This hash is a 40-character string tied to each and every commit.  The hash is displayed using **git log**.  The first entry is the current commit state (HEAD).

&nbsp;
To add a Git branch use the command **git branch** and supply a new branch name:

```git branch (-d) <branchname> [commit]```

Alternatively, you can specify a commit by a tag or commit hash.  By default, Git selects the latest commit.

You can delete a branch with the **-d** argument.

&nbsp;

Display the current branch with **git branch**.

The * next to a branch name shows the current branch you are in.

&nbsp;

To move branches and change your working directory, you use **git checkout**:

```git checkout [-b] (branchname or commit)```

The **-b** argument is for combining the **git branch** command, by creating and checking out (switching to) at the same time.

&nbsp;

### ***Merging Branches***

**git merge** is used to handle the combining of multiple branches into one.

```git merge (branch to merge with current)```

"Fast-forward" in the output refers to updating past the changes in the branch.

&nbsp;

### ***Handling Conflicts***

&nbsp;

### ***Comparing Commits with diff***

The **diff** command compares files and text to see which you want to use if there are multiple options.  It takes two sets of inputs and outputs the differences or changes between them:

```git diff [--stat] [branchname or commit]```

**git diff** looks at the history of your commits, individual files, branches, and other Git resources.  

-   **git diff**:  This command highlights the difference between your working directory and the index (that is, what isn't yet staged).
-   **git diff --cached**:  Shows any changes between the index and last commit.
-   **git diff HEAD**:  Shows the difference between most recent commit and current working directory.  Useful for seeing what will happen when you commit.

Use ONLY **q+enter** to exit.

**git diff (branchname)** lets you see the differences between a file in the branch you are currently in and one that you supply as an argument.

&nbsp;

##  **Conducting Code Review**

&nbsp;

***The intent behind a code review process is to take good code and make it better by showing it to others and having them critique it and look for potential errors.***

Benefits of code review:

-   It helps create higher-quality software.
-   It enables team cohesion and helps delivery software projects on time.
-   It helps find defects and inefficient code that unit tests and functional tests might miss, making software more reliable.

&nbsp;

#   03 - Introduction to Python

&nbsp;

##  **Getting Started with Python**

Python virtual environments fix the issue of different module version compatibility by making sure the right modules are loaded for the application you're working with.

To use a virtual environment, launch Python 3 with the **-m** argument to run the **venv** module.  You must supply a name for your virtual environment, which will also be the directory name.

Next you activate the virtual environment by using the **source** command.

```bash
#   MacOS or Linux

python -m venv myvenv

source myvenv/bin/activate
```

```bash
#   Windows

C:\py -3 -m venv myvenv

C:\myvenv\Scripts\activate.bat
```

You will see your virtual environment name in parentheses at the beginning of your command prompt:

```(myvenv)$```

This indicates you are running Python in your virtual environment.  

&nbsp;

To turn off the virtual environment, type **deactivate**.

&nbsp;

To install new module for Python, you use **pip**, which pulls from the PyPi repository.

<pre>
pip install <i>packagename</i>
</pre>

&nbsp;

The **pip** command also offers a search function that allows you to query the package index:

```pip search "search value"```

The output includes the name, version, and a brief description of what the package does.

&nbsp;

To install a specific version, you specify a version number or a minimum version:

```
pip install package=1.1.1.      To install a specific version
pip install package>=1.0        To install a version greater than or equal to 1.0
```

&nbsp;

A **requirements.txt** file included with your code gives **pip** a set of packages that need to be installed, and you can issue the following command to get them loaded:

```pip install -r requirements.txt```

The requirements.txt file is just a list that maps Python package names to versions.  Example:

```text
ansible=2.6.3
xmltodict=0.2.0
```

&nbsp;

The **freeze** command will automatically populate the requirements.txt file:

```pip freeze > requirements.txt```

&nbsp;

##  **Understanding Python Syntax**

&nbsp;

Python core philosophy (The Zen of Python):

-   Beautiful is better than ugly.
-   Explicit is better than implicit.
-   Simple is better than complex.
-   Complex is better than complicated.
-   Readability counts.

Python is a scripted language. 

Easiest way to start with Python code is to enter **python3**.

&nbsp;

Within Python code, **whitespace matters**.  Python uses indention to separate blocks of code.

You can use both spaces and tabs in Python 2, but Python 3 will return a syntax error.

The standard for Python from the PEP 8 style guide is to use four spaces or indention before each block of code.  One space will work, but it's hard to align.

&nbsp;

Comments in Python are created by **#** or a string of ***three quotation marks*** (either single or double).

&nbsp;

##  **Data Types and Variables**

&nbsp;

### ***Variables***

A variable is a label that maps to a Python object stored somewhere in memory.

Python auto types variables.

Rules for variable names:

-   A variable name must start with a letter or the underscore character.
-   A variable name cannot start with a number.
-   A variable name can only consist of alphanumeric characters and underscores (A-Z, 0-9), and _)
-   A variable name is case sensitive (so Value and value are two different variable names).

To assign a variable you just set the variable name equal to the value you want, as shown below:

| Variable | Type |
| -- | -- |
| Pip = "cat" | Variable assigned to a string |
| Age = 9 | Variable assigned to an integer |
| Chill = True | Variable assigned to a Boolean |
| Variable 1 = Variable 2 | Variable assigned to another Variable |

&nbsp;

### ***Data Types***

Everything in Python is an object.

When the object is created, it is assigned a type.  With these types, you are allowed to either change the object (mutable) or not allowed ot change the object (immutable) after it has been created.

This doesn't mean the variables are not able to change; it means that most of the basic data types are not able to be modified but need to be replaced (or ***assigned***, in Python terms) with another value.  *For example, you can't just add a character at the end of the string, you have to reassign the whole string to change it.*

Common data types:

| Name | Type | Mutable | Description |
| -- | -- | -- | -- |
| Integer | int | No | Whole numbers, such as 6,600, and 1,589 |
| Boolean | bool | No | Comparison value, either True or False |
| String | str | No | Sequence of characters delimited by quotes, such as "Cisco", 'Piper', and "2000" |
| List | list | Yes | Ordered sequence of objects, such as [10, "DNA", 19.8] |
| Tuple | tup | No | Ordered sequence of immutable objects, such as (10, "DNA", 19.8) |
| Dictionary | dict | Yes | Unordered key:value pairs, such as {"key1":"value1", "name":"Pip"} |
| Set | set | Yes | Unordered collection of unique objects, such as {"a", "b"} |

&nbsp;

### ***Integers, Floating Point, and Complex Numbers***

Integers and floating point numbers are the simplest data types:

-   **Integers**:  Whole numbers without decimals
-   **Floating point**:  Numbers with decimal points or exponents (such as 10e5, which indicates 10 to the fifth power)

List of Python's numeric operators:

| Operator | Description | Example | Evaluates to |
| -- | -- | -- | -- |
| + | Adds two expressions together | 5 + 5 | 10 |
| - | Subtracts one expression from another | 35 - 15 | 20 |
| * | Multiplies two expressions | 10 * 10 | 100 |
| / | Divides one expression by another | 20 / 5 | 4 |
| // | Performs integer division (leaving off the remainder) | 30 // 7 | 4 |
| % | Performs modulus division (printing the remainder only) | 30 & 7 | 2 | 
| ** | Indicates an exponent | 2 ** 8 | 258 |

Order of operations - PEMDAS:

-   **Parentheses**:  Parentheses are always evaluated first.
-   **Power**:  The exponent is evaluated.
-   **Multiplication**:  Any multiplication is performed.
-   **Division**:  Division is evaluated.
-   **Addition**:  Addition is performed.
-   **Subtraction**:  Subtraction is performed.
-   **Left to right**:  After PEMDAS, anything else (such as **sqrt()** or other math functions) is evaluated from left to right.

&nbsp;

### ***Booleans***

| Operator | What It Does | Example | Evaluates to |
| -- | -- | -- | -- |
| < | Less than | 5 < 10 | True|
| > | Greater than | 6.5 > 3.5 | True |
| <= | Less than | 0 <= -5 | False |
| >= | Greater than or equal to | 6 >= 6 | True |
| == | Equal to | 5 == "5" | False |
| != | Not equal to | 5 != "5" | True |

&nbsp;

### ***Strings***

The string data type is a sequence of characters and use quote to determine which characters are included.

&nbsp;

The **int()** function converts a string value to an integer.

```python
>>> int('10') + 1

11
```

&nbsp;

You can separate and manipulate component values of a string by using the index value.

```python
>>> a = 'DevNet'
>>> a[0]

'D'
```

You can specify ranges with the colon operator.  The first number is the beginning slice, and the second number determines the end (up to but not including).

```python
>>> a[0:3]

'Dev'
```

If you omit the first number, Python starts at 0:

```python
>>> a[:2]

'De'
```

If you omit the second value, Python prints to the end of the string:

```python
>>> a[2:]

'vNet'
```

You can reverse directions by using negative numbers.  If you put a negative number first, you start from the end of the first string:

```python
>>> a[-2:]

'et'
```

A negative value on the other side of the color causes Python to print using the end as a reference point:

```python
>>> a[:-2]

'DevN'
```

&nbsp;

You can perform operations on strings as well.

The + is used to add or concatenate two strings together:

```python
>>> 'DevNet' + 'Rocks'

'DevNetRocks'
```

Multiplication works as well:

```python
>>> 'DevNet Rocks ' * 5

'DevNet Rocks DevNet Rocks DevNet Rocks DevNet Rocks DevNet Rocks '
```

&nbsp;

String manipulation methods:

| Method | What It Does |
| -- | -- |
| str.capitalize() | Capitalize the string |
| str.center(width[, fillchar]) | Center justify the string |
| str.endwith(suffix[, start[, end]]) | Add an ending to the string |
| str.find(sub[, start[, end]]) | Find the index position of the characters in a string |
| str.lstrip([chars]) | Remove whitespace characters from the end of the string |
| str.replace(old, new[, count]) | Replace characters in the string |
| str.lower() | Make the string all lowercase |
| str.rstrip([chars]) | Strip whitespace characters from the front of the string |
| str.strip([chars]) | Remove whitespace characters from the beginning and the end of the string |
| str.upper() | Make the string all uppercase |

&nbsp;

### ***Lists***

To create a list you assign contents of the list to a variable with the **=** and **[]** and separate the items with commas:

```python
>>> kids = ['Caleb', 'Sydney', 'Savannah']
>>> kids

['Caleb', 'Sydney', 'Savannah']
```

A list can contain a Python object, such as integers, strings, and even other lists.  A list can also be empty and is often initialized in an empty state for programs that pull data from other sources.  To initialize a list in an empty state, you assign two brackets with nothing in them, or you use the built-in **list()** function:

```python
emptylist = []
emptylist = list()
```

Lists are similar to strings in that each is a set of items indexed by Python that you can interact with and slice.  To pull out values, use the variable name with brackets and the index number, starting at 0:

```python
>>> print(kids[1])

Sydney
```

Unlike strings lists are mutable objects:

```python
>>> kids

['Caleb', 'Sidney', 'Savannah']

>>> kids[1]='Sydney'
>>> kids

['Caleb', 'Sydney', 'Savannah']
```

Lists can also be concatenated together using the **+** operator.  The list items do not need to be unique.

The same principles of slicing strings apply to lists, but instead of having a single string with each letter, the elements in the list are the items.

&nbsp;

Most common list methods:

*Note:  Below you replace the word **list** before the **.** with the name of your list.*

| Method | What It Does |
| -- | -- |
| list.append(element) | Adds an element to the end of the list |
| list.clear() | Removes everything from the list |
| list.copy(alist) | Returns a copy of the list |
| list.count(element) | Shows the number of elements with the specified value |
| list.extend(alist) | Adds the elements of a list to the end of the current list |
| list.index() | Returns the index number of the first element with a specific value |
| list.insert(index, element) | Adds an element at a specific index value |
| list.pop(index) | Removes an element at a specific index position, or if no index position is provided, removes the last item from the list |
| list.remove() | Removes a list item with a specified value |
| list.reverse() | Reverses the list order |
| list.sort() | Sorts the list alphabetically and/or numerically |

&nbsp;

### ***Tuples***

Tuples are very similar to lists, with the difference between that lists are mutable and tuples are immutable.

To create a tuple, you use parenthesis instead of brackets.

```python
>>> perosn = (2012, 'Mike', 'CCNA')
```

You access data in a tuple the same way as a list - using brackets and the index value of the item.

```python
>>> person[0]

2012
```

You ***cannot*** make an assignment to the values:

```python
>>> person[0] = 15

Traceback (most recent call last):

    File "<stdin>" ,line 1, in <module>

TypeError:  'tuple' object does not support item assignment
```

Tuples can be used to assign a set of variables quickly:

```python
>>> (a, b, c) = (12, 'Fred', 18)
>>> c

18
```

&nbsp;

### ***Dictionaries***

Dictionaries are a collection of items with key:value pairs and doesn't have a defined order; all you need is the key.

Rules regarding dictionaries:

-   **Keys**:  A dictionary's keys are limited to only using immutable values (int, float, bool, str, tuple, and so on)
-   **Values**:  A value can be any Python object or any combination of objects.

To create a dictionary, you use braces and your keys and value separated by a colon.  You separate multiple items with commas.

```python
>>> cabinet = { "scores": (98, 76, 95), "name":"Chris", "company":"Cisco" }
```

Instead of using an index, you use the key:

```python
>>> cabinet["scores"]

(98, 76, 95)
```

To add more items to a dictionary, you can assign them with a new key.  You can even add another dictionary to an existing dictionary:

```python
>>> cabinet["address"] = {"street":"123 Anywhere Dr", "city":"Franklin", "state":"TN"}
>>> cabinet["address"]

{'street': '123 Anywhere Dr', 'city':'Franklin', 'state':'TN'}
```

&nbsp;

### ***Sets***

A set in Python consists of an unordered grouping of data and is defined using the curly braces of a dictionary without the key:value pairs.


Sets are mutable, and you can add or remove items from the set, however you can create a special case of sets called a frozen set that makes teh set immutable.

Defining a set:

```python
>>> numbs = {1, 2, 4, 5, 6, 8, 10}
>>> odds = {1, 3, 5, 7, 9}
```

To join sets you can use the **|** operator to show a combined set with no duplicates:

```python
>>> numbs | odds
{1, 2, 3, 4, 5, 6, 7, 8, 9, 10}
```

You can get an intersection of two sets and show what numbers are in both by using the **&** operator:

```python
>>> numbers & odds
{1, 5}
```

&nbsp;

##  **Input and Output**

&nbsp;

### ***Getting Input from the User***

The **input()** function gets information from the user and stores it as a string.

&nbsp;

### ***print() Function***

The **print()** function provides output that can be displayed in the user's terminal.

Every lined printed with the **print()** function includes a newline character (**\n**) at the end.

By default, the **print()** function uses a separator between elements.  You can change this by changing the separator that the **print()** function uses with the **sep=''** attribute.  This removes all automatic spacing.

Python 3.6 and up has the addition of f-string formatting.  These strings are easier to read, less prone to syntax errors and allow fasting formatting of code.

Creating an f-string:

```python
>>> name = 'Piper'
>>> name2 = 'Chris'
>>> print(f'{name2} says Hi to {name}!')

Chris says Hi to Piper!
```

&nbsp;

##  **Flow Control with Conditionals and Loops**

&nbsp;

Python has three primary control statements:

-   **if**:  Any **if** statement is a conditional statement that can compare values and make branching decisions.
-   **for**:  A **for** loop is a counting loop that can iterate through data a specific number of times.
-   **while**:  The **while** loop can iterate forever when certain conditions are met.

&nbsp;

### ***If Statement***

An **if** statement starts with an **if** and then sets up a comparison to determine the truth of the statement it is evaluating and ending with a **:** to tell Python to expect the clause (the action if the statement is true) block of code next:

```python
>>> n = 20
>>> if n == 20:
...    print('The number is 20')
...    
The number is 20
```

The goal of an **if** statement is to determine the "truth" of the element under evaluation.

An **if** statement can have as many **elif** conditions as you want to add to the condition check.

Since each **if** and **elif** statement does something only if the condition identified is true, you can assign a single **else** statement as the end.

&nbsp;

### ***For Loops***

The **for** statement iterates through the code a specific number of times.  It is also referred to as a counting loop.

A **for** loop starts with the **for** statement, followed by a variable name (which is a placeholder to hold each sequence of data), the **in** keyword, some data set to iterate through, and then a closing colon:

```python
>>> dataset = (1,2,3,4,5)
>>> for variable in dataset:
...    print(variable)
...    
1
2
3
4
5
```

The **for** loop continues through each item in a data set.  You can also use the **range()** function to iterate a specific number of times.

The **range()** function can take arguments that let you choose what number it starts or stops on and how it steps through each one.

By default, if you just give **range()** a number, it starts at 0 and goes by 1s until it reaches the number you provided.  Zero is a valid iteration, but if you don't want it, you can start at 1.

To change the increment from the default of 1, you can add a third attribute to the **range()** statement.

***The ranges are up to and not including the final number specified.***

&nbsp;

### ***While Loops***

The **while** loop is a condition loop, and the evaluation of the condition being true is what determines how many times the loop executes.

You can use **else** with a while loop.  An **else** statement after a **while** loop executes when the condition for the **while** loop to continue is no longer met.

You can use the **break** statement to exit the loop:

```python
while True:
    string = input('Enter some text to print. \nType "done" to quite.')
    if string == 'done':
        break
    print(string)
print('Done!')

# Example output:
#
# Enter some text to print.
# Type "done" to quit.>  Good luck on the test!
# Good luck on the test!
# Enter some text to print.
# Type "done" to quit.>  done
# Done!
```

&nbsp;

#   04 - Python Functions, Classes, and Modules

&nbsp;

##  **Python Functions**

&nbsp;

A ***function*** is a named block of code that can take a variety of input parameters (or none) and return some form of output back to the code that called the function to begin with.

Python offers two types of functions: built-in functions that are part of the standard library and functions you create yourself.  **print()** is an example of a built-in function.

To define a function in Python, you use the keyword **def**, a name for the function, a set of parentheses enclosing any arguments you want to pass to the function, and a colon at the end.

The name of the function must follow these rules:

-   Must not start with a number
-   Must not be a reserved Python word, a built-in function (for example, **print()**, **input()**, **type()**, etc), or a name that has already been used as a function or variable.
-   Can be any combination of A-Z, a-z, 0-9 and underscore (u) and dash (-)

Example of function syntax:

```python
>>> def devnet():
...    '''prints simple function'''
...    print('Simple function')
...  
>>> devnet()

Simple function
```

Three single quotation marks that appear on the first line of the indented text of the function are called a ***docstring*** and describe what the function does.

&nbsp;

##  **Using Arguments and Parameters**

&nbsp;

An ***argument*** is som value (or multiple values) that you pass to a function when you call the function within code.

Arguments allow a function to produce different results and make code reuse possible.

Arguments are placed within the parentheses after a function name.

&nbsp;

Each function must define how it will use arguments, using parameters to identify what gets passed in and how it gets used.

A parameter is simply a variable that is used in a function definition that allows code within the function to use the data passed to it.

To get results back from the function, you use the keyword **return** and the object you want to pass back.

```python
>>> def sub(arg1, arg2):
...    result = arg1 - arg2
...    return result
...  

>>> sub(10, 15)

-5
```

&nbsp;

The variable *result* is ***local***, meaning that it is not accessible to the main Python script, and it is used only within the function.  If you tried to call *result* directly, Python will produce an error saying that *result* is not defined.

You can access global variables from within the function.  An example of why you might do this is to set certain constants or key variables that any function ca use.

The difference in accessibility between a local variable and a global variable is important, because they allow your code to maintain separation and can keep your function self-contained.

&nbsp;

***Positional and Keyword Arguments***

A ***keyword argument*** is a name/value pair that you pass to a function.  Instead of using position, you specify the argument that the function uses.

With keyword arguments, it doesn't matter in what order they are passed to the function.

```python
>>> sub(arg2=15, arg1=10)

-5
```

&nbsp;

***\*args and \*\*kwargs***

Python allows you to use * an ** (often referred to as **\*args** and **\*kwargs**) to define any number of arguments or keyword arguments.  

\* and ** allow you to iterate through a list of other collations of data:

```python
>>> def hello(*args):
...    for arg in args:
...        print("Hello ", arg, "!", sep='')
...   
>>> hello('Caleb', 'Sydney', 'Savannah')

Hello Caleb!

Hello Sydney!

Hello Savannah!
```

By using keyword arguments, you can send a list of key/value pairs to a function:

```python
>>> def hello(**kwargs):
...    for key, value in kwargs.item():
...        print("Hello", value, "1", sep='')
...    
>>> hello(kwarg1='Caleb', kwarg2='Sydney', kwarg3='Savannah')

Hello Caleb!

Hello Sydney!

Hello Savannah!
```

Note the use of the **items()** function in the **for** statement to unpack and iterate through the values.

&nbsp;

You can also supply a default value argument in case of an empty value to send to a function.  By defining a function with an assigned key value, you prevent an error.  

If a value is not supplied, Python uses the default, and if it is supplied when the function is called it ignores the default value.

```python
>>> def greeting(name, message="Good morning!"):
...    print(f"Hello {name},  {message}")
...
>>> greeting('Caleb')

Hello caleb.  Good morning!

>>> greeting('Sydney', 'How are you?')

Hello Sydney.  How are you?
```

&nbsp;

##  **Object-Oriented Programming and Python**

&nbsp;

##  **Python Classes**

&nbsp;

### ***Creating a Class***

To create a class you first have to define it.  In Python you define a class by using the **class** keyword, and then closing with a colon.  PEP 8 recommends capitalizing a class name to differentiate it from a variable:

```python
>>> class Router:
...    pass
```

**pass** is a placeholder that allows the class to be defined and set up to be used as an object.

The first value is always **self**.  The **self** value passes the object name that you select to instantiate the class.

```python
class Router:
    '''Router Class'''
    def __init__(self, model, swversion, ip_add):
        ''initialize values'''
        self.model = model
        self.swversion = swversion
        self.ip_add = ip_add

rtr1 = Router('iosV', 15.6.7', '10.10.10.1')
```

After defining the class, you add a docstring to document what the class is for.

Then you create a function that calls **init**, which is a special case that is used for teh setup of the class.  In **init**, the double underscores are called ***dunder*** or ***magic methods***.  

Functions that are within the class are called ***methods*** and become actions that you can perform on the object you are creating.

To store attributes, you map the name **self** and the values you pass to it become variables inside the object, which then store those values as attributes.

&nbsp;

You can create more attributes that aren't defined during initialization:

```python
>>> rtr1.desc = 'virtual router'
>>> rtr1.desc

'virtual router'
```

&nbsp;

### ***Methods***

Attributes describe an object, and methods allow you to interact with an object.

Methods are functions you define as part of a class.

Notice that you pass **self** to this function only, as **self** can access the attributes applied during initialization:

```python
class Router:
    '''Router Class'''
    def __init__(self, model, swversion, ip_add):
        '''Initialize Values'''
        self.model = model
        self.swversion = swversion
        self.ip_add = ip_add

    def getdesc(self):
        '''Return a formatted description fo the router'''
        desc = f'Router Model              :{self.mode}\n'\
               f'Router Version            :{self.swversion}\n'\
               f'Router Management Address :{self.ip_add}\n'\
        
        return desc

rtr1 = Router('iosV', '15.6.7', '10.10.10.1')

rtr2 = Router('isr4221', '16.9.5', '10.10.10.5')

print('Rtr1\n', rtr1.getdesc(), '\n', sep='')

print('Rtr2\n', rtr2.getdesc(), sep='')
```

&nbsp;

### ***Inheritance***

***Inheritance in Python classes allows a class to take on attributes and methods of another class.***

When you use inheritance, you can replace methods and attributes that need to be different.

To inherit a class, you can create teh class as shown earlier, but before the colon, you add a parentheses that include the class from which you want to pull attributes and methods.

Note, the parent class must come before the child class in the Python code.

```python
class Router:
    '''Router Class'''
    def __init__(self, model, swversion, ip_add):
        '''Initialize Values'''
        self.mode = model
        self.swversion = swversion
        self.ip_add = ip_add

    def getdesc(self):
        '''return a formatted description of the router'''
        desc = f'Router Model               :{self.model}\n'\
               f'Router Version             :{self.swversion}\n'\
               f'Router Management Address  :{self.ip_add}\n'\

        return desc

class Switch(Router):
    def getdesc(self):
        '''return a formatted description for a switch'''
        desc = f'Switch Model               :{self.model}\n'\
               f'Switch Version             :{self.swversion}\n'\
               f'Switch Management Address  :{self.ip_add}\n'\

        return desc
```

More about classes, methods, and inheritance:

https://docs.python.org/3/tutorial/classes.html

&nbsp;

##  **Working with Python Modules**

&nbsp;

Code can be broken up into smaller chunks that hold key structures and classes and allow them to be physically moved into other files, called ***modules***, that can be included in the main Python code with the **import** statement.

Benefits of creating modular code:

-   **Easier readability/maintainability**:  Modular code is inherently easier to read and follow, and modularity makes maintaining and modifying code much easier.
-   **Low coupling/high cohesion**:  Modular code should not have interdependencies.  Each module should be self-contained so that changes to one module do not affect other modules or code.  A module should only include functions and capabilities related to what the module is supposed to do.  This paradigm is called low coupling/high cohesion modular design.
-   **Code reusability**:  Modules allow for easy reusability of code, which saves time and makes it possible to share useful code.
-   **Collaboration**:  Being able to split up work and have different people work on different modules speeds up the ode-production process.

&nbsp;

Three ways of using modules in Python

-   Use one of the modules that are included in the Python standard library or install a third-party module using **pip**, saving time.
-   Create your own module written in Python by appending .py extension to the file, adding overhead to the application.
-   Program a module in C language and compile it which will result in faster runtime but more work.

&nbsp;

### ***Importing a Module***

All modules are accessed the same way in Python: by using the **import** command.

At the very beginning of the code - you type **import** followed by the module name you want to use.

```python
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

After you import a module, you can use the **dir()** function to get a list of all the methods available as part of the module.  The ones beginning with the _ are internal to Python and are not generally useful in your programs.  All the others are functions that are available for your program to access.

&nbsp;

You can use **help()** to look at the documentation on a specific function:

```python
>>> help(math.sqrt)
Help on built-in function sqrt in module math:

sqrt(x, /)
    Return the square root of x.
```

&nbsp;

You have to type a module's name each time you want to use one of it's capability.  

Python lets you shorten the module name by adding **as** and a short version of the module name to the end of the import command:

```python
>>> import calendar as cal
```

&nbsp;

Importing a whole module when you only need a specific method or function adds unneeded overheard.  Python allows you to import specific methods by using the **from** syntax.

You can import more than one method by separating the methods you want with commas.

```python
>>> from math import sqrt, tan
>>> sqrt(15)

3.872983346207417
```

Notice you no longer need to use **math.sqrt** and can just call **sqrt()**.

&nbsp;

### ***The Python Standard Library***

The Python standard library is automatically installed when you load Python and has an extensive range of prebuilt modules you can use.  Many are built in C.  To get a complete list of modules in the standard library, go to https://docs.python.org/3/library.

&nbsp;

### ***Importing Your Own Modules***

You can import your own modules using the same methods shown previously with standard library modules.

By default, Python looks for a module in the same directory as the Python program you are importing into.  If it doesn't find the file there, it looks through your operating system's **path** statements.

&nbsp;

### ***Useful Python Modules for Cisco Infrastructure***

-   ***General purpose standard library modules***:
    -   **pprint**:  The pretty print module is a more intelligent print function that makes it much easier to display text and data by, for example, aligning data for better readability.  Use the following command to import this module:
        -   ```from pprint import pprint```
    -   **sys**:  This module allows you to interact with the Python interpreter and manipulate and view values.  Use the following command to import this module:
        -   ```import sys```
    -   **os**:  This module gives you access to the underlying operating system environment and file system.  It allows you to open files and interact with OS variables.  Use the following command to import this module:
        -   ```import os```
    -   **datetime**:  This module allows you to create, format, and work with calendar dates and time.  It also enables timestamps and other useful additions to logging and data.  Use the following command to import this module.
        -   ```import datetime```
    -   **time**:  This module allows you to add time-based delays an clock capabilities to your Python apps.  Use the following command to import this module:
        -   ```import time```
-   ***Modules for working with data***:
    -   **xmltodict**:  This module translates XML-formatted files into native Python dictionaries (key/value pairs) and back to XML, if needed.  Use the following commands to install and import this module:
        -   ```pip install xmltodict```
        -   ```import xmltodict```
    -   **csv**:  This is a standard library module for understanding CSV files.  It is useful for exporting Excel spreadsheets into a format that you can then import into Python as a data source.  It can, for example, read in a CSV file and use it as a Python list data type.  Use the following command to import this module:
        -   ```import csv```
    -   **json**:  This is a standard library module for reading JSON-formatted data sources and easily converting them to dictionaries.  Use the following command to import this module:
        -   ```import json```
    -   **PyYAML**:  This module converts YAML files to Python objects that can be converted to Python dictionaries or lists.  Use the following commands to install and import this module:
        -   ```pip install PyYAML```
        -   ```import yaml```
    -   **pyang**:  This isn't a typical module you import into a Python program.  It's a utility written in Python that you can use to verify your YANG models, create YANG code, and transform YANG models into other data structures, such as XSD (XML Schema Definitions).  Use the following command to install this module:
        -   ```pip install pyang```
-   ***Tools for API interaction***:
    -   **requests**:  This is a full library to interact with HTTP services and used extensively to interact with REST APIs.  Use the following commands to install and import this module:
        -   ```pip install requests```
        -   ```import requests```
    -   **ncclient**:  This Python library helps with client-side scripting and application integration for the NETCONF protocol.  Use the following commands to install and import this module:
        -   ```pip install ncclient```
        -   ```from ncclient import manager```
    -   **netmiko**:  This connection-handling library makes it easier to initiate SSH connections to network devices.  This module is intended to help bridge the programmability gap between devices with APIs and those without APIs that still rely on command-line interfaces and commands.  It relies on the paramiko module and works with multiple vendor platforms.  Use the following commands to install and import this module:
        -   ```pip install netmiko```
        -   ```from netmiko import ConnectHandler```
    -   **pysnmp**:  This is a Python implemenetation of an SMP engine for network management.  It allows you to interact with older infrastructure components without APIs but that do support SNMP for management.  Use the following commands to install and import this module:
        -   ```pip install pysnmp```
        -   ```import pysnmp```
-   ***Automation tools***
    -   **napalm**:  napalm (Network Automation and Programmability Abstraction Layer with Multivendor Support) is a Python module that provides functionality that works in a multivendor fashion.  Use the following commands to install and import this module:
        -   ```pip install napalm```
        -   ```import napalm```
    -   **nornir**:  This is an extendable, multithreaded framework with inventory management to work with large numbers of network devices.  Use the following commands to instal land import this module:
        -   ```pip install nornir```
        -   ```from nornir.core import InitNornir```
-   ***Testing tools***:
    -   **unittest**:  This standard library testing module is used to test the functionality of Python code.  It is often used for automated code testing and as part of test-driven development methodologies.  Use the following command to import this module:
        -   ```import unittest```
    -   **pyATS**:  This module was a gift from Cisco to the development community.  Originally named Genie, it was an internal testing framework used by cisco developers to validate their code for Cisco products.  pyATS is an incredible framework for constructing automated testing for infrastructure as code.  Use the following command to install this module:
        -   ```pip install pyats (just install the core framework, check documentation for more options)```
        -   Many parts of the **pyATS** framework can be imported.  Check the documentation on how to use it.

&nbsp;

#   05 - Working with Data in Python 

##  **File Input and Output**

&nbsp;

Python can natively extract data from a text file.  Binary files, on the other hand, need to be processed by a module or another external program first.

Python views text files as a sequence of lines, with each line typically being 79 characters long with a newline character (**\n**) at the end.

To open a file and read in its contents, first you have to tell Python the name of the file you want to work with.  this is done by using the **open()** function and assigned the output to a Python object.  The function returns a file handle, which Python uses to perform operations on the file:

```python
readdata = open("textfile.txt", "r")
```

The **open()** function requires two arguments: the name of the function as a string and the mode you want to open the file.

Mode options:

-   **r**:  Open for reading (default)
-   **w**:  Open for writing, truncating the file first
-   **x**:  Open for exclusive creation, failing if the file already exists
-   **a**:  Open for writing, appending to the end of the file if it exists
-   **b**:  Open in binary mode
-   **t**:  Open in text mode (default)
-   **+:**  Open for updating (reading and writing)

&nbsp;

With the file handling object named **readdata** you can use methods to interact with the file methods:

```python
print(readdata.read())

Line one of a text file.

Line two of a text file, just like line one, but the second one.

Third line of a text file.
```

&nbsp;

When using the **open()** function you must close the fine once finished with the **close()** method.

```python
readdata.close()
```

&nbsp;

The **with** statement (also called ***context manager***) uses the **open()** function but doesn't require direct assignment to a variable.  It also has better exception handling and automatically closes the file once finished reading in or writing to the file.

```python
with open("textfile.txt", "r") as data:
    print(data.read())
```

&nbsp;

To append data to a file you need to change how you open the file to allow for writing:

```python
with open("textfile.txt", "r') as data:
    data.write('\nFourth line added by Python')
```

The newline in front of the text you are appending makes it so that it isn't just tacked on at the very end of the text.

&nbsp;

##  **Parsing Data**

### ***Comma-Seperated Values (CSV)***

A CSV file is a plaintext spreadsheet or database file.  

Each line in a CSV file represents a row, and commas are used to separate the individual data fields to make it easier to parse the data.

Python has a built-in CSV module that you can import that understands the CSV format and simplifies your code.

Typical CSV file (routerlist.csv):

```csv
"router1","192.168.10.1","Nashville"
"router2","192.168.20.1","Tampa"
"router3","192.168.30.1","San Jose"
```

To start working with this data, you have to import the CSV module, and then create a **reader** object to read the CSV file into.  

First you have to read the file into a file handle, then run the CSV read function on it and pass the results on to a **reader** object.  

From here you can begin to use the CSV data.  You can create another variable and pass the **reader** object variable to the built-in **list()** function:

```python
>>> import csv
>>> samplefile = open('routerlist.csv')
>>> samplereader = csv.reader(samplefile)
>>> sampledata = list(samplereader)
>>> sampledata

[['router1', '192.168.10.1', 'Nashville'], ['router2',
'192.168.20.1', 'Tampa'], ['router3', '192.168.30.1', 'San Jose ']]
```

Now having lists of lists you can manipulate this data using list notation.

```python
>>> sampledata[0]

['router', '192.168.10.1', 'Nashville']

>>> sampledata[0][1]

'192.168.0.1'
```

&nbsp;

Using **with**, you can iterate throug the CSV data and display information in an easier way:

```python
import csv
with open("routerlist.csv") as data:
    csv_list = csv.reader(data)
    for row in csv_list:
        device = row[0]
        location = row[2]
        ip = row[]
        print(f"{device} is in {location.rstrip()} and has IP {ip}.")
```

> **Note**
>
> Why is list not needed?  **data** is the file handler, **csv_list** is the reader, but why do we not need the list function?*  After testing it seems to work with or without **list()**, not sure why.
>
> This was answered [here](https://www.reddit.com/r/learnpython/comments/wywuh5/no_list_needed_when_using_with_for_csv/).  Essentially though, **list()** works by essentially iterating over the items and building the list, similar to how a for loop iterates, so you can skip the list in the previous example and for loop over it as well. 

The **rstrip** function is used because the last entry in a CSV file will have a whitespace character at the very end.  Without **rstrip** the formatting will be cut off.

&nbsp;

Adding a line to the CSV file follows a similar process to text files.  Instead of using a **reader** object, you use a **writer** object to store the formatted CSV data and then write it to the file.

```python
import csv 

print("Please add a new router to the list")
hostname = input("What is the hostname? ")
ip = input("What is the ip address? ")
location = input("What is the location? ")

router = [hostname, ip, location]

with open("routerlist.csv", "a") as data:
    csv_writer = csv.writer(data)
    csv_writer.writerow(router)
```

&nbsp;

### ***JavaScript Object Notation (JSON)***

The data structure of JSON is built around key/value pairs.

You can easily convert JSON to lists (for a JSON array) and dictionaries (for JSON objects) with the built-in JSON module.

There are four functions to perform the conversion of JSON data into Python objects and back:

-   **load()**:  This allows you to import native JSON and convert it to a Python dictionary from a file.
-   **loads()**:  this will import JSON data from a string for parsing and manipulating within your program.
-   **dump()**:  This is used to write JSON data from Python objects to a file.
-   **dumps()**:  This allows you to take JSON dicitonary data and convert it into serialized string for parsing and manipulating within Python.

> **Note**
> 
> (*Personal Note*) One way to think about it is that when you are loading from or dumping to the file, you use load or dump (without s) but when you're loading the JSON object you already have out of the file handle out into a dictionary you loads (with s) and when you're dumping from a dictionary into the JSON object you use dumps.

The **s** at the end of **dump** and **load** refers to a string, as in *dump string*.  To see this in action, you load the JSON file and map the file handle to a Python object (data) like so:

```python
import json
with open("json_sample.json") as data:
    json_data = data.read()

json_dict = json_loads(json_data)
```

The object **json_dict** has taken the output of **json.loads(json_data)** and now holds the **json** object as a Python dictionary.

You can now modify the key/value pairs.  In order to save the new **json** object back to the file, you have to use the **dump()** function (without the **s**) to convert the Python dictionary back into the JSON file object.

To make it easier to read, you can use the **indent** keyword.

```python
with open("json_sample.json", "w") as filehandle:
    json.dump(json_dict, filehandle, indent=4)
```

&nbsp;

### ***Extensible Markup Language (XML)***

Extensible Markup Language (XML) was designed to work with HTML for data transport and storage between web services and APIs.  

XML is a tree structure, with the root element at the top.  

There are parent/child relationships between elements.

It's similar to JSON in that a tag acts as a key with a value.

You can also assign attributes to a tag:

```attribute name="some value"```

This work the same as an element in that it can provide a way to represent data:

```xml
<?xml version=".0" encoding="UTF-8" ?>
<interface xmlns="ietf-interfaces">
    <name>GigabitEthernet2</name>
    <description>Wide Area Network</description>
    <enabled>true</enabled>
    <ipv4>
        <address>
            <ip>92.168.1.5</ip>
            <netmask>255.255.255.0</netmask>
        </address>
    </ipv4>
</interface>
```

&nbsp;

To work with XML you can use the native XML library which can be a bit harder if you just want to convert XML into something you want to work with in Python.  More easily you can use a module called **xmltodict** to convert XML into an ordered dictionary in Python.  ***This is a special class of dictionary that does not allow elements to change order.***  Since dictionaries use key/value pairs, where the key/value pairs are stored is normally not a problem, but in the case of XML, order matters.

XML from previous example converted to an ordered dictionary:

```python
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

Now that the XML is in a Python dictionary, you can modify an element:

```python
xml_dict["interface"]["ipv4"]["address"]["ip"] = "192.168.55.3"
```

You can see the changes in XML foramt by using the **unparse** function (not XML doesn't care about whitespaces, but you can use **pretty=True** to make it more human readable):

```python
>>> print(xmltodict.unprase(xml_dct, pretty=True))

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

To write changes back to the original file:

```python
with open("xml_sample.xml", "w") as data:
    data.write(xmltodict.unparse(xml_dict, pretty=True))
```

&nbsp;

### ***YAML Ain't Markup Language (YAML)***

Example of YAML syntax:

```yaml
---
interface:
    name: GigabitEthernet2
    description: Wide Area NEtwork
    enabled: true
    ipv4:
        address:
        -   ip: 172.16.0.2
            netmask: 255.255.255.0
```

YAML can represent a list by using the **-** character to identify elements:

```yaml
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

To work with YAML in Python, you need to install and import the PyYAML module.

Once you have imported it into your code you can convert YAML to Python objects and back again.  

YAML objects are converted to dictionaries, and YAML lists automaticallybecome Python lists.  The two function taht perform this are **yaml.load** to convert from YAML object into Python and **yaml.dump** to convert Python objects back to YAML.

You can load a YAML file and then pass it to **yaml.load**.  

The latest PyYAML module requires that you add an argument to tell it which loader you want to use.  This is a security measure so that your code is not vulnerable to arbitrary code execution from a bad YAML file.

```python
import yaml

with open("yaml_sample.yaml") as data:
    yaml_sample = data.read()

yaml_dict = yaml.load(yaml_sample, Loader=yaml.FullLoader)
```

The variable **yaml_dict** is now a dictionary object containing the YAML file.  Had the key/value been a YAML list, it would have created a list instead.

You can modify this object:

```python
>>> yaml_dict["interface"]["name"] = "GigabitEthernet"
>>> print(yaml.dump(yaml_dict, default_flow_style=False))

interface:
    description: Wide Area Network
    enabled: true
    ipv4:
        address:
        -   ip: 92.168.0.2
            netmask: 255.255.255.0
    name: GigabitEthernet1
```

To write changes back to the YAML file:

```python
with open("yaml_sample.yaml", "w") as data:
    data.write(yaml.dump(yaml_dict, default_flow_style=False))
```

&nbsp;

##  **Error Handling in Python**

&nbsp;

**try-except-else-finally** code blocks.

To add error handling to code you can use the **try** statement:

```python
x = 0
while True:
    try:
        filename = input("Which file would you like to open?: ")
        with open(filename, "r") as filehandle:
            file_data = filehandle.read()
    except FileNotFoundError:
        print(f"Sorry, {filename} does not exist.  Please try again.")
    else:
        print(file_data)
        x = 0
        break
    finally:
        x += 1
        if x == 3:
            print('Wrong file name 3 times.\nCheck name and return.')
            break
```

&nbsp;

##  **Test-Driven Development (TDD)**

&nbsp;

Five steps of Test-Driven Development (TDD) process:

-   **Step 1.  Write a test**:  Write a test that tests for the new class or function you want to add to your code.  Think about the class name and structure you will need in order to call the new capability that doesn't exist yet - and nothing more.
-   **Step 2.  Test fails**:  Of course, the test fails because you haven't written the part that works yet.  The idea here is to think about what the class or function you want and test for its intendend output.  This initial test failures shows you exactly where you should focus your code writing to get it to pass.  This is like starting with your end state in mind, which is the most effective way to accomplish a goal.
-   **Step 3.  Write some code**:  Write only the code needed to maek the new function or class successfully pass.  This is about efficiency and focus.
-   **Step 4.  Test passes**:  The test now passes, and the code works.
-   **Step 5.  Refactor**:  Clean up the code as necessary, removing any test stubs or hard-coded variables used n testing.  Refine the code, if needed, for speed.

TDD works extremely well with the iterative nature of Agile development, with the side benefits of having plenty of test cases to show that the software works.

&nbsp;

##  **Unit Testing**

&nbsp;

A ***unit test*** is a type of test that is conducted on small, functional aspects of code.  It's the lowest level of software testing and is interested in the logic and operation of only a single function of code.

A ***unit*** is the smallest testable part of your software.

&nbsp;

There are other types of testing such as ***integration testing*** and ***functional testing***.  The differences between these types of testing and unit testing comes down to the scope of the test.  

As mentioned, a unit test is testing a small piece of code, such as a method or function.

An ***integration test*** tests how one software component works with the rest of the application.  It is often used when the modules of an application are developed by separate teams or when a distributed application has multiple components working together.

A ***function test*** (also called an ***end-to-end test***) is the broadest in scope from a testing perspsective.  This is where the entire system is tested against the function specification and requirements of the software application.

&nbsp;

**unittest** is Python's built-in unit test module.  

A simple function that computes the area of a circle:

```python
from math import pi
def area_of_circle(r):
    return pi*(r**2)
```

If this function is ran and odd values are passed to it errors will occur.  To test this you can create a unit test.

Naming the above code 'areacircle.py' the unit test file 'test_areacircle.py'.  Import the **unittest** module and from areacircle import the **area_of_circle** function.  Import the **pi** method from math to test the results. 

Next create a class for the test.  It can be named anything but must inherit **unittest.TestCase** from the **unittest** module.  This is what enables teh test function methods to be assigned to the **test** class.  Next define the first function.

You can test various inputs to validate the math in the function under **test** is working as it should.  Notice a new method called **assertAlmostEqual()**, which takes the function you are testing, passes a value to it, and checks the returned value against an expected value.

```python
import unittest
from areacircle import area_of_circle
from math import pi

class Test_Area_of_Circle_input(unittest.TestCase):
    def test_area(self):
        # Test radius >= 0
        self.assertAlmostEqual(area_of_circle(1), pi)
        self.assertAlmostEqual(area_of_circle(0), 0)
        self.assertAlmostEqual(area_of_circle(3.5), pi * 3.5**2)
```

You can go to the directory where the two scripts reside and enter ```python -m unittest test_areacircle.py``` to run the test.   Alternatively you can add the following to the bottom of the **test_areacircle.py** script to allow the **unittest** module to be launched when the test script is run:

```python
if __name__ = '__main__':
    unittest.main()
```

Output:

```
.
-------------------------------------------------------------------
Ran 1 test in 0.000s

OK
```

After executing the functions, the dot at the top of the results shows that number of tests ran to determine whether the valus submitted produced an error.

&nbsp;

You can check if a negative number causes a problem.  Create a new function under the previous **test_area** function, naming it **test_values** (**test** at the beginning is required, or unittest will ignore the function and not check it).  Use the **assertRaises** check which will look for a **ValueError** exception for the function **area_of_circle** and pass it a value of **-1**.

```python
def test_values(self):
    # Test that bad values are caught
    self.assertRaises(ValueError, area_of_circle, -1)
```

Output:

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

The first check is still good, so there is one dot at the top, but next is a **F** for fail.  There is a message saying that the **test_value** function is where it failed, and the original function did not catch this error.  This means the code is giving back tests, however a radisu of **-** is not possible, but the function gives you the follow output:

```python
>>> area_of_circle(-1)
3.141592653589793
```

To fix this you can use error-checking.  The **if** statement can check for a negative number, and raise a **ValueError** with a message about invalid input:

```python
from math import pi

def area_of_circle(r):
    if r < 0:
        raise ValueError('Negative radius value error')
    return pi*(r**2)
```

The unit test will now pass the checks.

&nbsp;

#   06 - Application Programming Interfaces (APIs)

&nbsp;

Application Programming Interfaces (APIs) are mechanisms used to communicate with applications and other software.

The two most common APIs: northbound and southbound APIs.

&nbsp;

###  ***Northbound APIs***

Northbound APIs are often used for communication from a network controller to its management software.

&nbsp;

### ***Southbound APIs***

Changes mode from a controller through a northbound API are then pushed to individual devices using a southbound API.

Southbound APIs can modify more than just the data plane on a device.

&nbsp;

### ***Synchronous vs. Asynchronous APIs***

APIs can handle transactions either in a synchronous or asynchronous manner.

A ***synchronous API*** causes an application to wait for a response from the API in order to continue processing data or function normally.  This can lead to interruptions in application processing or delay in response or failed responses could cause the application to hang or stop performing the way it was intended to work.

***Asynchronous APIs*** do exactly the opposite of synchronous APIs in that they do not wait until a response is received prior to continuing to function and process other aspects of data.  Asynchronous APIs provide a callback function so that the API response can be sent back at another time, without the application having to wait for the entire transaction to complete.

&nbsp;

### ***Representation State Transfer (REST) APIs***

An API that uses REST is often referred to as a RESTful API.

RESTful APIs use HTTP methods to gather and manipulate data.  Since there is a defined structure for how HTTP works, HTTP offers a consistent way to interact with APIs from multiple vendors.

REST uses different HTTP functions to interact with data.

HTTP functions are very similar to the functions that most applications and databases use to store or alter data.  These functions are called CRUD functions; CRUD is an acronym that stands for CREATE, READ, UPDATE, and DELETE.

HTTP functions and sample use cases:

| HTTP Function | Action | Use Case |
| -- | -- | -- |
| GET | Request data from a destination | Viewing a website |
| POST | Submit data to a specific destination | Submitting login credentials |
| PUT | Replaces data at a specific destination | Updating an NTP server |
| PATCH | Appends data to a specific destination | Adding an NTP server |
| DELETE | Removes data from a specific destination | Removing an NTP server |

CRUD functions and sample use cases:

| CRUD Function | Action | Use Cases |
| -- | -- | -- |
| CREATE | Insert data inside a database or an application | Creating a customer's home address in a database |
| READ | Retrieves data from a database or an application | Pulling up a customer's home address from a database |
| UPDATE | Modifies or replaces data in a database or an application | Changing a street address stored in a database |
| DELETE | Removes data from a database or an application | Removing a customer from a database |

&nbsp;

### ***RESTful API Authentication***

&nbsp;

### ***Basic Authentication***

The downfall of basic authentication is that the credentials are passed unencrypted.  The lack of encryption means that the credentials are in simple plaintext base 64 encoding in the HTTP header.  

Basic authentication is more commonly used in SSL or TLS to prevent attacks that sniff the traffic to capture a username and password.

Another issue with basic authentication is that the password is sent back and forth with each request, which increases the opportunity for an attacker to capture the traffic containing the password.

&nbsp;

### ***API Keys***

Some APIs use API keys for authentication.

An **API key** is a predetermined string that is passed from the client to the server.  It is intended to be a pre-shared secret and should not be well known or easy to guess, because it functions just like a password.

Any API key can be passed to the server in three ways:

-   String
-   Request header
-   Cookie

&nbsp;

***String*** based API key is sent with every API call and is often used as a one-off method of authentication.  When looking to do multiple API calls, it isn't convenient to manually enter the API key string every time.  This is where the request header or cookie options comes into play.

*String BaseD API Key Example:*

```
GET /something?api_key=abcdef2345
```

&nbsp;

***Request headers*** are frequently used when a user is making multiple API calls and doesn't want to keep having to put the API key into each API individually.  This is typically seen in Postman and Python scripts.  The header must include the string or token in the header of each API call.

*Request Header API Key Example:*

```
GET /something HTTP/1.1
X-API-Key:  abcdef12345
```

&nbsp;

***Cookies*** are one of the most common methods for recurring API calls.  A cookie stores the API key string and can be reused and stored over and over.  This is synonymous with a header.

*Cookie API Key Example:*

```
GET /something HTTP/1.1
Cookie:  X-API-KEY=abcdef12345
```

&nbsp;

### ***Custom Tokens***

A ***custom token*** allows a user to enter his or her username and password once and then receives a unique auto-generated and encrypted token.  This token can then be used to access protected pages or resources instead of having to continuously enter the login credentials.

Tokens can be time bound and set to expire after a specific amount of time has passed, forcing users to reauthenticate by reentering their credentials.

Tokens simplify the login process and reduces the number of times a user has to provide login credentials.

A token is stored in the user's browser and gets checked each time the user tries to access information requiring authentication.  Once the user logs out, the token is destroyed so it cannot be compromised.

&nbsp;

### ***Simple Object Access Protocol (SOAP)***

***Simple Object Access Token (SOAP)*** is used to access web services.

Although HTTP is the most commonly deployed transport for SOAP, SOAP can use either Simple Mail Transfer Protocol (SMTP) or HTTP.

SOAP is used to exchange data between applications that were build on different programming languages.

SOAP is based on XML.

SOAP uses XML to communicate between web services and clients.  

SOAP messages, which typically consist of the following four main components, are sent between the web applications and clients.

-   Envelope
-   Header
-   Body
-   Fault (optional)

&nbsp;

***Envelope:***
The SOAP envelope encloses the XML data and identifies it as a SOAP message.  the envelope indicates the beginning and the end of the SOAP message.  

&nbsp;

***Header:***
The next portion of a SOAP message is the SOAP header, and it can contain multiple header blocks.  Header blocks are targeted to specific SOAP receiver nodes.  If a SOAP message contains a header, it must come before the body element.

&nbsp;

***Body:***
The SOAP body contains the actual message that is designated for the SOAP receiver.  Every sOAP envelope must contain at least one body element.

&nbsp;

A benefit of SOAP is that because it primarily uses HTTP, it is efficient in passing through firewalls without requiring any additional ports be allowed or opened for the web service traffic to be permitted.

Benefits of SOAP:

-   Works between different languages
-   Uses simple and common HTTP and XML structure

&nbsp;

*Example SOAP Message:*
```html
POST /InStock HTTP/1.1
Host:  www.example.com
Content-Type:  application/soap+xml; charset=utf-8
Content-Length:  299
SOAPAction:  "http://www.w3.org/2003/05/soap-envelope"

<?xml version="1.0"?>
<soap:Envelope xmlns:soap="http://www.w3.org/2003/05/soap-envelope" xmlns:m="http://www.example.org">
    <soap:Header>
    </soap:Header>
    <soap:Body>
        <m:GetStockPrice>
            <m:StockName>CSCO</m:StockName>
        </m:GetStockPrice>
    </soap:Body>
</soap:Evenlope>
```

&nbsp;

*SOAP Fault Options:*

| SOAP Fault Code | Description |
| -- | -- |
| VersionMismatch | The faulting node found an invalid element information item instead of the expected envelope element information item.  The namespace, local name, or both did not match the envelope element information item required by this recommendation. |
| MustUnderstand | This is a child element of the SOAP header.  If this attribute is set, any information that was not understood triggers this fault code. |
| DataEncodingUnknown | A SOAP header block or SOAP body child element information item targeted at the faulting SOAP node is scoped. |
| Sender | The message was incorrectly formed or did not contain the information needed to succeed.  For example, the message might have lacked the proper authentication or payment information.  This code generally indicates that the message is not to be resent without change. |
| Receiver | The message could not be processed for reasons attributable to the processing of the message rather than to the contents of the message itself.  For example, processing could include communicating with an upstream SOAP node, which did not respond.  The message could succeed, however, if resent at a later point in time.


The fault message shown in example below was generated because the Detail value wasn't interpreted correctly due to the type in the XML ```<m:MaxTime>P5M</m:MaxTime>```.  The value P5M caused the issue in the case because the code was expecting it to be 5PM.  The XML code and value should be ```<m:MaxTime>5PM</m:MaxTime>``` in this case.

*Sample SOAP Fault:*

```html
<env:Envelope xmlns:env="http://www.w3.org/2005.05/soap-envelope"
    xmlns:m="http://www.example.org/timeouts"
    xmlns:="http://www.w3.org/XML/998/namespace">
    <env:Body>
        <env:Fault>
            <env:Code>
                <env:Value>end:Sender</env:value>
                <env:Subcode>
                    <env:Value>m:MessageTimeout</env:Value>
                </env:Subcode>
            </env:Code>
            <env:Reason>
                <env:Text xml:lang="en">Sender Timeout</env:Text>
            </env:Reason>
            </env:Detail>
                <m:MaxTime>P5M</m:MaxTime>
            </env:Detail>
        </env:Fault>
    </env:Body>
</env:Envelope>
```

&nbsp;

### ***Remote-Procedure Calls (RPCs)***

Remote-procedure calls (RPCs) make it possible to execute code or a program on a remote network.  RPCs behave as if the code were executed locally on the same local node, even though the code is executed on a remote address space

RPCs are sometimes also known as function or subroutine calls.

Using an RPC is a common way of executing specific commands, such as GET or POST operations to set API or URL.

When a client sends a request message, the RPC translates it and then sends it to the server.  A request may be a procedure or a function call destined to a remote server.  When a server receives the request, it sends back a response to the client.  While this communication is happening, the client is blocked, allowing the server time to process the call.  Once the call is processed and a response has been sent back to the client, the communication between the client and server is unblocked so the client can resume executing the procedure call.  

RPC calls are typically synchronous.  There are also asynchronous RPC calls, but the focus of this section is on synchronous RPC calls.

&nbsp;

There are different versions of RPC messages, however the most common is XML-RPC.

*Sample of XML-RPC Request Message:  Uses GET to retrieve the name of the 2st state added to the United States*

```html
<?xml version="1.0"?>
<methodCall>
    <methodName>example.getStateName</methodName>
    <params>
        <param>
            <value><i4>21</i4></value>
        </param>
    </params>
</methodCall>
```

&nbsp;

Below is an example of an XML-RPC reply or response message, in which the response is to the GET message from above.

*Sample XML-RPC Reply Message:*

```html
<?xml verison="1.0"?>
<methodResponse>
    <params>
        <param>
            <value><string>Illinois</string></value>
        </param>
    </params>
</methodResponse>
```

&nbsp;

#   07 - RESTful API Requests and Responses

&nbsp;

##  **RESTful API Fundamentals**

&nbsp;

An ***application programming interface (API)*** is a set of functions and procedures intended to be used as an interface for software components to communicate with each other.

&nbsp;

### ***API Types***

APIs can be broadly classified into three categories, based on the type of work that each one provides:

-   **Service API**:  In a service API, an application can call on another application to solve a particular problem.  Usually these systems can exist independently.  For example, in a payment system, an application can call the API to accept payments via credit cards.  As another example, with a user-management system, an application can call an API to validate and authenticate users.
    -   ***Solve or Execute This Task for Me***
        -   *Payment Systems*
        -   *User Management*
        -   *Social Media Handler*
-   **Information API**:  An information API allows one application to ask another application for information.  *Information* in this context can refer to data gathered over time, telemetry data, or a list of devices that are currently connected.
    -   ***Get Me the Current Information***
        -   *Analytics*
        -   *Device List*
        -   *Time Series*
-   **Hardware API**:  Application developers use hardware APIs to gain access to the features of hardware devices.  Usually these APIs encompass some kind of hardware or sensors, and an application can call this kind of API to get the GPS location or real-time sensor data such as temperature or humidity.
    -   ***Get Me the Current Location of the Vehicle***
        -   *Sensor Data*
        -   *Real-Time Hardware Status*
        -   *Device Management*

&nbsp;

### ***API Access Types***

There are typically three ways APIs can be accessed:

-   **Private**:  A private API is for internal use only.  This access type gives a company the most control over its API.
-   **Partner**:  A partner API is shared with specific business partners.  This can provide additional revenue streams without compromising security.
-   **Public**:  A public API is available to everyone.  This allows third parties to develop applications that interact with an API and can be a source of innovation.

Most APIs are accessed through a network (with the biggest network being the Internet) and with HTTP being so common it is the protocol underlying most APIs.

&nbsp;

### ***HTTP Basics***

Communication in HTTP centers around a concept called the request/response cycle, in which the client sends the server a request to do something and the server in turn sends the client a response saying whether or not the server can do what the client asked.

In HTTP, in order to make a successful request to a server, the client needs to include four items:

-   **URL (uniform resource locator)**
-   **Method**
-   **List of headers**
-   **Body**

&nbsp;

### ***Uniform Resource Locator (URL)***

A URL is similar to a house address in that it defines that location where a service resides on the internet.

A URL typically has four components:

-   **Protocol**:  http (Not Secure) or https (Secure)
-   **Server/host address**:  IP Address or Hostname to Connect to (myhouse.cisco.com)
-   **Resource**:  Location of the Data or Object on the Server (api/room/livingroom/)
-   **Parameters**:  Details to Scope, Filter, or Clarify the Request (lights?state=ON)

&nbsp;

### ***Method***

HTTP defines a set of request methods, outlined below.  A client can use one of these request methods to send a request to an HTTP server.

Request Methods

| Method | Explanation |
| - | - |
| GET | A client can use a GET request to get a web resource from the server. |
| HEAD | A client can use a HEAD request to get the header that a GET request would have obtained.  Because the header contains the last-modified date of the data, it can be used to check against the local cache copy. | 
| POST | A client can use a POST request to post data or add new data to the server. | 
| PUT | A client can use a PUT request to ask a server to store or update data. |
| PATCH | A client can use a PATCH request to ask a server to partially store or update data. |
| DELETE | A client can use a DELETE request to ask a server to delete data. |
| TRACE | A client can use a TRACE request to ask a server to return a diagnostic trace of the actions it takes. |
| OPTIONS | A client can use an OPTIONS request to ask a server to return a list of the request methods it supports. |
| CONNECT | A Client can use a CONNECT request to tell a proxy to make a connection opt another host and simply reply with the content, without attempting to parse or cache it.  This request is often used to make SSL connection through the proxy. |

&nbsp;

### ***REST Methods and CRUD***

REST is an architectural paradigm that allows developers to build RESTful services.  These RESTful applications make use of HTTP requests for handling all four CRUD operations: CREATE, READ, UPDATE, and DELETE.  These four operations are the operations most commonly used in manipulating data.  The HTTP methods map in a one-to-one way to the CRUD operations, as shown below:

Mapping HTTP Methods to CRUD Operations

| HTTP Method | Operation | Explanation |
| -- | -- | -- |
| POST | CREATE | Used to create a new object or resource.<br>Example:  Add new room to a house. |
| GET | READ | Used to retrieve resource details from the system.<br>Example:  Get a list of all the rooms or all the details of one room. |
| PUT | UPDATE | Typically used to replace or update a resource.  Can be used to modify or create a resource.<br>Example:  Update details of a room. |
| PATCH | UPDATE | Used to modify some details about a resource.<br>Example:  Change the dimensions of a room. |
| DELETE | DELETE | Used to remove a resource from the system.<br>Example:  Delete a room from a house. |

&nbsp;

### ***Deep Dive into GET and POST***

GET request methods fetch information and that's it; they have no side effects, make no modifications to the system, create nothing, an destroy nothing.

*Syntax of a GET Request*

> GET &nbsp;&nbsp;&nbsp; | &nbsp;&nbsp;&nbsp; Request URI &nbsp;&nbsp;&nbsp; | &nbsp;&nbsp;&nbsp; HTTP Version
> <br/>
> __
> <br/>
> Request Header (Optional)
> <br/>
> __
> <br/>
> Request Body (Optional)

-   **GET**:  The keyword GET must be all uppercase.
-   **Request URI**:  Specifies the path of the resource requested, which must begin with the root / of the document base directory.
-   **HTTP version**:  Either HTTP/1.0 or HTTP/1.1.  This client negotiates the protocol to be used for the current session.  For example, the client may request to use HTTP/1.1.  If the server does not support HTTP/1.1, it may inform the client in the response to use HTTP/1.0.
-   **Request headers (optional)**:  The client can use optional request headers (such as accept and accept language) to negotiate with the server and ask the server to deliver the preferred contents (such as the language the client prefers).
-   **Request body (optional)**:  A GET request message has an optional request body, which contains the query string (explained later in this chapter).

&nbsp;

The POST request method is used to post additional data to the server.  

Issuing an HTPT URL from the browser always triggers a GET request.  

To trigger a POST request, you can use an HTML form with attribute method="post" or write your own code.  

The POST request is the same as the GET request except that the URL-encoded query string is sent in the request body rather than appended behind the URL.

The POST request has the following components:

*Syntax of a POST Request*

> POST &nbsp;&nbsp;&nbsp; | &nbsp;&nbsp;&nbsp; Request URI &nbsp;&nbsp;&nbsp; | &nbsp;&nbsp;&nbsp; HTTP Version
> <br/>
> __
> <br/>
> Content Type
> <br/>
> __
> <br/>
> Content Length
> <br/>
> __
> <br/>
> Request Header (Optional)
> <br/>
> __
> <br/>
> Request Body (Optional)

-   **POST**:  The keyword POST must be in all uppercase.
-   **Request URI**:  Specifies the path of the resource requested, which must begin from the root / of the document base directory.
-   **HTTP version**:  Either HTTP/1.0 or HTTP/1.1.  This client negotiates the protocol to be used for the current session.  For example, the client may request to use HTTP/1.1.  If the server does not support HTTP/1.1, it may inform the client in the response to use HTTP/1.0.
-   **Request headers (optional)**:  The client can use optional request headers, such as content type and content length to inform the server of the media type and the length of the request body, respectively.
-   **Request body (optional)**:  A POST request message has an optional request body, which contains the query string (explained later in this chapter).

&nbsp;

### ***HTTP Headers***

HTTP headers and parameters provide a lot of information that can help you trace issues when you encounter them.  HTTP headers are an essential part of an API request and response as they represent the metadata associated with the API request and response.  

Headers carry information for the following:

-   Request and response body
-   Request authorization
-   Response caching
-   Response and cookies

In addition, HTTP headers have information about HTTP connection types, proxies, and so on.  Most of these headers are for managing connections between a client, a server, and proxies.

&nbsp;

Headers are classified as ***request headers*** and ***response headers***.  

You have to set the request headers when sending a request API and have to set the assertion against the response headers to ensure that the correct headers are returned.

&nbsp;

### ***Request Headers***

The request headers appear as name:value pairs.  Multiple values are separated by commas, can be specified as follows:

```
request-header-name: request-header-value1, request-header-value2, ...
```

The following is an example of request headers:

```
Host: myhouse.cisco.com
Connection:  Keep-Alive
Accept: image/gif, image/jpeg, */*
Accept-language: us-en, fr, cn
```

&nbsp;

### ***Response Headers***

The response headers also appear as name:value pairs, as with request headers, multiple values can be specified as followings:

```
request-header-name: response-header-value1, response-header-value2
```

The following are some examples of response headers:

```
Content-Type: text/html
Content-Length: 35
Connection:  Keep-Alive
Keep-Alive:  timeout=15, max=100
The response message body contains the resource data requested.
```

&nbsp;

The following are some examples of request and response headers:

-   **Authorization**:  Carries credentials containing the authentication information of the client for the resource being requested.
-   **WWW-Authenticate**:  This is sent by the server if it needs a form of authentication before it can response with the actual resource being requested.  It is often sent along with response code 401, which means "unauthorized".
-   **Accept-Charset**:  This request header tells the server which character sets are acceptable by the client.
-   **Content-Type**:  This header indicates the media type (text/HTML or application/JSON) of the client request sent to the server by the client, which help process the request body correctly.
-  **Cache-Control**:  This header is the cache policy defined by the server.  For this response, a cached response can be stored by the client and reused until the time defined in the Cache-Control header.

&nbsp;

### ***Response Codes***

The first line of a response message (that is, the status line) contains the response status code, which the server generates to indicate the outcome of the request.  Each status code is a three-digit number:

-   1xx (informational):  The request was successfully received; the server is continuing the process.
-   2xx (success):  The request was successfully received, understood, accepted, and serviced.
-   3xx (redirection):  Further action must be taken to complete the request.
-   4xx (client error):  The request cannot be understood or is unauthorized or the requested source could not be found.
-   5xx (server error):  The server failed to fulfill the request.

HTTP Status Codes

| Status Code | Meaning | Explanation |
| -- | -- | -- |
| 100 | Continue | The server received the request and is in the process of giving the response. |
| 200 | Okay | The request is fulfilled. |
| 301 | Move permanently | The resource required has been permanently moved to a new location.  The URL of the new location is given in the Location response header.  The client should issue a new request to the new location, and the application should update all references to this new location. |
| 302 | Found and redirected (or move temporarily) | This is the same as code 301, but the new location is temporary in nature.  The client should issue a new request, but applications need not update the reference. |
| 304 | Not modified | In response to the if-modified-since conditional GET request, the server notifies that the resource request has not been modified. |
| 400 | Bad request | The server could not interpret or understand the request; there is probably a syntax error in the request message. |
| 401 | Authentication required | The requested resource is protected and requires the client's credentials (username and password).  The client should resubmit the request with the appropriate credentials (username and password). |
| 403 | Forbidden | The server refuses to supply the resource, regardless of the identity of the client. |
| 404 | Not found | The requested resource cannot be found on the server. |
| 405 | Method not allowed | The requested method used (for example, POSt, PUT, DELETE) is a valid method.  However the server does not allowed that method for the resource requested.
| 408 | Request timeout | The request sent to the server took longer than the website's server was prepared to wait. |
| 414 | Request URI too large | The URI requested by the client is longer than the server is willing to interpret. |
| 500 | Internal server error | The server is confused; this may be caused by an error in the server-side program responding to the request. |
| 501 | Method not implemented | The request method used is invalid; this could be caused by a typing error, such as Get in place of GET. |
| 502 | Bad gateway | The proxy or gateway indicates that it received a bad response from the upstream server. |
| 503 | Service unavailable | The server cannot respond due to overloading or maintenance.  The client can try again later. |
| 504 | Gateway timeout | The proxy or gateway indicates that it received a timeout from an upstream server.

&nbsp;

### ***XML***

***Extensible Markup Language (XML)*** is a markup language that encodes information between descriptive tags.

XML is a superset of Hypertext Markup Language (HTML)

An entire XML document is stored as text, and it is both machine readable and human readable.

With XML you can assign some meaning to the tags in the document.  You can extract the various attributes from the response by simply locating the content surrounded by <study_room> and </study_room>; this content is technically known as the <study_room> ***element***.

XML Data Format:

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<root>
    <home>this is my house</home>
    <home>located in San Jose, CA</home>
    <rooms>
        <living_room>true</living_room>
        <kitchen>false</kitchen>
        <study_room>
            <size>20x30</size>
        </study_room>
        <study_room>
            <desk>true</desk>
        </study_room>
        <study_room>
            <lights>On</lights>
        </study_room>
    </rooms>
</root>
```

&nbsp;

### ***JSON***

***JavaScript Object Notation (JSON)*** format is derived from JavaScript object syntax, but it is entirely text based.  

JSON is a key:value data format that is typically rendered with curl braces {} and square brackets [].

A key/value pair has a colon (:) that separates the key from the value, and each such pair is separated by a comma in the document or the response.

JSON ***keys*** are valid strings.  The value of a key is one of the following data types:

-   **String**
-   **Number**
-   **Object**
-   **Array**
-   **Boolean (true or false)**
-   **Null**

```json
{
    "home": [
        "this is my house",
        "located in San Jose, CA"
    ],
    "rooms": {
        "living_room": "true",
        "kitchen": "false",
        "study_room": [
            {
                "size": "20x30"
            },
            {
                "desk": true
            },
            {
                "lights": "On"
            }
        ]
    }
}
```

&nbsp;

### ***YAML***

YAML is an acronym that stands for "***YAML Ain't Markup Language***."

YAML is a data serialization language.  It's a strict superset of JSON, another data serialization language.  But because it's a strict superset, it can do everything JSON can do and more.  One significant difference is that newlines and indentation means something in YAML, whereas JSON uses brackets and braces to convey similar ideas.  

YAML uses three main data formats:

-   **Scalars**:  The simplest is a *keyvalue* view.
-   **Lists/sequences**:  Data can be ordered by indexes.
-   **Dictionary mappings**:  These are similar to scalars but contain nested data, including other data types.

YAML Data Format

```yaml
---
home:
  -  this is my house
  -  located in San Jose, CA
rooms:
  living_room: 'true'
  kitche: 'false'
  study_room:
  -  size: 20x30
  -  desk: true
  -  lights: 'On'
```

&nbsp;

### ***Webhooks***

Webhooks are user-defined HTTP callbacks.  

A webhook is triggered by an event, such as pushing code to a repository or trying a keyword in a chat window.

An application implementing webhooks sends a POSt message to a URL when a specific event happens.  

Webhooks are also referred to as ***reverse APIs***, but more accurately a webhook lets you skip the request step in the request/response cycle.  Not request is required for a webhook, and a webhook sends data when triggered.

&nbsp;

For security reasons, the REST service may perform some validation to determine whether the receiver is valid.  A simple validation handshake performs validation, but this is just one way of validating.

&nbsp;

The validation token is a unique token specified by the server.

Validation tokens can be generated or revoked on the server side through the configuration UI.  

When the server sends data to a webhook URL, it includes a validation token in the request HTTP header.  The webhook URL should consist of the same validation token value in the HTTP response header.  This way, the server knows that it is sending to a validate endpoint and not a rogue endpoint.

&nbsp;

### ***Tools Used When Developing Webhooks***

&nbsp;

### ***Sequence Diagrams***

A sequence diagram models the interaction between various objects in a single use case.  It illustrates how the different parts of a system interact with each other to carry out a function and the order in which the interactions occur when a particular use case is executed.

In simpler terms, a sequence diagram shows how different parts of a system work in a sequence together to get something done.

&nbsp;

### ***REST Constraints***

REST defines six architectural constraints, also known as Fielding's constraints, that make any web service a truly RESTful API.

-   ***Client/server***
-   ***Stateless***
-   ***Cache***
-   ***Uniform interface***
-   ***Layered system***
-   ***Code on demand***

&nbsp;

### ***Client/Server***

The client and server exist independently.  They must have no dependency of any sort on each other.  The only information needed is for the client to know the source URIs on the server.  The interaction between them is only in the form of request initiated by the client and response that the server sends to the client in response to the requests.  The client/server constraint encourage separation of concerns between the client and the server and allows them to evolve independently.

&nbsp;

### ***Stateless***

REST services have to be stateless.  Each individual request contains all the information the server needs to perform the request and return a response, regardless of other requested made by the same API user.  The server should not need any additional information from previous requests to fulfill the current request.  The URI identifies the resource, and the body contains the state of the resource.  A stateless service is easy to scale horizontally, allowing additional servers to be added or removed as necessary without worry about routing subsequent requests to the same server.  The server can be further load balanced as necessary.

&nbsp;

### ***Cache***

With REST services, response data must be implicitly or explicitly labeled as cacheable or non-cacheable.  The service indicates the duration for which the response is valid.  Caching helps improve performance on the client side and capability on the server side.  If the client has access to a valid cached response for a given request, it avoids repeating the same request.  Instead, it uses its cached copy.  This helps alleviate some of the server's work and thus contributes to scalability and performance.

> Note
> <br>
> GET requests should be cacheable by default.  Usually browsers treat all GET requests as cacheable.
> <br>
> POST requests are not cacheable by default but can be made cacheable by adding either an Expires header or a Cache-Control header to the response.
> <br>
> PUT and DELETE are not cacheable at all.

&nbsp;

### ***Unform Interface***

The uniform interface is a contract for communication between a client and a server.  It is achieved through four subconstraints:

-  **Identification of resources**:  Resources are uniquely identified by URIs.  These identifies are stable and do not change across interactions, even when the resource state changes.
-  **Manipulation of resource through representation**:  A client manipulates resources by sending new representations of the resource to the service.  The server controls the resource representation and can accept or reject the new resource representation sent by the client.
-  **Self-descriptive messages**:  REST request and response messages contain all information needed for the service and the client to interpret the message and handle it appropriately.  The messages are quite verbose and include the method, the protocol use, and the content type.  This enables each message to be independent.
-  **Hypermedia as the Engine of Application State (HATEOS)**:  Hypermedia connects resources to each other and describes their capabilities in machine-readable ways.  Hypermedia refers to the hyperlinks, or simply links, that the server can include in the response.  Hypermedia is a way for the server to tell a client what HTTP requests the client might want to take in the future.

&nbsp;

### ***Layered System***

A layered system further builds on the concept of client/server architecture.  A layered system indicates that there can be more components than just the client and the server, and each system can have additional layers in it.  These layers should be easy to add, remove, or change.  Proxies, load balancers, and so on are examples of additional layers.

&nbsp;

### ***Code on Demand***

Code on demand is an optional constraint that gives the client flexibility by allowing it to download code.  The client can request code from the server, and the response from the server will contain some code, usually in the form of a script, when the response is in HTML format.  The client can then execute that code.

&nbsp;

### ***REST API Versioning***

Versioning is a crucial part of API design.  It gives developers the ability to improve an API without breaking the client's applications when new updates are rolled out.  Four strategies are commonly employed with API versioning:

-   **URI path versioning**:  In this strategy, the version number of the API is included in the URL path.
-   **Query parameter versioning**:  In this strategy, the version number is sent as a query parameter in the URL.
-   **Custom headers**:  REST APIs are versioned by providing custom headers with the version number included as an attribute.  The main difference between this approach and the previous ones is that it doesn't clutter the URI with versioning information.
-   **Content negotiations**:  This strategy allows you to version a single resource representation instead of versioning an entire API, which means it gives you more granular control over versioning.  Another advantage of this approach is that it doesn't require you to implement URI routing rules, which are introduced by versioning through the URI path.

&nbsp;

### ***Pagination***

There are two popular approaches to pagination:

-   **Offset-based pagination**
-   **Keyset-based pagination**, also known as *continuation token* or *cursor pagination* (recommended)

A simple approach to offset-based pagination is to use the parameters **offset** and **limit**:

*Pagination:  Offset and Limit*
```python
http://myhouse.cisco.com/api/room/livingroom/devices?offset=100&limit=15
# returns the devices between 100-115
```

Usually if the parameters are not specified, the default values are used.  Never return all resources.

&nbsp;

### ***Rate Limiting and Monetization***

Rate-limiting techniques are used to increase security, business impact, and efficiency across the board or end to end.  

-   Security:  Open access can decrease value and limit business success.  Rate limiting is a crucial component of an API's scalability.  Processing limits are typically measured in transactions per second (TPS).  If a user sends too many requests, API rate limiting can throttle client connections instead of disconnecting them immediately.  Throttling enables clients to keep using your service while still protecting your API.  Finally, there is always a risk of API requests timing out, and the open connections also increase the risk of DDoS attacks.
-   Business impact:  One approach to API rate limiting is to offer a free tier and a premium tier, with different limits for each tier.  Limits could be in terms of sessions or in terms of numbers of APIs per day or per month.  there are many factors to consider when deciding what to charge for premium API access.  API providers need to consider the following when setting up API rate limits:
    -   Are requested throttled when they exceed the limit?
    -   Do new calls and requests incur additional fees?
    -   Do new calls and requests receive a particular error code, and if so, which one?
-   Efficiency:  Unregulated API requests usually and eventually lead to slow page load times for websites.

&nbsp;

### ***Rate Limiting on the Client Side***

If you are writing client-side code, consider the following:

-   Avoid constant polling by using webhooks to trigger updates.
-   Cache your own data when you need to store specialized values or rapidly review very large data sets.
-   Query with special filters to avoid re-polling unmodified data.
-   Download data during off-peak hours.

&nbsp;

##  **REST Tools**

&nbsp;

### ***Postman***

&nbsp;

### ***curl***

curl is an extensive command-line tool.

Commonly used command-line options:

-   **-d**:  This option allows you to pass data to the remote server.  You can either embed the data in the command or pass the data using a file.
-   **-H**:  This option allows you to add an HTTP header to the request.
-   **-insecure**:  This option tells curl to ignore HTTPTs certification validation.
-   **-c**:  This option stores data received by the server.  You can reuse this data in subsequent commands with the -b option.
-   **-b**:  This option allows you to pass cookie data.
-   **-X**:  This option allows you to specify the HTTP method, which normally defaults to GET.

&nbsp;

### ***HTTPie***

HTTPie is a command-line HTTP client written in Python.

HTTPie is used primarily for testing, trouble-free debugging, and interacting with HTTP servers, web services, and RESTful APIs.

&nbsp;

### ***Python Requests***

Requests is a Python module that you can use to send HTTP requests.

You can use Requests with Python version 2.7 and 3.x.  

Requests is an external module, so it needs to be installed before you can use it:

```$ pip install requests```

To add HTTP headers to a request, you can simply pass them in a Python dict to the headers parameter.  Similarly, you can send your own cookies to a server by using a dict passed to the cookies parameter.

*Simple HTTP GET Using Python Requests*

```python
import requests

url = "https://postman-echo.com/get"
querystring = {"test":"123"}
headers = {}

response = requests.request("GET", url, headers=headers, params=querystring)
print(response.text)
```

*Simple HTTP POST Using Python Requests*

```python
import requests

url = "https://postman-echo.com/post"
payload = "hello DevNet"
headers = {'content-type': 'text/plain'}

response = requests.request("POST", url, data=payload, headers=headers)
print(response.text)
```

With the Requests library, authentication is usually done by passing the 'authorization' keyword along with the type key.

*Basic Auth Using Python Requests*

```python
import requests

url = "https://postman-echo.com/basic-auth"
headers = {
    'authorization': "Basic cG9zdG1hbjpwYXNzd29yZA=="
}

response = requests.request("GET", url, headers=headers)
print(response.text)
```

&nbsp;

### ***REST API Debugging Tools for Developing APIs***

&nbsp;

#   07 - Cisco Enterprise Networking Management Platforms and APIs

&nbsp;

##  **What is an SDK?**

&nbsp;

An SDK (software development kit) or devkit is a set of software development tools that developers can use to create software or applications for a certain platform, operating system, computer system, or device.

An SDK typically contains a set of libraries, APIs, documentation, tools, sample code, and processes that make it easier for developers to integrate, develop, and extend the platform.

A good SDK has these qualities:

-   Is easy to use
-   Is well documented
-   Has value-added functionality
-   Integrates well with other SDKs
-   Has minimal impact on hardware resources

SDKs provide the following advantage:

-   Quicker integration
-   Faster and more efficient development
-   Brand control
-   Increased security
-   Metrics

&nbsp;

##  **Cisco Meraki**

&nbsp;

Meraki cloud platform APIs:

-   ***Captive Portal API***
-   ***Scanning API***
-   ***MV Sense Camera API***
-   ***Dashboard API***

&nbsp;

The Cisco Meraki cloud platform also provides webhooks, which offer a way to subscribe to alerts sent from the Meraki cloud when an event occurs.

A Meraki alert includes a JSON-formatted message that can be configured to be sent to a unique URL, where it can be further processed, stored, and acted upon.

&nbsp;

The ***Captive Portal API*** extends the power of the built-in Meraki splash page functionality by providing complete control of the content and authentication process that a user interacts with when connecting to a Meraki wireless network.  This means Meraki network administrators can completely customize the portal, including the onboarding experience for clients connecting to the network, how the web page looks and feels, and then the authentication and billing process.

The ***Scanning API*** takes advantage of Meraki smart devices equipped with wireless and BLE (Bluetooth Low Energy) functionality to provide location analytics and report on user behavior.  The Scanning API delivers data in real time and can be used to detect Wi-Fi and BLE devices and clients.  The data is exported to a specific destination server through the HTTP POST and JSON documents.

The ***MV Sense Camera API*** takes advantage of the powerful onboard processor and a unique architecture to run machine learning workloads at the edge.  Through the MV Sense API, object detection, classification, and tracking are exposed and become available for application integration.  Both REST and MQTT API endpoints are provided, and information is available in a request or subscribe model.  MQ Telemetry Transport (MQTT) is a client/server publish/subscribe messaging transport protocol.  It is lightweight, simple, open, and easy to implement.  MQTT is ideal for use in constrained environments such as Internet of Things (IoT) and machine-to-machine communication where a small code footprint is required.

The Meraki APIs covered so far are mostly used to extract data from the cloud platform and build integrations and applications with that data.  

The ***Dashboard API***, provides endpoints and resources for configuration, management, and monitoring automation of the Meraki cloud platform.  The Dashboard API is meant to be open ended and can be used for many purposes and use cases.  Some of the most common use cases for the Dashboard API are as follows:

-   Provisioning new organizations, administrators, networks, devices, and more
-   Configuring networks at scale
-   Onboarding and decommissioning of clients
-   Building custom dashboards and applications

&nbsp;

To access the Dashboard API it must first be enabled.  Begin by logging into the Cisco Meraki dashboard at https://dashboard.meraki.com and navigating to **Organization > Settings**.  From there, scroll down and locate the section named **Dashboard API Access** and make sure to select **Enable Access** and save the configuration changes at the bottom of the page.  

Once the API has been enabled, select the username at the top-right corner of the web page, and select **My Profile**.  In the profile, scroll down and locate the section named **Dashboard API Access** and select **Generate New API Key**.  The API key generated is associated with your account.  You can generate, revoke, and regenerate an API key in the profile.  

For security reasons the API key is not stored in plaintext in the profile, so if it is lost you will have to revoke the old one and generate a new one.

&nbsp;

Every Dashboard APi request must specify the API key within the request header.  If a missing or incorrect API key is specified, the API returns a 404 HTTP error message.  

&nbsp;

The key for the authentication request header is **X-Cisco-Meraki-API-Key**, and the value is the API key obtained previously.

&nbsp;

In order to mitigate abuse and denial-of-service attacks, the Cisco Meraki Dashboard API is limited to 5 API calls per second per organization.  In the first second, a burst of an additional 5 calls is allowed, for a maximum of 15 API calls in the first 2 seconds per organization.  

If the rate limit is exceeded, an error message with HTTP status code 429 is returned.

The rate-limiting technique that tthe Dashboard API implements is based on the token bucket model.

&nbsp;

The Cisco Meraki Dashboard API uses the base URL **https://api.meraki.com/api/v0**.

&nbsp;

The Dashboard API is organized to mirror the structure of the Meraki dashboard.  The hierarchy of the Dashboard API looks as follows:

-   Organizations
    -   Networks
        -   Devices
            -   Uplinks

Most Dashboard API calls require either the organization ID or the network Id as part of the endpoint.  All API calls require an API key.

&nbsp;

The Meraki Dashboard API supports three special query parameters for pagination:

-   **perPage**:  The number of entries to be returned in the current request
-   **startingAfter**:  A value used to indicate that the returned data will start immediately after this value
-   **endingBefore**:  A value used to indicate that the returned data will end immediately before this value

While the types of the **startingAfter** and **endingBefore** values differ based on API endpoints, they generally are either timestamps specifying windows in time for which the data should be returned or integer values specifying IDs and ranges of IDs.

&nbsp;

The Dashboard API also supports action batches, which make it possible to submit multiple configuration requests in a single transaction and are ideal for initial provisioning of a large number of devices or performing large configuration changes through the whole network.  Action batches also provide a mechanism to avoid hitting the rate limitations implemented in the API for high-scale configuration changes as you can implement all the changes with one or a small number of transactions instead of a large number of individual API requests.  

Action batch transactions can be run either synchronously, waiting for the API call return before continuing or asynchronously, in which case the API call does not wait for a return as the call is placed in a queue for processing.

With action batches, you can be confident that all the updates contained in the transaction were submitted successfully before being committed because batches are run in an atomic fashion: all or nothing.

&nbsp;

At this point you need to obtain the organization ID for the account.

The base URL for the Dashboard API is **https://api.meraki.com/api/v0**.  To get the organization for the account with the API key, you have to append the **/organizations** resources to the base URL, resulting in **https://api.meraki.com/api/v0/organizations**.  You also need to indicate the **X-Cisco-Meraki-API-Key** header for authentication purposes.

The **curl** command would look as follows:

```curl
curl -I -X GET \
    --url 'https://api.meraki.com/api/v0/organizations' \
   -H 'X-Cisco-Meraki-API-Key: 6bec40cf957de430a6f1f2baa056b99a4fac9ea0'
    -H 'X-Cisco-Meraki-API-Key: '
```

Example of the response:

```
HTTP/1.1 302 Found
Server: nginx
Date: Sat, 17 Aug 2019 19:05:25 GMT
Content-Type: text/html; charset=utf-8
Transfer-Encoding: chunked
Connection: keep-alive
Cache-Control: no-cache, no-store, max-age=0, must-revalidate
Pragma: no-cache
Expires: Fri, 01 Jan 1990 00:00:00 GMT
X-Frame-Options: sameorigin
X-Robots-Tag: none
Location: https://n149.meraki.com/api/v0/organizations
X-UA-Compatible: IE=Edge,chrome=1
X-Request-Id: 87654dbd16ae23fbc7e3282a439b211c
X-Runtime: 0.320067
Strict-Transport-Security: max-age=15552000; includeSubDomains
```

The response code is a 302, indicating a redirect to the URL value in the **Location** header

When you specify the **-I** option for **curl**, only the headers of the response are displayed to the user.  You need to run the **curl** command again but this time specify the resource from the **Location** header which is **https://n149.meraki.com/api/v0/organizations**, remove the **-I** flag, and add an **Accept** header to specify that the response to the call should be in JSON format.

```curl
curl -X GET \
    --url 'https://n49.meraki.com/api/v0/organizations' \
    -H 'X-Cisco-Meraki-API-Key: 15da0c6ffff295f16267f88f98694cf29a86ed87' \
    -H 'Accept: application/json'
```

The response in this case contains the ID of the DevNet Sandbox organization JSON format:

```json
[
    {
        "name": "DevNet Sandbox",
        "id": "549236"
    }
]
```

&nbsp;

By default Postman has the **Automatically Follow Redirects** option enabled in Settings, so you don't have to change the resource address as it is already done in the background by Postman.

&nbsp;

To get a list of networks associated with an organization, you need to do a GET request to https://api.meraki.com/api/v0/organizations/{organizationID}/networks, where {organizationID} is the ID obtained previously:

```
curl - X GET \
    --url 'https://n149.meraki.com/api/v0/organizations/549236/networks' \
    -H 'X-Cisco-Meraki-API-Key: 15da0c6ffff295f16267f88f98694cf29a86ed87' \
    -H 'Accept: application/json'
```

The response from the API should contain a list of all the networks that are part of the DevNet Sandbox organization and should look similar to the output below:

```json
[
   {
      "timeZone" : "America/Los_Angeles",
      "tags" : " Sandbox ",
      "organizationId" : "549236",
      "name" : "DevNet Always On Read Only",
      "type" : "combined",
      "disableMyMerakiCom" : false,
      "disableRemoteStatusPage" : true,
      "id" : "L_646829496481099586"
   },
   {
      "organizationId" : "549236",
      "tags" : null,
      "timeZone" : "America/Los_Angeles",
      "id" : "N_646829496481152899",
      "disableRemoteStatusPage" : true,
      "name" : "test - mx65",
      "disableMyMerakiCom" : false,
      "type" : "appliance"
   }, ... omitted output
```

Once you've obtained a list of all the networks that are part of the organization, you can obtain a list of all devices that are part of a network using the associated network ID.  Like the previous step, the API resource that contains the information you are looking for is **/networks/{networkID}/devices**.

```curl
curl -X GET \
    --url 'https://n49.meraki.com/api/v0/networks/L_646829496481099586/devices' \
    -H 'X-Cisco-Meraki-API-Key: 15da0c6ffff295f16267f88f98694cf29a86ed87' \
    -H 'Accept: application/json'
```

&nbsp;

There are two SDKs for the Dashboard API: one is Python based and the other is Node.js based.

In order to get access to the Python SDK, you need to install the **meraki-sdk** module: 

```pip install meraki-sdk```

You then follow the same three steps previously: Get the organization ID, get a list of all networks the are part of the organization, and all the devices associated with a network.

You need to import the **MerakiSdkClient** class from the **meraki_sdk** module.  You can use the MerakiSdkClient class to create an API client by passing the API key as a parameter and creating an instance of this class called MERAKI.

```python
# /usr/bin/env python
from meraki_sdk.meraki_sdk_client import MerakiSdkClient

# Cisco DevNet Sandbox Meraki API key
X_CISCO_MERAKI_API_KEY = '15da0c6ffff295f16267f88f98694cf29a86ed87'

# Establish a new client connection to the Meraki REST API
MERAKI = MerakiSdkClient(X_CISCO_MERAKI_API_KEY)

# Get a list of all the organizations for the Cisco DevNet account
ORGS = MERAKI.organizations.get_organizations()

for ORG in ORGS:
    print("Org ID: {} and Org Name: {}".format(ORG['id'], ORG['name']))

PARAMS = {}
PARAMS["organization_id"] = "549236"    # Demo Organization "DevNet Sandbox"

# Get a list of all the networks for the Cisco DevNet organization
NETS = MERAKI.networks.get_organization_networks(PARAMS)
for NET in NETS:
    print("network ID: {0:20s}, Name: {1:45s},Tags: {2:<10s}".format(NET['id'], NET['name'], str(NET['tags'])))

# Get a list of all the devices that are part of the Always On Network
DEVICES = MERAKI.devices.get_network_devices("L_646829496481099586")
for DEVICES in DEVICES:
    print("Device Model: {0:9s},Serial: {1:14s},MAC: {2:17}, Firmware:{3:12s}").format(DEVICE['model', DEVICE['serial'], DEVICE['mac'], DEVICE['firmware']])
```

&nbsp;

##  **Cisco DNA Center**

&nbsp;

***Cisco Digital Network Architecture (DNA)*** is an open, extensible, software-driven architecture from Cisco that accelerates and simplifies enterprise network operations.  Behind this new architecture is the concept of intent-based networking.

***Cisco DNA Center*** is the network management and command center for Cisco DNA.  With Cisco DNA Center, you can provision and configure network devices, define consistent policy throughout a network, get live instantaneous statistics, and get granular networkwide views.  Multidomain and multivendor integrations are all built on top of a secure platform.

Cisco DNA Center provides a set of REST APIs and SDKs through the Cisco DNA Center platform that are grouped in the following categories:

-   ***Intent API***
-   ***Integration API***
-   ***Multivendor SDK***
-   ***Events and notifications***

&nbsp;

The ***Intent API*** is a northbound REST API that exposes specific capabilities of the Cisco DNA Center platform.The main purpose of the Intent API is to simplify the process of creating workflows that consolidate multiple network actions into one.

The Intent API provides automation capabilities and simplified workflows for QoS policy configuration, software image management and operating system updates for all devices  n the network, overall client health status, and monitoring of application health. 

&nbsp;

The ***Integration API*** was created to simplify and streamline end-to-end processes.  Through this API, Cisco DNA Center platform publishes network data, events, and notifications to external systems and at the same time can consume information from these connected systems.

Integrations with IT service management and ticketing systems are supported.  Automatic ticket creation and assignment based on network issues that are flagged by Cisco DNA Center are possible.  Cisco DNA Center can even suggest remediation steps based on the machine learning algorithms.

IP Address Management (IPAM) integrations are also supported by the Integration API.

Data as a service (DaaS) APIs that are part of the Integration API allow Cisco DNA Center to publish insights and data to external tools and reporting solutions.

The Integration aPI is also used for cross-domain integrations with other Cisco products, such as Cisco Meraki, Cisco Stealthwatch, and Cisco ACI.  The idea is to deliver a consistent intent-based infrastructure across data center, WAN, and security solutions.

&nbsp;

Cisco DNA Center allows customers to have their non-Cisco devices managed by DNA Center though a ***multivendor SDK***.  Cisco DNA Center communicates with third-party devices through ***device packages***.  The ***device packages*** are developed using the multivendor SDK and implemented southbound interfaces based on CLI, SNMP, or NETCONF.

&nbsp;

Cisco DNA Center also provides webhooks for ***events and notifications*** that are generated or on the Cisco DNA Center appliance itself.

You have the option of configuring a receiving URL to which the Cisco DNA Center platform can publish events.  Based on these events, the listening application can take business actions.

&nbsp;

The ***Intent API*** is organized into several distinct categories:

-   **Know Your Network category**:  This category contains API calls pertaining to sites, networks, devices, and clients:
    -   With the ***Site Hierarchy Intent API***, you can get information about, create, update, and delete sites as well as assigned devices to a specific site.  (Sites within Cisco DNA Center are logical groupings of network devices based on geographic location or site.)
    -   The ***Network Health Intent API*** retrieves data regarding network devices, their health, and how they are connected.
    -   The ***Network Device Detail Intent API*** retrieves detailed information about devices.  Different parameters can be passed to limit the scope of the information returned by the API, such as timestamp, MAC address, and UUID.  Besides all the detailed information you can retrieve for all the devices in the network, you can also add, delete, update, or sync specified devices.
    -   The ***Client Health Intent API*** returns overall client health information for both wired and wireless clients.
    -   The ***Client Detail Intent API*** returns detailed information about a single client.
-   **Site Management category**:  This category helps provision enterprise networks with zero-touch deployments and manage the activation and distribution of software images in these networks:
    -   The ***Site Profile Intent API*** gives you the option to provision NFV and ENCS devices as well as retrieve the status of the provisioning activities.
    -   The ***Software Image Management (SWIM)*** API enables you to completely manage the lifecycle of software images running within a network in an automated fashion.  With this API, you can retrieve information about available software images, import images into Cisco DNA Center, distribute images to devices, and activate software images that have been deployed to devices.
    -   The ***Plug and Play (PnP) API*** enables you to manage all PnP-related workflows.  With this API, you can create, update, and delete PnP workflows and PnP server profiles, claim and unclaim devices, add and remove virtual accounts, and retrieve information about all PnP-related tasks.
-   **Connectivity category**:  This category contains APIs that provide mechanisms to configure and manage both non-fabric wireless and Cisco SDA wired fabric devices.  For fabric devices, you can add and remove border devices to the fabric and get details about their status.  For non-fabric wireless devices, you can create, update, and delete wireless SSIDs, profiles, and provisioning activities.
-   **Operational Tools category**:  This category includes APIs for the most commonly used tools in the Cisco DNA Center toolbelt:
    -   The ***Command Runner API*** enables the retrieval of all valid keywords that Command Runner accepts and allows you to run read-only commands on devices to get their real-time configuration.
    -   The ***Network Discovery API*** provides access to the discovery functionalities of Cisco DNA Center.  You can use this API to create, update, delete, and manage network discoveries and the credentials needed for them.  You can also retrieve network discoveries, network devices that were discovered as part of a specific network discovery task, and credentials associated with these discoveries.
    -   The ***Temple Programmer API*** can be used to manage configuration templates.  You can create, view, edit, delete, version, add commands, check contents for errors, deploy, and check the status of template deployments.
    -   The ***Path Trace API*** provides access to the Path Trace application in Cisco DNA Center.  Path Trace can be used to troubleshoot and trace application paths throughout the network and provide statistics at each hop.  The API gives you access to initiating, retrieving, and deleting path traces.
    -   The ***File API*** enables you to retrieve files such as digital certificates, maps, and SWIM files from Cisco DNA Center.
    -   The ***Task API*** provides information about the network actions that are being run asynchronously.  Each of these background actions can take from seconds to minutes to completely, and each has a task associated with it.  You can query the Task API about the completion status of these tasks, get the task tree, retrieve tasks by their IDs, and so on.
    -   The ***Tag API*** gives you the option of creating, updating, and deleting tags as well as assigning tags to specific devices.  Tags are very useful in Cisco DNA Center; they are used extensively to group devices by different criteria.  You can then apply policies and provision and filter these groups of devices.

&nbsp;

The Cisco DNA Center platform APIs are rate limited to five API requests per minute.

&nbsp;

In Cisco DNA Center version .3, the REST API is not enabled by default.  Therefore, you need to log in to DNA Center with super-admin role account, navigate to Platform > Management > Bundles, and enable the DNA Center REST API bundle.  The status of the bundle should be active.

&nbsp;

The Cisco DNA Center platform API authorization is based on basic auth.  Basic auth is an authorization type that requires a username nad password.  The username and password are base-64 encoded and then transmitted to the API service in the Authorization header.  The authorization resource is **/system/api/v1/auth/token** and requires the API call to be POST.  The API endpoint then becomes **https://sandboxdnac2.cisco.com/system/api/v1/auth/token**.

```curl
curl -X POST \
    https://sandboxdnac2.cisco.com/dna/system/api/v1/auth/token \
    -H 'Authorization: Basic ZGV2bmV0dXNlcjpDaXNjbzEyMyE='
```

The result should be JSON formatted with the key **Token** and a value containing the actual authorization token:

```json
{"Token":"eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiI1Y2U3M-
TJiMDhlZTY2MjAyZmEyZWI4ZjgiLCJhdXRoU291cmNlIjoiaW50ZXJuYWwiL-
CJ0ZW5hbnROYW1lIjoiVE5UMCIsInJvbGVzIjpbIjViNmNmZGZmNDMwOTkwM-
DA4OWYwZmYzNyJdLCJ0ZW5hbnRJZCI6IjViNmNmZGZjNDMwOTkwMDA4OWYwZ-
mYzMCIsImV4cCI6MTU2NjU0Mzk3OCwidXNlcm5hbWUiOiJkZXZuZXR1c2VyIn0.
Qv6vU6d1tqFGx9GETj6SlDa8Ts6uJNk9624onLSNSnU"}
```

The token will be used in all subsequent API calls through a header that is called **X-Auth-Token**.

The API resource that will return a complete list of all network devices managed by Cisco DNA Center is **/dna/intent/api/v1/network-device**.

Since we're now retireving information, we need to do a GET request with the X-Auth-Token header:

```curl
curl -X GET \
    https://sandboxdnac2.cisco.com/dna/intent/api/v/network-device \
    -H 'X-Auth-token: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.
  eyJzdWIiOiI1Y2U3MTJiMDhlZTY2MjAyZmEyZWI4ZjgiLCJhdXRoU291c-
  mNlIjoiaW50ZXJuYWwiLCJ0ZW5hbnROYW1lIjoiVE5UMCIsInJvbGVzIjpbI-
  jViNmNmZGZmNDMwOTkwMDA4OWYwZmYzNyJdLCJ0ZW5hbnRJZCI6IjViNmNmZG-
  ZjNDMwOTkwMDA4OWYwZmYzMCIsImV4cCI6MTU2NjYwODAxMSwidXNlcm5hbWUiOi-
  JkZXZuZXR1c2VyIn0.YXc_2o8FDzSQ1YBhUxUIoxwzYXXWYeNJRkB0oKBlIHI'
```

The response should look like the following:

```json
{
   "response" : [
       {
         "type" : "Cisco 3504 Wireless LAN Controller",
         "roleSource" : "AUTO",
         "apManagerInterfaceIp" : "",
         "lastUpdateTime" : 1566603156991,
         "inventoryStatusDetail" : "<status><general code=\"SUCCESS\"/></status>",
         "collectionStatus" : "Managed",
         "serialNumber" : "FCW2218M0B1",
         "location" : null,
         "waasDeviceMode" : null,
         "tunnelUdpPort" : "16666",
         "reachabilityStatus" : "Reachable",
         "lastUpdated" : "2019-08-23 23:32:36",
         "tagCount" : "0",
         "series" : "Cisco 3500 Series Wireless LAN Controller",
         "snmpLocation" : "",
         "upTime" : "158 days, 13:59:36.00",
         "lineCardId" : null,
         "id" : "50c96308-84b5-43dc-ad68-cda146d80290",
         "reachabilityFailureReason" : "",
         "lineCardCount" : null,
         "managementIpAddress" : "10.10.20.51",
         "memorySize" : "3735302144",
         "errorDescription" : null,
         "snmpContact" : "",
         "family" : "Wireless Controller",
         "platformId" : "AIR-CT3504-K9",
         "role" : "ACCESS",
         "softwareVersion" : "8.5.140.0",
         "hostname" : "3504_WLC",
         "collectionInterval" : "Global Default",
         "bootDateTime" : "2019-01-19 02:33:05",
         "instanceTenantId" : "SYS0",
         "macAddress" : "50:61:bf:57:2f:00",
         "errorCode" : null,
         "locationName" : null,
         "softwareType" : "Cisco Controller",
         "associatedWlcIp" : "",
         "instanceUuid" : "50c96308-84b5-43dc-ad68-cda146d80290",
         "interfaceCount" : "8"
      },
      ... omitted output
   ],
   "version" : "1.0"
```

&nbsp;

The Cisco DNA Center Python SDK was developed for Python 3, and maps all the Cisco DNA Center APIs into classes and methods.  

Installing the SDK is as simple as issuing teh command **pip install dnacentersdk** from the command prompt.

```python
#! /usr/bin/env python
from dnacentersdk import api

# Create a DNACenterAPI connection obkect;
# it uses DNA Center sandbox URL, username, and password
DNAC = api.DNACenterAPI(username="devnetuser",
                        password="Cisco123!",
                        base_url="https://sandboxdnac2.cisco.com")

# Find all devices
DEVICES = DNAC.devices.get_device_list()

# Print select information about the retrieved devices
print('{0:25s}{1:1}{3:1}{4:15s}'.format("Device Name", "|", "Device Type", "|", "Up Time"))
print('-'*95)
for DEVICE in DEVICES.response:
    print('{0:25s}{1:1}{2:45s}{3:1}{4:15s}'.format(DEVICE.hostname, "|", DEVICE.type, "I", DEVICE.upTime))
print('-'*95)

# Get the health of all clients on Thursday, August 22, 2019 8:41:29 PM CMT
CLIENTS = DNAC.clients.get_overall_client_health(timestamp="1566506489000")

# Print select information about the retrieved client health statistics
print('{0:25s}{1:1}{2:45s}{3:1}{4:15s}'.format("Client Category", "|", "Number of Clients", "I", "Clients Score"))
print('-'*95)
for CLIENT in CLIENTS.response:
    for score in CLIENT.scoreDetail:
        print('{0:25s}{1:1}{2:<45d}{3:1}{4:<15d}'.format(score.scoreCategory.value, "|", score.clientCount, "|", score.scoreValue))
print('-'*95)
```

&nbsp;

##  **Cisco SD-WAN**

&nbsp;

Cisco SD-WAN (Software-Defined Wide Area Network) is a cloud-first architecture for deploying WAN connnectivity.  

An important feature of SDN is the separation of the control plane from the data plane.

The **control plane** includes a set of protocols and features that a network device implements so that it can determine which network path to use to forward data traffic.  Spanning tree protocols and routingprotocols are some of the protocols that make up the control plane in network devices.  

The **data plane** includes the protocols and features that a network device implements to forward traffic to its destination as quickly as possible.  Cisco Express Forward (CEF) is a proprietary switching mechanism that is part of the data plane.  

SDN separates the functionality of the control plane and data plane in different devices, and several benefits result.

-   The cost of the resulting network should be lower as not all devices have to implement expensive software and hardware features to accomodate both a control plane and data plane.
-   The convergence of this net network, which is the amount of time it takes for all devices to agree on a consistent view of the network, should be much lower than in the case of the non-SDN architecture.

&nbsp;

Cisco currently has two SD-WAN offerings.  The first one, based on the **Viptela** acquisition, is called **Cisco SD-WAN**; the second one, based on thet Meraki acquisition, is called **Meraki SD-WAN**.

-   **vManage**:  Cisco vManage is a centralized network managemente system that provides a GUI and REST API interface fto the SD-WAN fabric.  You can easily manage, monitor, and configure all Cisco SD-WAN components through this single pane of glass.
-   **vSmart**:  Cisco vSmart is the brains of the centralized control plane for the overlay SD-WAN network.  It maintains a centralized routing table and centralized routing policy that it propagates to all the network Edge devices through permanent DTLS tunnels.
-   **vBond**:  Cisco vBond is the orchestrator of the fabric.  It authenticates the vSmart controllers and the vEdge devices and coordinates connectivity between them.  The vBond orchestrator is the only component in the SD-WAN fabric that needs public IP reachability to ensure that all devices can connect to it.
-   **vEdge**:  Cisco vEdge routers, as the name implies, are Edge devices that are located at the perimeter of the fabric, such as in remote offices data center, branches, and campuses.  They represent the data plane and bring the whole fabric together and route traffic to and from their sites across the overlay network.

All the components of the Cisco SD-WAN fabric run as virtual appliances, adn the vEdges are also available as hardware routers.

Separating the WAN fabric this way makes it more scalable, faster to converge, and cheaper to deploy and maintain.

On top of the transport-independent underlay that supports all types of WAN circuits, an overlay network is built that runs OMP (Overlay Management Protocol).  Much like BGP, OMP propagates throughout the network all the routing information neede for all the components of the fabric to be able to forward data according to the routing policies configured in vManage.

&nbsp;

Cisco **vManage** provides a REST API that exposes the functionality of the Cisco SD-WAN software and hardware features.  The API resources that are avilabale through the REST itnerface are grouped in the following conditions:

-   **Administration**:  For management of users, groups, and local vManage instance
-   **Certificate Management**:  For management of SSL certificates and security keys
-   **Configuration**:  For creation of feature and device configuraiton templates and creation and configuraiton of vManage cluster
-   **Device Inventory**:  For collecting device inventory information including system status
-   **Monitoring**:  For getting access to status, statistics, and related operational information about all the deivces in the network every 10 minutes from all devices
-   **Real-Time Monitoring**:  For gathering real-time monitoring statistics and traffic information approximately once per second
-   **Troubleshooting Tools**:  For API calls used in troubleshooting, such as determine the effects of applying a traffic policy, updating software, or retrieving software version information

Cisco vManage exposes a self-documenting web interface for the REST API that is enabled by default and accessed at **https://vManage_IP_or_hostname:port/apidocs**.  The default port is 8443.

The web interface displays a list of all the REST API resources available, the methods associated with each one of them, and the model schema of the responses.

&nbsp;

The initial connection to a Cisco vManage instance is established through an authorization request to https://sandboxsdwan.cisco.com:8443/j_security_check.  The information sent over this POST call is a URL form encoded and contains the username and password.

```curl
curl -c -x -X POST -k \
    https://sandboxsdwan.cisco.com:8443/j_security_check \
    -H 'Content-Type: application/x-www-form-urlencoded' \
    -d 'j_username=devnetuser&j_password=Cisco123!'
```

&nbsp;

The **-c -** option passed to the **curl** request specifies that the returned authorization cookie should be printed to the console.  The **-k** option bypasses SSL certificate verification as the certificate for this sandbox is self-signed.  The output should look as follows:

```
# Netscape HTTP Cookie File

# https://curl.haxx.se/docs/http-cookies.html

# This file was generated by libcurl! Edit at your own risk.

#HttpOnly_sandboxsdwan.cisco.com.  FALSE  /  TRUE  0   JSESSIONID.
v9QcTVL_ZBdIQZRsI2V95vBi7Bz47IMxRY3XAYA6.4854266f-a8ad-4068-9651-
d4e834384f51
```

The long string after the **JSESSIONID** is the value of the authorization cookie that will be needed in all subsequent API calls.

To get a list of devices the resource is **/dataservice/device**:

```curl
curl -X GET -k \
    https://sandboxsdwan.cisco.com:8443/dataservice/device \
    -H 'Cookie: JSESSIONID=v9QcTVL_ZBdIQZRsI2V95vBi7Bz47IMxRY3XAYA6.4854266f-a8ad-4068-9651-d4e834384f51'
```

