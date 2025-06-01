## Bandit Level 12 → Level 13

### 🔍 Goal
- The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been **repeatedly** compressed. For this level it may be useful to create a directory under /tmp in which you can work. Use mkdir with a hard to guess directory name. Or better, use the command “*`mktemp -d`*”. Then copy the datafile using cp, and rename it using mv (read the manpages!)

### 🛠️ Tools / Commands Used
`hexdump`, `file`, `gunzip`

### 🔬 New Information
- A **hexdump** shows the raw contents of a file in hexadecimal (base 16) format, along with the ASCII equivalent if printable.
    - Command: `hexdump -C data.txt`
- **file** command tells us what kind of file it is.
    - `file data.txt`
- **File signatures**: Many compression formats have magic numbers (headers) at the start. For example:
    - 1F 8B → gzip
    - 42 5A 68 → bzip2
    - FD 37 7A 58 5A 00 → xz
    - 75 73 74 61 72 → tar archive (ustar)
    - These can show up multiple times if the file is compressed more than once.
- To **decompress gzip files** we use the command `gunzip filename.gz`
- To **decompress bzip2 files** we use the command `bunzip2 filename`
- To **decompress tar archive files** we use the command `tar -xf filename`
- To **rename** `mv` command is used.


### 🧭 Approach
- As the file has been compressed, lets first figure out the compression format.
- After inspecting the head `hexdump -C yourfile | head`, the file signature was `1F 8B` so it's gzip
- decompressing the file lead to another compressed file and checking it with `file` command was a bzip2 file
- so after repeatedly decompressing with the appropriate decompression method finally an ascii text file was achieved data8
- It contained the password!

### 🔑Password
 - FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn
