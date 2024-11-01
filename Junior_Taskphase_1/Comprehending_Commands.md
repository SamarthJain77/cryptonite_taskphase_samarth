# cat: not the pet, but the command!

1. **Understanding the `cat` Command**:
    - The basic usage of `cat` is to read and display the content of a file.
    - Example:
    ```bash
    hacker@commands~cat-not-the-pet-but-the-command:~$ cat myfile
    This is my file!
    ```
    - If `cat` is provided multiple file names as arguments, it will read and output their content in the order provided.
    - Example:
    ```bash
    hacker@commands~cat-not-the-pet-but-the-command:~$ cat myfile yourfile
    This is my file!
    This is your file!
    ```
    - When `cat` is invoked without any file arguments, it reads input from the terminal and echoes the input back to the terminal.

2. **Using `cat` to Read the `flag` File**:
    - Since the challenge starts with the shell located in the home directory (`~`), there is no need to change directories. We just need to read and display the content of the `flag` file.
    - Here’s the command I used:
    ```bash
    hacker@commands~cat-not-the-pet-but-the-command:~$ cat flag
    ```

3. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@commands~cat-not-the-pet-but-the-command:~$ cat flag
    pwn.college{8fo0nZ1k5L2RbwIM55Y68VbJOd2.dFzN1QDL2YTN0czW}
    ```

# catting absolute paths

1. **Understanding the `cat` Command with Absolute Paths**:
    - `cat` can be used with absolute paths to read any accessible file without needing to change directories.
    - Syntax:
    ```bash
    cat /absolute/path/to/file
    ```
2. **Understanding the Absolute Path**:
    - The challenge specifies that the flag file is located at `/flag`.
    
3. **Using `cat` to Read the `flag` File**:
    - Since `cat` can be used with absolute paths, there is no need to change directories. We just need to read and display the content of the `flag` file.
    - Here’s the command I used:
    ```bash
    hacker@commands~catting-absolute-paths:~$ cat /flag
    ```

4. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@commands~catting-absolute-paths:~$ cat /flag
    pwn.college{shAmmrjCPe7RIs1HMKTTCq7E3rR.dlTM5QDL2YTN0czW}
    ```

# more catting practice

1. **Understanding the Limitation**:
    - In this challenge, the `cd` command cannot be used, preventing navigation to the directory containing the flag.
    - When `cd` is not allowed, the only way to access files in other directories is by using their absolute paths.

2. **Understanding the Directory Structure**:
    - The flag is located at `/lib/racket/flag`, as specified in the challenge.

3. **Using `cat` to Read the `flag` File**:
    - Since `cd` is disabled, I used the `cat` command with the full path of the flag file to read its content.
    - Here’s the command I used:
    ```bash
    hacker@commands~more-catting-practice:~$ cat /lib/racket/flag
    ```

4. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@commands~more-catting-practice:~$ cat /lib/racket/flag
    pwn.college{8CtdCZx0vOpH-tOe1VAtLK8S6cd.dBjM5QDL2YTN0czW}
    ```

# grepping for a needle in a haystack

1. **Understanding the `grep` Command**:
    - `grep` is a command-line utility for searching text files for lines that match a specified pattern.
    - Basic Syntax:
    ```bash
    grep SEARCH_STRING /path/to/file
    ```
    - The above command searches for `SEARCH_STRING` in the specified file and prints the lines containing it to the console.

2. **Understanding the Search Pattern**:
    - The hint provided states that the flag always starts with `pwn.college`.
    
3. **Using `grep` to Find the Flag**:
    - I used `grep` to search for lines containing `pwn.college` in the large text file (`/challenge/data.txt`).
    - Here’s the command I used:
    ```bash
    hacker@commands~grepping-for-a-needle-in-a-haystack:~$ grep pwn.college /challenge/data.txt
    ```

4. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@commands~grepping-for-a-needle-in-a-haystack:~$ grep pwn.college /challenge/data.txt
    pwn.college{06K1SJyk-Py2887DLt_WJsJ_JpB.ddTM4QDL2YTN0czW}
    ```

