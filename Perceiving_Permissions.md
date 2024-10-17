# Changing File Ownership

1. **Understanding the `chown` Command**:
    - `chown` is a command used to change the ownership of a file to another user or group.
    - Basic Syntax:
    ```bash
    chown [username] [file]
    ```
    - Example:
    ```bash
    hacker@permissions~changing-file-ownership:~$ mkdir pwn_directory
    hacker@permissions~changing-file-ownership:~$ touch college_file
    hacker@permissions~changing-file-ownership:~$ ls -l
    total 4
    -rw-r--r-- 1 root root    0 May 22 13:42 college_file
    drwxr-xr-x 2 root root 4096 May 22 13:42 pwn_directory
    hacker@permissions~changing-file-ownership:~$ chown hacker college_file
    hacker@permissions~changing-file-ownership:~$ ls -l
    total 4
    -rw-r--r-- 1 hacker root    0 May 22 13:42 college_file
    drwxr-xr-x 2 root   root 4096 May 22 13:42 pwn_directory
    hacker@permissions~changing-file-ownership:~$
    ```

2. **Changing User Ownership of the `/Flag` File**:
    - We need to use the `chown` command to change the ownership of `/flag` to the `hacker` user.
    - Here’s the command I used:
    ```bash
    hacker@permissions~changing-file-ownership:~$ chown hacker /flag
    ```

3. **Using `cat` to Read the `/flag` File**:
    - After gaining the ownership, we need to read and display the content of the `/flag` file.
    - Here’s the command I used:
    ```bash
    hacker@permissions~changing-file-ownership:~$ cat /flag
    ```

4. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@permissions~changing-file-ownership:~$ cat /flag
    pwn.college{4L6wdD3NI8Cr-DqIicHI4DBfxKp.dFTM2QDL2YTN0czW}
    ```

# Groups and Files

1. **Understanding the `chgrp` Command**:
    - `chgrp` is a command used to change the group ownership of a file or directory.
    - Basic Syntax:
    ```bash
    chown [groupname] [file]
    ```
    - Example:
    ```bash
    hacker@permissions~groups-and-files:~$ mkdir pwn_directory
    hacker@permissions~groups-and-files:~$ touch college_file
    hacker@permissions~groups-and-files:~$ ls -l
    total 4
    -rw-r--r-- 1 root root    0 May 22 13:42 college_file
    drwxr-xr-x 2 root root 4096 May 22 13:42 pwn_directory
    hacker@permissions~groups-and-files:~$ chgrp hacker college_file
    hacker@permissions~groups-and-files:~$ ls -l
    total 4
    -rw-r--r-- 1 root hacker    0 May 22 13:42 college_file
    drwxr-xr-x 2 root root   4096 May 22 13:42 pwn_directory
    hacker@permissions~groups-and-files:~$
    ```

2. **Changing Group Ownership of the `/Flag` File**:
    - We need to use the `chgrp` command to change the ownership of `/flag` to the `hacker` group.
    - Here’s the command I used:
    ```bash
    hacker@permissions~groups-and-files:~$ chgrp hacker /flag
    ```

3. **Using `cat` to Read the `/flag` File**:
    - After gaining the ownership, we need to read and display the content of the `/flag` file.
    - Here’s the command I used:
    ```bash
    hacker@permissions~groups-and-files:~$ cat /flag
    ```

4. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@permissions~groups-and-files:~$ cat /flag
    pwn.college{8FSLxOpVnQeakfMNXVgVaHp_Cf_.dFzNyUDL2YTN0czW}
    ```

# Fun With Groups Names

1. **Understanding the `id` Command**:
    - `id` is a command used to display details such as the `user ID (UID)`, `group ID (GID)`, and the groups a user belongs to.
    - Example:
    ```bash
    hacker@permissions~fun-with-groups-names:~$ id
    uid=1000(hacker) gid=1000(hacker) groups=1000(hacker)
    hacker@permissions~fun-with-groups-names:~$
    ```

2. **Identifying the Randomized Group Name**:
    - We need to use the `id` command to identify the randomized group we belong to.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@permissions~fun-with-groups-names:~$ id
    uid=1000(hacker) gid=1000(grp12549) groups=1000(grp12549)
    ```
    - From the output, I observed the randomized group, which was named `grp12549`.

3. **Changing Group Ownership of the `/Flag` File**:
    - We need to use the `chgrp` command to change the ownership of `/flag` to the `grp12549` group.
    - Here’s the command I used:
    ```bash
    hacker@permissions~fun-with-groups-names:~$ chgrp grp12549 /flag
    ```

4. **Using `cat` to Read the `/flag` File**:
    - After gaining the ownership, we need to read and display the content of the `/flag` file.
    - Here’s the command I used:
    ```bash
    hacker@permissions~fun-with-groups-names:~$ cat /flag
    ```

5. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@permissions~fun-with-groups-names:~$ cat /flag
    pwn.college{sUsvH6315ibVcgbkX_wZ2oREbbC.dJzNyUDL2YTN0czW}
    ```

# Changing Permissions

1. **Understanding the `id` Command**:
    - `id` is a command used to display details such as the `user ID (UID)`, `group ID (GID)`, and the groups a user belongs to.
    - Example:
    ```bash
    hacker@permissions~fun-with-groups-names:~$ id
    uid=1000(hacker) gid=1000(hacker) groups=1000(hacker)
    hacker@permissions~fun-with-groups-names:~$
    ```

2. **Identifying the Randomized Group Name**:
    - We need to use the `id` command to identify the randomized group we belong to.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@permissions~fun-with-groups-names:~$ id
    uid=1000(hacker) gid=1000(grp12549) groups=1000(grp12549)
    ```
    - From the output, I observed the randomized group, which was named `grp12549`.

3. **Changing Group Ownership of the `/Flag` File**:
    - We need to use the `chgrp` command to change the ownership of `/flag` to the `grp12549` group.
    - Here’s the command I used:
    ```bash
    hacker@permissions~fun-with-groups-names:~$ chgrp grp12549 /flag
    ```

4. **Using `cat` to Read the `/flag` File**:
    - After gaining the ownership, we need to read and display the content of the `/flag` file.
    - Here’s the command I used:
    ```bash
    hacker@permissions~fun-with-groups-names:~$ cat /flag
    ```

5. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@permissions~fun-with-groups-names:~$ cat /flag
    pwn.college{sUsvH6315ibVcgbkX_wZ2oREbbC.dJzNyUDL2YTN0czW}
    ```
