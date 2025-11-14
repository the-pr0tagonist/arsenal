# cme (NFS)

% cme, crackmapexec, Active Directory, nxc, netexec, nfs

## Enumerate NFS reachable hosts
#assessment/AD #attack_type/Enumeration #port/111 #protocol/nfs #access/Anonymous 

Enumerate network hosts that can be reached via NFS.

```bash
cme nfs <ip>
```

## Enumerate shares
#assessment/AD #attack_type/Enumeration #port/111 #protocol/nfs #access/Anonymous 

Enumerate NFS shares.

```bash
cme nfs <ip> --shares
```

## Enumerate files on shares
#assessment/AD #attack_type/Enumeration #port/111 #protocol/nfs #access/Anonymous 

Enumerate all files and folders recursively on NFS shares.

```bash
cme nfs <ip> --enum-shares
```

### List files
#assessment/AD #attack_type/Other #port/111 #protocol/nfs #access/Anonymous

List all files within a directory on the remote target.

```bash
cme nfs <ip> --share <share> --ls <directory>
```

### Put file
#assessment/AD #attack_type/Other #port/111 #protocol/nfs #access/Anonymous

Send a local file to the remote target.

```bash
cme nfs <ip> --share <share> --put-file <local_file> <remote_path>
```

## Get file
#assessment/AD #attack_type/Other #port/111 #protocol/nfs #access/Anonymous

Get a local file from the remote target.

```bash
cme nfs <ip> --share <share> --get-file <remote_path> <local_file>
```
