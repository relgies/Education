# Software Development and Design

## Do I Know This Already?

&nbsp;

-   What is Waterfall?
    -   A description of how blame flows from management on failed software projects
    -   A type of SDLC
    -   A serial approach to software development that relies on a fixed scope
    -   All of the above

&nbsp;

-   What is Agile
    -   A form of project management for Lean
    -   An implementation of Lean for software development
    -   A strategy for passing the CCNA DevNet Exam
    -   A key benefit of automation in infrastructure

&nbsp;

-   The Model-View-Controller pattern is often used in which of the follow applications?  (Choose three.)
    -   Web application with graphical interfaces
    -   Client/server applications with multiple client types
    -   PowerShell scripts
    -   Django

&nbsp;

-   Which of the following are true of the Observer pattern?  (Choose two.)
    -   It is publisher/subscriber pattern
    -   It is multicast pattern.
    -   It is used for configuration management applications and event handling
    -   It is not commonly used in infrastructure application design.

&nbsp;

-   What does BASH stand for?
    -   Born Again Shell
    -   Basic Shell
    -   Bourne Again Shell
    -   None of the above

&nbsp;

-   Which of the following is the best option for displaying your current environment variables?
    -   env | cat > emv.txt
    -   env | more
    -   export $ENV | cat
    -   echo env

&nbsp;

-   Which of the following is true of software version control?
    -   It is a naming convention for software releases.
    -   It is also known as source code management.
    -   It is the same thing as BitKeeper
    -   None of hte above are true.

&nbsp;

-   Who created Git?
    -   Junio Hamano
    -   Marc Andreesen
    -   John Chamber
    -   Linus Torvalds

&nbsp;

-   What are the three main structures tracked by Git?
    -   Index, head, and local repo
    -   Local workspace, index, and local repository
    -   Remote repository, head, and local index
    -   None of the above

&nbsp;

-   What command do you use to add the specific filename file.py to the Git index?
    -   git add .
    -   git index file.py
    -   git index add .
    -   git add file.py

&nbsp;

-   Which is one of the key benefits of conducting a code review?
    -   It helps you create higher-quality software
    -   You can find weak programmers who need more training
    -   It can be used to identify defects in software that are obvious
    -   None of the above

&nbsp;

## **Software Development Lifecycle**

&nbsp;

In the world of software, the ***Software Development Lifecycle (SDLC)*** provides sanity by providing guidance on building sustainable software packages.  SDLC lays out a plan for building, fixing, replacing, and making alterations to software.

&nbsp;

These are the stages of the SDLC:
 
 &nbsp;

 -  **Stage 1 - Planning**:  Identify the current use case or problem the software is intended to solve.  Get input from stakeholders, end users, and experts to determine what success looks like.  This is also known as *requirements analysis*.
-   **Stage 2 - Defining**:  This stage involves analyzing the functional specifications of the software - basically defining what the software is supposed to do.
-   **Stage 3 - Designing**:  In this phase, you turn the software specifications into a design specification.  This is a critical stage as stakeholders need to be in agreement in order to build the software appropriately; if they arne't, users won't be happy, and the project will not be successful.
-   **Stage 4 - Building**:  Once the software design specification is complete, the programmers get to work on making it a reality.  If the previous stages are completed successfully, this stage is often considered the easy part.
-   **Stage 5 - Testing**:  Does the software work as expected?  In this stage, the programmers check for bugs and defects.  The software is continually examined and tested until it successfully meets the original software specifications.
-   **Stage 6 - Deployment**t:  During this stage, the software is put into production for the end users to put it through its paces.  Deployment is often initially done in a limited way to do any final tweaking or detect any missed bugs.  Once the user has accepted the software and it is in full production, this stage morphs into maintenance, where bug fixes and software tweaks or smaller changes are made at the request of the business user.

&nbsp;

There are quite a few SDLC models that further refine the generic process just described.  They all use the same core concepts but vary in terms of implementation and utility for different projects and teams.  The following are some of the most popular SDLC models:

-   Waterfall
-   Lean
-   Agile
-   Interactive model
-   Spiral model
-   V model
-   Big Bang model
-   Prototyping models

