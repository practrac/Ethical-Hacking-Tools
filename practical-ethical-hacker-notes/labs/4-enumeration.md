# 4 - Enumeration

## Mod 04 - Enumeration

* ping www.moviescope.com –f –l 1500 -> Frame size
* tracert www.moviescope.com -> Determining hop count

**SNMP Enumeration (161) :**

* nmap –sU –p 161 10.10.10.12
* nmap -sU -p 161 --script=snmp-brute 10.10.10.12
* msfconsole
* use auxiliary/scanner/snmp/snmp\_login
* set RHOSTS and exploit
* use auxiliary/scanner/snmp/snmp\_enum
* set RHOSTS and exploit

**NetBIOS Enumeration (139) :**&#x20;

* nbtstat –A 10.10.10.16
* net use
* net use \10.10.10.16\e ““\user:””
* net use \10.10.10.16\e ““/user:””
* NetBIOS Enumerator

**Enum4Linux Wins Enumeration :**

* enum4linux -u martin -p apple -U 10.10.10.12 -> Users Enumeration
* enum4linux -u martin -p apple -o 10.10.10.12 -> OS Enumeration
* enum4linux -u martin -p apple -P 10.10.10.12 -> Password Policy Information
* enum4linux -u martin -p apple -G 10.10.10.12 -> Groups Information
* enum4linux -u martin -p apple -S 10.10.10.12 -> Share Policy Information (SMB Shares Enumeration

**Active Directory LDAP Enumeration** : ADExplorer

**Enumeration using Metasploit :**

* msfdb init
* service postgresql start
* msfconsole
* msf > db\_status
* nmap -Pn -sS -A -oX Test 10.10.10.0/24
* db\_import Test
* hosts -> To show all available hosts in the subnet
* db\_nmap -sS -A 10.10.10.16 -> To extract services of particular machine
* services -> to get all available services in a subnet

**SMB Version Enumeration using MSF**

* use scanner/smb/smb\_version
* set RHOSTS 10.10.10.8-16
* set THREADS 100
* run
* hosts -> now exact os\_flavor information has been updated



### **Lab2 - Task1: Enumerate SNMP using snmp-check**

* nmap -sU -p 161 **\<Target IP>**
* **snmp-check \<Target IP>**

#### **Addition**

* nbtstat -a **\<Target IP>** (Windows)
* nbtstat -c