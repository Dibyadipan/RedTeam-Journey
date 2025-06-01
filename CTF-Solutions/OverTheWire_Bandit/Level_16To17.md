## Bandit Level 16 → Level 17

### 🔍 Goal

- The credentials for the next level can be retrieved by submitting the password of the current level to a port on localhost in the range 31000 to 32000. First find out which of these ports have a server listening on them. Then find out which of those speak SSL/TLS and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.

Helpful note: Getting “DONE”, “RENEGOTIATING” or “KEYUPDATE”? Read the “CONNECTED COMMANDS” section in the manpage.

### 🔬 New Information

-

### 🧭 Approach

- First we need to find out which port has a server listening.
  - We do that by running a nmap scan on the list of ports: `nmap -p 31000-32000 localhost`
  - Output:
    - 31046/tcp open unknown
    - 31518/tcp open unknown
    - 31691/tcp open unknown
    - 31790/tcp open unknown
    - 31960/tcp open unknown
- So in this 5 ports we need to find out which one of those accept SSL/TLS:
    - `nmap -p 31046,31518,31691,31790,31960 --script ssl-enum-ciphers localhost`
- We notice only `31518` and `31790` accept SSL/TLS
- Now only one of them will give the credentials other will mirror you what you send
- Lets try with `31790`
    - `openssl s_client -connect localhost:31790 -quiet`
    - enter the password
- We get a private ssh key
- save that ssh key in a temp folder `mktemp -d` and with `vim` (touch)
- change the file permission to private using `chmod 600 filename`
- try to ssh to bandit17 in localhost using the private key
    - `ssh -i private.key bandit17@localhost -p 2220`
- save the password from `/etc/bandit_pass/bandit17` for future ref

### 🔑Password
- EReVavePLFHtFlFsjn3hyzMlvSuSAcRD
