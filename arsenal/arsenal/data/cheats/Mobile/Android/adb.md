# ADB 

% adb, android, apk 

## Enable access as root
#assessment/Mobile #attack_type/Other #access/Anonymous

Enable root access to an Android device's system file.

```bash
adb root
```

## Shell access
#assessment/Mobile #attack_type/Other #access/Anonymous

Access to an Android device's system file through a shell.

```bash
adb shell
```

## Install application
#assessment/Mobile #attack_type/Other #access/Anonymous

Install an application on an Android device.

```bash
adb install <application>.apk 
```

## Install & launch Frida server
#assessment/Mobile #attack_type/Other #access/Anonymous

Install and launch a Frida server on an Android device.

```bash
adb push frida-server /data/local/tmp/frida-server && adb shell 'chmod 777 frida-server' && adb shell '/data/local/tmp/frida-server &'
```
