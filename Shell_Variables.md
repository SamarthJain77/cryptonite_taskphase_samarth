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

# Multi-word Variables

1. **Understanding Variable Assignment with Spaces**:
    - Variables in the shell can be assigned values using the `=` operator but to assign a value containing spaces to a variable, we must enclose the value in quotes (`" "`) to ensure that the shell treats it as a single token.
    - Example:
    ```bash
    hacker@variables~multi-word-variables:~$ VAR="1337 SAUCE"
    hacker@variables~multi-word-variables:~$ echo $VAR
    1337 SAUCE
    ```

2. **Assigning the Required Value to the `PWN` variable**:
    - We need to assign the value `COLLEGE YEAH` to the variable `PWN`.
    - Here’s the command I used:
    ```bash
    hacker@variables~multi-word-variables:~$ PWN="COLLEGE YEAH"
    ```

3. **Executing the Required Command**:
    - We need to use the `echo` command followed by `$PWN` argument to print the contents of the `PWN` variable.
    - Here’s the command I used:
    ```bash
    hacker@variables~multi-word-variables:~$ echo $PWN
    ```

4. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@variables~multi-word-variables:~$ echo $PWN
    COLLEGE YEAH
    You've set the PWN variable properly! As promised, here is the flag:
    pwn.college{Y18lbmT92tz2HZQOaQ5pU2cYbrV.dBjN1QDL2YTN0czW}
    ```

# Exporting Variables

1. **Understanding Local and Exported Variables**:
    - Local variables are the ones that are set in a shell session but are not accessible to child processes.
    - Exported variables are the ones that can be inherited by child processes, making them available in the environment of those processes.
    - Basic Syntax for Exporting a Variable:
    ```bash
    export Variable_Name
    ```

2. **Assigning the Required Value to the `COLLEGE` variable**:
    - We need to assign the value `PWN` to the variable `COLLEGE`.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@variables~exporting-variables:~$ COLLEGE=PWN
    ```

3. **Assigning the Required Value and Exporting the `PWN` variable**:
    - We need to assign the value `COLLEGE` to the variable `PWN` and export it.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@variables~exporting-variables:~$ export PWN=COLLEGE
    You've set the PWN variable to the proper value!
    You've set the COLLEGE variable to the proper value!
    ```

4. **Executing the `run` Program**:
    - After exporting the `PWN` variable, we need to use the absolute path `/challenge/run` to run the program.
    - Here’s the command I used:
    ```bash
    hacker@variables~exporting-variables:~$ /challenge/run
    ```

5. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@variables~exporting-variables:~$ /challenge/run
    CORRECT!
    You have exported PWN=COLLEGE and set, but not exported, COLLEGE=PWN. Great 
    job! Here is your flag:
    pwn.college{QkhFGHxhO7bFiCgqiTtEAXF85Np.dJjN1QDL2YTN0czW}
    You've set the PWN variable to the proper value!
    You've set the COLLEGE variable to the proper value!
    ```

# Printing Exported Variables

1. **Understanding the `env` Command**:
    - `env` is a command which prints all the exported environment variables and their values in the current shell session.
    - Environment variables are the ones that have been exported and are available to both the current shell and any child processes spawned by the shell.

2. **Executing the Required Command**:
    - We need to run the `env` command to get the list of all the exported variables in our shell.
    - Here’s the command I used:
    ```bash
    hacker@variables~printing-exported-variables:~$ env
    ```

3. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@variables~printing-exported-variables:~$ env
    SHELL=/run/dojo/bin/bash
    HOSTNAME=variables~printing-exported-variables
    PWD=/home/hacker
    DOJO_AUTH_TOKEN=9a27a8dfd79abb7a4b4f885d250bd3cf64ae3fa56c08c96814b03db0ba985020
    HOME=/home/hacker
    LANG=C.UTF-8
    LS_COLORS=rs=0:di=01;34:ln=01;36:mh=00:pi=40;33:so=01;35:do=01;35:bd=40;33;01:cd=40;33;01:or=40;31;01:mi=00:su=37;41:sg=30;43:ca=00:tw=30;42:ow=34;42:st=37;44:ex=01;32:*.7z=01;31:*.ace=01;31:*.alz=01;31:*.apk=01;31:*.arc=01;31:*.arj=01;31:*.bz=01;31:*.bz2=01;31:*.cab=01;31:*.cpio=01;31:*.crate=01;31:*.deb=01;31:*.drpm=01;31:*.dwm=01;31:*.dz=01;31:*.ear=01;31:*.egg=01;31:*.esd=01;31:*.gz=01;31:*.jar=01;31:*.lha=01;31:*.lrz=01;31:*.lz=01;31:*.lz4=01;31:*.lzh=01;31:*.lzma=01;31:*.lzo=01;31:*.pyz=01;31:*.rar=01;31:*.rpm=01;31:*.rz=01;31:*.sar=01;31:*.swm=01;31:*.t7z=01;31:*.tar=01;31:*.taz=01;31:*.tbz=01;31:*.tbz2=01;31:*.tgz=01;31:*.tlz=01;31:*.txz=01;31:*.tz=01;31:*.tzo=01;31:*.tzst=01;31:*.udeb=01;31:*.war=01;31:*.whl=01;31:*.wim=01;31:*.xz=01;31:*.z=01;31:*.zip=01;31:*.zoo=01;31:*.zst=01;31:*.avif=01;35:*.jpg=01;35:*.jpeg=01;35:*.mjpg=01;35:*.mjpeg=01;35:*.gif=01;35:*.bmp=01;35:*.pbm=01;35:*.pgm=01;35:*.ppm=01;35:*.tga=01;35:*.xbm=01;35:*.xpm=01;35:*.tif=01;35:*.tiff=01;35:*.png=01;35:*.svg=01;35:*.svgz=01;35:*.mng=01;35:*.pcx=01;35:*.mov=01;35:*.mpg=01;35:*.mpeg=01;35:*.m2v=01;35:*.mkv=01;35:*.webm=01;35:*.webp=01;35:*.ogm=01;35:*.mp4=01;35:*.m4v=01;35:*.mp4v=01;35:*.vob=01;35:*.qt=01;35:*.nuv=01;35:*.wmv=01;35:*.asf=01;35:*.rm=01;35:*.rmvb=01;35:*.flc=01;35:*.avi=01;35:*.fli=01;35:*.flv=01;35:*.gl=01;35:*.dl=01;35:*.xcf=01;35:*.xwd=01;35:*.yuv=01;35:*.cgm=01;35:*.emf=01;35:*.ogv=01;35:*.ogx=01;35:*.aac=00;36:*.au=00;36:*.flac=00;36:*.m4a=00;36:*.mid=00;36:*.midi=00;36:*.mka=00;36:*.mp3=00;36:*.mpc=00;36:*.ogg=00;36:*.ra=00;36:*.wav=00;36:*.oga=00;36:*.opus=00;36:*.spx=00;36:*.xspf=00;36:*~=00;90:*#=00;90:*.bak=00;90:*.crdownload=00;90:*.dpkg-dist=00;90:*.dpkg-new=00;90:*.dpkg-old=00;90:*.dpkg-tmp=00;90:*.old=00;90:*.orig=00;90:*.part=00;90:*.rej=00;90:*.rpmnew=00;90:*.rpmorig=00;90:*.rpmsave=00;90:*.swp=00;90:*.tmp=00;90:*.ucf-dist=00;90:*.ucf-new=00;90:*.ucf-old=00;90:
    FLAG=pwn.college{ErEzAcDcUgwMB4aF7oe2kqsEq05.dhTN1QDL2YTN0czW}
    LESSCLOSE=/usr/bin/lesspipe %s %s
    TERM=xterm
    LESSOPEN=| /usr/bin/lesspipe %s
    SHLVL=1
    LC_CTYPE=C.UTF-8
    PATH=/run/challenge/bin:/run/workspace/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
    _=/run/workspace/bin/env
    ```

# Storing Command Output

1. **Understanding `Command Substitution`**:
    - This is a shell feature that allows the output of a command to be captured and assigned to a variable.
     - Basic Syntax:
    ```bash
    Variable_Name=$(command)
    ```

2. **Executing the `run` Program and Storing its Output**:
    - We need to use the absolute path `/challenge/run` to run the program and then store its output in a variable named `PWN` using `command substitution`.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@variables~storing-command-output:~$ PWN=$(/challenge/run)
    Congratulations! You have read the flag into the PWN variable. Now print it out 
    and submit it!
    ```

