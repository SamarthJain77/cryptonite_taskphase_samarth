# cat: not the pet, but the command!

## About the Challenge
This challenge introduces the `cat` command, a tool in Linux used for displaying the content of files in the terminal. The name `cat` is short for **concatenate**, which reflects its ability to concatenate and display the content of one or more files.

## Process
1. **Understanding the `cat` Command**:
    - The basic usage of `cat` is to read and display the content of a file.
    - Example:
    ```bash
    hacker@commands~cat-not-the-pet-but-the-command:~$ cat myfile
    This is my file!
    ```
    - If `cat` is provided multiple file names as arguments, it will read and output their content in the order provided.
    - Example:
    ```bash
    hacker@commands~cat-not-the-pet-but-the-command:~$ cat myfile yourfile
    This is my file!
    This is your file!
    ```
    - When `cat` is invoked without any file arguments, it reads input from the terminal and echoes the input back to the terminal.

2. **Using `cat` to Read the `flag` File**:
    - Since the challenge starts with the shell located in the home directory (`~`), there is no need to change directories. We just need to read and display the content of the `flag` file.
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
- The `cat` command is used for displaying file content and concatenating multiple files.
- `cat <filename>` is used to read and output the content of a specific file.
- `cat <file1> <file2> <file3>` is used to read and output the content of multiple files in a specific order.

# catting absolute paths

## About the Challenge
In this challenge, we explore using `cat` to read files using **absolute paths**.

## Process
1. **Understanding the `cat` Command with Absolute Paths**:
    - `cat` can be used with absolute paths to read any accessible file without needing to change directories.
    - Syntax:
    ```bash
    cat /absolute/path/to/file
    ```
2. **Understanding the Absolute Path**:
    - The challenge specifies that the flag file is located at `/flag`.
    
3. **Using `cat` to Read the `flag` File**:
    - Since `cat` can be used with absolute paths, there is no need to change directories. We just need to read and display the content of the `flag` file.
    - Here’s the command I used:
    ```bash
    hacker@commands~catting-absolute-paths:~$ cat /flag
    ```

4. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@commands~catting-absolute-paths:~$ cat /flag
    pwn.college{shAmmrjCPe7RIs1HMKTTCq7E3rR.dlTM5QDL2YTN0czW}
    ```

## Key Takeaway
- When using `cat` with absolute paths, you can access files directly without navigating through directories.

# more catting practice

## About the Challenge
In this challenge, the focus is on using `cat` to access files located in deep directory structures using **absolute paths** without changing the current working directory.

## Process
1. **Understanding the Limitation**:
    - In this challenge, the `cd` command cannot be used, preventing navigation to the directory containing the flag.
    - When `cd` is not allowed, the only way to access files in other directories is by using their absolute paths.

2. **Understanding the Directory Structure**:
    - The flag is located at `/lib/racket/flag`, as specified in the challenge.

3. **Using `cat` to Read the `flag` File**:
    - Since `cd` is disabled, I used the `cat` command with the full path of the flag file to read its content.
    - Here’s the command I used:
    ```bash
    hacker@commands~more-catting-practice:~$ cat /lib/racket/flag
    ```

4. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@commands~more-catting-practice:~$ cat /lib/racket/flag
    pwn.college{8CtdCZx0vOpH-tOe1VAtLK8S6cd.dBjM5QDL2YTN0czW}
    ```

## Key Takeaway
- The `cat` command can read files from any directory as long as the correct path is provided.

# grepping for a needle in a haystack

## About the Challenge
In this challenge, we learn to use the `grep` command, a tool for searching text files for specific patterns or strings. The file provided (`/challenge/data.txt`) contains a hundred thousand lines of text, and the goal is to find and extract the flag using `grep`.

## Process
1. **Understanding the `grep` Command**:
    - `grep` is a command-line utility for searching text files for lines that match a specified pattern.
    - Basic Syntax:
    ```bash
    grep SEARCH_STRING /path/to/file
    ```
    - The above command searches for `SEARCH_STRING` in the specified file and prints the lines containing it to the console.

2. **Understanding the Search Pattern**:
    - The hint provided states that the flag always starts with `pwn.college`.
    
3. **Using `grep` to Find the Flag**:
    - I used `grep` to search for lines containing `pwn.college` in the large text file (`/challenge/data.txt`).
    - Here’s the command I used:
    ```bash
    hacker@commands~grepping-for-a-needle-in-a-haystack:~$ grep pwn.college /challenge/data.txt
    ```

4. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@commands~grepping-for-a-needle-in-a-haystack:~$ grep pwn.college /challenge/data.txt
    pwn.college{06K1SJyk-Py2887DLt_WJsJ_JpB.ddTM4QDL2YTN0czW}
    ```

## Key Takeaway
- The basic syntax of `grep` involves specifying the search string and the file path.
