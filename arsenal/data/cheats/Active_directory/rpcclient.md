# rpcclient

% rpcclient, rpc, windows

## rpcclient - enumdomusers
#assessment/AD #target/remote #cat/RECON 
```
rpcclient <ip> -U "<user>%<password>" -c "enumdomusers;quit"
```

## rpcclient - srvinfo
#assessment/AD #target/remote #cat/RECON 
```
rpcclient <ip> -U "<user>%<password>" -c "srvinfo;quit"
```

## rpcclient - get user sid
#assessment/AD #target/remote #cat/RECON 
```
rpcclient <ip> -c "lookupnales <name>; wmic useraccount get name,sid; quit"
```

## rpcclient - querydominfo
#assessment/AD #target/remote #cat/RECON 
```
rpcclient <ip> -U "<user>%<password>" -c "querydominfo;quit"
```

## rpcclient - getdompwinfo  (password policy)
#assessment/AD #target/remote #cat/RECON 
```
rpcclient <ip> -U "<user>%<password>" -c "getdompwinfo;quit"
```

## rpcclient - netshareenum  (password policy)
#assessment/AD #target/remote #cat/RECON 
```
rpcclient <ip> -U "<user>%<password>" -c "netshareenum;quit"
```

## Trying all username as password from list of users
#assessment/AD #target/remote #cat/ATTACK/BRUTEFORCE-SPRAY  
```
for u in `cat <file>`; do echo -n "user: $u " && rpcclient -U "$u%$u" -c "getusername;quit" <ip>; done
```

## rpcclient - enum (Enum commands list)
#assessment/AD #target/remote #cat/RECON
```
rpcclient <ip> -U "<user>%<pass>" -c "enum;quit"
```

## rpcclient - enumdomains (Current domain)
#assessment/AD #target/remote #cat/RECON
```
rpcclient <ip> -U "<user>%<pass>" -c "enumdomains;quit"
```

## rpcclient - enumdomgroups (Enum Domain groups)
#assessment/AD #target/remote #cat/RECON
```
rpcclient <ip> -U "<user>%<pass>" -c "enumdomgroups;quit"
```

## rpcclient - querygroup (Enum Group Information)
#assessment/AD #target/remote #cat/RECON
```
rpcclient <ip> -U "<user>%<pass>" -c "querygroup <RID>;quit"
```

## rpcclient - querygroupmem (Enum Group Membership)
#assessment/AD #target/remote #cat/RECON
```
rpcclient <ip> -U "<user>%<pass>" -c "querygroupmem <RID>;quit"
```

## rpcclient - queryuser (Enumerate specific User/ computer information by RID)
#assessment/AD #target/remote #cat/RECON
```
rpcclient <ip> -U "<user>%<pass>" -c "queryuser <RID>;quit"
```

## rpcclient - getusrdompwinfo (User password policies)
#assessment/AD #target/remote #cat/RECON
```
rpcclient <ip> -U "<user>%<pass>" -c "getusrdompwinfo <RID>;quit"
```

## rpcclient - lsaenumsid (Local Users LSA Enum SID)
#assessment/AD #target/remote #cat/RECON
```
rpcclient <ip> -U "<user>%<pass>" -c "lsaenumsid;quit"
```

## rpcclient - lookupsid (Local Users Lookup SID)
#assessment/AD #target/remote #cat/RECON
```
rpcclient <ip> -U "<user>%<pass>" -c "lookupsid <SID>;quit"
```

## rpcclient - setuserinfo2 (Reset AD user password)
#assessment/AD #target/remote #cat/EXPLOIT
```
rpcclient <ip> -U "<user>%<pass>" -c "setuserinfo2 <LOGIN> 23 '<NEWPASSWORD>';quit"
```

