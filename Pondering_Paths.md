# The Root

## About the Challenge
In this challenge, we are introduced to the concept of the filesystem structure in Linux, which starts at the root directory, `/`. The objective is to run a program named `pwn` located directly under the root directory (`/`).

## Process
1. **Navigating the Root Directory**:
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

## Key Takeaways
- The **root directory (`/`)** is the starting point of the entire filesystem.
- **Absolute paths** always start with `/` and specify the complete location of a file or program.

# Program and absolute paths

## About the Challenge
In this challenge, we delve deeper into navigating the filesystem using absolute paths. The goal is to run a program named `run` located within the `/challenge` directory.

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

## Key Takeaway
- **Absolute paths** specify the exact location of a program or file, starting from the root directory (`/`).

# Position thy self

## About the Challenge
In this challenge, we learn how to navigate the Linux filesystem using the `cd` (change directory) command. The objective is to execute the `run` program located in the `/challenge` directory, but from a specific path that the program specifies.

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

## Key Takeaways
- The `cd` command is used to change the current working directory.
- Use `cd <absolute_path>` for navigating directly to a specific location.

# Position elsewhere

## About the Challenge
In this challenge, we continue practicing how to navigate the Linux filesystem using the `cd` (change directory) command. The objective is to execute the `run` program located in the `/challenge` directory, but from a different path that the program specifies.

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

## Key Takeaways
- The `cd` command is used to change the current working directory.
- Use `cd <absolute_path>` for navigating directly to a specific location.

# Position yet elsewhere

## About the Challenge
In this challenge, we continue exploring how to navigate the Linux filesystem using the `cd` (change directory) command. The objective is to execute the `run` program located in the `/challenge` directory, but from a different path that the program specifies.

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

## Key Takeaways
- The `cd` command is used to change the current working directory.
- Use `cd <absolute_path>` for navigating directly to a specific location.

