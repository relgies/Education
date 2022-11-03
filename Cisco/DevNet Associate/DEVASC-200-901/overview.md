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