You don't need to know all of these for the 200-901 DevNet ASsociate DEVASC exam.  The following sections cover the ones you should know most about:  Waterfall, Lean, and Agile.

&nbsp;

### **Waterfall**

&nbsp;

Origin:  The construction industry followed a rigid process in which every step along the way was dependent on the completion of the previous step in the process.  If you wanted to end up with a building that stays standing and meets the original design, you can't start construction until you have a plan and analyze the requirements for the building.  This thought process mapped nicely to software development, and the complexity of designing and constructing a building was similar to that of creating software applications.  ***Waterfall, which is based on the construction industry approach, became one of the most popular SDLC approaches.***

Waterfall is a serial approach to software development that is divided into phases:

-   **Requirements / analysis**:  Software features and functionality needs are cataloged and assessed to determine the necessary capabilities of the software.
-   **Design**:  The software architecture is defined and documented.
-   **Coding**:  Software coding begins, based on the previously determined design.
-   **Testing**:  The completed code is tested for quality and customer acceptance.
-   **Maintenance**:  Bug fixes and patches are applied.

While this approach has worked successfully over the years, a number of shortcomings have become weaknesses in this approach.

-   First, the serial nature of Waterfall, while easy to understand, means that the scope of a software project is fixed at the design phase.  In construction, making changes to the first floor of a building after you have begun the fifth floor is extremely difficult - and may even be impossible unless you knock down the building and start from scratch.  In essence, the Waterfall approach does not handle change well at all.  When you finally get to the coding phase of the application development process, you might learn that the feature you are building isn't needed anymore or discover a new way of accomplishing a design goal; however, you cannot deviate from the predetermined architecture without redoing the analysis and design.  Unfortunately, it is often more painful to start over than to keep building.  It is similar to being stuck building a bridge over a river that no one needs anymore.
-   The second aspect of Waterfall that is challenging is that value is not achieved until the end of the whole process.  We write software to automate some business functions or capability - and value is only realized when the software is in production and producing results.  With the Waterfall approach, even if you are halfway done with a project, you still have no usable code or value to show to the business.  Halfway Finished?  50% Complete, 100% Unusable.
-   The third aspect of Waterfall that is challenging is quality.  As mentioned earlier, time is the enemy when it comes to delivering value.  If we had unlimited time, we could create perfect software every time, but we simply don't live in that world.  When software developers run out of time, testing often suffers or is sacrificed in the name of getting the project out the door.

In short:
1.  Fixed design means changes cannot be made after the analysis and design phase.
2.  Value is not achieved until 100% of the project is complete.
3.  Quality suffers in order to complete the project in time.

The three challenges for Waterfall led to the development of a new way of creating software that was faster, better, and more adaptive to a rapidly changing environment.

&nbsp;

### **Lean**

&nbsp;

Origin:  After World War II, Japan was in desperate need of rebuilding.  Most of Japan's production capabilities had been destroyed, including those in the auto industry.  When Japan tackled this rebuilding, it didn't concentrate on only the buildings and infrastructure; it looked at ways to do things differently.  Out of this effort, the **Toyota Production System (TPS)** was born.  *Created by Taiichi Ohno and Sakichi Toyoda (founder of Toyota), this management and manufacturing process focuses on the following important concepts*:

-   **Elimination of waste**:  If something doesn't add value to the final product, get rid of it.  There is no room for wasted work.
-   **Just-in-time**:  Don't build something until the customer is ready to buy it.  Excess inventory wastes resources.
-   **Continuous improvement (Kizan)**:  Always improve your process with lessons learned and communication.


TPS was the first implementation of these principles as a management philosophy.  TPS was the start of the more generalized Lean manufacturing approach that was introduced to the Western world in 1991 through a book written by Womack, Jones, and Roos, *The Machine That Changed the World*.  This book was based on a five-year study MIT conducted on TPS, and it has been credited with bringing Lean concepts and processes beyond the auto industry.

Why spend time talking about old management books?  Lean led to Agile software development, which has served as a lightning rod of change for IT operations.

