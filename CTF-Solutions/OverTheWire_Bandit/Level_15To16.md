## Bandit Level 15 → Level 16

### 🔍 Goal
- The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL/TLS encryption.

- Helpful note: Getting “DONE”, “RENEGOTIATING” or “KEYUPDATE”? Read the “CONNECTED COMMANDS” section in the manpage.

### 🔬 New Information
- **openssl s_client**
    - This is like netcat — but for encrypted channels.
    - So for plain TCP we use netcat but for Encrypted TLS we use this.
    - `openssl s_client -connect localhost:30001`

### 🧭 Approach
- When we try to connect throw the openssl client it prompts for the password.
- Once given the current password it spits out the new password.

### 🔑Password
 - kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx
