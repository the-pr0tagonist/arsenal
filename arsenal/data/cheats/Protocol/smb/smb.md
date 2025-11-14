# smbclient.py
% smb, smbclient

## nbtscan - scan network looking for hosts
#plateform/linux #target/remote #port/445 #protocol/smb #cat/RECON 
```
nbtscan -r <ip_range>
```

## Connect to a SMB server
#assessment/AD #attack_type/Enumeration #port/445 #port/139 #protocol/smb #access/Domain_user

Connect to a SMB remote server. To access a share : # use SHARE_NAME$.

```
smbclient.py "<domain>"/"<user>":"<password>"@"<target>"
```

## smbclient with username and password
#plateform/linux #target/remote #port/445 #protocol/smb #cat/ATTACK/CONNECT  
```
smbclient //<hostname>/<share> -U "<domain>"/"<user>"%""<password>"
```

## smbclient sessions without password
#plateform/linux #target/remote #port/445 #protocol/smb #cat/ATTACK/CONNECT  
```
smbclient \\\\<ip>\\<share> -U "<user>%"
```

## smbclient null session
#plateform/linux #target/remote #port/445 #protocol/smb #cat/ATTACK/CONNECT  
```
smbclient \\\\<ip>\\<share> -U "%"
```

## smb - find not signed  smb
#plateform/linux #target/remote #port/445 #protocol/smb #cat/RECON 
```
nmap -Pn -sS -T4 --open --script smb-security-mode -p445 <ip>
```

## smb mount folder
#plateform/linux #target/remote #port/445 #protocol/smb #cat/ATTACK/CONNECT  
```
mount -t cifs //<ip>/C\$ /tmp/mnttarget/ -o username=<user> -o domain=<domain>
```
