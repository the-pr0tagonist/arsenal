# addcomputer.py

% addcomputer


## Add a computer account to the domain
#assessment/AD #attack_type/Other #port/139 #port/445 #protocol/smb #access/Domain_user

Add a computer account to the domain.

⚠️ Requirement : Attribute ms-DS-MachineAccountQuota must at least be 1 for the current user (or all users)

```bash
addcomputer.py -computer-name '<computer_name>$' -computer-pass '<computer_password>' -dc-host "<dc-hostname>" -domain-netbios "<domain>" "<domain>"/"<user>":"<password>"
```

## Modify a computer account password
#assessment/AD #attack_type/Other #port/139 #port/445 #protocol/smb #access/Domain_user

Modify a computer account password on the domain.

⚠️ Requirement : User must at least have the GenericWrite permission over the computer oject.

```bash
addcomputer.py -computer-name '<computer_name>$' -computer-pass '<computer_password>' -dc-host "<dc-hostname>" -no-add "<domain>"/"<user>":"<password>"
```

## Delete a computer account from the domain
#assessment/AD #attack_type/Other #port/139 #port/445 #protocol/smb #access/Domain_user

Delete a computer account from the domain.

⚠️ Requirement : User must at least have the Delete permission over the computer oject.

```bash
addcomputer.py -computer-name '<computer_name>$' -dc-host "<dc-hostname>" -delete "<domain>"/"<user>":"<password>"
```

= dc-hostname: $DC
= user: $USER
= password: $PASSWORD
= domain: $DOMAIN
