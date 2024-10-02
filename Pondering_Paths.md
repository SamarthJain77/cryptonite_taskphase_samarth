# The Root

## About the Challenge
In this challenge, we are introduced to the concept of the filesystem structure in Linux, which starts at the root directory, `/`. The objective is to run a program named `pwn` located directly under the root directory (`/`).

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

# Program and absolute paths

## About the Challenge
In this challenge, we delve deeper into navigating the filesystem using absolute paths. The goal is to run a program named `run` located within the `/challenge` directory.

## Process
1. **Understanding the File Path**:
    - The program is located at `/challenge/run`.
    - This means the `run` program is inside the `/challenge` directory, which is located in the root directory (`/`).

2. **Executing the `run` Program**:
    - To solve this challenge, we need to use the absolute path `/challenge/run` to run the program.
    - Here’s the command I used:
    ```bash
    hacker@paths~program-and-absolute-paths:~$ /challenge/run
    ```

3. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@paths~program-and-absolute-paths:~$ /challenge/run
    Correct!!!
    /challenge/run is an absolute path! Here is your flag:
    pwn.college{UTmMp6V3sTsqu4nvB6VpPzttSwJ.dVDN1QDL2YTN0czW}
    ```

## Key Takeaway
- **Absolute paths** specify the exact location of a program or file, starting from the root directory (`/`).

