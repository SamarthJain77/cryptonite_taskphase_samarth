# Learning From Documentation

1. **Navigating to the Root Directory**:
    - We start with the current working directory set to `/`.
    - Here’s the command I used:
    ```bash
    hacker@man~learning-from-documentation:~$ cd /
    ```

2. **Executing the `challenge` Program with the Correct Argument**:
    - I executed the `challenge` program present in the `challenge` directory with the argument `--giveflag`.
    - Here’s the command I used:
    ```bash
    hacker@man~learning-from-documentation:/$ /challenge/challenge --giveflag
    ```

3. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@man~learning-from-documentation:/$ /challenge/challenge --giveflag
    Correct argument! Here is your flag:
    pwn.college{wXHIAUDZwr_YnJHY_lJJog_Rrtl.dRjM5QDL2YTN0czW}
    ```

# Learning Complex Usage

1. **Navigating to the Root Directory**:
    - We start with the current working directory set to `/`.
    - Here’s the command I used:
    ```bash
    hacker@man~learning-from-documentation:~$ cd /
    ```

2. **Executing the `challenge` Program with the Correct Argument & Sub-Argument**:
    - I executed the `challenge` program present in the `challenge` directory with the argument `--printfile` & sub-argument `flag`.
    - Here’s the command I used:
    ```bash
    hacker@man~learning-complex-usage:/$ /challenge/challenge --printfile flag
    ```

3. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@man~learning-complex-usage:/$ /challenge/challenge --printfile flag
    Correct argument! Here is the flag file:
    pwn.college{Qz96WqcEVAb_HHyJRkq5nNc_mjp.dVjM5QDL2YTN0czW}
    ```

# Reading Manuals

1. **Understanding the `man` Command**:
    - The `man` command is short for manual, and it displays the documentation for a command we specify as its argument.
    - Basic Syntax:
    ```bash
    man <command_name>
    ```

2. **Navigating to the Root Directory**:
    - We start with the current working directory set to `/`.
    - Here’s the command I used:
    ```bash
    hacker@man~reading-manuals:~$ cd /
    ```

3. **Using `man` to Read the Documentation for `challenge` Command**:
    - I used `man` to access the manual page for the `challenge` command by specifying it as an argument.
    - Here’s the command I used:
    ```bash
    hacker@man~reading-manuals:/$ man challenge
    ```

4. **Identifying the Secret Option**:
    - Here’s the command I used and the output I got:
    ```bash
    hacker@man~reading-manuals:/$ man challenge
    CHALLENGE(1)                  Challenge Commands                  CHALLENGE(1)
    NAME
       /challenge/challenge - print the flag!
    SYNOPSIS
       challenge OPTION
    DESCRIPTION
       Output the flag when called with the right arguments.

       --ovvjnk NUM
              print the flag if NUM is 044

     AUTHOR
       Written by Zardus.
    ```
    - From the description of the command in the manual page, I observed that `--ovvjnk` is a secret argument with `NUM` as the secret sub-argument that prints the flag if `NUM` is `044`.

5. **Executing the `challenge` Program with the Correct Argument & Sub-Argument**:
    - I executed the `challenge` program present in the `challenge` directory with the argument `--ovvjnk` & sub-argument `044`.
    - Here’s the command I used:
    ```bash
    hacker@man~reading-manuals:/$ /challenge/challenge --ovvjnk 044
    ```

6. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@man~reading-manuals:/$ /challenge/challenge --ovvjnk 044
    Correct usage! Your flag: pwn.college{Eo-vFBvH0j4nQ4P-JkiAxohJJL2.dRTM4QDL2YTN0czW}
    ```
    
# Searching Manuals

1. **Navigating to the Root Directory**:
    - We start with the current working directory set to `/`.
    - Here’s the command I used:
    ```bash
    hacker@man~searching-manuals:~$ cd /
    ```

2. **Using `man` to Read the Documentation for `challenge` Command**:
    - I used `man` to access the manual page for the `challenge` command by specifying it as an argument.
    - Here’s the command I used:
    ```bash
    hacker@man~searching-manuals:/$ man challenge
    ```

3. **Identifying the Correct Argument**:
    - I searched within the man page using the `/flag` command to find the option that will print the flag.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@man~searching-manuals:/$ man challenge
    CHALLENGE(1)                  Challenge Commands                  CHALLENGE(1)
    NAME
       /challenge/challenge - print the flag!
    SYNOPSIS
       challenge OPTION
    DESCRIPTION
       Output the flag when called with the right arguments.

       --bgmv This argument will give you the flag!

     AUTHOR
       Written by Zardus.
    ```
    - From the description of the command in the manual page, I observed that `--bgmv` is the correct argument that prints the flag.

4. **Executing the `challenge` Program with the Correct Argument**:
    - I executed the `challenge` program present in the `challenge` directory with the argument `--bgmv`.
    - Here’s the command I used:
    ```bash
    hacker@man~searching-manuals:/$ /challenge/challenge --bgmv
    ```

5. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@man~searching-manuals:/$ /challenge/challenge --bgmv
    Initializing...
    Correct usage! Your flag: pwn.college{cspwFm3Ocb18UopvQIc_tXEGCxt.dVTM4QDL2YTN0czW}
    ```

# Searching For Manuals

1. **Navigating to the Root Directory**:
    - We start with the current working directory set to `/`.
    - Here’s the command I used:
    ```bash
    hacker@man~searching-for-manuals:~$ cd /
    ```

2. **Using `man` to Read the Documentation for `man` Command**:
    - I used `man` to access the manual page for the `man` command by specifying it as an argument.
    - Here’s the command I used:
    ```bash
    hacker@man~searching-for-manuals:/$ man man
    ```

3. **Understanding the Search Features of the `man` Command**:
    - `man [man options] [[section] page ...]`: This option displays the manual page for a command when we specify the section and page (or command name) we want to view. 
    - `man -k [apropos options] keyword`: This command searches for keywords in the short descriptions and names of all available man pages.
    - `man -K [man options] [section] term`: This option performs a full-text search through all man pages to find instances of a specified keyword.
    - `man -f [whatis options] page`: This command displays a short description for each manual page provided.
    - `man -l [man options] file`: This option is used to view a local manual page from a file.
    - `man -w [man options] page`: This command displays the path to the manual page(s).
    - `man -W [man options] page`: This option displays the path to all available manual pages.

4. **Searching the Man Page Database**:
    - I used `man -k` to search for a man page related to the challenge.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@man~searching-for-manuals:/$ man -k challenge
    rntjzfslml (1)       - print the flag!
    ```

5. **Using `man` to Read the Documentation for `rntjzfslml` Command**:
    - I used `man` to access the manual page for the `rntjzfslml` command by specifying it as an argument.
    - Here’s the command I used:
    ```bash
    hacker@man~searching-for-manuals:/$ man rntjzfslml
    ```

6. **Identifying the Correct Argument & Sub-Argument**:
    - Here’s the command I used and the output I got:
    ```bash
    hacker@man~searching-for-manuals:/$ man rntjzfslml
    CHALLENGE(1)                  Challenge Commands                  CHALLENGE(1)
    NAME
       /challenge/challenge - print the flag!
    SYNOPSIS
       challenge OPTION
    DESCRIPTION
       Output the flag when called with the right arguments.

       --rntjzf NUM
              print the flag if NUM is 704

     AUTHOR
       Written by Zardus.
    ```
    - From the description of the command in the manual page, I observed that `--rntjzf` is a secret argument with `NUM` as the secret sub-argument that prints the flag if `NUM` is `704`.

7. **Executing the `challenge` Program with the Correct Argument & Sub-Argument**:
    - I executed the `challenge` program present in the `challenge` directory with the argument `--rntjzf` & sub-argument `704`.
    - Here’s the command I used:
    ```bash
    hacker@man~searching-for-manuals:/$ /challenge/challenge --rntjzf 704
    ```

8. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@man~searching-for-manuals:/$ /challenge/challenge --rntjzf 704
    Correct usage! Your flag: pwn.college{Yr7nK-RItjOOzUXQfYHHsPl0m_l.dZTM4QDL2YTN0czW}
    ```


# Helpful Programs

1. **Navigating to the Root Directory**:
    - We start with the current working directory set to `/`.
    - Here’s the command I used:
    ```bash
    hacker@man~helpful-programs:~$ cd /
    ```
    
2. **Executing the `challenge` Program with the Required Argument**:
    - I executed the `challenge` program present in the `challenge` directory with the argument `--help`.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@man~helpful-programs:/$ /challenge/challenge --help
    usage: a challenge to make you ask for help [-h] [--fortune] [-v]
                                            [-g GIVE_THE_FLAG] [-p]

    optional arguments:
    -h, --help            show this help message and exit
    --fortune             read your fortune
    -v, --version         get the version number
    -g GIVE_THE_FLAG, --give-the-flag GIVE_THE_FLAG             get the flag, if given the correct value
    -p, --print-value     print the value that will cause the -g option to give you the flag
    ```

 3. **Executing the `challenge` Program with the Identified Argument**:
    - I executed the `challenge` program present in the `challenge` directory with the argument `-p`.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@man~helpful-programs:/$ /challenge/challenge -p
    The secret value is: 805
    ```

4. **Executing the `challenge` Program with the Correct Argument & Identified Sub-Argument**:
    - I executed the `challenge` program present in the `challenge` directory with the argument `-g` & sub-argument `805`.
    - Here’s the command I used:
    ```bash
    hacker@man~helpful-programs:/$ /challenge/challenge -g 805
    ```

5. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@man~helpful-programs:/$ /challenge/challenge -g 805
    Correct usage! Your flag: pwn.college{cKl8GPyut_At0RYLBSM5GVS1mij.ddjM4QDL2YTN0czW}
    ```
 
# Help for Builtins

1. **Navigating to the Root Directory**:
    - We start with the current working directory set to `/`.
    - Here’s the command I used:
    ```bash
    hacker@man~helpful-programs:~$ cd /
    ```

2. **Understanding the `help` Comman**:
    -  The `help` command provides information on shell builtins, including usage, syntax, and available options where shell builtins are commands that are executed directly by the shell without launching a separate process.

3. **Retrieving the List of Builtins**:
    - I ran the `help` command to see all available builtins in the shell.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@man~help-for-builtins:~$ help
    challenge [--fortune] [--version] [-->  
    ```

4. **Executing the `help` Command with the Identified Argument**:
    - I executed the `help` command with the argument `challenge`.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@man~help-for-builtins:~$ help challenge
    challenge: challenge [--fortune] [--version] [--secret SECRET]
    This builtin command will read you the flag, given the right arguments!
    
    Options:
      --fortune		display a fortune
      --version		display the version
      --secret VALUE	prints the flag, if VALUE is correct

    You must be sure to provide the right value to --secret. That value
    is "ouu0a8r3".
    ```

5. **Executing the `challenge` Program with the Correct Argument & Sub-Argument**:
    - I executed the `challenge` program with the argument `--secret` & sub-argument `ouu0a8r3`.
    - Here’s the command I used:
    ```bash
    hacker@man~help-for-builtins:~$ challenge --secret ouu0a8r3
    ```

6. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@man~help-for-builtins:~$ challenge --secret ouu0a8r3
    Correct! Here is your flag!
    pwn.college{ouu0a8r3qWMa48k-eqrU0c32jMY.dRTM5QDL2YTN0czW}
    ```
