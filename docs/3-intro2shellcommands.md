# 3. Introduction to shell Commands (2)

## Examining file contents¶


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