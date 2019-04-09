# Secure Shell Notes

# Packages

OpenSSh Packages:

* openssh-client
* openssh-server (required for login at the target machine only)

## Delete ssh key completely for specific node

```
ssh-keygen -f "/home/gia/.ssh/known_hosts" -R host
```
