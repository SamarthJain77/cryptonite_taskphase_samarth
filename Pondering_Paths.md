# The Root

## About the Challenge
In this challenge, we are introduced to the concept of the filesystem structure in Linux, which starts at the root directory, `/`. The objective is to run a program named `pwn` located directly under the root directory (`/`) and capture the flag it provides.

## Process
1. **Navigating the Root Directory**:
    - The filesystem starts at the root directory `/`, which contains various directories and files.
    - For this challenge, we need to execute a program located directly at `/`.

2. **Executing the `pwn` Program**:
    - To solve this challenge, we must use the absolute path `/pwn` to run the program.
    - Here’s the command I used:
    ```bash
    hacker@paths~the-root:~$ /pwn
    ```

3. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@paths~the-root:~$ /pwn
    BOOM!!!
    Here is your flag:
    pwn.college{AmzkcYReifDVVEO4N5oobBGHCnM.dhzN5QDL2YTN0czW}
    ```

## Key Takeaways
- The **root directory (`/`)** is the starting point of the entire filesystem.
- **Absolute paths** always start with `/` and specify the complete location of a file or program.
