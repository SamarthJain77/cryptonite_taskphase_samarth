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

2. **Changing User Ownership of the `/flag` File**:
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

2. **Changing Group Ownership of the `/flag` File**:
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

3. **Changing Group Ownership of the `/flag` File**:
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

1. **Understanding File Permissions**:
    - In Linux, file permissions dictate what actions users and groups can perform on files and directories.
    - `r` refers to the ability to read the file's contents or list the directory's contents.
    - `w` refers to the ability to modify the file or create/delete files within the directory.
    - `x` refers to the ability to execute a file as a program or enter the directory.
    - Permissions are represented in the format `rwxrwxrwx`, split into user, group, and others.
    - Example:
    ```bash
    rw-r--r-- means user has read and write access, group has read access only and others also have read access only.
    ```

2. **Understanding the `chmod` Command**:
    - `chmod` allows us to tweak permissions with the mode format of `WHO`+/-`WHAT`, where `WHO` is `user`/`group`/`other` used as `u`/`g`/`o` and `WHAT` is `read`/`write`/`execute` used as `r`/`w`/`x`.
    - Basic Syntax:
    ```bash
    chmod MODE FILE
    ```

3. **Changing File Permissions of the `/flag` File**:
    - We need to use the `chmod` command to modify the `/flag` file’s permissions to make it readable.
    - Here’s the command I used:
    ```bash
    hacker@permissions~changing-permissions:~$ chmod o+rwx /flag
    ```

4. **Using `cat` to Read the `/flag` File**:
    - After giving the required permissions, we need to read and display the content of the `/flag` file.
    - Here’s the command I used:
    ```bash
    hacker@permissions~changing-permissions:~$ cat /flag
    ```

5. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@permissions~changing-permissions:~$ cat /flag
    pwn.college{Y2Gz9531i42tfJLr0unB7ldzjxl.dNzNyUDL2YTN0czW}
    ```

# Executable Files

1. **Changing Permissions of the `/challenge/run` Program**:
    - We need to use the `chmod` command to modify the `/challenge/run` program’s permissions to make it executable.
    - Here’s the command I used:
    ```bash
    hacker@permissions~executable-files:~$ chmod u+rwx /challenge/run
    ```

2. **Executing the `run` Program**:
   - After giving the required permissions, I executed the `run` program present in the `challenge` directory.
   - Here’s the command I used:
     ```bash
     hacker@permissions~executable-files:~$ /challenge/run
     ```

3. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@permissions~executable-files:~$ /challenge/run
    Successful execution! Here is your flag:
    pwn.college{4qz71kC1VZt-d0ovqowxRdKwv5d.dJTM2QDL2YTN0czW}
    ```

# Permission Tweaking Practice

1. **Executing the `run` Program**:
   - I executed the `run` program present in the `challenge` directory.
   - Here’s the command I used and the output I got:
     ```bash
     hacker@permissions~permission-tweaking-practice:~$ /challenge/run
     Round 0 (of 8)!

     Current permissions of "/challenge/pwn": rw-r--r--
     * the user does have read permissions
     * the user does have write permissions
     - the user doesn't have execute permissions
     * the group does have read permissions
     - the group doesn't have write permissions
     - the group doesn't have execute permissions
     * the world does have read permissions
     - the world doesn't have write permissions
     - the world doesn't have execute permissions

     Needed permissions of "/challenge/pwn": r--r--r--
     * the user does have read permissions
     - the user doesn't have write permissions
     - the user doesn't have execute permissions
     * the group does have read permissions
     - the group doesn't have write permissions
     - the group doesn't have execute permissions
     * the world does have read permissions
     - the world doesn't have write permissions
     - the world doesn't have execute permissions
     ```