&nbsp;

### **Agile**

&nbsp;

***Agile is an application of Lean principles to software development.***

With Agile, all of the lessons learned in optimizing manufacturing processes have been applied to the discipline of creating software.

Origin:  In 2001, 17 software developers converged on the Snowbird resort in Utah to discuss new lightweight development methods.  Tired of the missing deadlines, endless documentation, and the inflexibility of existing software development practices, these Agile pioneers created the "Manifesto for Agile Software Development," which codifies the guiding principles for Agile development practices.  The following 12 principles are the core of the Agile Manifesto:
-   Customer satisfaction is provided through early and continuous delivery of valuable software.
-   Changing requirements, even in late development, are welcome.
-   Working software is delivered frequently (in weeks rather than months).
-   The process depends on close, daily cooperation between business stakeholders and developers.
-   Projects are built around motivated individuals, who should be trusted.
-   Face-to-face conversation is the best form of communication (co-location).
-   Working software is the principal measure of progress.
-   Sustainable development requires being able to maintain a constant pace.
-   Continuous attention is paid to technical excellence and good design.
-   Simplicity - the art of maximizing the amount of work done - is essential.
-   The best architectures, requirements, and designs emerge from self-organizing teams.
-   A team regularly reflects on how to become more effective and adjusts according.

These core tenets were the main spark of the Agile movement.  Mary Poppendieck and Tom Poppendieck wrote *Lean Development:  An Agile Toolkit* in 2003, based on the principles of the Agile Manifesto and their many years of experience developing software.

With Waterfall, a project is not "finished" and deployable until the very end.  With Agile, the time frame is changed:  Agile uses smaller time increments (often 2 weeks), or "sprints," that encompass the full process of analysis, design, code, and test but on a much smaller aspect of an application.  The goal is to finish a feature or capability for each sprint, resulting in a potentially shippable incremental piece of software.  Therefore, with Agile, if you are 40% finished with a project, you have 100% usable code.

By leveraging Agile, you can keep adding value immediately and nimbly adapt to change.  If a new capability is needed in the software, or if a feature that was planned is determined to no longer be necessary, the project can pivot quickly and make those adjustments.

&nbsp;

## **Common Design Patterns**

&nbsp;

When creating software, you will often run into the same problem over and over again.  You don't want to reinvent the wheel each time you need a rolling thing to make something move.  In software engineering, many common design paradigms have already been created, and you can reuse them in your software project.  These design patterns make you faster and provide tried-and-true solutions that have been tested and refined.  The follow section introduces a couple of design patterns that are really useful for networking automation projects:  the ***Model-View-Controller (MVC)*** and ***Observer patterns***.  While there are many more that you may be interested in learning about, these are the ones you will most likely see on the 200-901 DevNet Associate DEVASC exam.

&nbsp;

### **Model-View-Controller (MVC) Pattern**

&nbsp;

***The Model-View-Controller (MVC) pattern was one of the first design patterns to leverage the separation of concerns (SoC) principle***.  The SoC principle is used to decouple an application's interdependencies and functions from its other parts.  The goal is to make the various layers of the application - such as data access, business logic, and presentation (to the end user) - modular.  This modularity makes the application easier to construct and maintain while also allowing the flexibility to make changes or additions to the business logic.  It also provides a natural organization structure for a program that anyone can follow for collaborative development.  If you have used a web-based application, more than likely the app was constructed using an MVC pattern.

&nbsp;

>  **Note**
> Numerous web frameworks use MVC concepts across many programming languages.  Angular, Express, and Backbone are all written in JAvaScript.  Django and Flask are two very popular examples written in Python.

&nbsp;

The classic MVC pattern has three main parts:
-   **Model**:  The model is responsible for retrieving and manipulating data.  It is often tied to some type of database but could be data from a simple file.  It conducts all data operations, such as select, insert, update, and delete operations.  The model receives instructions from the controller.
-   **View**:  The view is what the end users see on the device they are using to interact with the program.  It could be a web page or text from the command line.  The power of the view is that it can be tailored to any device and any representation without changing any of the business logic of the model.  The view communicates with the controller by sending data or receiving output from the model through the controller.  The view's primary function is to render data.
-   **Controller**:  The controller is the intermediary between what the user sees and the backend logic that manipulates the data.  The role of the controller is to receive requests from the user via the view and pass those requests on to the model and its underlying data store.

