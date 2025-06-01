## Bandit Level 18 → Level 19

### 🔍 Goal

- The password for the next level is stored in a file readme in the homedirectory. Unfortunately, someone has modified .bashrc to log you out when you log in with SSH.

### 🔬 New Information
- `bash.rc` is a shell startup file that executes when a user ssh into that machine remotely. It basically starts an interactive shell for the user.
- You can directly run a command while ssh ing into the machine

### 🧭 Approach
- As the `bash.rc` has been modified so we need to think of running a command without launching the interactive shell.
- The `bash.rc` file might contain some `exit` command which is logging me out.
- `ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme`

### 🔑Password
- cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8
