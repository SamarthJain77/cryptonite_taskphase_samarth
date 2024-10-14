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

3. **Reading the Flag File**:
    - I read the `/home/hacker/the-flag` file using the `cat` command.
    - Here’s the command I used:
    ```bash
    hacker@piping~appending-output:~$ cat /home/hacker/the-flag
    ```

4. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@piping~appending-output:~$ cat /home/hacker/the-flag
     | 
    \|/ This is the first half:
     v 
    pwn.college{QhsfYZ9-iyIoENBQzFQWnUF76XQ.ddDM5QDL2YTN0czW}
                              ^
     that is the second half /|\
                              |

    If you only see the second half above, you redirected in *truncate* mode (>) 
    rather than *append* mode (>>), and so the write of the second half to stdout 
    overwrote the initial write of the first half directly to the file. Try append 
    mode!
    ```

# Redirecting errors

1. **Understanding File Descriptors and Output Redirection**:
    - In Linux, `File Descriptors (FDs)` are used to identify communication channels for a process. There are three main file descriptors: `FD 0 (Standard Input)`, `FD 1 (Standard Output)` and `FD 2 (Standard Error)`.
    - `FD 0 (Standard Input)` is the input channel used by the program.
    - `FD 1 (Standard Output)` is where a program sends its regular output.
    - `FD 2 (Standard Error)`  is where error messages are sent.
    - Redirecting `standard output (FD 1)`:
    ```bash
    command > output_file OR command 1> output_file
    ```
    - Redirecting `standard error (FD 2)`:
    ```bash
    command 2> error_file
    ```
    - Redirecting both `standard output` and `error` to separate files:
    ```bash
    command > output_file 2> error_file
    ```

2. **Executing the Required Command with Output and Error Redirection**:
    - We need to run `/challenge/run` program and then redirect its `standard output` to a file named `myflag` and `standard error` to a file named `instructions`
    - Here’s the command I used:
    ```bash
    hacker@piping~redirecting-errors:~$ /challenge/run > myflag 2> instructions
    ```

3. **Reading the Flag File**:
    - I read the `myflag` file using the `cat` command.
    - Here’s the command I used:
    ```bash
    hacker@piping~redirecting-errors:~$ cat myflag
    ```

4. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@piping~redirecting-errors:~$ cat myflag

    [FLAG] Here is your flag:
    [FLAG] pwn.college{U2PC_R0GD7Q7SRXfTlT5CGv3E2W.ddjN1QDL2YTN0czW}
    ```

# Redirecting input

1. **Understanding the `<` Symbol**:
    - The `<` symbol represents input redirection which allows us to provide data to a program from a file, instead of typing the input manually.
    - Basic Syntax:
    ```bash
    command < input_file
    ```
    - Example:
    ```bash
    echo yo > message
    cat message
    yo
    rev < message
    oy
    ```

2. **Creating the `PWN` File**:
    - We need to create the `PWN` file containing the word `COLLEGE`. This can be done using the `echo` command with output redirection `(>)`.
    - Here’s the command I used:
    ```bash
    hacker@piping~redirecting-input:~$ echo COLLEGE > PWN
    ```

3. **Executing the Required Command with Input Redirection**:
    - We need to redirect the contents of the `PWN` file to the `/challenge/run` command. This is done using the `<` operator, which takes the contents of `PWN` as input for the command.
    - Here’s the command I used:
    ```bash
    hacker@piping~redirecting-input:~$ /challenge/run < PWN
    ```

4. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@piping~redirecting-input:~$ /challenge/run < PWN
    Reading from standard input...
    Correct! You have redirected the PWN file into my standard input, and I read 
    the value 'COLLEGE' out of it!
    Here is your flag:
    pwn.college{8ofFgQ0LDUMatUXjKV10v6BjoBG.dBzN1QDL2YTN0czW}
    ```

# Grepping stored results

1. **Executing the Required Command with Output Redirection**:
    - We need to run `/challenge/run` program and redirect its `standard output` to a file named `/tmp/data.txt`.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@piping~grepping-stored-results:~$ /challenge/run > /tmp/data.txt
    [INFO] WELCOME! This challenge makes the following asks of you:
    [INFO] - the challenge will check that output is redirected to a specific file path : /tmp/data.txt
    [INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

    [HYPE] ONWARDS TO GREATNESS!

    [INFO] This challenge will perform a bunch of checks.
    [INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

    [TEST] You should have redirected my stdout to a file called /tmp/data.txt. Checking...

    [HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
    [HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
    [HINT] creating and trying to pass in FDs in python.

    [PASS] The file at the other end of my stdout looks okay!
    [PASS] Success! You have satisfied all execution requirements.
    ```

2. **Using `grep` to Find the Flag**:
    - I used `grep` to search for lines containing `pwn.college` in the large text file (`/tmp/data.txt`).
    - Here’s the command I used:
    ```bash
    hacker@piping~grepping-stored-results:~$ grep pwn.college /tmp/data.txt
    ```

3. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@piping~grepping-stored-results:~$ grep pwn.college /tmp/data.txt
    pwn.college{MoKnF-Fobw9rDkeJN4F33-QF_zq.dhTM4QDL2YTN0czW}
    ```

# Grepping live output

1. **Understanding the `|` Operator**:
    - The pipe (`|`) operator connects the output of one command directly to the input of another command.
    - Example:
    ```bash
    hacker@piping~grepping-live-output:~$ echo no-no | grep no
    no-no
    ```

2. **Executing the Required Command with Pipe**:
    - Instead of saving the output to a file, we need to pipe the output of `/challenge/run` program directly to `grep` command.
    - Here’s the command I used:
    ```bash
    hacker@piping~grepping-live-output:~$ /challenge/run | grep pwn.college
    ```

3. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@piping~grepping-live-output:~$ /challenge/run | grep pwn.college
    [INFO] WELCOME! This challenge makes the following asks of you:
    [INFO] - the challenge checks for a specific process at the other end of stdout : grep
    [INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

    [HYPE] ONWARDS TO GREATNESS!

    [INFO] This challenge will perform a bunch of checks.
    [INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

    [TEST] You should have redirected my stdout to another process. Checking...
    [TEST] Performing checks on that process!

    [INFO] The process' executable is /nix/store/xpq4yhadyhazkcsggmqd7rsgvxb3kjy4-gnugrep-3.11/bin/grep.
    [INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
    [INFO] To pass the checks, the executable must be grep.

    [PASS] You have passed the checks on the process on the other end of my stdout!
    [PASS] Success! You have satisfied all execution requirements.
    pwn.college{AnksEEUEhJYaTRFiqyb9je8n_8G.dlTM4QDL2YTN0czW}
    ```

# Grepping errors

1. **Understanding the `>&` Operator**:
    - This operator redirects one file descriptor to another.
    - Example:
    `2>&1` redirects `stderr (fd 2)` to `stdout (fd 1)`, combining both channels.

2. **Executing the Required Command with Pipe and `>&` Operator**:
    - We'll use `2>&1` operator to redirect the `error output (fd 2)` to `standard output (fd 1)`. This combines both error messages and standard output into one stream. Then we need to pipe the output of `/challenge/run` program directly to `grep` command.
    - Here’s the command I used:
    ```bash
    hacker@piping~grepping-errors:~$ /challenge/run 2>& 1 | grep pwn.college
    ```

3. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@piping~grepping-errors:~$ /challenge/run 2>& 1 | grep pwn.college
    [INFO] WELCOME! This challenge makes the following asks of you:
    [INFO] - the challenge checks for a specific process at the other end of stderr : grep
    [INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

    [HYPE] ONWARDS TO GREATNESS!

    [INFO] This challenge will perform a bunch of checks.
    [INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

    [TEST] You should have redirected my stderr to another process. Checking...
    [TEST] Performing checks on that process!

    [INFO] The process' executable is /nix/store/xpq4yhadyhazkcsggmqd7rsgvxb3kjy4-gnugrep-3.11/bin/grep.
    [INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
    [INFO] To pass the checks, the executable must be grep.

    [PASS] You have passed the checks on the process on the other end of my stderr!
    [PASS] Success! You have satisfied all execution requirements.
    pwn.college{IOnWYBo0AkDF1UgDmvpHMgZdbZQ.dVDM5QDL2YTN0czW}
    ```

# Duplicating piped data with tee

1. **Understanding the `tee` Command**:
    - The basic usage of `tee` is that it duplicates the standard input, sending one copy to a file and the other to standard output.
    - Example:
    ```bash
    echo "hi" | tee pwn.txt college.txt
    ```
    - This command sends the output of `echo "hi"` into the `tee` command and then `tee` sends the output both to the terminal (stdout) and to the files `pwn.txt` and `college.txt`.

2. **Piping `/challenge/pwn` to `/challenge/college` Using `tee`**:
    - We need to pipe the output of `/challenge/pwn` into `/challenge/college` and in between need to intercept and display the data using `tee`.
    - Here’s the command I used:
    ```bash
    hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn | tee pwn_output | /challenge/college
    ```

3. **Reading the Intercepted Data File**:
    - I read the `pwn_output` file using the `cat` command.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@piping~duplicating-piped-data-with-tee:~$ cat pwn_output
    Usage: /challenge/pwn --secret [SECRET_ARG]

    SECRET_ARG should be "4LC7hZNI"
    ```

4. **Executing the Required Command with Pipe and Correct Argument**:
    - I executed the `/challenge/pwn` program with the argument `--secret 4LC7hZNI` and then piped the output directly to `/challenge/college` program.
    - Here’s the command I used:
    ```bash
    hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn --secret 4LC7hZNI | /challenge/college
    ```

5. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn --secret 4LC7hZNI | /challenge/college
    Processing...
    Correct! Passing secret value to /challenge/college...
    Great job! Here is your flag:
    pwn.college{4LC7hZNIouh1u-eCQGV6FyE87WE.dFjM5QDL2YTN0czW}
    ```
    
# Writing to multiple programs



# Split-piping stderr and stdout

