# ffuf

% fuzz, ffuf

## Fuzz URL (Classic)
#assessment/Web #attack_type/Fuzz #access/Anonymous

Fuzz an url.

```bash
ffuf -c -w <wordlist> -u "<http/s>://<target>/FUZZ"
```

## Fuzz URL with added cookies
#assessment/Web #attack_type/Fuzz #access/Anonymous

```bash
ffuf -c -w <wordlist> -u "<http/s>://<target>/FUZZ" -b "<cookies>"
```

## Fuzz Host filter response size
#assessment/Web #attack_type/Fuzz #access/Anonymous

```bash
ffuf -c -w <wordlist> -u "<http/s>://<target>" -H "Host: FUZZ" -fs <response_size>
```

## Fuzz POST parameter and filter response code 401
#assessment/Web #attack_type/Fuzz #access/Anonymous

```bash
ffuf -w <wordlist> -u <url> -X POST -d "username=admin\&password=FUZZ" -fc 401
```

= http/s:https
