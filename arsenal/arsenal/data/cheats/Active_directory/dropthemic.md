# DropTheMic

% dropthemic, Active Directory

## Scan for DropTheMic
#assessment/AD #attack_type/Quickwin #port/445 #port/139 #protocol/smb #access/Domain_user

Check if the targeted host is vulnerable to DroptheMic (CVE-2019-1040) using Fox-IT's scanner.

⚠️ Here, DropTheMic has been aliased to Fox-IT's scanner. Otherwise, launch the command with python3 scan.py ...

```bash
DropTheMic -target-file <targets_file> "<domain>/<user>:<password>@<dc-ip>"
```

= ip: 192.168.1.0
= dc-ip: $DC_IP
= user: $USER
= password: $PASSWORD
= domain: $DOMAIN
