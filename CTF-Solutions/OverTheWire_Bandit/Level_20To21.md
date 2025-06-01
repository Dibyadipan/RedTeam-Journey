## Bandit Level 20 → Level 21

### 🔍 Goal
- There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

NOTE: Try connecting to your own network daemon to see if it works as you think

### 🔬 New Information
- The **screen** command in Linux is a terminal multiplexer — it lets you open multiple shell sessions within a single terminal window and keeps them running even after you disconnect.
- **tmux** is the modern alternative to **screen**.

    - type `tmux` - this starts a new session
    - Create a new "window" (like a new terminal tab): Press: Ctrl + B, then C
    - switch between tabs by ctrl+B then 0 or 1 based on terminal window

- Unix job control lets you manage multiple processes in your shell — pausing, resuming, running them in background or foreground — without closing your terminal.
    - 🛠️ Key Concepts & Commands
        - Command / Key	Meaning
        - &	= *Run a command in the background*
        - jobs = *Show all background and stopped jobs*
        - fg [%job_id] = *Bring a job to the foreground*
        - bg [%job_id] = *Resume a stopped job in the background*
        - CTRL + Z = *Pause (stop) a running foreground process*
        - kill %job_id = *Kill a specific job by ID*
- A **network daemon** is a background process that runs on a server (or device) and listens for incoming network connections

### 🧭 Approach
- We have a setuid binary file in the directory.
- The suconnect binary acts like a TCP client:
    - It connects to localhost`:<port>` that you provide.
    - It waits to receive one line (the bandit20 password).
    - If the password is correct, it responds with the password for bandit21.
    - So we act as the TCP server, listening for that connection.
- Start a tmux session and split it into two panes
    - `tmux`
    - `Ctrl + B`, then `%`  → vertical split
- In the first pane, start a listener (TCP server) using netcat:
    - `nc -lv 4444`
- In the second pane, run the suconnect binary with the same port:
    - `./suconnect 4444`
- As soon as suconnect connects, type the bandit20 password into the nc pane and press Enter.
- If correct, you’ll receive the password for bandit21 in the same nc pane.

### 🔑Password
- EeoULMCra2q0dSkYj561DX7s1CpBuOBt
