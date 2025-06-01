## Bandit Level 9 → Level 10

### 🔍 Goal
- The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.

### 🛠️ Tools / Commands Used
`ls`, `grep`

### 🔬 New Information
- `strings` command extracts readable text from binary/obfuscated files.

### 🧭 Approach
- `strings data.txt` does output only the human readable text but we can do better.
- Let's grep the output to print only the lines with "====="
    - Command: `strings data.txt | grep '^='`

### 🔑Password
 - FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
