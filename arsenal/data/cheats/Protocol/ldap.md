# LDAP

%ldap

## Scan for LDAP
#assessment/AD #attack_type/Enumeration #port/389 #port/639 #protocol/ldap #access/Anonymous 

```bash
nmap -n -sV -sC --script "ldap* and not brute" -p 389 <ip> -vv
```

# Ldapsearch

## ldapsearch base
#cat/ATTACK/CONNECT 

```bash
ldapsearch -x -H ldap://<dc_fqdn> -s base
```

## ldapsearch SPN
#cat/ATTACK/CONNECT 

```bash
ldapsearch -Y GSSAPI -H ldap://<dc_fqdn> -D "<user>" -W -b "dc=<domain>,dc=<path>" "servicePrincipalName=*" servicePrincipalName
```
	
## ldapsearch with base dn
#cat/ATTACK/CONNECT 

```bash
ldapsearch -x -H ldap://<dc_fqdn> -b <basedn>
```

## ldapsearch base with authentication
#cat/ATTACK/CONNECT 
```bash
ldapsearch -x -H ldap://<dc_fqdn> -D <domain>\\<user> -w '<password>' -b 'DC=<domain>,DC=<path>'
```

## ldapsearch - list all users
#cat/ATTACK/CONNECT 
```bash
ldapsearch -x -H ldap://<dc_fqdn> -D <domain>\\<user> -w '<password>' -b 'DC=<domain>,DC=<path>' '(&(objectCategory=person)(objectClass=user))'
```

## ldapsearch - list all users protected by adminCount
#cat/ATTACK/CONNECT 
```bash
ldapsearch -x -H ldap://<dc_fqdn> -D <domain>\\<user> -w '<password>' -b 'DC=<domain>,DC=<path>' '(&(objectCategory=user)(adminCount=1))'
```

## ldapsearch - list all users with password, pass, identifiant or pwd in their description
#cat/ATTACK/CONNECT 
```bash
ldapsearch -x -H ldap://<dc_fqdn> -D <domain>\\<user> -w '<password>' -b 'DC=<domain>,DC=<path>' '(&(objectCategory=user)(|(description=*pass*)(description=*password*)(description=*identifiant*)(description=*pwd*)))'
```

## ldapsearch - list all computer with laps enabled and corresponding laps password if able
#cat/ATTACK/CONNECT 
```
ldapsearch -x -H ldap://<dc_fqdn> -D <domain>\\<user> -w '<password>' -b 'DC=<domain>,DC=<path>' '(ms-Mcs-AdmPwdExpirationtime=*)' ms-Mcs-AdmPwd
```

## ldapdomaindump
#cat/ATTACK/CONNECT 
```bash
ldapdomaindump --no-json --no-grep --authtype SIMPLE -o ldap_dump -r <ip> -u <domain>\\<user> -p '<password>'
```

## ldapsearch-ad - list all password policies including FGPP
#cat/ATTACK/CONNECT 
```bash
ldapsearch-ad.py --server '<dc_fqdn>' -d <domain> -u <user> -p <password> --type pass-pols
```

## ldapsearch-ad - get the FGPP applied to a group
#cat/ATTACK/CONNECT 
```bash
ldapsearch-ad.py --server '<dc_fqdn>' -d <domain> -u <user> -p <password> -t search -s '(samaccountname=<groupname>)' cn msDS-PSOApplied 
```

## ldapsearch-ad - get the FGPP applied to a user
#cat/ATTACK/CONNECT 
```bash
ldapsearch-ad.py --server '<dc_fqdn>' -d <domain> -u <user> -p <password> --type show-user -s '(samaccountname=<user>)'
```

# LdapRelayScan.py

## Check LDAPS / Signing / Channel Binding

#assessment/AD #attack_type/Enumeration #port/389 #port/639 #protocol/ldap #access/Anonymous 

```bash
LdapRelayScan.py -method BOTH -dc-ip <dc-ip> -u <user> -p <password>
```

= ip: 192.168.1.0/24
= dc-ip: $DC_IP
= user: $USER
= password: $PASSWORD
= domain: $DOMAIN

