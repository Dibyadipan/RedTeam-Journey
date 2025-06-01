## Bandit Level 19 → Level 20

### 🔍 Goal
- To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.

### 🔬 New Information
- **Executing a file in Linux**
    - `chmod +x filename`
    - `./filename`
- The **setuid** permission allows a file (usually a binary) to run with the permissions of the file owner, not the user who runs it.
For example, if a binary is owned by root and has setuid, then when a normal user runs it, it executes with root privileges.

### 🧭 Approach
- As the setuid permission is already enabled so we just need to execute the command to find the password.
- `./bandit20-do cat /etc/bandit_pass/bandit20`

### 🔑Password
- 0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