# listing files

1. **Understanding the `ls` Command**:
    - `ls` is a command-line utility used for listing files and directories.
    - Basic Syntax:
    ```bash
    ls [DIRECTORY]
    ```
    - If no directory is specified, `ls` lists the files in the current directory by default.

2. **Identifying the Executable File**:
    - We need to view the contents of the `/challenge` directory so I used the `ls` command to list all the files in `/challenge`.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@commands~listing-files:~$ ls /challenge
    26986-renamed-run-18015  DESCRIPTION.md
    ```
    - From the output, I observed the executable file, which was named `26986-renamed-run-18015`.

3. **Executing the File**:
    - I ran the executable file using its path.
    - Here’s the command I used:
    ```bash
    hacker@commands~listing-files:~$ /challenge/26986-renamed-run-18015
    ```

4. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@commands~listing-files:~$ /challenge/26986-renamed-run-18015
    Yahaha, you found me! Here is your flag:
    pwn.college{U2JYRqIV_xHRIAzUi2VLuH607Ei.dhjM4QDL2YTN0czW}
    ```

# touching files

1. **Understanding the `touch` Command**:
    - `touch` is primarily used to create empty files.
    - Basic Syntax:
    ```bash
    touch FILE_NAME
  - We can create multiple files in a single command by specifying multiple file names.

2. **Navigating to the `/tmp` Directory**:
    - `/tmp` is a directory in Linux used for storing temporary files.
    - Here’s the command I used:
    ```bash
    hacker@commands~touching-files:~$ cd /tmp
    ```

3. **Creating the Required Files**:
   - I used the `touch` command to create both `/tmp/pwn` and `/tmp/college` files in a single command.
   - Here’s the command I used:
     ```bash
     hacker@commands~touching-files:/tmp$ touch pwn college
     ```

4. **Executing the `run` Program**:
   - After creating the required files, I executed the `run` program present in the `challenge` directory.
   - Here’s the command I used:
     ```bash
     hacker@commands~touching-files:/tmp$ /challenge/run
     ```
     
5. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@commands~touching-files:/tmp$ /challenge/run
    Success! Here is your flag:
    pwn.college{gNJPy1h8RYfZNfiOfarZsHUs1hJ.dBzM4QDL2YTN0czW}
    ```

# removing files

1. **Understanding the `rm` Command**:
    - The `rm` command stands for "remove" and is used to delete files or directories.
    - Basic Syntax:
    ```bash
    rm FILE_NAME
    ```

2. **Removing the File**:
    - We know that the `delete_me` file is present in the home directory so we need to remove it using `rm`.
    - Here’s the command I used:
    ```bash
    hacker@commands~removing-files:~$ rm delete_me
    ```
    
3. **Executing the Required Program**:
   - I executed the `/challenge/check` program to verify the file's removal.
   - Here’s the command I used:
     ```bash
     hacker@commands~removing-files:~$ /challenge/check
     ```
     
4. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@commands~removing-files:~$ /challenge/check
    Excellent removal. Here is your reward:
    pwn.college{cYR_N1CyrMeD6XndpV61FEiGrTz.dZTOwUDL2YTN0czW}
    ```

# hidden files

1. **Understanding the `ls` Command with `-a` Option**:
    - By default, the `ls` command only displays visible files.
    - The `-a` option is used to list **all** files, including hidden ones.
    - Basic Syntax:
    ```bash
    ls -a [DIRECTORY_PATH]
    ```

2. **Navigating to the Root Directory**:
    - We start with the current working directory set to `/`.
    - Here’s the command I used:
    ```bash
    hacker@commands~hidden-files:~$ cd /
    ```

3. **Identifying the Hidden Flag File**:
    - We need to view all the files of the `/` directory so I used the `ls -a` command to list all the files, including hidden ones.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@commands~hidden-files:/$ ls -a
    .           .flag-8881596214312  challenge  home   lib64   mnt  proc  sbin  tmp
    ..          bin                  dev        lib    libx32  nix  root  srv   usr
    .dockerenv  boot                 etc        lib32  media   opt  run   sys   var
    ```
    - From the output, I observed the hidden flag file, which was named `.flag-8881596214312`.

