### -A, to enable OS and version detection, script scanning, and traceroute; -T4 for faster execution
```
nmap <ip> -p- -T4 -A
```

### check for weak ssl
```
nmap -p443 --script=ssl-enum-ciphers <ip>
``` 
