# hashcat

% password recovery, password cracking

#assessment/AD #attack_type/Bruteforce #access/None

## LM
#assessment/AD #attack_type/Bruteforce #access/None
Crack LM hashes.

```bash
hashcat -m 3000 --force -a 0 <hashes> <wordlist> 
```

## NTLM (NTDS.dit)
#assessment/AD #attack_type/Bruteforce #access/None
Crack NTLM hashes.

```bash
hashcat -m 1000 --force -a 0 <hashes> <wordlist> 
```

## NTLMv1
#assessment/AD #attack_type/Bruteforce #access/None
Crack NTLMv1 hashes.

```bash
hashcat -m 5500 --force -a 0 <hashes> <wordlist> 
```

## NTLMv2
#assessment/AD #attack_type/Bruteforce #access/None
Crack NTLMv2 hashes.

```bash
hashcat -m 5600 --force -a 0 <hashes> <wordlist> 
```

## NTLMv2 - Combination attack (ex:passpass,testtest,passtest,etc)
#assessment/AD #attack_type/Bruteforce #access/None


```bash
hashcat -m 5600 --force -a 1 <hashes> <custom_wordlist> <custom_wordlist>
```

## Kerberos ticket (after kerberoasting) 
#assessment/AD #attack_type/Bruteforce #access/None
Crack Kerberos 5 TGS-REP etype 23 hashes.

```bash
hashcat -m 13100 user_SPN.ticket <wordlist>
```

## Basic MD5 (joomla/wordpress) - wordlist
#assessment/Web #attack_type/Bruteforce #access/None
Crack basic MD5 hashes.

```bash
hashcat -a 0 -m 400 <hashes> <wordlist>
```

## Basic MD5 (joomla/wordpress) - wordlist with rules
#assessment/Web #attack_type/Bruteforce #access/None
Crack basic MD5 hashes using rulesets.

```bash
hashcat -a 0 -m 400 <hashes> <wordlist> -r /usr/share/doc/hashcat/rules/best64.rule 
```



## Generate wordlist using rules
#assessment/All #attack_type/Bruteforce #access/None
Generate a wordlist using rulesets.

```bash
cat keywords.txt | hashcat -r <rule_file> --stdout > ./<custom_wordlist>
```

= wordlist: `fzf-wordlists`
= rule_file: /usr/share/doc/hashcat/rules/best64.rule 
= custom_wordlist:
