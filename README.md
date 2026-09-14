# Linux 
# Linux Basic Commands

This README contains basic Linux commands for working with users, directories, files, searching, and disk usage.

---

## 1. Switching Users

### `sudo su`

Switch to a root shell while keeping the current user's environment/home directory.

```bash
$ sudo su
$ pwd
```

Example:

```text
/home/narendra
```

---

### `sudo su -`

Switch to the root user and load the root user's login environment.

```bash
$ sudo su -
$ pwd
```

Example:

```text
/root
```

### Difference

| Command     | User | Home Directory                       |
| ----------- | ---- | ------------------------------------ |
| `sudo su`   | root | Usually remains in current directory |
| `sudo su -` | root | `/root`                              |

---

## 2. `pwd` – Print Working Directory

Shows the directory you are currently in.

```bash
$ pwd
```

Example:

```text
/home/narendra
```

---

## 3. `cd` – Change Directory

### Go to the root directory

```bash
$ cd /
```

`/` is the root of the Linux filesystem.

---

### Go to your home directory

```bash
$ cd ~
```

or simply:

```bash
$ cd
```

`~` represents the current user's home directory.

For example:

```text
/home/narendra
```

---

## 4. Absolute Path

An absolute path starts from `/`, the root directory.

Example:

```bash
$ cd /var/www/html
```

The complete path is specified.

```text
/
└── var
    └── www
        └── html
```

Another example:

```bash
$ cd /home/narendra
```

---

## 5. Relative Path

A relative path starts from your **current directory**.

For example, if you are currently in:

```text
/var
```

You can use:

```bash
$ cd www
$ cd html
```

You do not need to specify `/var`.

### Important

Your original example:

```bash
cd var/
cd www/
cd html
```

works only if `var` exists inside your **current directory**.

If you are at `/`, then:

```bash
cd var
cd www
cd html
```

will take you to:

```text
/var/www/html
```

---

# 6. `ls` – List Files and Directories

### Basic `ls`

```bash
$ ls
```

Displays files and directories in the current directory.

---

### `ls -l` – Long Listing

```bash
$ ls -l
```

Shows detailed information such as:

* File permissions
* Owner
* Group
* File size
* Modification time
* File name

Example:

```text
-rw-r--r-- 1 root root 125 Sep 14 05:30 index.html
```

---

## 7. Hidden Files

Linux hidden files normally start with `.`.

Example:

```text
.config
.bashrc
```

### Show hidden files

```bash
$ ls -la
```

`-a` means **all files**, including hidden files.

---

# 8. Sort Files by Time

```bash
$ ls -lt
```

Where:

* `-l` = long listing
* `-t` = sort by modification time

The newest files are normally shown first.

---

# 9. Sort Files by Size

```bash
$ ls -lS
```

Where:

* `-l` = long listing
* `-S` = sort by file size

Largest files are normally shown first.

---

# 10. Get Command Help

Most Linux commands provide help.

```bash
$ ls --help
```

Example:

```bash
$ cat --help
```

This displays available options and usage information.

---

# 11. Creating a File

## `touch`

Create an empty file:

```bash
$ touch index.html
```

Check the file:

```bash
$ ls -l
```

---

# 12. Reading a File

## `cat`

Display the contents of a file:

```bash
$ cat index.html
```

`cat` displays the file contents in the terminal. It does **not** open the file in an editor.

---

# 13. Adding Content to a File

## Using `echo` with `>`

```bash
$ echo "This is my index file" > index.html
```

`>` means:

> Remove/replace the existing content and write the new content.

For example:

```bash
$ echo "First content" > index.html
$ echo "Second content" > index.html
```

The file will contain only:

```text
Second content
```

---

# 14. Append Content Using `>>`

```bash
$ echo "This is my 3rd Content" >> index.html
```

`>>` means:

> Add the new content to the end of the existing file.

Example:

```bash
$ echo "First line" > index.html
$ echo "Second line" >> index.html
$ echo "Third line" >> index.html
```

Result:

```text
First line
Second line
Third line
```

### Difference Between `>` and `>>`

| Operator | Meaning                    |
| -------- | -------------------------- |
| `>`      | Overwrite existing content |
| `>>`     | Append to existing content |

---

# 15. `vi` – Text Editor

Open a file using `vi`:

```bash
$ vi index.html
```

You can use `vi` to:

* Create files
* Edit files
* Delete text
* Search text
* Save files

---

# 16. `cat -n` – Display Line Numbers

```bash
$ cat -n index.html
```

Example:

```text
     1  This is my index file
     2  This is my second file
     3  This is my third content
```

---

# 17. `cat -E` – Show End of Lines

```bash
$ cat -E index.html
```

This displays `$` at the end of each line.

Example:

```text
Hello World$
Second Line$
Third Line$
```

This can help identify line endings and trailing spaces.

---

# 18. `grep` – Search Text

`grep` is used to search for text inside files.

### Search for `index`

