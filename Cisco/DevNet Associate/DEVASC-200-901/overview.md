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