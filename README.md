# Docker

```
sudo docker build -t mail-server .
sudo docker run -ti -p 127.0.0.1:25:25 -p 127.0.0.1:143:143 -p 127.0.0.1:993:993 mail-server
```

# Attack

## stmp

```
hydra -l 'debug@localdomain.test' -p 'debug'  -V -s 25 127.0.0.1 smtp
```

## imap

```
ncrack imap://172.17.0.2:993 -m imap --user 'debug@localdomain.test' --pass 'debug' -g ssl
hydra -l 'debug@localdomain.test' -p 'debug' 127.0.0.1 imap -S
```
