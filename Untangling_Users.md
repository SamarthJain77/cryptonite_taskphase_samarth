# Becoming root with su

1. **Understanding the `/etc/passwd` Command**:
    - The list of users in a Linux system is stored in the `/etc/passwd` file. Each line in the file contains user information in the format `username:x:UID:GID:Info:Directory:Shell`.
    - `username` is the user's name.
    - `x` is the placeholder where the password used to be stored.
    - `UID` is the `User ID` number.
    - `GID` is the `Group ID` number.
    - `User Info` is the user details.
    - `Home Directory` is the path to the user's home directory.
    - `Default Shell` is the shell used by the user.
    - Example:
    ```bash
    root:x:0:0:root:/root:/bin/bash
    daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
    bin:x:2:2:bin:/bin:/usr/sbin/nologin
    sys:x:3:3:sys:/dev:/usr/sbin/nologin
    sync:x:4:65534:sync:/bin:/bin/sync
    games:x:5:60:games:/usr/games:/usr/sbin/nologin
    man:x:6:12:man:/var/cache/man:/usr/sbin/nologin
    lp:x:7:7:lp:/var/spool/lpd:/usr/sbin/nologin
    mail:x:8:8:mail:/var/mail:/usr/sbin/nologin
    news:x:9:9:news:/var/spool/news:/usr/sbin/nologin
    uucp:x:10:10:uucp:/var/spool/uucp:/usr/sbin/nologin
    proxy:x:13:13:proxy:/bin:/usr/sbin/nologin
    www-data:x:33:33:www-data:/var/www:/usr/sbin/nologin
    backup:x:34:34:backup:/var/backups:/usr/sbin/nologin
    list:x:38:38:Mailing List Manager:/var/list:/usr/sbin/nologin
    irc:x:39:39:ircd:/var/run/ircd:/usr/sbin/nologin
    gnats:x:41:41:Gnats Bug-Reporting System (admin):/var/lib/gnats:/usr/sbin/nologin
    nobody:x:65534:65534:nobody:/nonexistent:/usr/sbin/nologin
    _apt:x:100:65534::/nonexistent:/usr/sbin/nologin
    systemd-timesync:x:101:101:systemd Time Synchronization,,,:/run/systemd:/usr/sbin/nologin
    systemd-network:x:102:103:systemd Network Management,,,:/run/systemd:/usr/sbin/nologin
    systemd-resolve:x:103:104:systemd Resolver,,,:/run/systemd:/usr/sbin/nologin
    mysql:x:104:105:MySQL Server,,,:/nonexistent:/bin/false
    messagebus:x:105:106::/nonexistent:/usr/sbin/nologin
    sshd:x:106:65534::/run/sshd:/usr/sbin/nologin
    hacker:x:1000:1000::/home/hacker:/bin/bash
    ```

2. **Understanding the `su` Command**:
    - The `su` command is a setuid binary, meaning it runs with the privileges of the file owner.
    - By using the `su` command, we can switch to another user account. When switching to the root user, the `su` command prompts for the root password. If the correct password is entered, we are granted a root shell.
    - Example:
    ```bash
    hacker@users~becoming-root-with-su:~$ su
    Password: 
    su: Authentication failure
    hacker@users~becoming-root-with-su:~$
    ```

3. **Switching to the `root` User**:
    - We need to use the `su` command to switch to the `root` user. The `root` password for this challenge is provided as `hack-the-planet`.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@users~becoming-root-with-su:~$ su
    Password:
    root@users~becoming-root-with-su:/home/hacker#
    ```

4. **Using `cat` to Read the `/flag` File**:
    - After switching to the `root` user, we need to read and display the content of the `/flag` file.
    - Here’s the command I used:
    ```bash
    root@users~becoming-root-with-su:/home/hacker# cat /flag
    ```

5. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    root@users~becoming-root-with-su:/home/hacker# cat /flag
    pwn.college{oYHkhoFmgNuVBfTCEqKFBNUNCYA.dVTN0UDL2YTN0czW}
    ```

# Other users with su

1. **Understanding the `su` Command with Argument**:
    - The `su` command allows us to switch to another user account. By specifying a username as an argument, we can switch to that specific user instead of `root`.
    - Basic Syntax:
    ```bash
    su some-user
    ```
    - This will prompt for the password of the specified user and if entered correctly, we will switch to that user's shell.

2. **Switching to the `zardus` User**:
    - We need to switch to the `zardus` user using the `su` command. The password for the `zardus` user is provided as `dont-hack-me`.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@users~other-users-with-su:~$ su zardus
    Password: 
    zardus@users~other-users-with-su:/home/hacker$
    ```

3. **Executing the `run` Program**:
   - After switching to the `zardus` user, I executed the `run` program present in the `challenge` directory.
   - Here’s the command I used:
     ```bash
     zardus@users~other-users-with-su:/home/hacker$ /challenge/run
     ```

4. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    zardus@users~other-users-with-su:/home/hacker$ /challenge/run
    Congratulations, you have become Zardus! Here is your flag:
    pwn.college{YwvbaZChzSELttesgYM7iGbrnVR.dZTN0UDL2YTN0czW}
    ```

# Cracking passwords

