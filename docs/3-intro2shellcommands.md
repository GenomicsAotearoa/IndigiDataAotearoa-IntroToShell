# 3. Introduction to shell Commands (2)

## Examining file content¶


!!! terminal 

    There are a number of ways to examine the content of a file. `cat` and `less` are two commonly used programs for a quick look. Check the content of SRR097977.fastq by using these commands. Take a note of the differences.

    - Take a look at the content of `gen360_1.tsv` with `cat` command as below
    
    ```bash
    cat gen360_1.tsv
    ```

    - `cat` command will print the content of the file to *display* . This is not convenient for files with a lot of rows as it **Terminals** in their default settings will not allow us to scroll all the way back to the top. Using `less` command is slightly better

    ```bash
    less gen360_1.tsv
    ```

    - Use <KBD>Up</KBD> and <KBD>Down</KBD> arrow keys to navigate in `less` output

    <center>![image](./images/ex1_less_shortcuts.jpg){width="400"}</center>

    - What if we want to take a look at the "beginning" (`head`) or just the "end"(`tail`) of the file

    ```bash
    head gen360_1.tsv
    ```
    ```bash
    tail gen360_1.tsv
    ```
    
    - `head` and `tail`command will print top and bottom **10** lines, respectively. 
    - What If we want to take a look at top 15 lines ? . Both `head` and `tail` commands have a `-n` (number of lines) which allows us to over-ride the default

    ```bash
    head -n 15 gen360_1.tsv
    ```
    ```bash
    tail -n 15 gen360_1.tsv
    ```
## Doesn't require a full "view", just want to count the number of lines ?

!!! terminal 
    - `wc` (short for word count) is a command line tool in Unix/Linux operating systems, which is used to find out the number of newline count, word count, byte and character count in the files specified

    ```bash
    wc gen360_1.tsv
    ```
    ??? success "output"
        ```bash
        1500  3000 25504 gen360_1.tsv
        ```

        - `1500` : Number of lines 
        - `3000` : Number of Words
        - `25504` : Number of bytes

    ??? clipboard-question "Run `wc` command with `-l` , `-w` and `-m`  options against the `gen360_1.tsv` file and review the outputs ?"

## Redirection and extraction¶

!!! terminal 

    - Although using `cat` and `less` commands will allow us to view the content of the whole file, most of the time we are in search of particular characters (strings) of interest, rather than the full content of the file. One of the most commonly used command-line utilities to search for strings is `grep`. Let's use this command to search for the string **EUR**  in `gen360_1.tsv` file.
    
    ```bash
    grep EUR gen360_1.tsv
    ```
    
    - We can think of `grep` as a "extremely" powerful "search" command
    - Running `grep EUR gen360_1csv` printed the output to terminal which is not reliable during when we have to revise or re-use. In order for "string" of interest to be used for other operations, this has to be "redirected" (captured and written into a file). The command for redirecting output to a file is `>`. Redirecting the string of `EUR` that was searched using the grep command to a file `eur.txt` can be done with

    ```bash
    grep EUR gen360_1.tsv > eur.txt
    ```

    - In other words, `>` operates as a `Save` command

