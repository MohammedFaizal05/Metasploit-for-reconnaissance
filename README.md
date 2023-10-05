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

![image](https://github.com/MohammedFaizal05/Metasploit-for-reconnaissance/assets/120553195/ac8aa168-27e0-4b3c-8296-a5345a9c48a3)

## Invoke msfconsole:
## OUTPUT:
![image](https://github.com/MohammedFaizal05/Metasploit-for-reconnaissance/assets/120553195/8a07b361-ec92-45c7-97bc-e518b4701c03)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.
## OUTPUT:
![image](https://github.com/MohammedFaizal05/Metasploit-for-reconnaissance/assets/120553195/7d7b42d4-028e-4259-ab77-61ad89bc5f80)

Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000

## OUTPUT:

![image](https://github.com/MohammedFaizal05/Metasploit-for-reconnaissance/assets/120553195/0c207914-611e-4036-a71f-a7ff6a8fb0f7)

 ## Step4: use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24

## OUTPUT:
![image](https://github.com/MohammedFaizal05/Metasploit-for-reconnaissance/assets/120553195/a63a5ab9-3a6b-46d7-b4e4-4ea30d9a0b5e)

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l

## OUTPUT:

![image](https://github.com/MohammedFaizal05/Metasploit-for-reconnaissance/assets/120553195/f1bd1e99-4192-41fe-b4d6-f3a519f8212f)

![image](https://github.com/MohammedFaizal05/Metasploit-for-reconnaissance/assets/120553195/484d4671-215f-4b3b-b642-8e6a642f323b)

Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

![image](https://github.com/MohammedFaizal05/Metasploit-for-reconnaissance/assets/120553195/ce0c89ee-0d52-44bd-bf49-70704b815bc5)

The info command provides information regarding a module or platform
## OUTPUT:

![image](https://github.com/MohammedFaizal05/Metasploit-for-reconnaissance/assets/120553195/ec3608f0-fb06-4f7e-ba15-38ff90114a2d)

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init ##MYSQL ENUMERATION Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>

![image](https://github.com/MohammedFaizal05/Metasploit-for-reconnaissance/assets/120553195/f60ee985-91f9-4db7-abcc-16d31209d209)

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql

![image](https://github.com/MohammedFaizal05/Metasploit-for-reconnaissance/assets/120553195/f04cff32-402a-4c9c-9cf2-e7f2bb4a27df)

use the auxiliary/scanner/mysql/mysql_version module by typing the module name or associated number to scan MySQL version details. use 11 Or: use auxiliary/scanner/mysql/mysql_version

![image](https://github.com/MohammedFaizal05/Metasploit-for-reconnaissance/assets/120553195/4872b6af-35ab-4ec1-853f-50441393769e)

Use the set rhosts command to set the parameter and run the module, as follows:

![image](https://github.com/MohammedFaizal05/Metasploit-for-reconnaissance/assets/120553195/7a0b7609-5eda-4469-a471-a9f2aec8342d)

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.

![image](https://github.com/MohammedFaizal05/Metasploit-for-reconnaissance/assets/120553195/75f82cbb-f436-408c-b374-5c4c1575bdf0)

set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true

![image](https://github.com/MohammedFaizal05/Metasploit-for-reconnaissance/assets/120553195/9c947d6e-3be6-4d96-ad3f-21eaae8a3416)


## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
