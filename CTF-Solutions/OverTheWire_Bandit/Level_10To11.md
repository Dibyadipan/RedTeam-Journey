## Bandit Level 10 → Level 11

### 🔍 Goal
- The password for the next level is stored in the file data.txt, which contains base64 encoded data

### 🛠️ Tools / Commands Used
`ls`, `base64`

### 🔬 New Information
- **Base64 encoded data** is a way of representing binary data (like images, files, or any non-text content) using only printable ASCII characters.


### 🧭 Approach
- As the data is base64 encoded so we can try decoding the file.
    - Command: `base64 -d data.txt`
    - Output: `The password is dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr`

### 🔑Password
 - dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
