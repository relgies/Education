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

