Enumartion is similar to reconassiance but on the inside. You are scanning or manually searching the system for attack vectors that could continue the attack.

In order to escalate your privileges which will come from enumerating the system, you may need to attempt an attack such as the below to gain credentials or access.

1. Kerberoasting attack (TryHack me Has a room on this) 
2. Pass-the-ticket attack
3. Initial enumeration using tools like Kerbrute and Rubeus
4. AS-REP Roasting with Rubeus and Impacket
5. Golden/Silver Ticket Attacks
6. Pass the Ticket
7. Skeleton key attacks using mimikatz

NTLM also has a number of attack vectors

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
