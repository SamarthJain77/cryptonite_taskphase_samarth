# The Root

## Process
1. **Understanding the Root Directory**:
    - The filesystem starts at the root directory `/`, which contains various directories and files.
    - For this challenge, we need to execute a program located directly at `/`.

2. **Executing the `pwn` Program**:
    - To solve this challenge, we must use the absolute path `/pwn` to run the program.
    - Here’s the command I used:
    ```bash
    hacker@paths~the-root:~$ /pwn
    ```

3. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@paths~the-root:~$ /pwn
    BOOM!!!
    Here is your flag:
    pwn.college{AmzkcYReifDVVEO4N5oobBGHCnM.dhzN5QDL2YTN0czW}
    ```

# Program and absolute paths

## Process
1. **Understanding the File Path**:
    - The program is located at `/challenge/run`.
    - This means the `run` program is inside the `/challenge` directory, which is located in the root directory (`/`).

2. **Executing the `run` Program**:
    - To solve this challenge, we need to use the absolute path `/challenge/run` to run the program.
    - Here’s the command I used:
    ```bash
    hacker@paths~program-and-absolute-paths:~$ /challenge/run
    ```

3. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@paths~program-and-absolute-paths:~$ /challenge/run
    Correct!!!
    /challenge/run is an absolute path! Here is your flag:
    pwn.college{UTmMp6V3sTsqu4nvB6VpPzttSwJ.dVDN1QDL2YTN0czW}
    ```

# Position thy self

## Process
1. **Understanding the `cd` Command**:
    - `cd` stands for "change directory" and is used to navigate between directories.
    - Syntax: `cd <path_to_directory>`
    - For example:
    ```bash
    hacker@paths~position-thy-self:~$ cd /some/new/directory
    hacker@paths~position-thy-self:/some/new/directory$
    ```

2. **Navigating to the Specified Directory**:
    - When we start the challenge and run the `run` program, it provides a specific path where we need to be located to re-run the program successfully.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@paths~position-thy-self:~$ /challenge/run
    Incorrect...
    You are not currently in the /home directory.
    Please use the `cd` utility to change directory appropriately.
    ```

3. **Changing the Directory Using `cd`**:
    - Next, I used the `cd` command to navigate to the `/home` directory.
    - Here’s the command I used:
    ```bash
    hacker@paths~position-thy-self:~$ cd /home
    ```

4. **Re-executing the `run` Program**:
    - After navigating to the `/home` directory, I re-executed the program using its absolute path.
    - Here’s the command I used:
    ```bash
    hacker@paths~position-thy-self:/home$ /challenge/run
    ```

5. **Capturing the Flag**:
    - After running the command from the correct directory, the terminal displays the flag.
    - Output:
    ```bash
    hacker@paths~position-thy-self:/home$ /challenge/run
    Correct!!!
    /challenge/run is an absolute path, invoked from the right directory!
    Here is your flag:
    pwn.college{AtFRGrHc_Q429It7b7QdF5NBl3t.dZDN1QDL2YTN0czW}
    ```

# Position elsewhere

## Process
1. **Understanding the `cd` Command**:
    - `cd` stands for "change directory" and is used to change the shell’s current working directory.
    - Syntax: `cd <path_to_directory>`
    - For example:
    ```bash
    hacker@paths~position-elsewhere:~$ cd /some/new/directory
    hacker@paths~position-elsewhere:/some/new/directory$ cd /some/new/directory
    ```

2. **Navigating to the Specified Directory**:
    - When we start the challenge and run the `run` program, it provides a specific path where we need to be located to re-run the program successfully.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@paths~position-elsewhere:~$ /challenge/run
    Incorrect...
    You are not currently in the /usr/include directory.
    Please use the `cd` utility to change directory appropriately.
    ```

3. **Changing the Directory Using `cd`**:
    - Next, I used the `cd` command to navigate to the `/usr/include` directory.
    - Here’s the command I used:
    ```bash
    hacker@paths~position-elsewhere:~$ cd /usr/include
    ```

