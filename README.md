# Metasploit-for-reconnaissance
# Metasploit
Metasploit for reconnaissance in pentesting

# AIM:

To get introduced to Metasploit Framework and to  perform reconnaissance  in pentesting .

## DESIGN STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:

Open terminal and try execute some kali linux commands

## PROGRAM:
Find out the ip address of the attackers system

## OUTPUT:
![image](https://github.com/Prasanth9025/Metasploit-for-reconnaissance/assets/118343686/68142247-95c9-4239-bef0-aa2d9452b265)
## Invoke msfconsole:
## OUTPUT:
![image](https://github.com/Prasanth9025/Metasploit-for-reconnaissance/assets/118343686/072d4232-2f3c-4826-abd8-2640a4d46156)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

## OUTPUT:
![image](https://github.com/Prasanth9025/Metasploit-for-reconnaissance/assets/118343686/ab944410-c851-4b16-98b0-46c17881bffe)

Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000

## OUTPUT:
![image](https://github.com/Prasanth9025/Metasploit-for-reconnaissance/assets/118343686/040ce2ff-2218-49bc-8431-af45a6a857da)

## Step4: use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24

## OUTPUT:
![image](https://github.com/Prasanth9025/Metasploit-for-reconnaissance/assets/118343686/2c49935a-82d0-4874-855f-6094d37771f6)
Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l

## OUTPUT:
![image](https://github.com/Prasanth9025/Metasploit-for-reconnaissance/assets/118343686/82ec2957-e232-4162-b6a9-54887871e7d1)
![image](https://github.com/Prasanth9025/Metasploit-for-reconnaissance/assets/118343686/3458a2af-908d-4243-98ee-71647309494b)

Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

![image](https://github.com/Prasanth9025/Metasploit-for-reconnaissance/assets/118343686/2d32b083-bd1d-49fa-9b5b-853d98e92696)
The info command provides information regarding a module or platform

## OUTPUT:
![image](https://github.com/Prasanth9025/Metasploit-for-reconnaissance/assets/118343686/ebe829ee-37e1-4f91-8696-636d18377373)
Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init ##MYSQL ENUMERATION Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>

![image](https://github.com/Prasanth9025/Metasploit-for-reconnaissance/assets/118343686/77a2377a-aafc-4c72-bb0b-6d497970ba64)

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql

![image](https://github.com/Prasanth9025/Metasploit-for-reconnaissance/assets/118343686/27d562d1-791e-414c-9a7c-d3d6c352cafd)

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version

![image](https://github.com/Prasanth9025/Metasploit-for-reconnaissance/assets/118343686/892f3151-f891-48e2-a628-3b1c7d12ec56)
Use the set rhosts command to set the parameter and run the module, as follows:
![image](https://github.com/Prasanth9025/Metasploit-for-reconnaissance/assets/118343686/4343c960-2b91-401a-b9bc-c4a0fb1edd4d)

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.
![image](https://github.com/Prasanth9025/Metasploit-for-reconnaissance/assets/118343686/ad50a7f2-fbcb-4633-bc83-a62541513065)

set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true

![image](https://github.com/Prasanth9025/Metasploit-for-reconnaissance/assets/118343686/545f3f5b-65c0-49f8-88db-34c9d0f606d8)

## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
