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