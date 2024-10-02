# Intro to Commands

## About the Challenge
In this challenge, we are introduced to basic Linux commands. The goal is to invoke the `hello` command to retrieve the flag. Linux commands are case-sensitive, so `hello` is different from `HELLO`.

## Process
1. **Understanding the Prompt**:
    - When you see the prompt `hacker@hello~intro-to-commands:~$`, it indicates that the shell is ready to accept commands.
    - For example:
    ```bash
    hacker@hello~intro-to-commands:~$ whoami
    hacker
    hacker@hello~intro-to-commands:~$
    ```
    This shows the execution of the `whoami` command, which outputs the username (`hacker`).

2. **Executing the `hello` Command**:
    - To solve this challenge, we simply need to run the `hello` command.
    - Here’s the command I used:
    ```bash
    hacker@hello~intro-to-commands:~$ hello
    ```

3. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@hello~intro-to-commands:~$ hello
    Success! Here is your flag:
    pwn.college{grxHYj_sxtXT3WanuZILok8NTdM.ddjNyUDL2YTN0czW}
    ```

## Key Takeaway
- Commands in Linux are **case-sensitive**.