```bash
$ grep index index.html
```

---

### Search for `command`

```bash
$ grep command index.html
```

---

## Case-Insensitive Search

```bash
$ grep -i command index.html
```

`-i` means ignore uppercase/lowercase differences.

For example, it can match:

```text
command
Command
COMMAND
CoMmAnD
```

---

## Count Matching Lines

```bash
$ grep -c command index.html
```

`-c` counts the number of matching lines.

---

## Case-Insensitive + Count

```bash
$ grep -ic command index.html
```

This means:

```text
-i → ignore case
-c → count matching lines
```

---

# 19. Creating Directories

## Create One Directory

```bash
$ mkdir page1
```

---

## Create Multiple Directories

```bash
$ mkdir page1 page2 page3
```

This creates:

```text
page1/
page2/
page3/
```

---

# 20. Creating Parent Directories

Use `mkdir -p` when you want to create multiple directories at once.

```bash
$ mkdir -p f1/f2/f3
```

This creates:

```text
f1/
└── f2/
    └── f3/
```

If the parent directories don't exist, `-p` creates them automatically.

---

## 21. `mkdir -v`

```bash
$ mkdir -v f5
```

`-v` means **verbose**.

It displays information about what the command is doing.

---

# 22. Removing Files

## `rm`

Remove a file:

```bash
$ rm index.html
```

After running the command, `index.html` is deleted.

⚠️ Be careful with `rm` because deleted files may not be recoverable easily.

---

# 23. Removing Empty Directories

## `rmdir`

```bash
$ rmdir page1
```

`rmdir` removes an **empty directory**.

If the directory contains files, `rmdir` will fail.

---

# 24. Removing Parent Directories

```bash
$ rmdir -p f1/f2/f3
```

This can remove the specified directory and empty parent directories.

For example:

```text
f1/
└── f2/
    └── f3/
```

If `f3`, `f2`, and `f1` are empty, they can all be removed.

---

# 25. Remove Directory with Content

The command for recursively removing a directory is:

```bash
$ rm -r page4
```

`-r` means **recursive**.

It removes the directory and its contents.

---

## Force Remove Directory

```bash
$ rm -rf page4
```

Where:

* `-r` = recursive
* `-f` = force


# Linux `cp` and `mv` Commands

## 29. Copy Files – `cp`

The `cp` command is used to **copy files and directories**.

### Copy a File into a Directory

```bash
$ cp file1.txt folder1/
```

This copies `file1.txt` into `folder1`.

Before:

```text
.
├── file1.txt
└── folder1/
```

After:

```text
.
├── file1.txt
└── folder1/
    └── file1.txt
```

The original `file1.txt` still exists.

---

### Copy a File to `/tmp`

```bash
$ cp file1.txt /tmp/
```

This copies `file1.txt` into the `/tmp` directory.

The original file remains in the current directory.

---

## 30. Copy and Rename a File

You can specify a **different filename at the destination**.

```bash
$ cp file1.txt folder1/page1.txt
```

This means:

```text
Source:      file1.txt
Destination: folder1/page1.txt
```

Result:

```text
folder1/
└── page1.txt
```

The original `file1.txt` is not changed.

---

### Copy a File and Create a Copy with a New Name

```bash
$ cp file1.txt file1_copy.txt
```

Result:

```text
file1.txt
file1_copy.txt
```

Both files exist.

---

# 31. Copy Directories – `cp -r`

To copy a directory and everything inside it, use `-r`.

```bash
$ cp -r folder1 folder_copy
```

`-r` means **recursive**.

For example:

```text
folder1/
├── file1.txt
├── file2.txt
└── page1/
    └── index.html
```

Run:

```bash
$ cp -r folder1 folder_copy
```

You get:

```text
folder1/
├── file
```
``` text
Quick Cheat Sheet
Copy
$ cp file1.txt folder1/
Copy to /tmp
$ cp file1.txt /tmp/
Copy and rename
$ cp file1.txt folder1/page1.txt
Create a file copy
$ cp file1.txt file1_copy.txt
Copy directory
$ cp -r folder1 folder_copy
Move file
$ mv file1.txt folder2/
Rename file
$ mv file1.txt page1.txt
Easy Way to Remember
cp = COPY
     Original + Copy

mv = MOVE
     Original is moved

mv = RENAME
     Same file, new name
```


# Symbolic Link 
<img width="1098" height="644" alt="image" src="https://github.com/user-attachments/assets/43a11391-811e-4776-b103-bd9b9b7b6e8c" />

```
$ln -s file2.txt simlinktest.txt 
$ls -l 
simlinktest.txt --> file2.txt
```
### Hard Link 
<img width="1103" height="801" alt="image" src="https://github.com/user-attachments/assets/a99985d6-b6f9-42e4-8282-59ab3451bf93" />

I-Node value is unique data Structure that used to store metadata
```
$ln file3.txt file3_hard.txt 
$ls -l
to show i-Node value 
$ls -li
```