3. **Printing the contents of the `PWN` variable**:
    - We need to use the `echo` command followed by `$PWN` argument to print the contents of the `PWN` variable.
    - Here’s the command I used:
    ```bash
    hacker@variables~storing-command-output:~$ echo $PWN
    ```

4. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@variables~storing-command-output:~$ echo $PWN
    pwn.college{435AI44jZlGyLEzG2DocbcBtaqg.dVzN0UDL2YTN0czW}
    ```

# Reading Input

1. **Understanding the `read` Command and the `-p` Argument**:
    - `read` is a built-in command in bash that reads a line of input from standard input and stores it in a variable.
    - `-p` argument allows us to specify a prompt for the user, so it's clear when input is expected.
    - Example:
    ```bash
    hacker@variables~reading-input:~$ read MY_VARIABLE
    Hello!
    hacker@variables~reading-input:~$ echo "You entered: $MY_VARIABLE"
    You entered: Hello!
    hacker@variables~reading-input:~$ read -p "Enter value for PWN: " PWN
    Enter value for PWN: COLLEGE
    hacker@variables~reading-input:~$ echo "The PWN variable is set to: $PWN"
    The PWN variable is set to: COLLEGE
    ```

2. **Executing the Required Command**:
    - We need to use the `read` command to prompt the user for input and store it in the `PWN` variable and then we need to provide the value `COLLEGE` when prompted.
    - Here’s the command I used:
    ```bash
    hacker@variables~reading-input:~$ read PWN
    COLLEGE
    ```

3. **Printing the contents of the `PWN` variable**:
    - We need to use the `echo` command followed by `$PWN` argument to print the contents of the `PWN` variable.
    - Here’s the command I used:
    ```bash
    hacker@variables~reading-input:~$ echo $PWN
    ```

4. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@variables~reading-input:~$ echo $PWN
    COLLEGE
    You've set the PWN variable properly! As promised, here is the flag:
    pwn.college{4o0Sy31YRYm-xHVp37_UNc02Dq_.dhzN1QDL2YTN0czW}
    ```

# Reading Files

1. **Executing the Required Command with `read` command and File Redirection**:
    - We need to use the `read` command to read the contents of `/challenge/read_me` directly into the `PWN` variable.
    - Here’s the command I used:
    ```bash
    hacker@variables~reading-files:~$ read PWN < /challenge/read_me
    ```

2. **Printing the contents of the `PWN` variable**:
    - We need to use the `echo` command followed by `$PWN` argument to print the contents of the `PWN` variable.
    - Here’s the command I used:
    ```bash
    hacker@variables~reading-files:~$ echo $PWN
    ```

3. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@variables~reading-files:~$ echo $PWN
    KTbHwAsnArSlIegx6x1B21koOMWkQUsV4nbpz8TkVXum1v15CHvaK
    You've set the PWN variable properly! As promised, here is the flag:
    pwn.college{oVcQvBnjryyVyd3Em31pnmxkKWN.dBjM4QDL2YTN0czW}
    ```
