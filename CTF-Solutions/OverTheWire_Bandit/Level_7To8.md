## Bandit Level 7 → Level 8

### 🔍 Goal
- The password for the next level is stored in the file data.txt next to the word millionth

### 🛠️ Tools / Commands Used
`ls`, `grep`

### 🔬 New Information
-  The grep command is a filter that is used to search for lines matching a specified pattern and print the matching lines to standard output.

### 🧭 Approach
- There was a data.txt file.
- grep the line as the password is next to the word "millionth"
    - `grep -w "millionth" data.txt`

### 🔑Password
 - dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