4. **Reading the Hidden Flag File**:
    - I read the identified file using the `cat` command.
    - Here’s the command I used:
    ```bash
    hacker@commands~hidden-files:/$ cat .flag-8881596214312
    ```

5. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@commands~hidden-files:/$ cat .flag-8881596214312
    pwn.college{gns8xBoKtHXd8ZkPjsWP_yq039a.dBTN4QDL2YTN0czW}
    ```

# An Epic Filesystem Quest

1. **Navigating to the Root Directory**:
    - We start with the current working directory set to `/`.
    - Here’s the command I used:
    ```bash
    hacker@commands~an-epic-filesystem-quest:~$ cd /
    ```

2. **Identifying the First Clue File**:
    - We need to view all the files of the `/` directory.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@commands~an-epic-filesystem-quest:/$ ls
    DOSSIER  challenge  flag  lib32   media  opt   run   sys  var
    bin      dev        home  lib64   mnt    proc  sbin  tmp
    boot     etc        lib   libx32  nix    root  srv   usr
    ```
    - From the output, I observed the initial clue file, which was named `DOSSIER`.

3. **Reading the First Clue File**:
    - I read the identified file using the `cat` command.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@commands~an-epic-filesystem-quest:/$ cat DOSSIER
    Lucky listing!
    The next clue is in: /usr/share/javascript/mathjax/jax/output/HTML-CSS/fonts/Gyre-Pagella/Normal/Regular
    ```

4. **Navigating to the Specified Directory**:
    - We need to be located in the path specified by the clue file.
    - Here’s the command I used:
    ```bash
    hacker@commands~an-epic-filesystem-quest:/$ cd  /usr/share/javascript/mathjax/jax/output/HTML-CSS/fonts/Gyre-Pagella/Normal/Regular
    ```

5. **Identifying the Next Clue File**:
    - We need to view all the files of the `/usr/share/javascript/mathjax/jax/output/HTML-CSS/fonts/Gyre-Pagella/Normal/Regular` directory.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/jax/output/HTML-CSS/fonts/Gyre-Pagella/Normal/Regular$ ls
    Main.js  TEASER
    ```
    - From the output, I observed the next clue file, which was named `TEASER`.

6. **Reading the Next Clue File**:
    - I read the identified file using the `cat` command.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/jax/output/HTML-CSS/fonts/Gyre-Pagella/Normal/Regular$ cat TEASER
    Congratulations, you found the clue!
    The next clue is in: /opt/kropr/.git/objects/5f

    The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
    ```

7. **Navigating to the Specified Directory**:
    - We need to be located in the path specified by the clue file.
    - Here’s the command I used:
    ```bash
    hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/jax/output/HTML-CSS/fonts/Gyre-Pagella/Normal/Regular$ cd /opt/kropr/.git/objects/5f
    ```

8. **Identifying the Next Clue File**:
    - We need to view all the files of the `/opt/kropr/.git/objects/5f` directory, including the hidden ones.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@commands~an-epic-filesystem-quest:/opt/kropr/.git/objects/5f$ ls -a
    .  ..  .CLUE  0abecb613308dce446c76ad65bd2d5842b87be
    ```
    - From the output, I observed the next clue file, which was named `.CLUE`.

9. **Reading the Next Clue File**:
    - I read the identified file using the `cat` command.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@commands~an-epic-filesystem-quest:/opt/kropr/.git/objects/5f$ cat .CLUE
    Yahaha, you found me!
    The next clue is in: /usr/share/perl/5.30.0/App/Prove/State

    Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
    ```

10. **Identifying the Next Clue File**:
    - We need to view all the files of the `/usr/share/perl/5.30.0/App/Prove/State` directory, without 'cd'ing into it.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@commands~an-epic-filesystem-quest:/opt/kropr/.git/objects/5f$ ls /usr/share/perl/5.30.0/App/Prove/State
    INSIGHT-TRAPPED  Result  Result.pm
    ```
    - From the output, I observed the next clue file, which was named `INSIGHT-TRAPPED`.

