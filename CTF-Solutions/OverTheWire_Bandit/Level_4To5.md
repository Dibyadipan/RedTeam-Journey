## Bandit Level 4 → Level 5

### 🔍 Goal
- The password for the next level is stored in the only human-readable file in the inhere directory. Tip: if your terminal is messed up, try the “reset” command.

### 🛠️ Tools / Commands Used
`ls` , `cat`, `file ./-file*`

### Brute Force Approach
- Found a bunch of files in the `inhere` directory
- The only human readable file was file07 (checking all files)
- Note to read the contents you need to use `cat < -file07` command as it has a special character.
- The password was found in the file07!

# Better Approach
 - Instead of checking individual files we can check which file has human-readable text
 - As per the question only 1 file has human readable data, so to know what kind of content the file has `file ./-file*` command is issued.
 - cat the contents to see the password!

### 🔑Password
 - 4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw



