# John the Ripper

% john, password cracking

## LM
#assessment/AD #attack_type/Bruteforce #access/None

```bash
john --wordlist=<wordlist> --format=lm hash.txt
```

## NTLM
#assessment/AD #attack_type/Bruteforce #access/None

```bash
john --wordlist=<wordlist> --format=nt hash.txt
```

## NTLMv1
#assessment/AD #attack_type/Bruteforce #access/None

```bash
john --wordlist=<wordlist> --format=netntlm hash.txt
```

## NTLMv2
#assessment/AD #attack_type/Bruteforce #access/None

```bash
john --wordlist=<wordlist> --format=netntlmv2 hash.txt
```

## Crack a 7z/Zip/SSH/KDBX password
#assessment/All #attack_type/Bruteforce #access/None

Crack the password of encrypted objects (7z & Zip archive, SSH private key, Office document, KeePass2 database).

```bash
john --wordlist <wordlist> <tool>.hashes
```

# Unshadow

## Convert Shadow passwords
#assessment/Linux #attack_type/Bruteforce #access/None

Convert /etc/passwd and /etc/shadow to form pairs breakable using John the Ripper.

```bash
unshadow passwd.txt shadow.txt > unshadowed.hash
```

# SSH2John

## Convert SSH key 
#assessment/All #attack_type/Bruteforce #access/None

Convert a SSH private key into a hash breakable using John the Ripper.

```bash
ssh2john.py <private_key> > ssh.hash
```

# 7z2John

## Convert encrypted 7z
#assessment/All #attack_type/Bruteforce #access/None

Convert an encrypted 7z archive into a hash breakable using John the Ripper.

```bash
7z2john.pl <filename>.7z > 7z.hash
```

# Zip2John

## Convert encrypted Zip
#assessment/All #attack_type/Bruteforce #access/None

Convert an encrypted zip archive into a hash breakable using John the Ripper.

```bash
zip2john <filename>.zip > zip.hash
```

# Office2John
#assessment/All #attack_type/Bruteforce #access/None

## Convert encrypted XLS/PPT/DOC

Convert an encrypted office document (XLS / PPT / DOC) into a hash breakable using John the Ripper.

```bash
office2john.py <filename>.xls > office.hash
```

# KeePass2John
#assessment/All #attack_type/Bruteforce #access/None

## Convert KeePass2 database
#assessment/AD #attack_type/Bruteforce #access/None

Convert a KDBX database into a hash breakable using John the Ripper.

```bash
keepass2john <filename>.kdbx > kbdx.hashes
```



= private_key: id_rsa