11. **Reading the Next Clue File**:
    - I read the identified file using the `cat` command.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@commands~an-epic-filesystem-quest:/opt/kropr/.git/objects/5f$ cat /usr/share/perl/5.30.0/App/Prove/State/INSIGHT-TRAPPED
    Tubular find!
    The next clue is in: /usr/include/x86_64-linux-gnu/c++/9
    ```

12. **Navigating to the Specified Directory**:
    - We need to be located in the path specified by the clue file.
    - Here’s the command I used:
    ```bash
    hacker@commands~an-epic-filesystem-quest:/opt/kropr/.git/objects/5f$ cd /usr/include/x86_64-linux-gnu/c++/9
    ```

13. **Identifying the Next Clue File**:
    - We need to view all the files of the `/usr/include/x86_64-linux-gnu/c++/9` directory.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@commands~an-epic-filesystem-quest:/usr/include/x86_64-linux-gnu/c++/9$ ls
    32  BLUEPRINT  bits  ext  x32
    ```
    - From the output, I observed the next clue file, which was named `BLUEPRINT`.

14. **Reading the Next Clue File**:
    - I read the identified file using the `cat` command.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@commands~an-epic-filesystem-quest:/usr/include/x86_64-linux-gnu/c++/9$ cat BLUEPRINT
    Lucky listing!
    The next clue is in: /opt/linux/linux-5.4/tools/arch/arm64/include

    Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
    ```

15. **Identifying the Next Clue File**:
    - We need to view all the files of the `/opt/linux/linux-5.4/tools/arch/arm64/include` directory, without 'cd'ing into it.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@commands~an-epic-filesystem-quest:/usr/include/x86_64-linux-gnu/c++/9$ ls /opt/linux/linux-5.4/tools/arch/arm64/include
    GIST-TRAPPED  asm  uapi
    ```
    - From the output, I observed the next clue file, which was named `GIST-TRAPPED`.

16. **Reading the Next Clue File**:
    - I read the identified file using the `cat` command.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@commands~an-epic-filesystem-quest:/usr/include/x86_64-linux-gnu/c++/9$ cat /opt/linux/linux-5.4/tools/arch/arm64/include/GIST-TRAPPED
    Tubular find!
    The next clue is in: /usr/local/lib/python3.8/dist-packages/decorator-5.1.1.dist-info

    The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
    ```

17. **Navigating to the Specified Directory**:
    - We need to be located in the path specified by the clue file.
    - Here’s the command I used:
    ```bash
    hacker@commands~an-epic-filesystem-quest:/usr/include/x86_64-linux-gnu/c++/9$ cd /usr/local/lib/python3.8/dist-packages/decorator-5.1.1.dist-info
    ```

18. **Identifying the Next Clue File**:
    - We need to view all the files of the `/usr/local/lib/python3.8/dist-packages/decorator-5.1.1.dist-info` directory.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/decorator-5.1.1.dist-info$ ls
    INSTALLER  LICENSE.txt  METADATA  RECORD  REVELATION  WHEEL  pbr.json  top_level.txt
    ```
    - From the output, I observed the next clue file, which was named `REVELATION`.

19. **Reading the Next Clue File**:
    - I read the identified file using the `cat` command.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/decorator-5.1.1.dist-info$ cat REVELATION
    Tubular find!
    The next clue is in: /opt/linux/linux-5.4/include/config/have/cmpxchg

    Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
    ```

20. **Identifying the Next Clue File**:
    - We need to view all the files of the `/opt/linux/linux-5.4/include/config/have/cmpxchg` directory, without 'cd'ing into it.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/decorator-5.1.1.dist-info$ ls /opt/linux/linux-5.4/include/config/have/cmpxchg
    WHISPER-TRAPPED  double.h  local.h
    ```
    - From the output, I observed the next clue file, which was named `WHISPER-TRAPPED`.