&nbsp;

### **Observer Pattern**

&nbsp;

**The Observer pattern was created to address the problem of sharing information between one object to many other objects.**

This type of pattern describes a very useful behavior for distributed systems that need to share configuration information or details on changes as they happen.  The Observer pattern is actually very simple and consists of only two logical components:

-   **Subject**:  The subject refers to the object state being observed - in other words, the data that is to be synchronized.  The subject has a registration process that allows other components of an application or even remote systems to subscribe to the process.  Once registered, a subscriber is sent an update notification whenever there is a change in the subject's data so that the remote systems can synchronize.  
-   **Observer**:  The observer is the component that registers with the subject to allow the subject to be aware of the observer and how to communicate to it.  The only function of the observer is to synchronize its data with the subject when called.  The key thing to understand about the observer is that it does not use a polling process, which can be very inefficient with a larger number of observers registered to a subject.  Updates are push only.

*In short:  A single Subject can have multiple Observers.  When an Event Happens on the Subject, it will push a notify() to the Observers.*

***The Observer pattern is often used to handle communications between the model and the view in the MVC pattern.***  Say, for example, that you have two different views available to an end user.  One view provides a bar graph, and the other provides a scatter plot.  Both use the same data source from the model.  When the data changes or is updated, the two views need to be updated.  This is a perfect job for the Observer pattern.

&nbsp;

## **Linux BASH**

&nbsp;

For the DEVASC exam, you need to know how to use BASH and be familiar with some of the key commands.

&nbsp;

###  **Getting to Know BASH**

&nbsp;

***BASH is a shell, and a shell is simply a layer between a user and the internal workings of an operating system.***  A user can use the shell to input commands that the operating system will interpret and perform.

While there are many shells you can use, ***BASH, which stands for Bourne Again Shell***, is one of the most popular.  It has been around since 1989 and is the default shell on most Linux operating systems.  Until recently, it was also the default for the Mac operating system, but Apple has replaced BASH with Z shell.  The commands and syntax you will learn with BASH are transferable to Z shell, as it was built to maintain compatibility with BASH.

BASH is not only a shell for command processing using standard Linux operating system commands.  It can also read and interpret scripts for automation.  These capabilities are beyond the scope of what you need to know for the DEVASC exam, however are worth looking into as these automation scripts are where BASH really shines.  Like all other UNIX shells, BASH supports features such as ***piping*** (which involves feeding output from one command as the input of another command), ***variables***, ***evaluation of conditions***, and ***iteration*** (repeated processing of a command with **if** statements).  You also have a ***command history*** as part of the shell, where you can use the arrow keys to cycle through and edit previous commands.

&nbsp;

UNIX platforms such as Linux and OSX have built-in documentation for each command the operating system uses.  To access help for any command, type **man** (short for manual) and then the command you are curious about.  The output gives you a synopsis of the command, any optional flags, and required attributes.

&nbsp;

Not every command is intended to be run with user-level privileges.  You can temporarily upgrade your privileges by prepending the **sudo** command before you execute a command that needs higher-level access.  You will often be prompted for a password to verify that you have the right to use **sudo**.  You need to be careful when using **sudo**, as the whole idea of reduced privileges is to increase security and prevent average users from running commands that are dangerous.  Use **sudo** only when required, such as when you need to kick off an update for your Linux distribution, which you can do by using the **apt-get update** command:

&nbsp;

```
$sudo apt-get update
```

&nbsp;

As mentioned earlier, one of the most powerful features of BASH is something called piping.  This feature allows you to string together commands.  For example, the **cat** command displays the contents of a file to the screen.  What if a file contains too much to fit on a single screen?  The **cat** command will happily spew every character of the file at the screen until it reaches the end, regardless of whether you could keep up with it.  To address this, you can pipe the output of **cat** to the **more** command to stream the content from **cat** to **more**, which gives you a prompt to continue one page at a time.  To use the piping functionality, use the pipe character (|) between the commands.

