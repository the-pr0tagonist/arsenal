# FindUncommonShare.py

% share, finduncommonshare

## List shares
#assessment/AD #attack_type/Enumeration #port/445 #port/139 #protocol/smb #access/Domain_user

List all shares on a remote host.

```bash
FindUncommonShares.py -d "<domain>" -u "<user>" -p "<password>" --dc-ip "<dc-ip>"
```
= user: $USER
= password: $PASSWORD
= domain: $DOMAIN
= dc-ip: $DC_IP
