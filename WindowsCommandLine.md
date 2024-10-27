Check Path: `set` 
Version: `ver` , `systeminfo` 
piping: `driverquery | more` 
Other: `cls, help` 
Files: `dir /a` (hidden files), `dir /s`, `tree`, `mkdir`, `rmdir`, `more` (can help read large files by page clicking space or by line clicking enter)
`copy`, `move`, `del` or `erase`.
Processes: `tasklist`, check for filters using `tasklist /f`, `tasklist /FI "imagename eq sshd.exe`, `taskill /PID <number>`.

Powershell 

List Available cmdlets: `Get-Command`, there are different types of commands and they can be filtered like so `Get-Command -CommandType "Function"` 
Man Page: `Get-Help <commandlet>`
Aliases: `Get-Alias` shows all aliases, for example, `cd` is an alis for `Set-Location` 
Download Additional cmdlets: `Find-Module` + `Install-Module -Name <name>` 