2. **Changing Permissions of the `/challenge/pwn` Program**:
    - We need to use the `chmod` command to modify the `/challenge/pwn` program’s permissions as specified.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@permissions~permission-tweaking-practice:~$ chmod u-wx /challenge/pwn
    You set the correct permissions!
    Round 1 (of 8)!

    Current permissions of "/challenge/pwn": r--r--r--
    * the user does have read permissions
    - the user doesn't have write permissions
    - the user doesn't have execute permissions
    * the group does have read permissions
    - the group doesn't have write permissions
    - the group doesn't have execute permissions
    * the world does have read permissions
    - the world doesn't have write permissions
    - the world doesn't have execute permissions

    Needed permissions of "/challenge/pwn": r--r-xr--
    * the user does have read permissions
    - the user doesn't have write permissions
    - the user doesn't have execute permissions
    * the group does have read permissions
    - the group doesn't have write permissions
    * the group does have execute permissions
    * the world does have read permissions
    - the world doesn't have write permissions
    - the world doesn't have execute permissions
    ```

3. **Changing Permissions of the `/challenge/pwn` Program**:
    - We need to use the `chmod` command to modify the `/challenge/pwn` program’s permissions as specified.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@permissions~permission-tweaking-practice:~$ chmod g+x /challenge/pwn
    You set the correct permissions!
    Round 2 (of 8)!

    Current permissions of "/challenge/pwn": r--r-xr--
    * the user does have read permissions
    - the user doesn't have write permissions
    - the user doesn't have execute permissions
    * the group does have read permissions
    - the group doesn't have write permissions
    * the group does have execute permissions
    * the world does have read permissions
    - the world doesn't have write permissions
    - the world doesn't have execute permissions

    Needed permissions of "/challenge/pwn": rw-rwxr--
    * the user does have read permissions
    * the user does have write permissions
    - the user doesn't have execute permissions
    * the group does have read permissions
    * the group does have write permissions
    * the group does have execute permissions
    * the world does have read permissions
    - the world doesn't have write permissions
    - the world doesn't have execute permissions
    ```

4. **Changing Permissions of the `/challenge/pwn` Program**:
    - We need to use the `chmod` command to modify the `/challenge/pwn` program’s permissions as specified.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@permissions~permission-tweaking-practice:~$ chmod ug+w /challenge/pwn
    You set the correct permissions!
    Round 3 (of 8)!

    Current permissions of "/challenge/pwn": rw-rwxr--
    * the user does have read permissions
    * the user does have write permissions
    - the user doesn't have execute permissions
    * the group does have read permissions
    * the group does have write permissions
    * the group does have execute permissions
    * the world does have read permissions
    - the world doesn't have write permissions
    - the world doesn't have execute permissions

    Needed permissions of "/challenge/pwn": rw-r--r--
    * the user does have read permissions
    * the user does have write permissions
    - the user doesn't have execute permissions
    * the group does have read permissions
    - the group doesn't have write permissions
    - the group doesn't have execute permissions
    * the world does have read permissions
    - the world doesn't have write permissions
    - the world doesn't have execute permissions
    ```

5. **Changing Permissions of the `/challenge/pwn` Program**:
    - We need to use the `chmod` command to modify the `/challenge/pwn` program’s permissions as specified.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@permissions~permission-tweaking-practice:~$ chmod g-wx /challenge/pwn
    You set the correct permissions!
    Round 4 (of 8)!

    Current permissions of "/challenge/pwn": rw-r--r--
    * the user does have read permissions
    * the user does have write permissions
    - the user doesn't have execute permissions
    * the group does have read permissions
    - the group doesn't have write permissions
    - the group doesn't have execute permissions
    * the world does have read permissions
    - the world doesn't have write permissions
    - the world doesn't have execute permissions

    Needed permissions of "/challenge/pwn": r--r--r--
    * the user does have read permissions
    - the user doesn't have write permissions
    - the user doesn't have execute permissions
    * the group does have read permissions
    - the group doesn't have write permissions
    - the group doesn't have execute permissions
    * the world does have read permissions
    - the world doesn't have write permissions
    - the world doesn't have execute permissions
    ```

