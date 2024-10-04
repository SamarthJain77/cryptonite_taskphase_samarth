# cat: not the pet, but the command!

## About the Challenge
This challenge introduces the `cat` command, a fundamental tool in Linux used for displaying the contents of files in the terminal. The name `cat` is short for **concatenate**, which reflects its ability to concatenate and display the contents of one or more files.

## Process
1. **Understanding the `cat` Command**:
    - The basic usage of `cat` is to read and display the contents of a file.
    - Example:
    ```bash
    hacker@commands~cat-not-the-pet-but-the-command:~$ cat myfile
    This is my file!
    ```
    - If `cat` is provided multiple file names as arguments, it will read and output their contents in the order provided.
    - Example:
    ```bash
    hacker@commands~cat-not-the-pet-but-the-command:~$ cat myfile yourfile
    This is my file!
    This is your file!
    ```
    - When `cat` is invoked without any file arguments, it reads input from the terminal and echoes the input back to the terminal.

2. **Using `cat` to Read the `flag` File**:
    - Since the challenge starts with the shell located in the home directory (`~`), there is no need to change directories. We just need to read and display the contents of the `flag` file.
    - Here’s the command I used:
    ```bash
    hacker@commands~cat-not-the-pet-but-the-command:~$ cat flag
    ```

3. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@commands~cat-not-the-pet-but-the-command:~$ cat flag
    pwn.college{8fo0nZ1k5L2RbwIM55Y68VbJOd2.dFzN1QDL2YTN0czW}
    ```

## Key Takeaways
- The `cat` command is used for displaying file contents and concatenating multiple files.
- `cat <filename>` is used to read and output the content of a specific file.
