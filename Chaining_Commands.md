# Chaining with Semicolons

1. **Understanding Command Chaining with Semicolons (`;`)**:
    - Semicolons allow us to execute multiple commands in sequence on the same line, separated by `;`.
    - Basic Syntax:
    ```bash
    command1; command2; command3
    ```
    - Each command will be executed in order, and the next command will only run once the previous one finishes.

2. **Chaining the Two Commands**:
    - We need to combine the two commands on a single line using a semicolon (`;`) between them.
    - Here’s the command I used:
    ```bash
    hacker@chaining~chaining-with-semicolons:~$ /challenge/pwn; /challenge/college
    ```

3. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@chaining~chaining-with-semicolons:~$ /challenge/pwn; /challenge/college
    Yes! You chained /challenge/pwn and /challenge/college! Here is your flag:
    pwn.college{Q3O2V548RRpLf2nsZ2X52EWefff.dVTN4QDL2YTN0czW}
    ```

# Your First Shell Script

1. **Understanding the Shell Script**:
    - A shell script is simply a file that contains a list of shell commands. Shell scripts have a `.sh` extension.
    - We can execute a shell script by passing the file to the shell, such as `bash script.sh`.

2. **Writing the Shell Script**:
    - We need to create a new shell script named `x.sh` and then write the two commands `/challenge/pwn` and `/challenge/college` inside it.
    - Here’s the command I used:
    ```bash
    hacker@chaining~your-first-shell-script:~$ echo /challenge/pwn > x.sh && echo /challenge/college >> x.sh
    ```

3. **Running the Shell Script with `bash`**:
   - After creating the `x.sh` shell script, we need to run the script by passing it to the `bash` shell.
   - Here’s the command I used:
    ```bash
    hacker@chaining~your-first-shell-script:~$ bash x.sh
    ```

4. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@chaining~your-first-shell-script:~$ bash x.sh
    Great job, you've written your first shell script! Here is the flag:
    pwn.college{gn9EbqUCyuSRNHi2LBBOZmvJue1.dFzN4QDL2YTN0czW}
    ```

# Redirecting Script Output

1. **Writing the Shell Script**:
    - We need to create a new shell script named `x.sh` and then write the two commands `/challenge/pwn` and `/challenge/college` inside it.
    - Here’s the command I used:
    ```bash
    hacker@chaining~redirecting-script-output:~$ echo /challenge/pwn > x.sh && echo /challenge/college >> x.sh
    ```

2. **Piping the Output**:
    - After creating the `x.sh` script, we need to pipe its output to the `/challenge/solve` command.
    - Here’s the command I used:
    ```bash
    hacker@chaining~redirecting-script-output:~$ bash x.sh | /challenge/solve
    ```

3. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@chaining~redirecting-script-output:~$ bash x.sh | /challenge/solve
    Correct! Here is your flag:
    pwn.college{UKNNz4bjvj4YGi5BJe94U4VudK_.dhTM5QDL2YTN0czW}
    ```
    
# Executable Shell Scripts

1. **Writing the Shell Script**:
    - We need to create a new shell script named `y.sh` and then write the command `/challenge/solve` inside it.
    - Here’s the command I used:
    ```bash
    hacker@chaining~executable-shell-scripts:~$ echo /challenge/solve > y.sh
    ```

2. **Changing File Permissions of the `y.sh` File**:
    - We need to use the `chmod` command to modify the `y.sh` file’s permissions to make it readable.
    - Here’s the command I used:
    ```bash
    hacker@chaining~executable-shell-scripts:~$ chmod u+x y.sh
    ```

3. **Running the Shell Script Using the Relative Path**:
   - After creating the `y.sh` shell script, we need to run the script using its relative path.
   - Here’s the command I used:
    ```bash
    hacker@chaining~executable-shell-scripts:~$ ./y.sh
    ```

4. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@chaining~executable-shell-scripts:~$ ./y.sh
    Congratulations on your shell script execution! Your flag:
    pwn.college{ktkknva-zIETuaw7B3DPHKrznYh.dRzNyUDL2YTN0czW}
    ```
