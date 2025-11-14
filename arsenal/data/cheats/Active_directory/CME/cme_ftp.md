# cme (FTP)

% cme, crackmapexec, Active Directory, nxc, netexec, ftp

## Enumerate FTP reachable hosts
#assessment/AD #attack_type/Enumeration #port/21 #protocol/ftp #access/Anonymous 

Enumerate network hosts that can be reached via FTP.

```bash
cme ftp <ip>
```

## FTP auth
#assessment/AD #attack_type/Authentication #port/21 #protocol/ftp #access/Local_user

Authenticate via a FTP account on the remote target.

```bash
cme ftp <ip> -u <user> -p <password> --local-auth
```

## FTP auth (anonymous)
#assessment/AD #attack_type/Authentication #port/21 #protocol/ftp #access/Anonymous

Authenticate via an anonymous FTP account on the remote target.

```bash
cme ftp <ip> -u <user> -p '' 
```

## Kerberos auth
#assessment/AD #attack_type/Authentication #port/21 #protocol/ftp #access/Domain_user 

Authenticate via Kerberos on the remote target.

```bash
cme ftp <ip> -u <user> -p <password> -k
```

## Kerberos TGT auth
#assessment/AD #attack_type/Authentication #port/21 #protocol/ftp #access/Domain_user 

Authenticate via a Kerberos TGT on the remote target.

Previously import ticket : 
    $ export KRB5CCNAME=ticket.ccache

```bash
cme ftp <ip> -u <user> -k --use-kcache
```

## Password spray (username=password)
#assessment/AD #attack_type/Bruteforce #port/21 #protocol/ftp #access/Anonymous 

Password spray to find domain accounts with weak passwords.

```bash
cme ftp <ip> -u <users.list> -p <users.list> --no-bruteforce --continue-on-success
```

## List files
#assessment/AD #attack_type/Other #port/21 #protocol/ftp #access/Local_user

List all files within a directory on the remote target.

```bash
cme ftp <ip> -u <user> -p <password> --ls <directory>
```

## Put file
#assessment/AD #attack_type/Other #port/21 #protocol/ftp #access/Local_user

Send a local file to the remote target.

```bash
cme ftp <ip> -u <user> -p <password> --put <local_file> <remote_path>
```

## Get file
#assessment/AD #attack_type/Other #port/21 #protocol/ftp #access/Local_user

Get a local file from the remote target.

```bash
cme ftp <ip> -u <user> -p <password> --get <remote_path> <local_file>
```

= dc-ip: $DC_IP
= user: $USER
= password: $PASSWORD
= domain: $DOMAIN
