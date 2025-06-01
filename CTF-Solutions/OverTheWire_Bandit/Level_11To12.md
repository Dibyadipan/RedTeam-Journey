## Bandit Level 11 → Level 12

### 🔍 Goal
- The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

### 🛠️ Tools / Commands Used
`ls`, `tr`

### 🔬 New Information
- **tr command** is used for character subsitution


### 🧭 Approach
- As the lower and upper case characters are rotated by 13 places (Ceizer Cipher type) we use the `tr` command to decipher it.
    - Command: `tr 'a-zA-Z' 'n-za-mN-ZA-M' < data.txt`
    - Output: `The password is 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4`

### 🔑Password
 - 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
