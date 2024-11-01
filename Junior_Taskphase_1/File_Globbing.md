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
    - After navigating to the `/challenge/files` diirectory, we need to use the absolute path `/challenge/run` to run the program with the argument `file_[bash]`.
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

1. **Understanding Path Based File Globbing with `[]`**:
    - File Globbing is a mechanism in Unix-like shells that allows for wildcard characters in commands.
    - We can use `[]` within paths, which allows us to match files not just by filename, but also by path.
    - Example Usage:
    ```bash
    hacker@globbing~matching-paths-with-:~$ touch /home/hacker/file_a /home/hacker/file_b /home/hacker/file_c
    hacker@globbing~matching-paths-with-:~$ ls /home/hacker
    file_a file_b file_c
    hacker@globbing~matching-paths-with-:~$ echo Look: /home/hacker/file_[ab]
    Look: /home/hacker/file_a /home/hacker/file_b
    hacker@globbing~matching-paths-with-:~$ echo Look: /home/hacker/file_[a-c]
    Look: /home/hacker/file_a /home/hacker/file_b /home/hacker/file_c
    ```

2. **Using Bracket Globbing with Absolute Path**:
    - Instead of just matching filenames, we need to construct a glob that specifies the full absolute path to each file.
    - As it is mentioned that we need to execute the command with a globbing pattern that matches `file_b`, `file_a`, `file_s`, and `file_h`, so the argument must be `/challenge/files/file_[bash]`.

3. **Executing the `run` Program with the Correct Argument**:
    - This time we need to run the program from the `home` directory so we will use the absolute path `/challenge/run` to run the program with the argument `/challenge/files/file_[bash]`.
    - Here’s the command I used:
    ```bash
    hacker@globbing~matching-paths-with-:~$ /challenge/run /challenge/files/file_[bash]
    ```

4. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@globbing~matching-paths-with-:~$ /challenge/run /challenge/files/file_[bash]
    You got it! Here is your flag!
    pwn.college{wVX-L-s_M7joOxvoTNmMOp8JCqB.dRjM4QDL2YTN0czW}
    ```

# Mixing globs

1. **Navigating to the `/challenge/files` Directory**:
    - We start with the current working directory set to `/challenge/files`.
    - Here’s the command I used:
    ```bash
    hacker@globbing~mixing-globs:~$ cd /challenge/files
    ```

2. **Identifying the Correct Argument**:
    - As it is mentioned that we need to execute the command with a single, short (6 characters or less) glob that will match the files `challenging`, `educational`, and `pwning`, so the argument must be `[cep]*`.

3. **Executing the `run` Program with the Correct Argument**:
    - After navigating to the `/challenge/files` diirectory, we need to use the absolute path `/challenge/run` to run the program with the argument `[cep]*`.
    - Here’s the command I used:
    ```bash
    hacker@globbing~mixing-globs:/challenge/files$ /challenge/run [cep]*
    ```

4. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@globbing~mixing-globs:/challenge/files$ /challenge/run [cep]*
    You got it! Here is your flag!
    pwn.college{MncLo-dtft4uTJiLtIsbAm2PFnj.dVjM4QDL2YTN0czW}
    ```

# Exclusionary globbing

1. **Understanding Exclusion in Glob Patterns**:
    - File Globbing is a mechanism in Unix-like shells that allows for wildcard characters in commands.
    - When `! `or `^` is the first character inside `[]`, it negates the pattern, matching any single character not listed within the brackets.
    - Exclusion Syntax:
    ```bash
    [!characters] or [^characters]
    ```
    - Example Usage:
    ```bash
    hacker@globbing~exclusionary-globbing:~$ touch file_a
    hacker@globbing~exclusionary-globbing:~$ touch file_b
    hacker@globbing~exclusionary-globbing:~$ touch file_c
    hacker@globbing~exclusionary-globbing:~$ ls
    file_a  file_b  file_c
    hacker@globbing~exclusionary-globbing:~$ echo Look: file_[!ab]
    Look: file_c
    ```

2. **Navigating to the `/challenge/files` Directory**:
    - We start with the current working directory set to `/challenge/files`.
    - Here’s the command I used:
    ```bash
    hacker@globbing~exclusionary-globbing:~$ cd /challenge/files
    ```

3. **Identifying the Correct Argument**:
    - As it is mentioned that we need to execute the command with all files that don't start with `p`, `w`, or `n`, so the argument must be `[!pwn]*`.

4. **Executing the `run` Program with the Correct Argument**:
    - After navigating to the `/challenge/files` diirectory, we need to use the absolute path `/challenge/run` to run the program with the argument `[!pwn]*`.
    - Here’s the command I used:
    ```bash
    hacker@globbing~exclusionary-globbing:/challenge/files$ /challenge/run [!pwn]*
    ```

5. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@globbing~exclusionary-globbing:/challenge/files$ /challenge/run [!pwn]*
    You got it! Here is your flag!
    pwn.college{4kuWw3n57MkLM58Oxu9eArsFPLt.dZjM4QDL2YTN0czW}
    ```
