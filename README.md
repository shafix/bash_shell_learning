# bash_shell_learning
Bash / Shell learning

## What are bash scripts?
A Bash script is a plain text file which contains a series of commands. These commands are a mixture of commands we would normally type ouselves on the command line (such as ls or cp for example) and commands we could type on the command line.
Anything you can run normally on the command line can be put into a script and it will do exactly the same thing.

It is convention to give files that are Bash scripts an extension of .sh (myscript.sh for example).

## Filesystem
A filesystem organizes a computer's files and directories into a tree structure:
-The first directory in the filesystem is the root directory. It is the parent of all other directories and files in the filesystem.
-Each parent directory can contain more child directories and files. Here blog/ is the parent of 2014/, 2015/, and hardware.txt.
-Each directory can contain more files and child directories. The parent-child relationship continues as long as directories and files are nested.

## Command options
Options modify the behavior of commands. 
Example : Here we used ls -a to display the contents of the working directory in more detail.

``` ls -a ```

In addition to using each option separately, like ls -a or ls -l, multiple options can be used together, like ls -alt.

## Listing all files in a directory
``` ls OR ls -a ``` 
Files started with a dot are hidden, and don't appear when using ls alone.

**-a** - lists all contents, including hidden files and directories

**-l** - lists all contents of a directory in long format

**-t** - order files and directories by the time they were last modified.

## ls -l listed files components
Example
```
drwxr-xr-x 5  cc  eng  4096 Jun 24 16:51  action
drwxr-xr-x 4  cc  eng  4096 Jun 24 16:51  comedy
drwxr-xr-x 6  cc  eng  4096 Jun 24 16:51  drama
-rw-r--r-- 1  cc  eng     0 Jun 24 16:51  genres.txt
```
1.Access rights. These are actions that are permitted on a file or directory.

2.Number of hard links. This number counts the number of child directories and files. This number includes the parent directory link 
(..) and current directory link (.).

3.The username of the file's owner. Here the username is cc.

4.The name of the group that owns the file. Here the group name is eng.

5.The size of the file in bytes.

6.The date & time that the file was last modified.

7.The name of the file or directory.

## Wildcards
In addition to using filenames as arguments, we can use special characters like * to select groups of files. These special characters are called wildcards. The ```*``` selects all files in the working directory.

```m*.txt``` selects all files in the working directory starting with "m" and ending with ".txt"

## Redirection / Pipeline
Through redirection you can direct the input and output of a command to and from other files and programs, and chain commands together in a pipeline. Let's try it out.

***standard input***, abbreviated as ```stdin```, is information inputted into the terminal through the keyboard or input device.

***standard output***, abbreviated as ```stdout```, is the information outputted after a process is run.

***standard error***, abbreviated as ```stderr```, is an error message outputted by a failed process.

The ```>``` command redirects the standard output to a file. 

Example: ``` echo "Hello" > hello.txt ```

## Redirecting content from one file to another:
``` cat oceans.txt > continents.txt ```
Note that ```>``` **overwrites all original content** in continents.txt. 

```  cat glaciers.txt >> rivers.txt ```
```>>``` takes the standard output of the command on the left and **appends (adds)** it to the file on the right. 

## Pipeline
```|``` is a "pipe". The ```|``` takes the standard output of the command on the left, and pipes it as standard input to the command on the right. You can think of this as "command to command" redirection.

Example:
``` cat volcanoes.txt | wc | cat > islands.txt ```

### Find and replace
``` sed 's/snow/rain/' forests.txt ```

```sed``` stands for "stream editor". It **accepts standard input and modifies it based on an expression**, before displaying it as output data. It is similar to "find and replace".

Let's look at the expression 's/snow/rain/':

-s: stands for "substitution". it is always used when using sed for substitution.
-snow: the search string, the text to find.
-rain: the replacement string, the text to add in place.

In this case, sed searches forests.txt for the word "snow" and replaces it with "rain." Importantly, the above command **will only replace the first instance** of "snow" on a line. Use ```-g``` to replace all instances.

# Environment
Each time we launch the terminal application, it creates a new session. The session immediately loads settings and preferences that make up the command line environment.

We can configure the environment to support the commands and programs we create. This enables us to customize greetings and command aliases, and create variables to share across commands and programs.

### Bash profile:
First need to create a bash_profile file:
``` nano ~/.bash_profile ```

The command ```source ~/.bash_profile ``` activates the changes in ```~/.bash_profile``` for the current session. Instead of closing the terminal and needing to start a new session, source makes the changes available right away in the session we are in.

### Assigning aliases in the .bash_profile file:
``` alias new_alias="what it does" ```

``` alias ll="ls -la" ```

### Environmental variables:
Environment variables are variables that can be used across commands and programs and hold information about the environment.
``` export USER="Jane Doe" ```

1.The line USER="Jane Doe" sets the environment variable USER to a name "Jane Doe". Usually the USER variable is set to the name of the computer's owner.
2.The line export makes the variable to be available to all child sessions initiated from the session you are in. This is a way to make the variable persist across programs.
3.At the command line, the command echo $USER returns the value of the variable. Note that $ is always used when returning a variable's value. Here, the command echo $USER returns the name set for the variable.


# Using NANO (Similar to VIM)
``` nano FILENAME.TXT ```

Note: Creates a new file if it does not exist yet

```^O``` saves the file, ```^X``` exits the file



# Commands:

### Print working directory
``` pwd ```

### Change directory
``` cd ```

### Change to root directory
``` cd / ```

### Change to home directory
``` cd ~/ ```

### Go back one step in the filesystem
``` cd .. ```

### Make a directory
``` mkdir DIRECTORY_NAME ```

### Create a new file
``` touch FILE_NAME.TXT ```

### Copying (copy+paste)
To copy multiple files into a directory, use cp with a list of source files as the first arguments, and the destination directory as the last argument.
Copying to an existing file owerwrites it.
``` cp PATH1/FILE1.TXT PATH2/FILE2.TXT DESTINATION_PATH/ ```

### Moving (cut+paste)
``` mv PATH1/FILE1.TXT PATH2/FILE2.TXT DESTINATION_PATH/ ```

### Remove (delete)
``` rm PATH/FILE.TXT ```

The ```-r``` stands for "recursive," and it's used to delete a directory and all of its child directories.

``` rm -r DIRECTORY ```

### Echo (standard input)
Standard input command lets you enter strings via keyboard.
``` echo "bullshit" ```

### Cat (standard output)
The ```cat``` command outputs the contents of a file to the terminal.

``` cat hello.txt ```

### WC (word count)
The ```wc``` command outputs the number of lines, words, and characters.

``` wc FILENAME.TXT ```

### Sort (sorting the lines in a textfile)
```sort``` takes the standard input and orders it alphabetically for the standard output.

### Uniq (Unique)
```uniq``` stands for "unique" and filters out adjacent, duplicate lines in a file. 

### Grep (global regular expression print)
```grep``` stands for "global regular expression print". It searches files for lines that match a pattern and returns the results. It is also case sensitive.

Example:
``` grep -i Mount mountains.txt ```

```grep -i``` enables the command to be case insensitive. Here, grep searches for capital or lowercase strings that match Mount in mountains.txt.

### Grep -R (search directory)
```grep -R``` searches all files in a directory and outputs filenames and lines containing matched results. -R stands for "recursive". 

