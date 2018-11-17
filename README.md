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

### Copying
To copy multiple files into a directory, use cp with a list of source files as the first arguments, and the destination directory as the last argument.
Copying to an existing file owerwrites it.
``` cp PATH1/FILE1.TXT PATH2/FILE2.TXT DESTINATION_PATH/ ```