6. **Changing Permissions of the `/challenge/pwn` Program**:
    - We need to use the `chmod` command to modify the `/challenge/pwn` program’s permissions as specified.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@permissions~permission-tweaking-practice:~$ chmod u-w /challenge/pwn
    You set the correct permissions!
    Round 5 (of 8)!

    Current permissions of "/challenge/pwn": r--r--r--
    * the user does have read permissions
    - the user doesn't have write permissions
    - the user doesn't have execute permissions
    * the group does have read permissions
    - the group doesn't have write permissions
    - the group doesn't have execute permissions
    * the world does have read permissions
    - the world doesn't have write permissions
    - the world doesn't have execute permissions

    Needed permissions of "/challenge/pwn": r--r--rwx
    * the user does have read permissions
    - the user doesn't have write permissions
    - the user doesn't have execute permissions
    * the group does have read permissions
    - the group doesn't have write permissions
    - the group doesn't have execute permissions
    * the world does have read permissions
    * the world does have write permissions
    * the world does have execute permissions
    ```

7. **Changing Permissions of the `/challenge/pwn` Program**:
    - We need to use the `chmod` command to modify the `/challenge/pwn` program’s permissions as specified.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@permissions~permission-tweaking-practice:~$ chmod o+wx /challenge/pwn
    You set the correct permissions!
    Round 6 (of 8)!

    Current permissions of "/challenge/pwn": r--r--rwx
    * the user does have read permissions
    - the user doesn't have write permissions
    - the user doesn't have execute permissions
    * the group does have read permissions
    - the group doesn't have write permissions
    - the group doesn't have execute permissions
    * the world does have read permissions
    * the world does have write permissions
    * the world does have execute permissions

    Needed permissions of "/challenge/pwn": r--r-----
    * the user does have read permissions
    - the user doesn't have write permissions
    - the user doesn't have execute permissions
    * the group does have read permissions
    - the group doesn't have write permissions
    - the group doesn't have execute permissions
    - the world doesn't have read permissions
    - the world doesn't have write permissions
    - the world doesn't have execute permissions
    ```

8. **Changing Permissions of the `/challenge/pwn` Program**:
    - We need to use the `chmod` command to modify the `/challenge/pwn` program’s permissions as specified.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@permissions~permission-tweaking-practice:~$ chmod o-rwx /challenge/pwn
    You set the correct permissions!
    Round 7 (of 8)!

    Current permissions of "/challenge/pwn": r--r-----
    * the user does have read permissions
    - the user doesn't have write permissions
    - the user doesn't have execute permissions
    * the group does have read permissions
    - the group doesn't have write permissions
    - the group doesn't have execute permissions
    - the world doesn't have read permissions
    - the world doesn't have write permissions
    - the world doesn't have execute permissions

    Needed permissions of "/challenge/pwn": ---r-----
    - the user doesn't have read permissions
    - the user doesn't have write permissions
    - the user doesn't have execute permissions
    * the group does have read permissions
    - the group doesn't have write permissions
    - the group doesn't have execute permissions
    - the world doesn't have read permissions
    - the world doesn't have write permissions
    - the world doesn't have execute permissions
    ```

9. **Changing Permissions of the `/challenge/pwn` Program**:
    - We need to use the `chmod` command to modify the `/challenge/pwn` program’s permissions as specified.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@permissions~permission-tweaking-practice:~$ chmod u-r /challenge/pwn
    You set the correct permissions!
    You've solved all 8 rounds! I have changed the ownership
    of the /flag file so that you can 'chmod' it. You won't be able to read
    it until you make it readable with chmod!

    Current permissions of "/flag": ---------
    - the user doesn't have read permissions
    - the user doesn't have write permissions
    - the user doesn't have execute permissions
    - the group doesn't have read permissions
    - the group doesn't have write permissions
    - the group doesn't have execute permissions
    - the world doesn't have read permissions
    - the world doesn't have write permissions
    - the world doesn't have execute permissions
    ```

10. **Changing File Permissions of the `/flag` File**:
    - We need to use the `chmod` command to modify the `/flag` file’s permissions to make it readable.
    - Here’s the command I used:
    ```bash
    hacker@permissions~permission-tweaking-practice:~$ chmod u+rwx /flag
    ```

11. **Using `cat` to Read the `/flag` File**:
    - After giving the required permissions, we need to read and display the content of the `/flag` file.
    - Here’s the command I used:
    ```bash
    hacker@permissions~permission-tweaking-practice:~$ cat /flag
    ```

12. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@permissions~permission-tweaking-practice:~$ cat /flag
    pwn.college{YBonyCA3Dj6NFRaTozUz8xKDpIX.dBTM2QDL2YTN0czW}
    ```

# Permissions Setting Practice

1. **Understanding Setting and Chaining of Permissions**:
    - Instead of modifying specific bits, we can overwrite existing permissions using the `=` operator.
    - Example:
    ```bash
    u=rw sets the user permissions to read and write, removing any execute permissions.
    o=x sets only the executable permission for others, removing read and write permissions.
    a=rwx sets read, write, and execute permissions for the user, group, and others.
    ```
    - We can chain permission settings for different categories (user, group, others) using a comma `,`.
    - Example:
    ```bash
    chmod u=rw,g=r /challenge/pwn sets user permissions to read and write, group permissions to read-only.
    chmod u=rw,g=r,o=- /challenge/pwn sets user permissions to read and write, group permissions to read-only, and no permissions for others.
    ```

2. **Executing the `run` Program**:
   - I executed the `run` program present in the `challenge` directory.
   - Here’s the command I used and the output I got:
     ```bash
     hacker@permissions~permissions-setting-practice:~$ /challenge/run
     Round 0 (of 8)!

     Current permissions of "/challenge/pwn": rw-r--r--
     * the user does have read permissions
     * the user does have write permissions
     - the user doesn't have execute permissions
     * the group does have read permissions
     - the group doesn't have write permissions
     - the group doesn't have execute permissions
     * the world does have read permissions
     - the world doesn't have write permissions
     - the world doesn't have execute permissions

     Needed permissions of "/challenge/pwn": r--rwxrw-
     * the user does have read permissions
     - the user doesn't have write permissions
     - the user doesn't have execute permissions
     * the group does have read permissions
     * the group does have write permissions
     * the group does have execute permissions
     * the world does have read permissions
     * the world does have write permissions
     - the world doesn't have execute permissions
     ```

3. **Changing Permissions of the `/challenge/pwn` Program**:
    - We need to use the `chmod` command to modify the `/challenge/pwn` program’s permissions as specified.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@permissions~permissions-setting-practice:~$ chmod u=r,g=rwx,o=rw /challenge/pwn
    You set the correct permissions!
    Round 1 (of 8)!

    Current permissions of "/challenge/pwn": r--rwxrw-
    * the user does have read permissions
    - the user doesn't have write permissions
    - the user doesn't have execute permissions
    * the group does have read permissions
    * the group does have write permissions
    * the group does have execute permissions
    * the world does have read permissions
    * the world does have write permissions
    - the world doesn't have execute permissions

    Needed permissions of "/challenge/pwn": -wxr-xrw-
    - the user doesn't have read permissions
    * the user does have write permissions
    * the user does have execute permissions
    * the group does have read permissions
    - the group doesn't have write permissions
    * the group does have execute permissions
    * the world does have read permissions
    * the world does have write permissions
    - the world doesn't have execute permissions
    ```

4. **Changing Permissions of the `/challenge/pwn` Program**:
    - We need to use the `chmod` command to modify the `/challenge/pwn` program’s permissions as specified.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@permissions~permissions-setting-practice:~$ chmod u=wx,g=rx,o=rw /challenge/pwn
    You set the correct permissions!
    Round 2 (of 8)!

    Current permissions of "/challenge/pwn": -wxr-xrw-
    - the user doesn't have read permissions
    * the user does have write permissions
    * the user does have execute permissions
    * the group does have read permissions
    - the group doesn't have write permissions
    * the group does have execute permissions
    * the world does have read permissions
    * the world does have write permissions
    - the world doesn't have execute permissions

    Needed permissions of "/challenge/pwn": -w--w-r-x
    - the user doesn't have read permissions
    * the user does have write permissions
    - the user doesn't have execute permissions
    - the group doesn't have read permissions
    * the group does have write permissions
    - the group doesn't have execute permissions
    * the world does have read permissions
    - the world doesn't have write permissions
    * the world does have execute permissions
    ```

5. **Changing Permissions of the `/challenge/pwn` Program**:
    - We need to use the `chmod` command to modify the `/challenge/pwn` program’s permissions as specified.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@permissions~permissions-setting-practice:~$ chmod u=w,g=w,o=rx /challenge/pwn
    You set the correct permissions!
    Round 3 (of 8)!

    Current permissions of "/challenge/pwn": -w--w-r-x
    - the user doesn't have read permissions
    * the user does have write permissions
    - the user doesn't have execute permissions
    - the group doesn't have read permissions
    * the group does have write permissions
    - the group doesn't have execute permissions
    * the world does have read permissions
    - the world doesn't have write permissions
    * the world does have execute permissions

    Needed permissions of "/challenge/pwn": -w--w-rwx
    - the user doesn't have read permissions
    * the user does have write permissions
    - the user doesn't have execute permissions
    - the group doesn't have read permissions
    * the group does have write permissions
    - the group doesn't have execute permissions
    * the world does have read permissions
    * the world does have write permissions
    * the world does have execute permissions
    ```

