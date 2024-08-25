# 2. Access the shell and Introduction to shell Commands (1)

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

    ??? success "output - may vary a bit from one computer to another. Check whether the output contains `shell-data`"

        ```bash
        shell-data ...
        ```
    <br>

    We can make the ls output more comprehensible by using the flag `-F`, which tells ls to add a trailing / to the names of directories:

    * Anything with a “`/`” after it is a directory. Things with a “`*`” after them are programs. If there are **no** decorations, it’s a file.
        
    ```bash
    ls -l
    ```
    ??? success "output"
        ```bash
        shell-data/  .....
        ``` 
!!! square-pen "All commands have a lots of "options" similar to `-F` in `ls`"
    - Retrieving the list of  "options" for a command can be done with `command --help`  ( For an example `ls --help`).  However, some command don't implement `--help` and even the ones with it might not show the full set of options. Solution for this to use `man` command ( or the modern day solution is to search online 😊)
    - `man` (short for manual) displays detailed documentation (also referred as man page or man file) for bash commands. It is a powerful resource to explore bash commands, understand their usage and flags. Some manual files are very long. You can scroll through the file using your keyboard’s down arrow or use the <KBD>Space</KBD> key to go forward one page and the <KBD>b</KBD> key to go backwards one page. When you are done reading, hit <KBD>q</KBD> to quit.

!!! terminal 
    Let’s say we want to navigate to the <KBD>shell-data</KBD> directory we saw above. We can use the following command to get there:

    ```bash
    cd shell-data
    ```
    and run `pwd` to check the the *change* in current working directory followed by `ls` to list the contents of that directory

    ```bash
    pwd
    ```
    ??? success "output"
        ```bash
        /home/USER/shell-data
        ```

    ```bash
    ls  
    ```
    ??? success "output"
        ```
        sra_metadata  untrimmed_fastq

        ```
!!! feather "Shortcut - Tab Completion"

    Typing out file or directory names can waste a lot of time and it’s easy to make typing mistakes. Instead we can use tab complete as a shortcut. When you start typing out the name of a directory or file, then hit the <KBD>Tab</KBD> key, the shell will try to fill in the rest of the directory or file name.

    !!! terminal-2 "Return to your home directory and navigate back to `shell-data` with the help of <KBD>Tab</KBD>:"

        ```bash
        cd
        ```

        - `cd` command without a follow up argument will revert the working directory to `/home`directory. Same can be done with `cd ~`
        
        - Now enter
        
        ```bash
        cd she<Tab>/untr<Tab>
        ```

        - The shell will fill in the rest of the directory name for `shell-data`
        - Using <KBD>Tab</KBD> complete can be very helpful. However, it will only autocomplete a file or directory name if you’ve typed enough characters to provide a unique identifier for the file or directory you are trying to access.

        - For example, if we now try to list the files which names start with `gen` by using tab complete:

        ```bash
        ls SR<tab>
        ```

        - The shell auto-completes your command to `SRR09_`, because all file names in the directory begin with this prefix. When you hit Tab again, the shell will list the possible choices.

!!! terminal "code"

    So far, we have navigated to `shell-data` directory from `/home` with `cd` command and return to `/home` via the same method. What if we want to take a look at the content of `/home` directory without navigating back to it 

    - Confirming the current working directory is `/home/USER/shell-data/untrimmed_fastq`

    ```bash
    pwd
    ```

    - use `ls ..` command where `..` represents "one step up"

    ```
    ls ..
    ```
## Copying, renaming, removing files and creating directories

!!! terminal 

    - Confirm the current working directory is `/home/USER/shell-data/untrimmed_fastq`

    - Let's create a sub-directory within the `..shell-data` directory and name it `backup`. This can be done with the `mkdir` command

    ```bash
    mkdir backup
    ```
    - List the content of the current directory with `ls -F` to make sure the directory was created 
    
    ```bash
    ls -F
    ```
    ??? success "output"
        ```bash
        backup/  SRR097977.fastq*  SRR098026.fastq*
        ```

    - create a copy of `SRR097977.fastq` file and name it `SRR097977.fastq.backup`
    
    ```bash
    cp SRR097977.fastq SRR097977.fastq.backup
    ```
    
    - "move" `SRR097977.fastq.backup` file to `backup/` directory  with `mv` command 

    ```bash
    mv SRR097977.fastq.backup backup/
    ```

    - Check the content of `backup/` directory with `ls` 

    ```bash
    ls backup/
    ```

    - Delete the file in backup directory 

    ```bash
    rm backup/SRR097977.fastq.backup
    ```

    !!! clipboard-question "Check whether you can delete the `backup/` directory with `rm` command"