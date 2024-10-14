Enumartion is similar to reconassiance but on the inside. You are scanning or manually searching the system for attack vectors that could continue the attack.

Tools.
1. WinPeas (Can be detected by Windows Defender) 


Commands 
``systeminfo`` 
``wmic qfe get Caption,Description`` - check installed updates 
``whoami /priv`` - know what you are capable of, i.e., your privileges, you can use
`net user` - can view users
Network Enumeration
`whoami /groups` - know what groups you are apart of

TCP and UDP open ports
```PS C:\Users\thm> netstat -na```

Established Connections
```PS C:\Users\thm> arp -a```

Active Directory Enumeration
```Get-ADUser  -Filter *``` -  get all active directory user accounts
We can also use the LDAP hierarchical tree structure to find a user within the AD environment

``Get-ADUser -Filter * -SearchBase "CN=Users,DC=THMREDTEAM,DC=COM"``

Installed Applications
``PS C:\Users\thm> wmic product get name,version, vendor`` - list all installed applications and their version.

``Get-ChildItem -Hidden -Path C:\Users\kkidd\Desktop\`` - Another interesting thing is to look for particular text strings, hidden directories, backup files. Then we can use the PowerShell cmdlets, Get-ChildItem, as follow:



Services and Process
MITRE: https://attack.mitre.org/techniques/T1057/
https://tryhackme.com/room/btwindowsinternals

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