6. **Changing Permissions of the `/challenge/pwn` Program**:
    - We need to use the `chmod` command to modify the `/challenge/pwn` program’s permissions as specified.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@permissions~permissions-setting-practice:~$ chmod u=w,g=w,o=rwx /challenge/pwn
    You set the correct permissions!
    Round 4 (of 8)!

    Current permissions of "/challenge/pwn": -w--w-rwx
    - the user doesn't have read permissions
    * the user does have write permissions
    - the user doesn't have execute permissions
    - the group doesn't have read permissions
    * the group does have write permissions
    - the group doesn't have execute permissions
    * the world does have read permissions
    * the world does have write permissions
    * the world does have execute permissions

    Needed permissions of "/challenge/pwn": rw--wx--x
    * the user does have read permissions
    * the user does have write permissions
    - the user doesn't have execute permissions
    - the group doesn't have read permissions
    * the group does have write permissions
    * the group does have execute permissions
    - the world doesn't have read permissions
    - the world doesn't have write permissions
    * the world does have execute permissions
    ```

7. **Changing Permissions of the `/challenge/pwn` Program**:
    - We need to use the `chmod` command to modify the `/challenge/pwn` program’s permissions as specified.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@permissions~permissions-setting-practice:~$ chmod u=rw,g=wx,o=x /challenge/pwn
    You set the correct permissions!
    Round 5 (of 8)!
 
    Current permissions of "/challenge/pwn": rw--wx--x
    * the user does have read permissions
    * the user does have write permissions
    - the user doesn't have execute permissions
    - the group doesn't have read permissions
    * the group does have write permissions
    * the group does have execute permissions
    - the world doesn't have read permissions
    - the world doesn't have write permissions
    * the world does have execute permissions

    Needed permissions of "/challenge/pwn": --xrw---x
    - the user doesn't have read permissions
    - the user doesn't have write permissions
    * the user does have execute permissions
    * the group does have read permissions
    * the group does have write permissions
    - the group doesn't have execute permissions
    - the world doesn't have read permissions
    - the world doesn't have write permissions
    * the world does have execute permissions
    ```

8. **Changing Permissions of the `/challenge/pwn` Program**:
    - We need to use the `chmod` command to modify the `/challenge/pwn` program’s permissions as specified.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@permissions~permissions-setting-practice:~$ chmod u=x,g=rw,o=x /challenge/pwn
    You set the correct permissions!
    Round 6 (of 8)!

    Current permissions of "/challenge/pwn": --xrw---x
    - the user doesn't have read permissions
    - the user doesn't have write permissions
    * the user does have execute permissions
    * the group does have read permissions
    * the group does have write permissions
    - the group doesn't have execute permissions
    - the world doesn't have read permissions
    - the world doesn't have write permissions
    * the world does have execute permissions

    Needed permissions of "/challenge/pwn": ---r--rwx
    - the user doesn't have read permissions
    - the user doesn't have write permissions
    - the user doesn't have execute permissions
    * the group does have read permissions
    - the group doesn't have write permissions
    - the group doesn't have execute permissions
    * the world does have read permissions
    * the world does have write permissions
    * the world does have execute permissions
    ```

9. **Changing Permissions of the `/challenge/pwn` Program**:
    - We need to use the `chmod` command to modify the `/challenge/pwn` program’s permissions as specified.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@permissions~permissions-setting-practice:~$ chmod u=-,g=r,o=rwx /challenge/pwn
    You set the correct permissions!
    Round 7 (of 8)!

    Current permissions of "/challenge/pwn": ---r--rwx
    - the user doesn't have read permissions
    - the user doesn't have write permissions
    - the user doesn't have execute permissions
    * the group does have read permissions
    - the group doesn't have write permissions
    - the group doesn't have execute permissions
    * the world does have read permissions
    * the world does have write permissions
    * the world does have execute permissions

    Needed permissions of "/challenge/pwn": --x--x-wx
    - the user doesn't have read permissions
    - the user doesn't have write permissions
    * the user does have execute permissions
    - the group doesn't have read permissions
    - the group doesn't have write permissions
    * the group does have execute permissions
    - the world doesn't have read permissions
    * the world does have write permissions
    * the world does have execute permissions
    ```

