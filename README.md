## Example Shell Script

Below is a basic shell script that creates multiple folders and users on a Linux system.

```bash
#!/bin/bash

# Create directories
mkdir Folder1
mkdir Folder2
mkdir Folder3

# Create users
sudo useradd user1
sudo useradd user2
sudo useradd user3
```

## Task: Creating and Running a Shell Script

### Steps:

1. **Create a folder on an Ubuntu server** and name it `shell-scripting`.
2. **Using the Vim editor, create a file** called `my_first_shell_script.sh`.
3. **Insert the shell script code above** into the newly created file.
4. **Save the file**.
5. Use the `cd` command to **change into the shell-scripting directory**.
6. Use the `ls -latr` command to **confirm that the file is created**.

### Expected Output:

```sh
# ls -latr
total 12
-rw-r--r-- 1 root root  149 Feb 11 14:35 my_first_shell_script.sh
drwxr-xr-x 1 root root 4096 Feb 11 14:36 ..
drwxr-xr-x 2 root root 4096 Feb 11 14:36 .
```

### Understanding File Permissions

The output `-rw-r--r--` means:

- The owner has **read (r) and write (w)** permissions.
- Members of the file's group have **read (r)** permission.
- Others have **read (r)** permission.
- No one has **execute (x)** permission, so the script **cannot be executed yet**.

### Running the Script

Attempting to execute the script directly:

```sh
./my_first_shell_script.sh
```

Results in:

```sh
bash: ./my_first_shell_script.sh: Permission denied
```

This error occurs because **execute permissions are missing**.

## Granting Execute Permission and Running the Script

### Steps:

1. **Add execute permission** for the owner:
   ```sh
   chmod u+x my_first_shell_script.sh
   ```
2. **Run the script:**
   ```sh
   ./my_first_shell_script.sh
   ```
3. **Evaluate if folders are created:**
   ```sh
   ls
   ```
4. **Evaluate if users are created:**
   ```sh
   id user1
   id user2
   id user3
   ```

### Expected Output:

```sh
# id user1
uid=1000(user1) gid=1000(user1) groups=1000(user1)
```

## Understanding the Shebang (`#!/bin/bash`)

At the beginning of the shell script, `#!/bin/bash` is written. This is known as a **shebang**. It specifies the interpreter that should be used to execute the script.

- `/bin/bash`: The absolute path to the Bash shell.
- If using another shell like `sh`, the shebang would be `#!/bin/sh`.
- Without a shebang, you may need to explicitly specify the interpreter while running the script.

## Variable Declaration and Initialization

Variables in shell scripting store data such as numbers, strings, and arrays.

### Example:

Assigning a value to a variable:

```sh
name="John"
```

Retrieving the value of a variable:

```sh
echo $name
```

**Output:**

```sh
John
```

