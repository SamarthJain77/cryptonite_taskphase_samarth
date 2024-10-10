# Matching with *

1. **Understanding File Globbing with `*`**:
    - File Globbing is a mechanism in Unix-like shells that allows for wildcard characters in commands.
    - The asterisk (`*`) as a wildcard can match any sequence of characters (except for the directory separator `/` and leading `.` characters).
    - If no files match the pattern, the shell retains the asterisk unchanged.
    - Example Usage:
    ```bash
    hacker@globbing~matching-with-:~$ touch file_a file_b file_c
    hacker@globbing~matching-with-:~$ ls
    file_a  file_b  file_c
    hacker@globbing~matching-with-:~$ echo Look: file_*
    Look: file_a file_b file_c
    hacker@globbing~matching-with-:~$ echo Look: nope_*
    Look: nope_*
    hacker@globbing~matching-with-:~$ echo ONE: /ho*/*ck*
    ONE: /home/hacker
    ```

2. **Changing Directory using Globbing**:
    - We start in our `home` directory and need to navigate to the `/challenge` directory using globbing but the condition is that the argument passed to the `cd `command must be limited to at most four characters.
    - Here’s the command I used:
    ```bash
    hacker@globbing~matching-with-:~$ cd /ch*
    ```

3. **Executing the `run` Program**:
    - After navigating to the `/challenge` diirectory, we need to use the absolute path `/challenge/run` to run the program.
    - Here’s the command I used:
    ```bash
    hacker@globbing~matching-with-:/challenge$ /challenge/run
    ```

4. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@globbing~matching-with-:/challenge$ /challenge/run
    You ran me with the working directory of /challenge! Here is your flag:
    pwn.college{0icKr3HQxlk_o6MRFUcqK4sEU8O.dFjM4QDL2YTN0czW}
    ```

# Matching with ?

1. **Understanding File Globbing with `?`**:
    - File Globbing is a mechanism in Unix-like shells that allows for wildcard characters in commands.
    - The question mark (`?`) as a wildcard matches exactly one character.
    - When no matches are found, the shell retains the question mark unchanged.
    - Example Usage:
    ```bash
    hacker@globbing~matching-with-:~$ touch file_a file_b file_cc
    hacker@globbing~matching-with-:~$ ls
    file_a  file_b  file_cc
    hacker@globbing~matching-with-:~$ echo Look: file_?
    Look: file_a file_b
    hacker@globbing~matching-with-:~$ echo Look: file_??
    Look: file_cc
    ```

2. **Changing Directory using Globbing**:
    - We start in our `home` directory and need to navigate to the `/challenge` directory using globbing but the condition is that we can only replace the characters `c` and `l` with `?` in the argument passed to the `cd `command.
    - Here’s the command I used:
    ```bash
    hacker@globbing~matching-with-:~$ cd /?ha??enge
    ```

3. **Executing the `run` Program**:
    - After navigating to the `/challenge` diirectory, we need to use the absolute path `/challenge/run` to run the program.
    - Here’s the command I used:
    ```bash
    hacker@globbing~matching-with-:/challenge$ /challenge/run
    ```

4. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@globbing~matching-with-:/challenge$ /challenge/run
    You ran me with the working directory of /challenge! Here is your flag:
    pwn.college{4rT40fRvvGGDeHIcxEKF0FOZDop.dJjM4QDL2YTN0czW}
    ```

# Matching with []

1. **Understanding File Globbing with `[]`**:
    - File Globbing is a mechanism in Unix-like shells that allows for wildcard characters in commands.
    - The square brackets (`[]`) provide a way to match any single character within the specified set of characters.
    - We can specify multiple characters within the square brackets.
    - Example Usage:
    ```bash
    hacker@globbing~matching-with-:~$ touch file_a file_b file_c
    hacker@globbing~matching-with-:~$ ls
    file_a  file_b  file_c
    hacker@globbing~matching-with-:~$ echo Look: file_[ab]
    Look: file_a file_b
    ```

2. **Navigating to the `/challenge/files` Directory**:
    - We start with the current working directory set to `/challenge/files`.
    - Here’s the command I used:
    ```bash
    hacker@globbing~matching-with-:~$ cd /challenge/files
    ```

3. **Identifying the Correct Argument**:
    - As it is mentioned that we need to execute the command with a globbing pattern that matches `file_b`, `file_a`, `file_s`, and `file_h`, so the argument must be `file_[bash]`.

4. **Executing the `run` Program with the Correct Argument**:
    - After navigating to the `/challenge` diirectory, we need to use the absolute path `/challenge/run` to run the program with the argument `file_[bash]`.
    - Here’s the command I used:
    ```bash
    hacker@globbing~matching-with-:/challenge/files$ /challenge/run file_[bash]
    ```

5. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@globbing~matching-with-:/challenge/files$ /challenge/run file_[bash]
    You got it! Here is your flag!
    pwn.college{EGDB9GAucP9Scwdt6vCqhz-Hb0H.dNjM4QDL2YTN0czW}
    ```

# Matching paths with []
# Mixing globs
# Exclusionary globbing
