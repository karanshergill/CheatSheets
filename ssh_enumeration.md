# What after gaining complete SSH access on a target machine?
Check `socket statistics` to know which ports are listening locally on a the target machine.

## Check Listening Ports
```
▶ ss -tln

# -l : Display only listening sockets.
# -t : Display TCP sockets.
# -n : Do not try to resolve service names.
```

## Check Listening Ports with Service Name
```
▶ ss -tln

# -l : Display only listening sockets.
# -t : Display TCP sockets.
```

