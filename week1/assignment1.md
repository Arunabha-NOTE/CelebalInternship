# Assignment Linux 

---

## 1. File Permissions

### Objective

Create a file, assign and modify permissions for owner, group, and others using `chmod`.

### Solution

1. **Create a new file:**

   ```bash
   touch my_file.txt
   ```

2. **Check file permissions:**

   ```bash
   ls -l my_file.txt
   ```

   Output:

   ![Screenshot of work](screenshots/filecreation.png) 

   * `-`: regular file
   * `rw-`: owner has read and write
   * `r--`: group has read
   * `r--`: others have read

3. **Change permissions:**

   * Give **owner (7)** = read (4) + write (2) + execute (1)
     **group (5)** = read (4) + execute (1)
     **others (4)** = read (4)

        ```bash
        chmod 754 my_file.txt
        ```

   * Give the group write permission:

     ```bash
     chmod g+w my_file.txt
     ```

4. **Verify changes:**

   ```bash
   ls -l my_file.txt
   ```
    Output:  
    ![Screenshot of work](screenshots/givingpermissions.png) 
---

## 2. Basic Linux Commands

### 🎯 Objective

Execute basic Linux commands to manipulate files and directories.

### 📝 Solution

1. **Create a new directory:**

   ```bash
   mkdir my_directory
   ```

2. **Change into the directory:**

   ```bash
   cd my_directory
   ```

3. **List directory contents:**

   ```bash
   ls -l
   ```

4. **Create files:**

   ```bash
   touch file1.txt file2.txt file3.txt
   ls -l
   ```

5. **Remove a file:**

   ```bash
   rm file1.txt
   ls -l
   ```

6. **Move a file to a different directory:**

   ```bash
   mv file2.txt ../
   ls -l ../
   ```

7. **Additional commands:**

   ```bash
   cp file3.txt copy_of_file3.txt   # Copy file
   mv copy_of_file3.txt ../backup/  # Move file
   ```

---

## 3. Directory Navigation

### 🎯 Objective

Practice navigating through directories and managing file locations.

### 📝 Solution

1. **Show current directory:**

   ```bash
   pwd
   ```

2. **Navigate using absolute path:**

   ```bash
   cd /home/youruser/Documents
   ```

3. **Navigate using relative path:**

   ```bash
   cd ../Desktop
   ```

4. **List with options:**

   ```bash
   ls -lah
   ```

5. **Go up one level:**

   ```bash
   cd ..
   ```

6. **Go to home directory:**

   ```bash
   cd ~
   ```

7. **Move files between directories:**

   ```bash
   mkdir test_move
   mv file2.txt test_move/
   ls test_move/
   ```

8. **Explain paths:**

   * **Absolute path:** full path from root (e.g., `/home/user/...`)
   * **Relative path:** relative to current directory (e.g., `../folder`).

---

## 4. User and Group Management

### 🎯 Objective

Create and manage users/groups and set permissions.

### 📝 Solution

1. **Create a new group:**

   ```bash
   sudo groupadd new_group
   ```

2. **Create a new user in the group:**

   ```bash
   sudo useradd -m -g new_group new_user
   ```

3. **Set user password:**

   ```bash
   sudo passwd new_user
   ```

4. **Modify user's groups:**

   ```bash
   sudo groupadd other_group    # if needed
   sudo usermod -aG other_group new_user
   id new_user
   ```

5. **Delete the user:**

   ```bash
   sudo userdel -r new_user
   ```

6. **Command purposes:**

   * `groupadd`: create group
   * `useradd`: create user
   * `passwd`: set password
   * `usermod -aG`: add to supplementary group
   * `userdel -r`: delete user and home directory

---

## 5. Additional Linux Commands

### 🎯 Objective

Enhance command-line skills with searching, compression, and system info.

### 📝 Solution

1. **Search files:**

   ```bash
   find . -name "*.txt"
   grep "example" my_file.txt
   ```

2. **Compression & archiving:**

   ```bash
   tar -cvf archive.tar my_directory/
   gzip archive.tar
   ```

3. **Redirection & piping:**

   ```bash
   ls -l > directory_contents.txt
   cat directory_contents.txt | grep "my_file"
   ```

4. **System info:**

   ```bash
   uname -a   # Kernel/system info
   df -h      # Disk space
   du -sh .   # Directory size
   ```

5. **Document usage**
   Provide examples and brief descriptions for each command.
