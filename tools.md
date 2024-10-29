1. PowerView/SharpView
- These tools are great for checking what additional access we may have with a new set of credentials, targeting specific users or computers, or finding some "quick wins" such as users that can be attacked via Kerberoasting or ASREPRoasting.
  
2. BloodHound (and bloudhound.py)
- 	Used to visually map out AD relationships and help plan attack paths that may otherwise go unnoticed. Uses the SharpHound PowerShell or C# ingestor to gather data to later be imported into the BloodHound JavaScript (Electron) application with a Neo4j database for graphical analysis of the AD environment

3. SharpHound

4. Kerbrute - https://github.com/ropnop/kerbrute
    - Can get usernames


5. Impacket toolkit

6. Responder is a tool built to listen, analyze, and poison LLMNR, NBT-NS, and MDNS requests and responses. It has many more functions, but for now, all we are utilizing is the tool in its Analyze mode. This will passively listen to the network and not send any poisoned packets. We'll cover this tool more in-depth in later sections.

7. Inveigh.ps1

8. C# Inveigh (InveighZero)

9. rpcinfo

10. rpcclient

11. CrackmapExec (CME)

12. Rubeus - https://github.com/GhostPack/Rubeus

Rubeus has a wide variety of attacks and features that allow it to be a very versatile tool for attacking Kerberos. Just some of the many tools and attacks include overpass the hash, ticket requests and renewals, ticket management, ticket extraction, harvesting, pass the ticket, AS-REP Roasting, and Kerberoasting.

14. GetUsersSPNs.py

15. Hashcat

16. enum4linux

17. ldapsearch

18. windaspearch

19. DomainPasswordSpray.ps1

20. LAPSToolkit

21. smbmap

22. psexec.py

23. wmiexec.py

24. Snaffler

25. smbserver.py

26. setspn.exe

27. Mimikatz

28. secretsdump.py

29. evil-winrm

30. mssqlclient.py

31. noPac.py

32. rpcdump.py

33. CVE-2021-1675.py

34. ntlmrelayx.py

35. PetitPotam.py

36. gettgtpkinit.py

37. getnthash.py

38. adidnsdump

39. gpp-decrypt

40. GetNPusers.py

41. lookupsid.py

42. ticketer.py

43. raiseChild.py

44. Active Directory Explorer

45. PingCastle

46. Group3r

47. ADRecon

48. Fping provides us with a similar capability as the standard ping application in that it utilizes ICMP requests and replies to reach out and interact with a host. Where fping shines is in its ability to issue ICMP packets against a list of multiple hosts at once and its scriptability. Also, it works in a round-robin fashion, querying hosts in a cyclical manner instead of waiting for multiple requests to a single host to return before moving on. These checks will help us determine if anything else is active on the internal network. ICMP is not a one-stop-shop, but it is an easy way to get an initial idea of what exists. Other open ports and active protocols may point to new hosts for later targeting. Let's see it in action. 
