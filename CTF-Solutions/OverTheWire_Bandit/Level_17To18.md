## Bandit Level 17 → Level 18

### 🔍 Goal

- There are 2 files in the homedirectory: passwords.old and passwords.new. The password for the next level is in passwords.new and is the only line that has been changed between passwords.old and passwords.new

NOTE: if you have solved this level and see ‘Byebye!’ when trying to log into bandit18, this is related to the next level, bandit19

### 🔬 New Information
- `diff` command compares two files and helps to spot the difference on which lines changes were made.

### 🧭 Approach
- Let's compare the two files side by side and filter the changed line - that is our password.
    - `diff -y --suppress-common-lines passwords.old passwords.new`

### 🔑Password
- x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO
