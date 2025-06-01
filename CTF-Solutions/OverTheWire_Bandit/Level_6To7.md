## Bandit Level 6 → Level 7

### 🔍 Goal
- The password for the next level is stored **somewhere on the server** and has all of the following properties:
    - owned by user bandit7
    - owned by group bandit6
    - 33 bytes in size

### 🛠️ Tools / Commands Used
`cat`, `find`

### 🔬 New Information
- File Ownership: `stat -c '%U' filename`
- File group: `stat -c '%G' filename`
- We can also find files with users and groups by the find command flags `find / -user bandit7 -group bandit6 -type f -size 33c`
- Filter by size: `find / -type f -size 33c 2>/dev/null`
    - the `2>/dev/null` hides the error messages

### 🧭 Approach
- As the password is stored **somewhere on the server**, not specifically inside that directory so we have to search in all files in the root directory
    - Command: `find / -user bandit7 -group bandit6 -type f -size 33c 2>/dev/null`
    - This command searches in the root folder with the given conditions
    - Output: `/var/lib/dpkg/info/bandit7.password`
- `cat` that file to get that password!

### 🔑Password
 - morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj
