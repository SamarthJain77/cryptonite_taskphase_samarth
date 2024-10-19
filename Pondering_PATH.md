# The PATH Variable

1. **Understanding the `PATH` Variable**:
    - The `PATH` variable stores a list of directories that the shell searches through to find commands.
    - By modifying the `PATH` variable, we can influence which commands the shell can find and execute. If we remove all directories from `PATH`, commands will not be found unless specified with an absolute path.
    - Basic Syntax:
    ```bash
    PATH=[Directory_Name]
    ```

2. **Modifying the `PATH` Variable**:
    - We need to modify the `PATH` variable so that the `/challenge/run` program cannot find the `rm` command.
    - Here’s the command I used:
    ```bash
    hacker@path~the-path-variable:~$ PATH=""
    ```

3. **Executing the `run` Program**:
   - After modifying the `PATH` variable, I executed the `run` program present in the `challenge` directory.
   - Here’s the command I used:
     ```bash
     hacker@path~the-path-variable:~$ /challenge/run
     ```

4. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@path~the-path-variable:~$ /challenge/run
    Trying to remove /flag...
    /challenge/run: line 4: rm: No such file or directory
    The flag is still there! I might as well give it to you!
    pwn.college{EcPeLzRrJVCH858V0nY2gFV-tkd.dZzNwUDL2YTN0czW}
    ```

# Setting PATH

1. **Modifying the `PATH` Variable**:
    - We need to modify the `PATH` variable so that the `/challenge/run` program can find the `win` command.
    - Here’s the command I used:
    ```bash
    hacker@path~setting-path:~$ PATH=/challenge/more_commands/
    ```

2. **Executing the `run` Program**:
   - After modifying the `PATH` variable, I executed the `run` program present in the `challenge` directory.
   - Here’s the command I used:
     ```bash
     hacker@path~setting-path:~$ /challenge/run
     ```

3. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@path~setting-path:~$ /challenge/run
    Invoking 'win'....
    Congratulations! You properly set the flag and 'win' has launched!
    pwn.college{E0UEIEfH71I5uGXdHrugi572EvS.dVzNyUDL2YTN0czW}
    ```

# Adding Commands

1. **Writing the Shell Script**:
    - We need to create a new shell script named `win.sh` and then write the command `cat /flag` inside it.
    - Here’s the command I used:
    ```bash
    hacker@path~adding-commands:~$ echo cat /flag > win.sh
    ```

2. **Changing File Permissions of the `win.sh` File**:
    - We need to use the `chmod` command to modify the `win.sh` file’s permissions to make it executable.
    - Here’s the command I used:
    ```bash
    hacker@path~adding-commands:~$ chmod +x win.sh
    ```

3. **Modifying the `PATH` Variable**:
    - We need to modify the `PATH` variable so that the `/challenge/run` program can find the `win` command.
    - Here’s the command I used:
    ```bash
    hacker@path~adding-commands:~$ PATH=$PATH:/home/hacker
    ```

4. **Executing the `run` Program**:
   - After modifying the `PATH` variable, I executed the `run` program present in the `challenge` directory.
   - Here’s the command I used:
     ```bash
     hacker@path~adding-commands:~$ /challenge/run
     ```

5. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@path~adding-commands:~$ /challenge/run
    Invoking 'win'....
    pwn.college{cUJsKhTLLVzK7e2Oxy-kHY2TsFH.dZzNyUDL2YTN0czW}
    ```

# Hijacking Commands

1. **Writing the Shell Script**:
    - We need to create a new shell script named `rm.sh` and then write the command `cat /flag` inside it.
    - Here’s the command I used:
    ```bash
    hacker@path~hijacking-commands:~$ echo cat /flag > rm.sh
    ```

2. **Changing File Permissions of the `rm.sh` File**:
    - We need to use the `chmod` command to modify the `rm.sh` file’s permissions to make it executable.
    - Here’s the command I used:
    ```bash
    hacker@path~hijacking-commands:~$ chmod +x rm.sh
    ```

3. **Modifying the `PATH` Variable**:
    - We need to modify the `PATH` variable so that the `/challenge/run` program can find the `rm` command.
    - Here’s the command I used:
    ```bash
    hacker@path~hijacking-commands:~$ PATH=/home/hacker:$PATH
    ```

4. **Executing the `run` Program**:
   - After modifying the `PATH` variable, I executed the `run` program present in the `challenge` directory.
   - Here’s the command I used:
     ```bash
     hacker@path~hijacking-commands:~$ /challenge/run
     ```

5. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@path~hijacking-commands:~$ /challenge/run
    Trying to remove /flag...
    Found 'rm' command at /home/hacker/rm. Executing!
    pwn.college{o1bFNvLZW-nmvXR_EXmhbBm-ika.ddzNyUDL2YTN0czW}
    ```
