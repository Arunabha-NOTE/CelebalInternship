# Linux Assignment

## 1. File Permissions

* **Objective:** Create a file, assign permissions (read, write, execute) to different user categories (owner, group, others), and practice changing permissions using `chmod`.
* **Resources:** [YouTube Video](https://www.youtube.com/watch?v=iwolPf6kN-khttps://www.pluralsight.com/blog/it-ops/linux-file-permissions)
* **Solution:**
    1.  Create a new file using the `touch` command:
        ```bash
        touch my_file.txt
        ```
        ![Figure 1 from paper](vit_figure.png)  
        2.  List the file's permissions using `ls -l`:
        ```bash
        ls -l my_file.txt
        ```
        * Explain the output (e.g., what do the `rwx` characters mean?).
    3.  Change the file permissions using `chmod`.
        * Example 1: Give the owner read, write, and execute permissions; the group read and execute; and others read.
            ```bash
            chmod 754 my_file.txt
            ```
            * Explain the numeric representation of permissions.
        * Example 2: Give the group write permission.
            ```bash
            chmod g+w my_file.txt
            ```
            4.  Verify the changes using `ls -l`.
        ```bash
        ls -l my_file.txt
        ```

## 2. Basic Linux Commands

* **Objective:** Execute basic Linux commands (e.g., `ls`, `cd`, `mkdir`, `rm`, `touch`) to manipulate files and directories, with an emphasis on understanding their usage.
* **Resources:** [Red Hat Article](https://www.redhat.com/sysadmin/create-delete-files-directories-linux)
* **Solution:**
    1.  Create a new directory:
        ```bash
        mkdir my_directory
        ```
        2.  Change the current directory:
        ```bash
        cd my_directory
        ```
        3.  List the contents of the current directory:
        ```bash
        ls -l
        ```
        4.  Create several files using `touch`.
        ```bash
        touch file1.txt file2.txt file3.txt
        ```
        ```bash
        ls -l
        ```
        5.  Remove one of the files:
        ```bash
        rm file1.txt
        ```
        ```bash
        ls -l
        ```
        6.  Move a file to a different location.
        ```bash
        mv file2.txt ../
        ```
        ```bash
        ls -l ../
        ```
        7.  Explain the purpose and usage of each command.
    8.  Explore other useful commands and their options (e.g., `cp`, `mv`).

## 3. Directory Navigation

* **Objective:** Using the terminal, practice navigating through directories, listing file contents, and moving files to different locations.
* **Resources:** [Red Hat Article](https://www.redhat.com/sysadmin/navigating-filesystem-linux-terminal)
* **Solution:**
    1.  Use `pwd` to display the current directory.
        ```bash
        pwd
        ```
        2.  Use absolute and relative paths to navigate to different directories.
        * Example (Absolute):
            ```bash
            cd /home/youruser/Documents
            ```
            * Example (Relative):
            ```bash
            cd ../Desktop
            ```
            3.  Use `ls` with different options (e.g., `-a`, `-l`, `-h`) to list directory contents in various formats.
        ```bash
        ls -lah
        ```
        4.  Use `cd ..` to go up one directory level.
        ```bash
        cd ..
        ```
        5.  Use `cd ~` to go to the home directory.
        ```bash
        cd ~
        ```
        6.  Move files between directories using `mv`.
        *Example (assuming you are in your home directory and moved `file2.txt` there earlier)*
        ```bash
        mkdir test_move
        ```
        ```bash
        mv file2.txt test_move/
        ```
        ```bash
        ls test_move/
        ```
        7.  Explain the differences between absolute and relative paths.

## 4. User and Group Management

* **Objective:** Create a new user and group, set their permissions, and explore user management commands like `useradd`, `usermod`, and `userdel`.
* **Resources:** [Red Hat Article](https://www.redhat.com/sysadmin/manage-permissions)
* **Solution:**
    1.  Create a new group:
        ```bash
        sudo groupadd new_group
        ```
        2.  Create a new user and add them to the group:
        ```bash
        sudo useradd -m -g new_group new_user
        ```
        3.  Set a password for the new user:
        ```bash
        sudo passwd new_user
        ```
        4.  Modify the user's group:
        ```bash
        sudo groupadd other_group # Create this group if it doesn't exist for the example
        ```
        ```bash
        sudo usermod -aG other_group new_user
        ```
        ```bash
        id new_user
        ```
        5.  Delete the user:
        ```bash
        sudo userdel -r new_user
        ```
        6.  Explain the purpose of each command and the options used.

## 5. Additional Linux Commands

* **Objective:** Practice more Linux commands to enhance your command-line skills.
* **Resources:** [JavaTpoint Tutorial](https://www.javatpoint.com/linux-tutorial)
* **Solution:**
    1.  Explore commands for searching files (e.g., `find`, `grep`).
        ```bash
        find . -name "*.txt"
        ```
        ```bash
        grep "example" my_file.txt
        ```
        2.  Learn about file compression and archiving (e.g., `tar`, `gzip`).
        ```bash
        tar -cvf archive.tar my_directory/
        ```
        ```bash
        gzip archive.tar
        ```
        3.  Practice using redirection and piping (`>`, `|`).
        ```bash
        ls -l > directory_contents.txt
        ```
        ```bash
        cat directory_contents.txt | grep "my_file"
        ```
        4.  Investigate system information commands (e.g., `uname`, `df`, `du`).
        ```bash
        uname -a
        ```
        ```bash
        df -h
        ```
        ```bash
        du -sh .
        ```
        5.  Document your findings and provide examples of how to use each command.