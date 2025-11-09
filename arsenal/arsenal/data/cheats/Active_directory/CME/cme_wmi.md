# cme (WMI)

% cme, crackmapexec, Active Directory, nxc, netexec, wmi

## Enumerate WMI reachable hosts
#assessment/AD #attack_type/Enumeration #port/135 #protocol/wmi #access/Anonymous 

Enumerate network hosts that can be reached via WMI.

```bash
cme wmi <ip>
```

## Enumerate Spooler
#assessment/AD #attack_type/Enumeration #port/135 #protocol/wmi #access/Domain_user 

Enumerate if the Spooler service is running on the remote target.

```bash
cme wmi <ip> -u <user> -p <password> -M spooler
```

## Enumerate BitLocker
#assessment/AD #attack_type/Enumeration #port/135 #protocol/wmi #access/Admin 

Enumerate BitLocker status on the remote target.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme wmi <ip> -u <user> -p <password> -M bitlocker
```

## Enumerate DNS entries
#assessment/AD #attack_type/Enumeration #port/135 #protocol/wmi #access/Admin 

Enumerate ADIDNS entries.

⚠️ Requirement : Domain admin privileges.

```bash
cme wmi <ip> -u <user> -p <password> -M enum_dns
```

## Domain auth
#assessment/AD #attack_type/Authentication #port/135 #protocol/wmi #access/Domain_user 

Authenticate via a domain account on the remote target.

```bash
cme wmi <ip> -u <user> -p <password> -d <domain>
```

## Domain auth with hash
#assessment/AD #attack_type/Authentication #port/135 #protocol/wmi #access/Domain_user 

```bash
cme wmi <ip> -u <user> -H <hash> -d <domain>
```

## Local auth
#assessment/AD #attack_type/Authentication #port/135 #protocol/wmi #access/Local_user

Authenticate via a local account on the remote target.

```bash
cme wmi <ip> -u <user> -p <password> --local-auth
```

## Local auth with hash
#assessment/AD #attack_type/Authentication #port/135 #protocol/wmi #access/Local_user

Authenticate via a local account using the hash on the remote target.

```bash
cme wmi <ip> -u <user> -H <hash> --local-auth
```

## Kerberos auth
#assessment/AD #attack_type/Authentication #port/135 #protocol/wmi #access/Domain_user 

Authenticate via Kerberos on the remote target.

```bash
cme wmi <ip> -u <user> -p <password> -k
```

## Kerberos TGT auth
#assessment/AD #attack_type/Authentication #port/135 #protocol/wmi #access/Domain_user 

Authenticate via a Kerberos TGT on the remote target.

Previously import ticket : 
    $ export KRB5CCNAME=ticket.ccache

```bash
cme wmi <ip> -u <user> -k --use-kcache
```

## Password spray (username=password)
#assessment/AD #attack_type/Bruteforce #port/135 #protocol/wmi #access/Anonymous 

Password spray to find accounts with weak passwords.

```bash
cme wmi <ip> -u <users.list> -p <users.list> --no-bruteforce --continue-on-success
```

## ZeroLogon
#assessment/AD #attack_type/Quickwin #port/135 #protocol/wmi #access/Anonymous 

Check if the Domain Controller is vulnerable to ZeroLogon.

```bash
cme wmi <dc-ip> -M zerologon
```

## Dump NTDS (raw)
#assessment/AD #attack_type/Authentication #port/135 #protocol/wmi #access/Domain_Admin

Dump the NTDS.dit, SAM and SYSTEM files by accessing the raw hard drive.

⚠️ Requirement : Domain Admin ou Local admin privileges on the Domain Controller

```bash
cme wmi <dc-ip> -u <user> -p <password> -M ntds-dump-raw
```

## Execute remote commands (CMD)
#assessment/AD #attack_type/Command_Execution #port/135 #protocol/wmi #access/Domain_user 

Execute remote commands through Windows CMD.

```bash
cme wmi <ip> -u <user> -p <password> -x <command>
```

## Execute remote commands (PowerShell)
#assessment/AD #attack_type/Command_Execution #port/135 #protocol/wmi #access/Domain_user 

Execute remote commands through Windows PowerShell.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme wmi <ip> -u <user> -p <password> -X <command>
```

## Execute WMI query
#assessment/AD #attack_type/Command_Execution #port/135 #protocol/wmi #access/Domain_user 

Execute remote WMI queries.

```bash
cme wmi <ip> -u <user> -p <password> --wmi <query>
```

## Enable/disable RDP
#assessment/AD #attack_type/Other #port/135 #protocol/wmi #access/Domain_user 

ACTION values :
    - enable (default)
    - enable-ram
    - disable
    - disable-ram

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme wmi <ip> -u <user> -p <password> -M rdp -o ACTION=<action>
```

= dc-ip: $DC_IP
= user: $USER
= password: $PASSWORD
= domain: $DOMAIN
