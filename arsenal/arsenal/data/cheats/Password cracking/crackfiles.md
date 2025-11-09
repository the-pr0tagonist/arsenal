# Crack files

% bruteforce, crack, files

#plateform/linux  #target/local  #cat/CRACKING/PASSWORD 

## ZIP - fcrackzip
```
fcrackzip -u -D -p <wordlist> <file>.zip
```

## 7z - 7za
```
cat <wordlist> | 7za t <file>.7z
```

## PDF - pdfcrack
```
pdfcrack <file>.pdf -w <wordlist>
```

## PDF decrypt - qpdf
```
qpdf --password=<PASSWORD> --decrypt <encrypted_pdf>.pdf <plaintext_pdf>.pdf
```

= wordlist: /usr/share/wordlists/rockyou.txt
