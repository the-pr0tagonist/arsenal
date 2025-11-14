# PTSD.py

% ptsd, pdf, secretsdump, sam, hives


## Parse SAM/SECURITY/LSA PDF export
#assessment/AD #attack_type/Dump #access/Admin

Parse PDF exports of SAM, SECURITY registries to .reg format files. Parse LSA to calculate the bootkey.
Then .reg files can be imported in a Windows VM and extracted in a .hive format for SecretsDump.

```bash
ptsd.py --sam <sam> --security <security> --lsa <lsa>
```

## Import .reg files
#assessment/AD #attack_type/Dump #access/Admin

Import .reg file in the Windows registry.

```bash
reg import <file>.reg
```

## Export SAM/SECURITY hives
#assessment/AD #attack_type/Dump #access/Admin

Export SAM and SECURITY registries to .hive formatted files.

```bash
reg save HKEY_CURRENT_USER\HELLO\SAM SAM.hive
reg save HKEY_CURRENT_USER\HELLO\SECURITY SECURITY.hive
```

= sam: SAM.pdf
= security: SECURITY.pdf
= lsa: LSA.pdf
