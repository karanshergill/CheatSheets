# DIG (Domian Information Groper)

### Name to Address Mapping
```
▶ dig @<NAME-SERVER-TO-QUERY> <FQDN> <RECORD_TYPE>
```

### Address to Name Mapping
```
▶ dig @<NAME-SERVER-TO-QUERY> -x <TARGET-IPv4/IPv6>
```

### Digging Recursive DNS
```
▶ dig @<NAME-SERVER-TO-QUERY> <FQDN> <RECORD_TYPE> +nostat +noquestion +noadditional +noauthority +noedns 
```

### Digging Authoritative DNS
```
▶ dig @<NAME-SERVER-TO-QUERY> <FQDN> <RECORD_TYPE> +nostat +noquestion +noadditional +noauthority +noedns +norecurse
```

### Digging For Query Statistics
```
▶ dig @<NAME-SERVER-TO-QUERY> <FQDN> NS +noquestion +noanswer +noadditional +noauthority +noedns 
```

### Digging for Zone Transfer
```
▶ dig @<NAME-SERVER-TO-QUERY> <FQDN> axfr 
```

### Digging the Internet Protocol (IPv4)
```
▶ dig <FQDN> AAAA -4 +noall +additional
```

### Digging the Internet Protocol (IPv6)
```
▶ dig <FQDN> AAAA -6 +noall +additional
```

### Digging Specific Ports
```
▶ dig @<NAME-SERVER-TO-QUERY> <FQDN> <RECORD-TYPE> -p <PORT> +noall +answer
```


