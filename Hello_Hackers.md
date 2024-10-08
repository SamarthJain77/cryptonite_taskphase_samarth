# Intro to Commands

1. **Understanding the Prompt**:
    - When we see the prompt `hacker@hello~intro-to-commands:~$`, it indicates that the shell is ready to accept commands.
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

# Intro to Arguments

1. **Understanding the Prompt**:
    - When we see the prompt `hacker@hello~intro-to-arguments:~$`, it indicates that the shell is ready to accept commands.
    - For example:
    ```bash
    hacker@hello~intro-to-arguments:~$ echo Hello Hackers!
    Hello Hackers!
    hacker@hello~intro-to-arguments:~$
    ```
    In this case, the command was `echo`, and `Hello` and `Hackers!` were the two arguments to `echo`. `echo` is a simple command that "echoes" all of its arguments back out       onto the terminal.

2. **Executing the `hello` Command with an Argument**:
    - To solve this challenge, we need to run the `hello` command with `hackers` as its argument.
    - Here’s the command I used:
    ```bash
    hacker@hello~intro-to-arguments:~$ hello hackers
    ```

3. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@hello~intro-to-arguments:~$ hello hackers
    Success! Here is your flag:
    pwn.college{o2RrqidMD31RHRlnTopbufTt0la.dhjNyUDL2YTN0czW}
    ```
