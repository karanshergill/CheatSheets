# SSH Tunneling/ Port Forwarding
Establish an encrypted SSH connection is established between the local computer and the remote server.
Any traffic sent to the local port specified in the command will be encrypted and forwarded to the remote server, which will then forward it to the specified remote port.
Similarly, any traffic sent to the specified remote port on the remote server will be encrypted and forwarded back through the SSH connection to the local computer,
where it will be forwarded to the local port.

```
▶ ssh -L {local_port}:localhost:{remote_port} {remote_username}@{target_IP or URL}

Example:
▶ ssh -L 1234:localhost:5432 christine@10.10.10.101

# -L : Set up local port forwarding

## {local_port} : The port on the local computer that will be forwarded to the remote server.
## localhost : Specifies that the remote server should forward traffic to its own loopback interface, rather than routing it to a different machine.
## {remote_port} : The port on the remote server to which traffic will be forwarded.
## {remote_username} : The username to use when logging into the remote server.
## {target_IP or URL} : The IP address or domain name of the remote server to connect.
```

