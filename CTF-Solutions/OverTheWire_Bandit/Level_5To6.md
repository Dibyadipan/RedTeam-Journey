## Bandit Level 5 → Level 6

### 🔍 Goal
- The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:
    - human-readable
    - 1033 bytes in size
    - not executable

### 🛠️ Tools / Commands Used
`ls -l`, `ls -lh`, `find`, `cat`, `cd`

### 🔬 New Information
- Different color files has different meanings when `ls` command is issued.
    - blue means directory
    - green means executable file
    - white means normal file
    - Cyan/Light blue means symlink
    - purple means those files have images
- `ls -l` or `ls -lh` gives the file sizes
- `find` command helps to search recursively in directories



### 🧭 Approach
- when the `ls` command was issued, I found many sub-directories in side the "inhere" directory.
- Each subdirectory contained some files. It is not possible to check individual files for the password.
- My first approach was to find all the regular files. So I issued the `find . -type f` command
- There were a lot of files so let's specify the files size. `find . -type f -size 1033c`
    - The c=bytes. By default 512bytes chunked are considered.
    - got an output : `./maybehere07/.file2`
- went to that file and re-checked that it was not executable
    - Command: `ls -l ./.file2`
    - Output: `-rw-r----- 1 root bandit5 1033 Apr 10 14:23 ./.file2`
- The file had the password!

- One liner script: `find . -type f -size 1033c ! -executable -exec file {} \; | grep 'text' | cut -d: -f1 | xargs cat`

### 🔑Password
 - HWasnPhtq9AVKe0dmk45nxy20cvUa6EG



