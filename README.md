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


### Listing all files in a directory
``` ls OR ls -a ``` 
Files started with a dot are hidden, and don't appear when using ls alone.
**-a** - lists all contents, including hidden files and directories
**-l** - lists all contents of a directory in long format
**-t** - order files and directories by the time they were last modified.

### Print working directory
``` pwd ```

### Change directory
``` cd ```

### Change to root directory
``` cd / ```

### Go back one step in the filesystem
``` cd .. ```

### Make a directory
``` mkdir DIRECTORY_NAME ```

### Create a new file
``` touch FILE_NAME.TXT ```
