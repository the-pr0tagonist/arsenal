# cme (SSH)

% cme, crackmapexec, Active Directory, nxc, netexec, ssh

## Enumerate SSH reachable hosts
#assessment/AD #attack_type/Enumeration #port/22 #protocol/ssh #access/Anonymous 

Enumerate network hosts that can be reached via MSSQL.

```bash
cme ssh <ip>
```

## SSH auth
#assessment/AD #attack_type/Authentication #port/22 #protocol/ssh #access/Local_user 

Authenticate via a SSH account on the remote target.

```bash
cme ssh <ip> -u <user> -p <password> 
```

## SSH auth with private key
#assessment/AD #attack_type/Authentication #port/22 #protocol/ssh #access/Local_user 

Authenticate via a SSH account using a private key on the remote target. Treats the password parameter as the key's passphrase.

```bash
cme ssh <ip> -u <user> -p <password> --key-file <key_file>
```

## Kerberos auth
#assessment/AD #attack_type/Authentication #port/22 #protocol/ssh #access/Domain_user 

Authenticate via Kerberos on the remote target.

```bash
cme ssh <ip> -u <user> -p <password> -k
```

## Kerberos TGT auth
#assessment/AD #attack_type/Authentication #port/22 #protocol/ssh #access/Domain_user 

Authenticate via a Kerberos TGT on the remote target.

Previously import ticket : 
    $ export KRB5CCNAME=ticket.ccache

```bash
cme ssh <ip> -u <user> -k --use-kcache
```

## Password spray (username=password)
#assessment/AD #attack_type/Bruteforce #port/22 #protocol/ssh #access/Anonymous 

Password spray to find SSH accounts with weak passwords.

```bash
cme ssh <ip> -u <users.list> -p <users.list> --no-bruteforce --continue-on-success
```

## Check for sudo privileges
#assessment/AD #attack_type/Command_Execution #port/22 #protocol/ssh #access/Local_user

Check the sudo privileges of a given account.

```bash
cme ssh <ip> -u <user> -p <password> --sudo-check
```

## Execute remote commands (shell)
#assessment/AD #attack_type/Command_Execution #port/22 #protocol/ssh #access/Local_user 

Execute remote commands through a bash-type shell.

```bash
cme ssh <ip> -u <user> -p <password> -x <command>
```

## Put file
#assessment/AD #attack_type/Other #port/22 #protocol/ssh #access/Local_user

Send a local file to the remote target.

```bash
cme ssh <ip> -u <user> -p <password> --put-file <local_file> <remote_path>
```

## Get file
#assessment/AD #attack_type/Other #port/22 #protocol/ssh #access/Local_user

Get a local file from the remote target.

```bash
cme ssh <ip> -u <user> -p <password> --get-file <remote_path> <local_file>
```

= dc-ip: $DC_IP
= user: $USER
= password: $PASSWORD
= domain: $DOMAIN
