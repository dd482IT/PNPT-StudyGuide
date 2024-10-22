Enumartion is similar to reconassiance but on the inside. You are scanning or manually searching the system for attack vectors that could continue the attack.

In order to escalate your privileges which will come from enumerating the system, you may need to attempt an attack such as the below to gain credentials or access.

1. Kerberoasting attack (TryHack me Has a room on this)
   Kerberoasting allows a user to request a service ticket for any service with a registered SPN then use that ticket to crack the service password. If the service has a registered SPN then it can be Kerberoastable however the success of the attack depends on how strong the password is and if it is trackable as well as the privileges of the cracked service account. To enumerate Kerberoastable accounts I would suggest a tool like BloodHound to find all Kerberoastable accounts, it will allow you to see what kind of accounts you can kerberoast if they are domain admins, and what kind of connections they have to the rest of the domain

   Method 1: Rubeus (local only). Once you get a hash for a target account, you can crack it using hashcat and a password list.
   Method 2: Impacket (remote): Once you get a hash for a target account, it can be cracked.

   Once you gain access a some sort of admin, you may have access to the NTDS.dit file if you'd want to pivot to a different account. 

3. 
4. Pass-the-ticket attack

   On the target system, the LSASS stores Kerberos tickets. Mimikatz can export all tickets on the system. You can then impersonate as the account with that ticket.
      `mimikatz.exe`
      `privilege::debug`
      `sekurlsa::tickets /export`
      `kerberos::ptt <ticket>`
   
6. Initial enumeration using tools like Kerbrute and Rubeus
7. AS-REP Roasting with Rubeus and Impacket

This exploits users that have Kerberos pre-authentication disabled. Using 'Rubeus.exe asreproast', command looking for vulnerable users and then dump found vulnerable user hashes. Then crack the passwords with hashcat. 


7. Golden/Silver Ticket Attacks
8. Pass the Ticket
9. Skeleton key attacks using mimikatz


Enumerate AD: 
1. Kerbrute: DNS may be required. `./kerbrute userenum --dc CONTROLLER.local -d CONTROLLER.local User.txt`. This will list users and services. You must add the domain controller IP to your /etc/hosts. `echo <ip> <domainname> >> /etc/hosts`
2. Rubeus.exe: Collect tickets that can be used with pass the ticket attack.
   You can also brute force with a given password, no ticket. If the provided password matches, it will tell you the user but a lockout policy could prevent the attack. `Rubeus.exe brute /password:Password1 /noticket`

Enumerating Shares:


Commands 
``systeminfo`` 
``wmic qfe get Caption,Description`` - check installed updates 
``whoami /priv`` - know what you are capable of, i.e., your privileges, you can use
`net user` - can view users
Network Enumeration
`whoami /groups` - know what groups you are apart of
`net group` (Windows Domain Controler) 
`net localgroup` (Nont Windows Domain Controler) 
`net localgroup administrators`

Use `net accounts` to see the local settings on a machine; moreover, you can use net accounts /domain if the machine belongs to a domain. This command helps learn about password policy, such as minimum password length, maximum password age, and lockout duration.

TCP and UDP open ports
-```PS C:\Users\thm> netstat -na```

Established Connections
-```PS C:\Users\thm> arp -a```

Active Directory Enumeration

- ```Get-ADUser  -Filter *``` -  get all active directory user accounts
We can also use the LDAP hierarchical tree structure to find a user within the AD environment

- ``Get-ADUser -Filter * -SearchBase "CN=Users,DC=THMREDTEAM,DC=COM"``

Installed Applications

- ``PS C:\Users\thm> wmic product get name,version, vendor`` - list all installed applications and their version.

- ``Get-ChildItem -Hidden -Path C:\Users\kkidd\Desktop\`` - Another interesting thing is to look for particular text strings, hidden directories, backup files. Then we can use the PowerShell cmdlets, Get-ChildItem, as follow:



Services and Process
MITRE: https://attack.mitre.org/techniques/T1057/
https://tryhackme.com/room/btwindowsinternals



SMB
``net share`` 
SNMP


`net start` - shows running services 
`Get-Process -Name <insert name here, remove brackets>` - get additional information on a process 
`netstat -noa |findstr "LISTENING" |findstr "<inssert process ID here"` - shows if it is a network service.

Enumerate DNS
Perform a Zone transfer using nslookup.exe


Sharing files and Printers
Internal services: DNS, local web applications, etc
1.DNS Services
2.Email Services
3.Network File Share
4.Web application
5.Database service




Resoureces: 
https://svch0st.medium.com/active-directory-recon-cheat-sheet-76ccc16dc6e8
