## Bandit Level 13 → Level 14

### 🔍 Goal
- The password for the next level is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. Note: localhost is a hostname that refers to the machine you are working on

### 🛠️ Tools / Commands Used
`ssh`

### 🔬 New Information
- 


### 🧭 Approach
- the directory has a SSH private RSA key. So lets try to ssh into bandit14 via localhost
- `ssh -i sshkey.private bandit14@localhost -p 2220`


### 🔑Password
 - MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS

