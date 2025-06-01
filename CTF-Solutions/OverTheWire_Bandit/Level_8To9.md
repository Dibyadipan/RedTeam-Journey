## Bandit Level 8 → Level 9

### 🔍 Goal
- The password for the next level is stored in the file data.txt and is the only line of text that occurs only once

### 🛠️ Tools / Commands Used
`ls`, `grep`

### 🔬 New Information
- `sort` essentially groups the duplicate lines together
- `uniq -c` gives the count of the unique lines in that file
- `grep '^ *1 '` filters the lines with count 1

### 🧭 Approach
-  As the password was the only unique line so we can use the sort and unique commands to filter that out.
    - Command:  `sort data.txt | uniq -c | grep '^ *1 '`
    - Output: `1 4CKMh1JI91bUIZZPXDqGanal4xvAg0JM`

### 🔑Password
 - 4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
