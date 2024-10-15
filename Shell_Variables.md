# Printing Variables

1. **Understanding the `echo` Command with Variable Substitution**:
    - `echo` is a simple command that prints its arguments to standard output and using this, we can access the value of a variable by prefixing the variable name with a `$` symbol.
    - Basic Syntax:
    ```bash
    echo $Variable_Name
    ```

2. **Executing the Required Command**:
    - We need to use the `echo` command followed by `$FLAG` argument to print the contents of the `FLAG` variable.
    - Here’s the command I used:
    ```bash
    hacker@variables~printing-variables:~$ echo $FLAG
    ```

3. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@variables~printing-variables:~$ echo $FLAG
    pwn.college{4DAZQA-pAjzZQSUjQMgs5E__tqK.ddTN1QDL2YTN0czW}
    ```

# Setting Variables

1. **Understanding Variable Assignment**:
    - Variables in the shell can be assigned values using the `=` operator but we need to note that no spaces should surround the `=` sign.
    - Basic Syntax:
    ```bash
    hacker@variables~setting-variables:~$ VARIABLE_NAME=VALUE
    ```

2. **Assigning the Required Value to the `PWN` variable**:
    - We need to assign the value `COLLEGE` to the variable `PWN`.
    - Here’s the command I used:
    ```bash
    hacker@variables~setting-variables:~$ PWN=COLLEGE
    ```

3. **Executing the Required Command**:
    - We need to use the `echo` command followed by `$PWN` argument to print the contents of the `PWN` variable.
    - Here’s the command I used:
    ```bash
    hacker@variables~setting-variables:~$ echo $PWN
    ```

4. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@variables~setting-variables:~$ echo $PWN
    COLLEGE
    You've set the PWN variable properly! As promised, here is the flag:
    pwn.college{YNpfaFtRqcweIf0BzNKkypaVYNB.dlTN1QDL2YTN0czW}
    ```
