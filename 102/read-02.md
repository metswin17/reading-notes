the command line (also known as a terminal) running Bash.

**Don't think of the command line** as leaving the GUI behind so much as adding to it.

we can have several command lines open and doing different tasks in each at the same time.
 command line, or terminal, is a text based interface to the system. You are able to enter commands by typing them on the keyboard and feedback will be given to you 

*Within a terminal* you have what is known as a shell. This is a part of the operating system that defines how the terminal will behave and looks after running (or executing) commands for you.similarly as text.
There are various shells available but the most common one is called BASH which stands for Bourne Again SHell.
 you may use a command called echo to display a system variable stating your current shell. echo is a command which is used to display messages. Helps with list of prior commands up to 1000

**Basic Navigation**  

The first command we are going to learn is pwd which stands for Print Working Directory. 

What we learned 
pwd
Print Working Directory - ie. Where are we currently.
ls
List the contents of a directory.
cd
Change Directories - ie. move to another directory.
  


 **Important concept** 

***Relative path***
A file or directory location relative to where we currently are in the file system.
***Absolute path***
A file or directory location in relation to the root of the file system.

In the previous section we learnt about something called Tab Completion. If you use that before encountering the space in the directory name then the terminal will automatically escape any spaces in the name for you.


**Summary** 
What we learnt

file
obtain information about what type of file a file or directory is.
ls -a
List the contents of a directory, including hidden files.

**Important concepts** 

Everything is a file under Linux
Even directories.
Linux is an extensionless system
Files can have any extension they like or none at all.
Linux is case sensitive
Beware of silly typos.

*Answer*
What are four important features to look for in a text editor?

a) Code completion

b) syntax highlighting

c) variety of 'Themes' User friendly interface

d) good selection of extensions

>What do the following commands do?> 

ls Pwd  Print working Directory what your current or present working directory is in (Folder or path you are currently in) 

Ls is a command that lists the contents of folder you are in.

Cd If you run the command cd without any arguments then it will always take you back to your home directory. But it will change your directory 

Mkdir  in Linux is a command used to create a new directory (folder) like right click

Touch is a command used primarily to create empty files or update the timestamps of existing files.makes a file


Can you explain what is happening in the following scenario if these commands and arguments are entered into the command line? 

(Arguments are extra instructions given to a command.)

cd projects   The command cd projects is used in the terminal to change your current directory to a folder named projects.

**Breakdown**:

cd = change directory  mouse as opposed to command


projects = the name of the folder you want to move into

touch new-project/newfile.md  Creates a new empty file named newfile.md inside the new-project directory.

**Breakdown**:

touch → A command used in Unix/Linux/macOS to create an empty file or update the timestamp of an existing file.


new-project/newfile.md → The path where the new file should be created.


cd = change directory


.. = the parent directory (one level up)


So:
cd .. moves you up one folder from your current location.



ls projects/new-project  is a shell (Linux/macOS) command. Here’s what is happening step-by-step:
**Breakdown**:
ls — lists the contents of a directory.


projects/new-project — is the path to the directory whose contents you want to list.


📌 What the command does
It tells the system:
“Show me all files and folders inside the directory new-project, which is inside the projects directory.”




