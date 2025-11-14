# Get-GPPPassword

% get-gpppassword, sysvol, Active Directory

## Find GPP passwords in SYSVOL
#assessment/AD #attack_type/Quickwin #port/445 #port/139 #protocol/smb #access/Domain_user

Retrieves plaintext passwords and other information for accounts pushed through Group Policy Preferences.

```bash
Get-GPPPassword.py <domain>/<user>:<password>@<dc-ip>
```

= ip: 192.168.1.0/24
= dc-ip: $DC_IP
= user: $USER
= password: $PASSWORD
= domain: $DOMAIN


