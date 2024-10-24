# Listing Processes

1. **Understanding the `ps` Command**:
    - The basic usage of `ps` is to list the processes running on our system.
    - Standard Syntax: We can use `-e` to list every process and `-f` for a "full format" output. These can be combined into a single argument `-ef`.
    - Example:
    ```bash
    hacker@processes~listing-processes:~$ ps -ef
    UID          PID    PPID  C STIME TTY          TIME CMD
    hacker         1       0  0 05:34 ?        00:00:00 /sbin/docker-init -- /bin/sleep 6h
    hacker         7       1  0 05:34 ?        00:00:00 /bin/sleep 6h
    hacker       102       1  1 05:34 ?        00:00:00 /usr/lib/code-server/lib/node /usr/lib/code-server --auth=none -
    hacker       138     102 11 05:34 ?        00:00:07 /usr/lib/code-server/lib/node /usr/lib/code-server/out/node/entr
    hacker       287     138  0 05:34 ?        00:00:00 /usr/lib/code-server/lib/node /usr/lib/code-server/lib/vscode/ou
    hacker       318     138  6 05:34 ?        00:00:03 /usr/lib/code-server/lib/node --dns-result-order=ipv4first /usr/
    hacker       554     138  3 05:35 ?        00:00:00 /usr/lib/code-server/lib/node /usr/lib/code-server/lib/vscode/ou
    hacker       571     554  0 05:35 pts/0    00:00:00 /usr/bin/bash --init-file /usr/lib/code-server/lib/vscode/out/vs
    hacker       695     571  0 05:35 pts/0    00:00:00 ps -ef
    hacker@processes~listing-processes:~$
    ```
    - We can use `a` to list processes for all users, `x` to list processes that aren't running in a terminal and `u` for a user-readable output. These can be combined into a single argument `aux`.
    - Example:
    ```bash
    hacker@processes~listing-processes:~$ ps aux
    USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
    hacker         1  0.0  0.0   1128     4 ?        Ss   05:34   0:00 /sbin/docker-init -- /bin/sleep 6h
    hacker         7  0.0  0.0   2736   580 ?        S    05:34   0:00 /bin/sleep 6h
    hacker       102  0.4  0.0 723944 64660 ?        Sl   05:34   0:00 /usr/lib/code-server/lib/node /usr/lib/code-serve
    hacker       138  3.3  0.0 968792 106272 ?       Sl   05:34   0:07 /usr/lib/code-server/lib/node /usr/lib/code-serve
    hacker       287  0.0  0.0 717648 53136 ?        Sl   05:34   0:00 /usr/lib/code-server/lib/node /usr/lib/code-serve
    hacker       318  3.3  0.0 977472 98256 ?        Sl   05:34   0:06 /usr/lib/code-server/lib/node --dns-result-order=
    hacker       554  0.4  0.0 650560 55360 ?        Rl   05:35   0:00 /usr/lib/code-server/lib/node /usr/lib/code-serve
    hacker       571  0.0  0.0   4600  4032 pts/0    Ss   05:35   0:00 /usr/bin/bash --init-file /usr/lib/code-server/li
    hacker      1172  0.0  0.0   5892  2924 pts/0    R+   05:38   0:00 ps aux
    hacker@processes~listing-processes:~$

2. **Identifying the Executable File**:
    - We need to use the `ps` command with appropriate argument to list all running processes and then we need to find the process corresponding to the `/challenge/run` program.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@processes~listing-processes:~$ ps -ef
    UID          PID    PPID  C STIME TTY          TIME CMD
    root           1       0  0 09:12 ?        00:00:00 /sbin/docker-init -- /nix/va
    root           7       1  0 09:12 ?        00:00:00 /run/dojo/bin/sleep 6h
    root          68       1  0 09:12 ?        00:00:00 /challenge/30178-run-30924
    root          72      68  0 09:12 ?        00:00:00 sleep 6h
    hacker        73       0  0 09:13 pts/0    00:00:00 /run/dojo/bin/ssh-entrypoint
    hacker        90      73  0 09:13 pts/0    00:00:00 ps -ef
    ```
    - From the output, I observed the executable program, which was named `/challenge/30178-run-30924`.

3. **Executing the Program**:
    - I ran the executable program using its path.
    - Here’s the command I used:
    ```bash
    hacker@processes~listing-processes:~$ /challenge/30178-run-30924
    ```

4. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@processes~listing-processes:~$ /challenge/30178-run-30924
    Yahaha, you found me! Here is your flag:
    pwn.college{ovQH445lTrtpGD5XJ9uzd9xoyl4.dhzM4QDL2YTN0czW}
    Now I will sleep for a while (so that you could find me with 'ps').
    ```

# Killing Processes

1. **Understanding the `kill` Command**:
    - The basic usage of `kill` is to terminate processes by sending them signals. It sends a termination signal allowing the process to perform cleanup before exiting.
    - Example:
    ```bash
    hacker@processes~killing-processes:~$ ps -e | grep sleep
    342 pts/0    00:00:00 sleep
    hacker@processes~killing-processes:~$ kill 342
    hacker@processes~killing-processes:~$ ps -e | grep sleep
    hacker@processes~killing-processes:~$
    ```

2. **Identifying the `PID` of `/challenge/dont_run`**:
    - In order to kill the process, we need to identify its `Process ID (PID)`, which can be done using the `ps` command and filtering with `grep`.
    - Here’s the command I used and the output I got:
    ```bash
   hacker@processes~killing-processes:~$ ps -ef | grep dont_run
   hacker        73      71  0 09:29 ?        00:00:00 /challenge/dont_run
   hacker        93      75  0 09:30 pts/0    00:00:00 grep --color=auto dont_run
    ```
    - From the output, I observed the `PID` of the `/challenge/dont_run` program, which was `73`.

3. **Killing the `/challenge/dont_run` Program**:
    - We need to use the `kill` command with the `PID` as `73` of the `/challenge/dont_run` process to terminate it.
    - Here’s the command I used:
    ```bash
    hacker@processes~killing-processes:~$ kill 73
    ```

4. **Executing the `run` Program**:
   - After terminating the required process, I executed the `run` program present in the `challenge` directory.
   - Here’s the command I used:
     ```bash
     hacker@processes~killing-processes:~$ /challenge/run
     ```

5. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@processes~killing-processes:~$ /challenge/run
    Great job! Here is your payment:
    pwn.college{c2u-uTfbEDuCq30Nwr4nUWkdx7c.dJDN4QDL2YTN0czW}
    ```

# Interrupting Processes

1. **Understanding Process Interruption**:
    - Pressing `Ctrl-C` in the terminal sends the interrupt signal to the running process. This causes the process to cleanly exit.

2. **Interrupting the `run` Program**:
   - We need to run the `/challenge/run` program and while the process is running, we need to press `Ctrl-C` to send an interrupt signal.
   - Here’s the command I used and the output I got:
     ```bash
     hacker@processes~interrupting-processes:~$ /challenge/run
     I could give you the flag... but I won't, until this process exits. Remember, 
     you can force me to exit with Ctrl-C. Try it now!
     ^C
     ```

3. **Capturing the Flag**:
    - After interrupting the program, the terminal displays the flag.
    - Output:
    ```bash
    hacker@processes~interrupting-processes:~$ /challenge/run
    I could give you the flag... but I won't, until this process exits. Remember, 
    you can force me to exit with Ctrl-C. Try it now!
    ^C
    Good job! You have used Ctrl-C to interrupt this process! Here is your flag:
    pwn.college{cHegN28zdQwMo0XJd6u0PynCe_y.dNDN4QDL2YTN0czW}
    ```

# Suspending Processes

1. **Understanding Process Suspension**:
    - Pressing `Ctrl-Z` while a process is running in the terminal sends a stop signal, which pauses the process and sends it to the background.

2. **Suspending the `run` Program**:
   - We need to run the `/challenge/run` program and while the process is running, we need to press `Ctrl-Z` to suspend it to the background.
   - Here’s the command I used and the output I got:
     ```bash
     hacker@processes~suspending-processes:~$ /challenge/run
     I'll only give you the flag if there's already another copy of me running in 
     this terminal... Let's check!

     UID          PID    PPID  C STIME TTY          TIME CMD
     root          82      65  0 09:54 pts/0    00:00:00 bash /challenge/run
     root          84      82  0 09:54 pts/0    00:00:00 ps -f

     I don't see a second me!

     To pass this level, you need to suspend me and launch me again! You can 
     background me with Ctrl-Z or, if you're not ready to do that for whatever 
     reason, just hit Enter and I'll exit!
     ^Z
     [1]+  Stopped                 /challenge/run
     ```

3. **Executing the Second Instance of the `run` Program**:
   - After suspending the required program, I executed the `run` program present in the `challenge` directory.
   - Here’s the command I used:
     ```bash
     hacker@processes~suspending-processes:~$ /challenge/run
     ```

4. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@processes~suspending-processes:~$ /challenge/run
    I'll only give you the flag if there's already another copy of me running in 
    this terminal... Let's check!

    UID          PID    PPID  C STIME TTY          TIME CMD
    root          82      65  0 09:54 pts/0    00:00:00 bash /challenge/run
    root          89      65  0 09:54 pts/0    00:00:00 bash /challenge/run
    root          91      89  0 09:54 pts/0    00:00:00 ps -f

    Yay, I found another version of me! Here is the flag:
    pwn.college{EOmU8XyIHuoVxhXYECXhwR8xtfd.dVDN4QDL2YTN0czW}
    ```

# Resuming Processes

1. **Understanding Process Resumption**:
    - Once a process is suspended, we can use the `fg` command to bring it back to the foreground and continue its execution.

2. **Suspending the `run` Program**:
   - We need to run the `/challenge/run` program and while the process is running, we need to press `Ctrl-Z` to suspend it to the background.
   - Here’s the command I used and the output I got:
     ```bash
     hacker@processes~resuming-processes:~$ /challenge/run
     Let's practice resuming processes! Suspend me with Ctrl-Z, then resume me with 
     the 'fg' command! Or just press Enter to quit me!
     ^Z
     [1]+  Stopped                 /challenge/run
     ```

3. **Resuming the `run` Program**:
   - We need to use the `fg` command to resume the process and bring it back to the foreground.
   - Here’s the command I used:
     ```bash
     hacker@processes~resuming-processes:~$ fg
     ```

4. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@processes~resuming-processes:~$ fg
    /challenge/run
    I'm back! Here's your flag:
    pwn.college{UFYO6YBg9wWKchYh-OdIDBVjN31.dZDN4QDL2YTN0czW}
    Don't forget to press Enter to quit me!
    ```

# Backgrounding Processes

1. **Understanding Process Backgrounding**:
    - Once a process is suspended, we can use the `bg` command to resume it in the background, allowing the process to run without occupying the terminal.

2. **Suspending the `run` Program**:
   - We need to run the `/challenge/run` program and while the process is running, we need to press `Ctrl-Z` to suspend it to the background.
   - Here’s the command I used and the output I got:
     ```bash
     hacker@processes~backgrounding-processes:~$ /challenge/run
     I'll only give you the flag if there's already another copy of me running *and 
     not suspended* in this terminal... Let's check!

     UID          PID STAT CMD
     root          82 S+   bash /challenge/run
     root          84 R+   ps -o user=UID,pid,stat,cmd

     I don't see a second me!

     To pass this level, you need to suspend me, resume the suspended process in the 
     background, and then launch a new version of me! You can background me with 
     Ctrl-Z (and resume me in the background with 'bg') or, if you're not ready to 
     do that for whatever reason, just hit Enter and I'll exit!
     ^Z
     [1]+  Stopped                 /challenge/run
     ```

3. **Backgrounding the `run` Program**:
   - We need to use the `bg` command to resume the process in the background.
   - Here’s the command I used and the output I got:
     ```bash
     hacker@processes~backgrounding-processes:~$ bg
     [1]+ /challenge/run &



     Yay, I'm now running the background! Because of that, this text will probably 
     overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times 
     to scroll this text out.
     ```

4. **Executing the Second Instance of the `run` Program**:
   - After backgrounding the required program, I executed the `run` program present in the `challenge` directory.
   - Here’s the command I used:
     ```bash
     hacker@processes~backgrounding-processes:~$ /challenge/run
     ```

5. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@processes~backgrounding-processes:~$ /challenge/run
    I'll only give you the flag if there's already another copy of me running *and 
    not suspended* in this terminal... Let's check!

    UID          PID STAT CMD
    root          82 S    bash /challenge/run
    root          92 S    sleep 6h
    root          93 S+   bash /challenge/run
    root          95 R+   ps -o user=UID,pid,stat,cmd

    Yay, I found another version of me running in the background! Here is the flag:
    pwn.college{wKloq-RLlZENSBmibDhx4FysOv2.ddDN4QDL2YTN0czW}
    ```

# Foregrounding Processes

1. **Understanding Process Foregrounding**:
    - Once a process is backgrounded or suspended, we can use the `fg` command to bring it back to the foreground.

2. **Suspending the `run` Program**:
   - We need to run the `/challenge/run` program and while the process is running, we need to press `Ctrl-Z` to suspend it to the background.
   - Here’s the command I used and the output I got:
     ```bash
     hacker@processes~foregrounding-processes:~$ /challenge/run
     To pass this level, you need to suspend me, resume the suspended process in the 
     background, and *then* foreground it without re-suspending it! You can 
     background me with Ctrl-Z (and resume me in the background with 'bg') or, if 
     you're not ready to do that for whatever reason, just hit Enter and I'll exit!
     ^Z
     [1]+  Stopped                 /challenge/run
     ```

3. **Backgrounding the `run` Program**:
   - We need to use the `bg` command to resume the process in the background.
   - Here’s the command I used and the output I got:
     ```bash
     hacker@processes~foregrounding-processes:~$ bg
     [1]+ /challenge/run &



     Yay, I'm now running the background! Because of that, this text will probably 
     overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times 
     to scroll this text out. After that, resume me into the foreground with 'fg'; 
     I'll wait.
     ```

4. **Foregrounding the `run` Program**:
   - We need to use the `fg` command to resume the process in the foreground.
   - Here’s the command I used and the output I got:
     ```bash
     hacker@processes~foregrounding-processes:~$ fg
     /challenge/run
     YES! Great job! I'm now running in the foreground. Hit Enter for your flag!
     ```

5. **Capturing the Flag**:
    - After hitting enter, the terminal displays the flag.
    - Output:
    ```bash
    hacker@processes~foregrounding-processes:~$ fg
    /challenge/run
    YES! Great job! I'm now running in the foreground. Hit Enter for your flag!

    pwn.college{w41-MSgqHQp7uA41EBGtxze4ib6.dhDN4QDL2YTN0czW}
    ```

# Starting Backgrounded Processes

1. **Understanding Process Commencement in the Background**:
    - Appending an `&` to a command starts the process in the background immediately.
    - Example:
    ```bash
    hacker@processes~starting-backgrounded-processes:~$ sleep 1337 &
    [1] 1771
    hacker@processes~starting-backgrounded-processes:~$ ps -o user,pid,stat,cmd
    USER         PID STAT CMD
    hacker      1709 Ss   bash
    hacker      1771 S    sleep 1337
    hacker      1782 R+   ps -o user,pid,stat,cmd
    hacker@processes~starting-backgrounded-processes:~$
    ```

2. **Starting the `run` Program in the Background**:
   - We need to start the `/challenge/run` program in the background by appending an `&` to the command.
   - Here’s the command I used:
     ```bash
     hacker@processes~starting-backgrounded-processes:~$ /challenge/run &
     ```

3. **Capturing the Flag**:
    - After starting the program in the background successfully, the terminal displays the flag.
    - Output:
    ```bash
    hacker@processes~starting-backgrounded-processes:~$ /challenge/run &
    [1] 82
    hacker@processes~starting-backgrounded-processes:~$ 


    Yay, you started me in the background! Because of that, this text will probably 
    overlap weirdly with the shell prompt, but you're used to that by now...

    Anyways! Here is your flag!
    pwn.college{gSQxzlfp0L2AldefAh6X48PXSgJ.dlDN4QDL2YTN0czW}
    ```

# Process Exit Codes

1. **Understanding Exit Codes**:
    - Exit codes are numerical values returned by commands that indicate the outcome of the command's execution.
    - An exit code of `0` signifies success while any non-zero code indicates an error.

2. **Understanding the `?` Variable**:
    - We can read the exit code of the last executed command by using the variable `?`.
    - Example:
    ```bash
    hacker@processes~process-exit-codes:~$ touch test-file
    hacker@processes~process-exit-codes:~$ echo $?
    0
    hacker@processes~process-exit-codes:~$ touch /test-file
    touch: cannot touch '/test-file': Permission denied
    hacker@processes~process-exit-codes:~$ echo $?
    1
    hacker@processes~process-exit-codes:~$
    ```

3. **Executing the `get-code` Program**:
   - I executed the `get-code` program present in the `challenge` directory.
   - Here’s the command I used and the output I got:
     ```bash
     hacker@processes~process-exit-codes:~$ /challenge/get-code
     Exiting with an error code!
     ```

4. **Identifying the exit code of the `get-code` Program**:
   - We need to use the `echo` command followed by `$?` argument to print the contents of the `?` variable.
   - Here’s the command I used and the output I got:
     ```bash
     hacker@processes~process-exit-codes:~$ echo $?
     28
     ```

5. **Executing the `submit-code` Program with the Identified Argument**:
   - I executed the `submit-code` program present in the `challenge` directory with the argument `28`.
   - Here’s the command I used:
     ```bash
     hacker@processes~process-exit-codes:~$ /challenge/submit-code 28
     ```

6. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@processes~process-exit-codes:~$ /challenge/submit-code 28
    CORRECT! Here is your flag:
    pwn.college{cax7bz6dx9MLLBF3Lo7fydi7BY9.dljN4UDL2YTN0czW}
    ```