10. **Changing Permissions of the `/challenge/pwn` Program**:
    - We need to use the `chmod` command to modify the `/challenge/pwn` program’s permissions as specified.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@permissions~permissions-setting-practice:~$ chmod u=x,g=x,o=wx /challenge/pwn
    You set the correct permissions!
    You've solved all 8 rounds! I have changed the ownership
    of the /flag file so that you can 'chmod' it. You won't be able to read
    it until you make it readable with chmod!

    Current permissions of "/flag": ---------
    - the user doesn't have read permissions
    - the user doesn't have write permissions
    - the user doesn't have execute permissions
    - the group doesn't have read permissions
    - the group doesn't have write permissions
    - the group doesn't have execute permissions
    - the world doesn't have read permissions
    - the world doesn't have write permissions
    - the world doesn't have execute permissions
    ```

11. **Changing File Permissions of the `/flag` File**:
    - We need to use the `chmod` command to modify the `/flag` file’s permissions to make it readable.
    - Here’s the command I used:
    ```bash
    hacker@permissions~permissions-setting-practice:~$ chmod u=r,g=r,o=r /flag
    ```

12. **Using `cat` to Read the `/flag` File**:
    - After giving the required permissions, we need to read and display the content of the `/flag` file.
    - Here’s the command I used:
    ```bash
    hacker@permissions~permissions-setting-practice:~$ cat /flag
    ```

13. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@permissions~permissions-setting-practice:~$ cat /flag
    pwn.college{AS5NQaMbk3vxk2r_mnNvMTHNSmi.dNTM5QDL2YTN0czW}
    ```

# The SUID Bit

1. **Understanding the `SUID` Bit**:
    - When a program has the `SUID` bit set, it runs with the privileges of the file's owner rather than the user who executed it.
    - Files with SUID are marked with an `s` in the user permission section.
    - Example:
    ```bash
    hacker@permissions~the-suid-bit:~$ ls -l /usr/bin/sudo
    -rwsr-xr-x 1 root root 232416 Dec 1 11:45 /usr/bin/sudo
    hacker@permissions~the-suid-bit:~$
    ```
    - The `s` part in place of the executable bit means that the program is executable with `SUID`. It means that, regardless of what user runs the program (as long as they have executable permissions), the program will execute as the owner user.
    - As the owner of a file, we can set the `SUID` bit using `chmod`.
    - - Basic Syntax:
    ```bash
    chmod u+s [program]
    ```

2. **Setting the `SUID` Bit on the Specified Program**:
    - We need to set the `SUID` bit on the `/challenge/getroot` program using `chmod u+s`.
    - Here’s the command I used:
    ```bash
    hacker@permissions~the-suid-bit:~$ chmod u+s /challenge/getroot
    ```

3. **Executing the `getroot` Program**:
   - I executed the `getroot` program present in the `challenge` directory.
   - Here’s the command I used and the output I got:
     ```bash
     hacker@permissions~the-suid-bit:~$ /challenge/getroot
     SUCCESS! You have set the suid bit on this program, and it is running as root! 
     Here is your shell...
     root@permissions~the-suid-bit:~#
     ```

4. **Using `cat` to Read the `/flag` File**:
    - After giving the required permissions, we need to read and display the content of the `/flag` file.
    - Here’s the command I used:
    ```bash
    root@permissions~the-suid-bit:~# cat /flag
    ```

5. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    root@permissions~the-suid-bit:~# cat /flag
    pwn.college{AsjT9-fjzD2ah7Ch37UkM8zag3j.dNTM2QDL2YTN0czW}
    ```
