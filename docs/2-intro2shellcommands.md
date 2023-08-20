# 2. Access the shell and Introduction to shell Commands 

## How to access the shell 

On a Mac or Linux machine, you can access a shell through a program called “Terminal”, which is already available on your computer. The Terminal is a window into which we will type commands. If you’re using Windows, you’ll need to download a separate program to access the shell.


## Navigating your file system 

The part of the operating system that manages files and directories is called the file system. It organizes our data into files, which hold information, and directories (also called “folders”), which hold files or other directories.

Several commands are frequently used to create, inspect, rename, and delete files and directories.

!!! terminal "code"

    Let’s find out where we are by running a command called pwd (which stands for “print working directory”). At any moment, our current working directory is our current default directory, i.e., the directory that the computer assumes we want to run commands in, unless we explicitly specify something else. Here, the computer’s response is /home/USERNAME

    ```bash
    pwd
    ```
    ??? success "output"

        ```
        /home/USERNAME
        ```
!!! terminal 

    Let’s look at how our file system is organized. We can see what files and subdirectories are in this directory by running `ls`, which stands for “listing”. `ls` prints the names of the files and directories in the current directory in alphabetical order, arranged neatly into columns. We’ll be working within the shell_data subdirectory, and creating new subdirectories, throughout this workshop.

    ```bash
    ls
    ```

    ??? success "output - may vary a bit from one computer to another. Check whether the output contains `sample-data`"

        ```bash
        sample-data ...
        ```
    <br>

    We can make the ls output more comprehensible by using the flag `-F`, which tells ls to add a trailing / to the names of directories:

    * Anything with a “`/`” after it is a directory. Things with a “`*`” after them are programs. If there are **no** decorations, it’s a file.
        
    ```bash
    ls -l
    ```
    ??? success "output"
        ```bash
        sample-data/  .....
        ``` 
!!! square-pen "All commands have a lots of "options" similar to `-F` in `ls`"
    - Retrieving the list of  "options" for a command can be done with `command --help`  ( For an example `ls --help`).  However, some command don't implement `--help` and even the ones with it might not show the full set of options. Solution for this to use `man` command ( or the modern day solution is to search online 😊)
    - `man` (short for manual) displays detailed documentation (also referred as man page or man file) for bash commands. It is a powerful resource to explore bash commands, understand their usage and flags. Some manual files are very long. You can scroll through the file using your keyboard’s down arrow or use the <KBD>Space</KBD> key to go forward one page and the <KBD>b</KBD> key to go backwards one page. When you are done reading, hit <KBD>q</KBD> to quit.

!!! terminal 
    Let’s say we want to navigate to the <KBD>sample-data</KBD> directory we saw above. We can use the following command to get there:

    ```bash
    cd sample-data
    ```
    and run `pwd` to check the the *change* in current working directory followed by `ls` to list the contents of that directory

    ```bash
    pwd
    ```
    ```bash
    ls 
    ```