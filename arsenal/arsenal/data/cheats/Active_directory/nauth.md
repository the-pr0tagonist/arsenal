# NauthRPC

% nauth, Active Directory, users

## Enumerate valid domain user
#assessment/AD #attack_type/Enumeration #port/445 #port/139 #protocol/smb #access/Anonymous

Enumerate valid domain users from a list of usernames.

```bash
nauth.py -t <ip> -u <users.list>
```