&nbsp;

```
$cat weather.py | more
```

&nbsp;

###  **Directory Navigation**

&nbsp;

A UNIX-based file system has a directory tree structure.  The top of the tree is called the *root* (as it's an upside down tree), and you use the forward slash (/) to refer to root.  From root you have numerous directories and under each directory you have more directories or files.

Whenever you call a file, you have to supply its path.  Everything you execute in UNIX is in relationship to root.  To execute a file in the directory you are in, you can use the **./filename.sh**, where the leading **.** is simply an alias for the current directory.

In addition to the root file system, each user has a home directory that the user controls and that stores the user's individual files and applications.  The full path to the home directory often looks something like /home/*username* on Linux and /Users/*username* on Mac OS X, but you can also use the tilde shortcut (~/) to reference the home directory.

The following sections describe some of the commands most commonly used to interact with the BASH shell and provide examples of their options and use.

&nbsp;

**cd**

The **cd** command is used to change directories and move around the file system.  You can use it as follows:

| Command | Use |
| -- | -- |
| **$ cd /** | Changes directory to the root directory|
| **$ cd /home/username** | Changes directory to the /home/username directory|
| **$ cd test** | Changes directory to the test folder|
| **$ cd ..** | Moves up one directory |

&nbsp;

**pwd**

If you ever get lost while navigating around the file system, you can use the **pwd** command to print out your current working directory path.  You can use it as follows:

| Command | Use |
| -- | -- |
| **$ pwd** | Print your current working directory |

&nbsp;

**ls**

The **ls** command gives you a list of the current directory.  If you execute it without any parameters, it just displays whatever is in the directory.  It doesn't show any hidden files (such as configuration files).  Anything that starts with a **.** does not show up in a standard directory listing, and you need to use the **-a** flag to see all files, including hidden files.  By using the **-l** flag, you can see permissions and the user and group that own the file or directory.  You can also use the wildcard * to list specific filename values, for example, to find any files with test as a part of the name, you can use **ls \*test\***, which would match both 1test and test1.  You can use the ls command as follows:

| Command | Use |
| -- | -- |
| **$ ls** | Lists files and directories in the current working directory |
| **$ ls -a** | Lists everything in the current directory, including hidden files |
| **$ ls /home/username** | Lists everything in the /home/username directory | 
| **$ ls -l** | Lists permissions and user and group ownership |
| **$ ls -F** | Displays files and directories and denotes which are which |

&nbsp;

**mkdir**

To create a directory, you use the **mkdir** command.  If you are in your home directory or in another directory where you have appropriate permissions, you can use this command without **sudo**.  You can use the **mkdir** command as follows:

| Command | Use |
| -- | -- |
| **$ mkdir test** | Makes a new directory called test in the current working directory if you have permission |
| **$ mkdir /home/username/test** | Makes a new directory called test at /home/username/test |

&nbsp;

### **File Management**

&nbsp;

Working with files is easy with BASH.  There are just a few commands that you will use often, and they are described in the following sections.

&nbsp;

**cp**

The purpose of the **cp** command is to copy a file or folder someplace.  It does not delete the source file but instead makes an identical duplicate.  When editing configuration files or making changes that you may want to roll back, you can use the **cp** command to create a copy as a sort of backup.  The command requires several parameters:  the name of the file you want to copy and where you want to copy it to and the name of the copy.  When copying the contents of a folder, you need to use the **-r**, or recursive, flag.  You can use the **cp** command as follows:

| Command | Use |
| -- | -- |
| **$ cp sydney.text sydney2.txt** | Copies a file called sydney.txt from teh current directory and names the copy sydney2.txt |
| **$ cp /home/username/sydney.txt ~/sydney2.txt** | Copies a file as described above but using the full path and the home directory path |
| **$ cp -r folder folder.old** | Copies a folder |

&nbsp;

**mv**

The **mv** command allows you to move a file or folder from one directory to another, and it is also used to rename files or folders from teh command line, as BASH does not have a dedicated renaming function.  The **mv** command takes a source and destination, just as **cp** does.  You can use the **-i** flag to create an interactive option prompt when moving files that exist at the destination.  The **-f** flag forces the move and overwrites any files at the destination.  Wildcards also work to select multiple source files or directories.  You can use the **mv** command as follows:

| Command | Use |
| -- | -- |
| **$ mv caleb.txt calebfinal.txt** | Renames a file called caleb.txt to calebfinal.txt |
| **$ mv /home/username/caleb.txt ~calebfinal.txt** | Renames a file as described above but using full paths |
| **$ mv -i \* /home/username/new/** | Moves all files and directories in the current folder to a directory called new | 

&nbsp;

**rm**

To delete a file or directory, you use the **rm** command.  If the item you are deleting is a file or any empty directory, you just need to supply the name and press Enter.  On the other hand, if you try to delete a directory that has files in it, **rm** tells you that the directory is not empty.  In that case you can use the **-rf** flag to force the deletion.  You can use the **rm** command as follows:

| Command | Use | 
| -- | -- |
| **$ rm test.txt** | Deletes the file test.txt in the current working directory |
| **$ rm -rf test** | Forces the deletion of the folder test and everything in it |

&nbsp;

**touch**

The **touch** command is used to create a file and/or change the timestamps on a file's access without opening it.  This command is often used when a developer wants to create a file but doesn't want to put any content in it.  You can use the **touch** command as follows:

| Command | Use | 
| -- | -- |
| **$ touch emptyfile.txt** | Creates an empty file named emptyfile.txt |
| **$ touch file{1..20}.txt** | Bulk creates files from file1.txt to file20.txt |

&nbsp;

**cat**

The **cat** (which stands for *concatenate*) command allows you to view or create files and also pipe to other commands.  It's one of the most useful commands in UNIX when it comes to working with files.  You can use the **cat** command as follows:

| Command | Use |
| -- | -- |
| **$ cat file1.txt** | Displays the contents of file1.txt |
| **$ cat file1.txt \| more** | Displays the contents of file1.txt and pipes the output to **more** to add page breaks |
| **$ cat >file2.txt** | Sends a user's typed or copied content from the command line to ifile2.txt |

&nbsp;

### **Environment Variables** 

&nbsp;

BASH environment variables contain information about the current session.  Environment variables are available in all operating systems and are typically set when you open your terminal from a configuration file associated with your login.  You set these variables with similar syntax to how you set them when programming.  You do not often use these variables directly, but the programs and applications you launch do.  You can view all of your currently set environment variables by entering the **env** command.  Since there can be more entries than you have room to display on a single terminal page, you can pipe the results to the **more** command to pause between pages:

| Command | Use |
| -- | -- |
| **$ env \| more** | Shows all environment variables with page breaks |

If you execute this command, you are likely to notice a lot of keywords with the = sign tied to values.  One environment variable that you use every time you execute a command is the PATH variable.  This is where your shell looks for executable files.  If you add a new command and can't execute it, more than likely the place where the command was copied is not listed in your PATH.  To view any variable value, you can use the **echo** command and the variable you want to view.  You also need to tell bASH that it's a variable by using the **$** in front of it.  Here's an example:

&nbsp;

```
echo $PATH

/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin:/Applications/VMware
Fusion.app/Contents/Public:/opt/X11/bin
```

&nbsp;

To add a new value to the PATH variable, you can't just type **$PATH=/new_directory** because the operating system reads the environment variables only when the terminal session starts.  To inform Linux that an environment variable needs to be updated, you use the **export** command.  This command allows you to append your additional path to BASH and exists for the duration of the session.  Make sure you add the **:** or **,** in front of your new value, depending on your operating system.  The following example is for a Linux-style OS:

&nbsp;

```
$ export PATH=$PATH:/Home/chrijack/bin
```

&nbsp;

When you end your terminal session, the changes you made are not saved.  To retain the changes, you need to write the path statement to your **.bashrc** (or **.zshrc** if using Z shell) profile settings.  Anything written here will be available anytime you launch a terminal.  You can simply copy, add the previous command to the end of the **.bashrc** with your favorite text editor, or use the following command:

&nbsp;

```
$ echo "export PATH=$PATH:/Home/chrijack/bin" >> .bashrc
```

&nbsp;

This addition becomes active only after you close your current session or force it to reload the variable.  The **source** command can be used to reload the variables from the hidden configuration file **.bashrc**:

&nbsp;

```
$ source ~/.bashrc
```

&nbsp;

THe following command does the same thing as the previous one because **.** is also an alias for the **source** command:

&nbsp;

```
$ . ~/.bashrc
```

&nbsp;

## **Software Version Control**

&nbsp;

**The term ***version control*** is used to describe the process of saving various copies of a file or set of files in order to track changes made to those files.**  This description highlights how incredibly useful it is to the world of programming.  ***Software version control (SVC)*** typically involves a database that stores current and historical versions of source code to allow multiple people or teams to work on it at the same time.  If a mistake is made and you want to go back a revision (or to any previous version), SVC is the answer.  You may also hear it called revision control or source control, but it all falls under the topic of software configuration management.

Version control can protect your code by allowing changes to be checked in (through a process known as ***code commit***) to a hierarchical tree structure of folders with files in them.  Each check-in is tagged with who made the change and what the person changed within the code.  Instead of using inefficient techniques such as file locking, a version control system handles concurrent check-ins, allowing two programmers to commit code at the same time.

Another aspect of a version control system is the ability to branch and merge code built independently.  This is very useful if you are writing code on a part of an application that could conflict with another part written by another team.  By creating a branch, you effectively create a separate work stream that has its own history and does not impact the main "trunk" of the code base.  Once the code is written and any conflicts are resolved, the code from the branch can be merged back into the main trunk. 

Git is one of the most commonly used version control systems today, and the 200-901 DevNet Associate DEVASC exam will test your knowledge of it, so the next section covers how to use Git.

&nbsp;

## **Git**

&nbsp;

Git is free and open source.  In 2005, Linus Torvalds (the father of Linux) created Git as an alternative to the SCM system BitKeeper, when the original owner of BitKeeper decided to stop allowing free use of the system for Linux kernel development.  Git was created to be fast and scalable, with a distributed workflow that could support the huge number of contributors to the Linux kernel.  His creation was turned over to Junio Hamano in 2006, and it has become the most widely used source management system in the world.

&nbsp; 

> **Note**
> GitHub is not Git.  GitHub is a cloud-based social networking platform for programmers that allows anyone to share and contribute to software projects (open source or private).  While GitHub uses Git as its version control system underneath the graphical front end, it is not directly tied to the Git open-source project (much as a Linux distribution, such as Ubuntu or Fedora, uses the Linux kernel but is independently developed from it).

&nbsp;

### **Understanding Git**

&nbsp;

Git is a distributed version control system built with scalability in mind.  It uses a multi-tree structure, and if you look closely at the design, you see that it looks a lot like a file system.  (Linus Torvalds is an operating system creator after all.)  Git keeps track of three main structures or trees:
-   **Local workspace**:  This is where you store source code, files, binaries, images, documentation, and whatever else you need.
-   **Staging area**:  This is an intermediary storage area for items to be synchronized (changes and new items).
-   **Head, or local repository**:  This is where you store all committed items.

*Personal Comment:  Working Directory => Staging Area (Index) => Local Repository*

Another very important concept with Git is the file lifecycle.  Each file that you add to your working directory has a status attributed to it.  This status determines how Git handles the file.  Git file status lifecycle includes the following statuses:

-   Untracked:  When you first create a file in a directory that Git is managing, it is given an untracked status.  Git sees this file but does not perform any type of version control operation on it.  For all intents and purposes, the file is invisible to the rest of the world.  Some files, such as those containing settings or passwords or temporary files, may be stored in the working directory, but you may not want to include them in version control.  If you want Git to start tracking a file, you have to explicitly tell it to do so with the **git add** command; once you do this, the status of the file changes to tracked.