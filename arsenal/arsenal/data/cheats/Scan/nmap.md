# nmap
% nmap, scan, ports

#plateform/linux #target/remote #cat/RECON #tag/scan

## nmap - hosts alive
```
nmap -sn <ip_range>
```

## nmap - classic scan
```
nmap -sC -sV <ip>
```

## nmap - read targets from a file
```
nmap -iL <targets_file>
```

## nmap - classic scan + save
```
nmap -sC -sV -oA <output_file> <ip>
```

## nmap - quick scan top ports 100
```
nmap --top-ports 100 --open -sV <ip>
```

## nmap - big top ports 5000
```
nmap --top-ports 5000 --open -sV <ip>
```

## nmap - full port
```
nmap -p- -sV <ip>
```

## nmap - host with a given port
```
nmap <ip> -p<port_list> --open
```

## nmap - FULL
```
IP=<ip>;
ports=$(nmap -p- --min-rate=1000 -n -T4 $IP | grep ^[0-9] | cut -d '/' -f 1 | tr '\n' ',' | sed s/,$//);
nmap -Pn -sC -sV -p$ports $IP -oN scan.txt --reason --script=vuln
```

## nmap - udp scan
```
nmap -sU <ip>
```

## nmap - low rate Classic
```
nmap --max-rate 100 -sC -sV <ip>
```

## massscan - full port
```
masscan -p 1-65535 <ip> -e <dev> --rate=1000
```

## nmap - SMB signing disabled
```
nmap -Pn -sS -T4 --open --script smb-security-mode -p445 <ip>
```

## nmap behind proxy - tcp connect (-sT) - no dns (-n)
```
proxychains nmap -n -sT -sV -Pn --open -oA <output_file> -iL <targets_file>
```

## Scan for MS17-010 (EternalBlue)
#assessment/AD #attack_type/Quickwin #port/445 #port/139 #protocol/smb #access/Anonymous 

Scan remote targets for MS17-010 (Eternalblue).

```bash
nmap -p445 --script smb-vuln-ms17-010 -iL <targets_file> -vv -oN <output_file>
```

## Scan for VEEAM servers
#assessment/AD #attack_type/Quickwin #port/9401 #protocol/veeam #access/Anonymous 

Scan for VEEAM backup servers.

```bash
nmap -sV -sC -p9401 --open <ip> -vv
```