4. **Re-executing the `run` Program**:
    - After navigating to the `/usr/include` directory, I re-executed the program using its absolute path.
    - Here’s the command I used:
    ```bash
    hacker@paths~position-elsewhere:/usr/include$ /challenge/run
    ```

5. **Capturing the Flag**:
    - After running the command from the correct directory, the terminal displays the flag.
    - Output:
    ```bash
    hacker@paths~position-elsewhere:/usr/include$ /challenge/run
    Correct!!!
    /challenge/run is an absolute path, invoked from the right directory!
    Here is your flag:
    pwn.college{orG6sJjz0CcyTyaAW0Aqc6HzCdt.ddDN1QDL2YTN0czW}
    ```

# Position yet elsewhere

## Process
1. **Understanding the `cd` Command**:
    - `cd` stands for "change directory" and is used to change the shell’s current working directory.
    - Syntax: `cd <path_to_directory>`
    - For example:
    ```bash
    hacker@paths~position-yet-elsewhere:~$ cd /some/new/directory
    hacker@paths~position-yet-elsewhere:/some/new/directory$ cd /some/new/directory
    ```

2. **Navigating to the Specified Directory**:
    - When we start the challenge and run the `run` program, it provides a specific path where we need to be located to re-run the program successfully.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@paths~position-yet-elsewhere:~$ /challenge/run
    Incorrect...
    You are not currently in the /sys/kernel directory.
    Please use the `cd` utility to change directory appropriately.
    ```

3. **Changing the Directory Using `cd`**:
    - Next, I used the `cd` command to navigate to the `/system/kernel` directory.
    - Here’s the command I used:
    ```bash
    hacker@paths~position-yet-elsewhere:~$ cd /sys/kernel
    ```

4. **Re-executing the `run` Program**:
    - After navigating to the `/sys/kernel` directory, I re-executed the program using its absolute path.
    - Here’s the command I used:
    ```bash
    hacker@paths~position-yet-elsewhere:/sys/kernel$ /challenge/run
    ```

5. **Capturing the Flag**:
    - After running the command from the correct directory, the terminal displays the flag.
    - Output:
    ```bash
   hacker@paths~position-yet-elsewhere:/sys/kernel$ /challenge/run
   Correct!!!
   /challenge/run is an absolute path, invoked from the right directory!
   Here is your flag:
   pwn.college{4-NG-m9nljg3qpflKQF7jr1jP5H.dhDN1QDL2YTN0czW}
    ```

# implicit relative paths, from /

## Process
1. **Understanding Relative Paths**:
    - A relative path does not start with a `/` and is based on the current working directory.
    - Example:
    - If the cwd is `/`, a relative path to `/tmp/a/b/my_file` would be `tmp/a/b/my_file`.
    - If the cwd is `/tmp`, the relative path becomes `a/b/my_file`.
    - If the cwd is `/tmp/a/b/c`, the relative path would be `../my_file`, where `..` refers to the parent directory.
    - cwd refers to current working directory or the directory where your terminal prompt is currently located.

2. **Setting the Current Work Directory**:
    - We start with the current working directory set to `/`.
    - Here’s the command I used:
    ```bash
    hacker@paths~implicit-relative-paths-from-:~$ cd /
    ```

3. **Identifying the Relative Path to the `run` Program**:
    - The challenge hints that the relative path to use begins with the letter `c`.
    - From the current location (`/`), we need to navigate to the `/challenge/run` program.
    - The relative path to the `run` program is `challenge/run`.

4. **Running the Program Using the Relative Path**:
    - I executed the `run` program using the identified relative path.
    - Here’s the command I used:
    ```bash
    hacker@paths~implicit-relative-paths-from-:/$ challenge/run
    ```

5. **Capturing the Flag**:
    - After running the command using the correct relative path, the terminal displays the flag.
    - Output:
    ```bash
    hacker@paths~implicit-relative-paths-from-:/$ challenge/run
    Correct!!!
    challenge/run is a relative path, invoked from the right directory!
    Here is your flag:
    pwn.college{c82vLpewZdGlcNPhcdQov-JSF1X.dlDN1QDL2YTN0czW}
    ```

# explicit relative paths, from /

## Process
1. **Understanding `.` in Explicit Relative Paths**:
  - `.` allows us to refer to the current directory explicitly.
  - Examples:
  - `./challenge`
  - `./././challenge/././` 
  - Both paths above are equivalent and refer to the same directory as `challenge` from the current directory.

2. **Setting the Current Work Directory**:
    - We start with the current working directory set to `/`.
    - Here’s the command I used:
    ```bash
    hacker@paths~explicit-relative-paths-from-:~$ cd /
    ```

3. **Identifying the Relative Path to the `run` Program**:
    - The challenge requires us to use explicit relative paths incorporating `.`.
    - Since the `run` program is located in the `/challenge` directory, the relative path to the program is `./challenge/run`.

4. **Running the Program Using the Relative Path**:
    - I executed the `run` program using the identified relative path.
    - Here’s the command I used:
    ```bash
    hacker@paths~explicit-relative-paths-from-:/$ ./challenge/run
    ```

5. **Capturing the Flag**:
    - After running the command using the correct relative path, the terminal displays the flag.
    - Output:
    ```bash
    hacker@paths~explicit-relative-paths-from-:/$ ./challenge/run
    Correct!!!
    ./challenge/run is a relative path, invoked from the right directory!
    Here is your flag:
    pwn.college{MIuwfYvk9Pja092Ko4OeOnyDiNh.dBTN1QDL2YTN0czW}
    ```

# implicit relative path

## Process
1. **Understanding `./` to Explicitly Refer Programs in the Current Directory**:
  - To execute a program in the current directory, use `./<program_name>`.
  - The `./` indicates that the program is in the **current directory** and should be executed from there.

2. **Setting the Current Work Directory**:
    - We start with the current working directory set to `/challenge`.
    - Here’s the command I used:
    ```bash
    hacker@paths~implicit-relative-path:~$ cd /
    hacker@paths~implicit-relative-path:/$ cd /challenge
    ```

3. **Identifying the Relative Path to the `run` Program**:
    - The challenge requires us to invoke the `run` program using an explicit relative path indicating that it is being executed from the current directory.
    - Since the `run` program is located in the `/challenge` directory, the relative path to the program is `./run`.

4. **Running the Program Using the Relative Path**:
    - I executed the `run` program using the identified relative path.
    - Here’s the command I used:
    ```bash
    hacker@paths~implicit-relative-path:/challenge$ ./run
    ```

5. **Capturing the Flag**:
    - After running the command using the correct relative path, the terminal displays the flag.
    - Output:
    ```bash
    hacker@paths~implicit-relative-path:/challenge$ ./run
    Correct!!!
    ./run is a relative path, invoked from the right directory!
    Here is your flag:
    pwn.college{wvPv9XAi699QyWQpmQZ7mJnrpM8.dFTN1QDL2YTN0czW}
    ```

# home sweet home

## Process
1. **Understanding `~` Expansion**:
  - When `~` is used at the beginning of a path, it expands to the absolute path of our home directory (`/home/hacker`).
  - Only the leading `~` is expanded; for instance, `~/file` becomes `/home/hacker/file`, but `~/~/file` would become `/home/hacker/~/file`.

2. **Understanding the Constraints**:
    - Given the constraints, I decided to use the `~` symbol to specify the absolute path within the home directory. Since the `~` itself expands to `/home/hacker`, path like `~/s` will satisfy the requirements.
    
3. **Executing the Program Using the Identified Path**:
    - I ran the `run` program with a three-character argument that expands into an absolute path inside `/home/hacker`.
    - Here’s the command I used:
    ```bash
    hacker@paths~home-sweet-home:~$ /challenge/run ~/s
    ```

4. **Capturing the Flag**:
    - After running the command with the correctly identified argument, the terminal displays the flag.
    - Output:
    ```bash
    hacker@paths~home-sweet-home:~$ /challenge/run ~/s
    Writing the file to /home/hacker/s!
    ... and reading it back to you:
    pwn.college{YcYTUT34x_hLUhctmoMC8YkWvgz.dNzM4QDL2YTN0czW}
    ```
