# Redirecting output

1. **Understanding the `>` Symbol**:
    - The `>` symbol is used to redirect the `standard output (stdout)` of a command to a specified file.
    - Basic Syntax:
    ```bash
    command > filename
    ```
    - Example:
    ```bash
    hacker@piping~redirecting-output:~$ echo "hello" > file.txt
    ```
    - This command runs `echo "hello"`, which outputs hello and then redirects that output to `file.txt` instead of printing it to the terminal.

2. **Executing the Required Command**:
    - We need to write the word `PWN` to a file named `COLLEGE` by using output redirection.
    - Here’s the command I used:
    ```bash
    hacker@piping~redirecting-output:~$ echo PWN > COLLEGE
    ```

3. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@piping~redirecting-output:~$ echo PWN > COLLEGE
    Correct! You successfully redirected 'PWN' to the file 'COLLEGE'! Here is your 
    flag:
    pwn.college{cgVN5pzRAzecVUb0ToIzx201pOB.dRjN1QDL2YTN0czW}
    ```

# Redirecting more output

1. **Understanding `Standard Output` and `Standard Error`**:
    - In Unix-based systems, commands generally use two output streams: `Standard Output (stdout)` and `Standard Error (stderr)`.
    - `Standard Output (stdout)` is used for normal output.
    - `Standard Error (stderr)` is used for error messages or other informational feedback.

2. **Executing the Required Command with Output Redirection**:
    - We need to run `/challenge/run` program and redirect its `standard output` to a file named `myflag`.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@piping~redirecting-more-output:~$ /challenge/run > myflag
    [INFO] WELCOME! This challenge makes the following asks of you:
    [INFO] - the challenge will check that output is redirected to a specific file path : myflag
    [INFO] - the challenge will output a reward file if all the tests pass : /flag

    [HYPE] ONWARDS TO GREATNESS!

    [INFO] This challenge will perform a bunch of checks.
    [INFO] If you pass these checks, you will receive the /flag file.

    [TEST] You should have redirected my stdout to a file called myflag. Checking...

    [PASS] The file at the other end of my stdout looks okay!
    [PASS] Success! You have satisfied all execution requirements.
    ```

3. **Reading the Flag File**:
    - I read the `myflag` file using the `cat` command.
    - Here’s the command I used:
    ```bash
    hacker@piping~redirecting-more-output:~$ cat myflag
    ```

4. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@piping~redirecting-more-output:~$ cat myflag

    [FLAG] Here is your flag:
    [FLAG] pwn.college{09cX0L4wFZJYVh2Vt1vZ2bBdvD5.dVjN1QDL2YTN0czW}
    ```

# Appending output

1. **Understanding the `>>` Symbol**:
    - When we want to append output to an existing file, rather than overwrite it, we use the `>>` redirection operator.
    - Basic Syntax:
    ```bash
    command >> filename
    ```
    - Example:
    ```bash
    hacker@piping~appending-output:~$ echo pwn > outfile
    hacker@piping~appending-output:~$ echo college >> outfile
    hacker@piping~appending-output:~$ cat outfile
    pwn
    college
    ```
    - `>` represents `Truncation Mode` which creates or overwrites the file with new content each time it's used while `>>` represents `Append Mode` which appends the new content to the existing file contents, rather than overwriting them.

2. **Executing the Required Command in Append Mode**:
    - We need to run `/challenge/run` program with append-mode redirection to ensure that both halves of the flag are written to the file `/home/hacker/the-flag`.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@piping~appending-output:~$ /challenge/run >> /home/hacker/the-flag
    [INFO] WELCOME! This challenge makes the following asks of you:
    [INFO] - the challenge will check that output is redirected to a specific file path : /home/hacker/the-flag

    [HYPE] ONWARDS TO GREATNESS!

    [INFO] This challenge will perform a bunch of checks.
    [INFO] Good luck!

    [TEST] You should have redirected my stdout to a file called /home/hacker/the-flag. Checking...

    [HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
    [HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
    [HINT] creating and trying to pass in FDs in python.

    [PASS] The file at the other end of my stdout looks okay!
    [PASS] Success! You have satisfied all execution requirements.
    I will write the flag in two parts to the file /home/hacker/the-flag! I'll do 
    the first write directly to the file, and the second write, I'll do to stdout 
    (if it's pointing at the file). If you redirect the output in append mode, the 
    second write will append to (rather than overwrite) the first write, and you'll 
    get the whole flag!
    ```

3. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@piping~redirecting-output:~$ echo PWN > COLLEGE
    Correct! You successfully redirected 'PWN' to the file 'COLLEGE'! Here is your 
    flag:
    pwn.college{cgVN5pzRAzecVUb0ToIzx201pOB.dRjN1QDL2YTN0czW}
    ```

# Redirecting errors



# Redirecting input



# Grepping stored results



# Grepping live output



# Grepping errors



# Duplicating piped data with tee



# Writing to multiple programs



# Split-piping stderr and stdout