21. **Reading the Next Clue File**:
    - I read the identified file using the `cat` command.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/decorator-5.1.1.dist-info$ cat /opt/linux/linux-5.4/include/config/have/cmpxchg/WHISPER-TRAPPED
    Tubular find!
    The next clue is in: /usr/local/lib/python3.8/dist-packages/angr/analyses/decompiler/structuring/__pycache__

    The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
    ```

22. **Navigating to the Specified Directory**:
    - We need to be located in the path specified by the clue file.
    - Here’s the command I used:
    ```bash
    hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/decorator-5.1.1.dist-info$ cd /usr/local/lib/python3.8/dist-packages/angr/analyses/decompiler/structuring/__pycache__
    ```

23. **Identifying the Last Clue File**:
    - We need to view all the files of the `/usr/local/lib/python3.8/dist-packages/angr/analyses/decompiler/structuring/__pycache__` directory, including the hidden ones.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/angr/analyses/decompiler/structuring/__pycache__$ ls -a
    .   .CUE                     dream.cpython-38.pyc    recursive_structurer.cpython-38.pyc  structurer_nodes.cpython-38.pyc
    ..  __init__.cpython-38.pyc  phoenix.cpython-38.pyc  structurer_base.cpython-38.pyc
    ```
    - From the output, I observed the last clue file, which was named `.CUE`.

24. **Reading the Last Clue File**:
    - I read the identified file using the `cat` command.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/angr/analyses/decompiler/structuring/__pycache__$ cat .CUE
    ```

25. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/angr/analyses/decompiler/structuring/__pycache__$ cat .CUE
    CONGRATULATIONS! Your perserverence has paid off, and you have found the flag!
    It is: pwn.college{Iot2UOagg9045KmxlaHo8aSBbng.dljM4QDL2YTN0czW}
    ```

# making directories

1. **Understanding the `mkdir` Command**:
    - The `mkdir` command creates a new directory at the specified location.
    - Example:
    ```bash
    hacker@commands~making-directories:~$ mkdir my_directory
    hacker@commands~making-directories:~$ ls
    my_directory
    ```

2. **Navigating to the `/tmp` Directory**:
    - `/tmp` is a directory in Linux used for storing temporary files.
    - Here’s the command I used:
    ```bash
    hacker@commands~making-directories:~$ cd /tmp
    ```

3. **Creating the `pwn` Directory**:
    - I used the `mkdir` command to create a directory named `pwn`.
    - Here’s the command I used:
    ```bash
    hacker@commands~making-directories:/tmp$ mkdir pwn
    ```

4. **Navigating into the `pwn` Directory**:
    - I changed the directory to `pwn` using `cd` command.
    - Here’s the command I used:
    ```bash
    hacker@commands~making-directories:/tmp$ cd pwn
    ```

5. **Creating the Required File**:
   - I used the `touch` command to create an empty file named `college` in the `pwn` directory.
   - Here’s the command I used:
     ```bash
     hacker@commands~making-directories:/tmp/pwn$ touch college
     ```

6. **Executing the `run` Program**:
   - After creating the required file, I executed the `run` program present in the `challenge` directory.
   - Here’s the command I used:
     ```bash
     hacker@commands~making-directories:/tmp/pwn$ /challenge/run
     ```
     
7. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@commands~making-directories:/tmp/pwn$ /challenge/run
    Success! Here is your flag:
    pwn.college{Uy6kjd2xxINIqJ69_Tubq_Wc10j.dFzM4QDL2YTN0czW}
    ```

# finding files

1. **Understanding the `find` Command**:
    - `find` is used to search for files and directories within the filesystem.
    - By default, `find` starts searching from the current directory if no path is specified.
    - `find -name <filename>` is used to search for files or directories with a specific name.
    - `find <directory>` is used to specify the starting directory for the search.

2. **Using `find` to Search the Entire Filesystem**:
    - We need to search the root directory (`/`) and look for files named `flag`.
    - Here’s the command I used:
    ```bash
    hacker@commands~finding-files:~$ find / -name flag
    ```

3. **Interpreting the Search Results**:
    - The output of the `find` command listed every file named `flag` under the root directory (`/`).
    - Output:
    ```bash
    hacker@commands~finding-files:~$ find / -name flag
    /usr/local/lib/python3.8/dist-packages/pwnlib/flag
    /usr/local/share/radare2/5.9.5/flag
    /usr/share/racket/pkgs/redex-pict-lib/redex/compiled/flag
    /opt/pwndbg/.venv/lib/python3.8/site-packages/pwnlib/flag
    /opt/radare2/libr/flag
    /nix/store/1yagn5s8sf7kcs2hkccgf8d0wxlrv5sz-radare2-5.9.0/share/radare2/5.9.0/flag
    /nix/store/pmvk2bk4p550w182rjfm529kfqddnvh3-python3.11-pwntools-4.12.0/lib/python3.11/site-packages/pwnlib/flag
    ```
    - Each of these files could potentially contain the correct flag, but some may be directories.

4. **Reading the Files**:
    - I used `cat` command to read each file sequentially until I found the correct one.
    - Here’s the command I used and the output I got:
    ```bash
    hacker@commands~finding-files:~$ cat /usr/local/lib/python3.8/dist-packages/pwnlib/flag
    cat: /usr/local/lib/python3.8/dist-packages/pwnlib/flag: Is a directory
    hacker@commands~finding-files:~$ cat /usr/local/share/radare2/5.9.5/flag
    cat: /usr/local/share/radare2/5.9.5/flag: Is a directory
    hacker@commands~finding-files:~$ cat /usr/share/racket/pkgs/redex-pict-lib/redex/compiled/flag
    ```
     
5. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@commands~finding-files:~$ cat /usr/share/racket/pkgs/redex-pict-lib/redex/compiled/flag
    pwn.college{kwipyjjTRmUO9-dAzJ2k-z6K6NV.dJzM4QDL2YTN0czW}
    ```

# linking files

1. **Understanding Hard & Soft (Symbolic) Links**:
    - Hard links are like multiple addresses leading directly to the same location.
    - Symbolic links (symlinks) are references to the original file or directory. They point to the original file path, making the data accessible via different addresses.
    - `ln -s <original_file_path> <link_path>` is used to create a symlink at `/path/to/symlink` that points to `/path/to/original`.
    - We can identify symlinks using the `file` command, which shows the file type as a "symbolic link" along with the path it points to.

2. **Identifying the Problem**:
    - The script `/challenge/catflag` reads from `/home/hacker/not-the-flag` so we need to remove the `/home/hacker/not-the-flag` file and then create a new symlink from `/home/hacker/not-the-flag` to `/flag` to redirect it to the correct flag file.

3. **Removing the `/home/hacker/not-the-flag` File**:
    - I used the `rm` command to remove the file named `/home/hacker/not-the-flag`.
   - Here’s the command I used:
     ```bash
     hacker@commands~linking-files:~$ rm /home/hacker/not-the-flag
     ```

4. **Creating the Symlink**:
    - I used the `ln -s` command to create a symbolic link called `/home/hacker/not-the-flag` that points to `/flag.`
    - Here’s the command I used:
    ```bash
    hacker@commands~linking-files:~$ ln -s /flag /home/hacker/not-the-flag
    ```
     
5. **Running the Challenge Script**:
    - I executed the script `/challenge/catflag` to read the actual flag file.
    - Here’s the command I used:
    ```bash
    hacker@commands~linking-files:~$ /challenge/catflag
    ```

6. **Capturing the Flag**:
    - After running the command, the terminal displays the flag.
    - Output:
    ```bash
    hacker@commands~linking-files:~$ /challenge/catflag
    About to read out the /home/hacker/not-the-flag file!
    pwn.college{Y1B3t60h1VqC7uyRo3tZbDxM3nT.dlTM1UDL2YTN0czW}
    ```