1. **Understanding the `/etc/shadow` File**:
    - This file stores password hashes in Linux systems, separated by colons. The second field contains the hashed password for each user, while some accounts have login disabled (denoted by `*` or `!`), or no password at all (denoted by a blank field).
    - By using the `su` command, we can switch to another user account. When switching to the root user, the `su` command prompts for the root password. If the correct password is entered, we are granted a root shell.
    - Example:
    ```bash
    root:$6$s74oZg/4.RnUvwo2$hRmCHZ9rxX56BbjnXcxa0MdOsW2moiW8qcAl/Aoc7NEuXl2DmJXPi3gLp7hmyloQvRhjXJ.wjqJ7PprVKLDtg/:19921:0:99999:7:::
    daemon:*:19873:0:99999:7:::
    bin:*:19873:0:99999:7:::
    sys:*:19873:0:99999:7:::
    sync:*:19873:0:99999:7:::
    games:*:19873:0:99999:7:::
    man:*:19873:0:99999:7:::
    lp:*:19873:0:99999:7:::
    mail:*:19873:0:99999:7:::
    news:*:19873:0:99999:7:::
    uucp:*:19873:0:99999:7:::
    proxy:*:19873:0:99999:7:::
    www-data:*:19873:0:99999:7:::
    backup:*:19873:0:99999:7:::
    list:*:19873:0:99999:7:::
    irc:*:19873:0:99999:7:::
    gnats:*:19873:0:99999:7:::
    nobody:*:19873:0:99999:7:::
    _apt:*:19873:0:99999:7:::
    systemd-timesync:*:19901:0:99999:7:::
    systemd-network:*:19901:0:99999:7:::
    systemd-resolve:*:19901:0:99999:7:::
    mysql:!:19901:0:99999:7:::
    messagebus:*:19901:0:99999:7:::
    sshd:*:19901:0:99999:7:::
    hacker::19916:0:99999:7:::
    zardus:$6$bEFkpM0w/6J0n979$47ksu/JE5QK6hSeB7mmuvJyY05wVypMhMMnEPTIddNUb5R9KXgNTYRTm75VOu1oRLGLbAql3ylkVa5ExuPov1.:19921:0:99999:7:::
    ```

2. **Understanding `John the Ripper` Tool**:
    - This famous tool is used to crack passwords by attempting to match the hash to known values.
    - Example:
    ```bash
    hacker@users~cracking-passwords:~$ john ./my-leaked-shadow-file
    Loaded 1 password hash (crypt, generic crypt(3) [?/64])
    Will run 32 OpenMP threads
    Press 'q' or Ctrl-C to abort, almost any other key for status
    password1337      (zardus)
    1g 0:00:00:22 3/3 0.04528g/s 10509p/s 10509c/s 10509C/s lykys..lank
    Use the "--show" option to display all of the cracked passwords reliably
    Session completed
    hacker@users~cracking-passwords:~$
    ```

3. **Cracking the Password of the `zardus` User**:
    - We need to load the leaked `/etc/shadow` file into `John the Ripper` to crack the `zardus` password.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@users~cracking-passwords:~$ john /challenge/shadow-leak
    Loaded 1 password hash (crypt, generic crypt(3) [?/64])
    Press 'q' or Ctrl-C to abort, almost any other key for status
    aardvark         (zardus)
    1g 0:00:00:21 100% 2/3 0.04688g/s 272.9p/s 272.9c/s 272.9C/s Johnson..buzz
    Use the "--show" option to display all of the cracked passwords reliably
    Session completed
    ```

4. **Switching to the `zardus` User**:
    - We need to switch to the `zardus` user using the `su` command. The identified password for the `zardus` user is `aardvark`.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@users~cracking-passwords:~$ su zardus
    Password: 
    zardus@users~cracking-passwords:/home/hacker$
    ```

5. **Executing the `run` Program**:
   - After switching to the `zardus` user, I executed the `run` program present in the `challenge` directory.
   - Here’s the command I used:
     ```bash
     zardus@users~cracking-passwords:/home/hacker$ /challenge/run
     ```

6. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    zardus@users~cracking-passwords:/home/hacker$ /challenge/run
    Congratulations, you have become Zardus! Here is your flag:
    pwn.college{wnZ3fwpsyW6e0GOc90NhkFnLcLS.ddTN0UDL2YTN0czW}
    ```

# Using sudo

1. **Understanding the `/etc/sudoers` File**:
    - This file contains the rules that define which users can run specific commands with `sudo`. The policies in this file ensure that only authorized users can execute commands as root or other users.

2. **Understanding the `sudo` Command**:
    - `sudo` allows us to run commands as another user (typically root) based on policies defined in the `/etc/sudoers` file, without needing the root password.
    - Basic Syntax:
    ```bash
    sudo [command]
    ```
    - Example:
    ```bash
    hacker@users~using-sudo:~$ grep hacker /etc/shadow
    grep: /etc/shadow: Permission denied
    hacker@users~using-sudo:~$ sudo grep hacker /etc/shadow
    hacker:$6$Xro.e7qB3Q2Jl2sA$j6xffIgWn9xIxWUeFzvwPf.nOH2NTWNJCU5XVkPuONjIC7jL467SR4bXjpVJx4b/bkbl7kyhNquWtkNlulFoy.:19921:0:99999:7:::
    hacker@users~using-sudo:~$
    ```

3. **Using `cat` to Read the `/flag` File**:
    - We need to use `sudo` to read the protected `/flag` file., simulating the elevated access required.
    - Here’s the command I used:
    ```bash
    hacker@users~using-sudo:~$ sudo cat /flag
    ```

4. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@users~using-sudo:~$ sudo cat /flag
    pwn.college{s45KBFWY9TCW2CGQ4OSPLtmIjrG.dhTN0UDL2YTN0czW}
    ```
