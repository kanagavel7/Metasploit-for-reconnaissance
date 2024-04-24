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

## EXECUTION STEPS AND ITS OUTPUT:

Find out the ip address of the attackers system

## OUTPUT:

![Screenshot 2024-04-24 081408](https://github.com/kanagavel7/Metasploit-for-reconnaissance/assets/162578954/6b5ecd74-b0ac-4563-8872-3df150753bf8)

Invoke msfconsole:

## OUTPUT:

![Screenshot 2024-04-24 081514](https://github.com/kanagavel7/Metasploit-for-reconnaissance/assets/162578954/b1f3a87b-c232-414a-af85-53097b44e4fe)

Type help or a question mark "?" to see the list of all available commands you can use inside msfconsole.

## OUTPUT:

![Screenshot 2024-04-24 081617](https://github.com/kanagavel7/Metasploit-for-reconnaissance/assets/162578954/79a9aa6f-fb2f-4d54-a2fd-c49bcc1a27e0)

Port Scanning: Following command is executed for scanning the systems on our local area network with a TCP scan (-sT) looking for open ports between 1 and 1000 (-p1-1000). msf > nmap -sT 192.168.1810/24 -p1-1000

## OUTPUT:

![Screenshot 2024-04-24 081704](https://github.com/kanagavel7/Metasploit-for-reconnaissance/assets/162578954/2544c002-4115-4fbd-972b-7d4474b557bc)

use the db-nmap command to scan and save the results into Metasploit's postgresql attached database. In that way, you can use those results in the exploitation stage later.

scan the targets with the command db_nmap as follows. msf > db_nmap 192.168.181.0/24

## OUTPUT:

![Screenshot 2024-04-24 081750](https://github.com/kanagavel7/Metasploit-for-reconnaissance/assets/162578954/66ae3ba4-105d-4220-a995-6c89ba7cfe1f)

Metasploit has a multitude of scanning modules built in. If we open another terminal, we can navigate to Metasploit's auxiliary modules and list all the scanner modules. cd /usr/share /metasploit-framework/modules/auxiliary kali > ls -l

## OUTPUT:

![Screenshot 2024-04-24 081852](https://github.com/kanagavel7/Metasploit-for-reconnaissance/assets/162578954/3f06bcbb-9422-4fdd-932d-6f79f0ad8e14)

Search is a powerful command in Metasploit that you can use to find what you want to locate. msf >search name:Microsoft type:exploit

## OUTPUT:

![Screenshot 2024-04-24 081946](https://github.com/kanagavel7/Metasploit-for-reconnaissance/assets/162578954/cfb0765e-a8d5-4161-9336-114abe4e969a)

The info command provides information regarding a module or platform,

## OUTPUT:

![Screenshot 2024-04-24 082035](https://github.com/kanagavel7/Metasploit-for-reconnaissance/assets/162578954/adcbf59d-6671-49f0-aa4d-c6f4fe58a15c)

Before beginning, set up the Metasploit database by starting the PostgreSQL server and initialize msfconsole database as follows: systemctl start postgresql msfdb init ##MYSQL ENUMERATION Find the IP address of the Metasploitable machine first. Then, use the db_nmap command in msfconsole with Nmap flags to scan the MySQL database at 3306 port. db_nmap -sV -sC -p 3306 <metasploitable_ip_address>

## OUTPUT:

![Screenshot 2024-04-24 082117](https://github.com/kanagavel7/Metasploit-for-reconnaissance/assets/162578954/6d69d557-e116-4949-a488-315a5b18517e)

Use the search option to look for an auxiliary module to scan and enumerate the MySQL database. search type:auxiliary mysql

## OUTPUT:

![Screenshot 2024-04-24 082217](https://github.com/kanagavel7/Metasploit-for-reconnaissance/assets/162578954/d74131ba-5d20-4844-adfc-62a3b30880eb)

use 11 Or: use auxiliary/scanner/mysql/mysql_version

## OUTPUT:

![Screenshot 2024-04-24 082259](https://github.com/kanagavel7/Metasploit-for-reconnaissance/assets/162578954/418f4851-579f-4242-9ca6-c9ade851a1b8)

Use the set rhosts command to set the parameter and run the module, as follows:

## OUTPUT:

![Screenshot 2024-04-24 082338](https://github.com/kanagavel7/Metasploit-for-reconnaissance/assets/162578954/2a3bde77-c8f4-47c4-8b19-d34ca8b40921)

After scanning, you can also brute force MySQL root account via Metasploit's auxiliary(scanner/mysql/mysql_login) module.

## OUTPUT:

![Screenshot 2024-04-24 082411](https://github.com/kanagavel7/Metasploit-for-reconnaissance/assets/162578954/55391aa2-481a-4144-b96a-5b92b6adbd9f)

set the PASS_FILE parameter to the wordlist path available inside /usr/share/wordlists: set PASS_FILE /usr/share/wordlistss/rockyou.txt Then, specify the IP address of the target machine with the RHOSTS command. set RHOSTS Set BLANK_PASSWORDS to true in case there is no password set for the root account. set BLANK_PASSWORDS true

## OUTPUT:

![Screenshot 2024-04-24 082449](https://github.com/kanagavel7/Metasploit-for-reconnaissance/assets/162578954/4452af24-eba0-46ee-8bde-6a7f9a6fae90)

## RESULT:
The Metasploit framework for reconnaissance is  examined successfully
