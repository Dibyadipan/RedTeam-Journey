## Bandit Level 14 → Level 15

### 🔍 Goal
- The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost.

### 🛠️ Tools / Commands Used
`ssh`, `nc` (netcat)

### 🔬 New Information
- 🔌 What **Netcat** does:
    - Connects to TCP or UDP ports
    - Sends and receives raw data
    - Can act as a client or a server
    - Useful for debugging, file transfers, and networking CTFs
    - Netcat only speaks plaintext not encrypted protocols


### 🧭 Approach
- Lets fetch the current password of bandit14 from the `/etc/bandit_pass` and pass it to the localhost on the port `30000`
    - Command: `echo "MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS" | nc localhost 30000`


### 🔑Password
 - 8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo

