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


*Piping, Filtering and Snorting Data*

`Get-ChildItem | Sort-Object Length`
`Get-ChildItem | Where-Object -Property "Extension" -eq ".txt" `

-ne: "not equal". This operator can be used to exclude objects from the results based on specified criteria.
-gt: "greater than". This operator will filter only objects which exceed a specified value. It is important to note that this is a strict comparison, meaning that objects that are equal to the specified value will be excluded from the results.
-ge: "greater than or equal to". This is the non-strict version of the previous operator. A combination of -gt and -eq.
-lt: "less than". Like its counterpart, "greater than", this is a strict operator. It will include only objects which are strictly below a certain value.
-le: "less than or equal to". Just like its counterpart -ge, this is the non-strict version of the previous operator. A combination of -lt and -eq.

`Get-ChildItem | Where-Object -Property "Name" -like "ship*"`  
`Get-ChildItem | Select-Object Name,Length `

GREP Equivalent: `Select-String -Path ".\captain-hat.txt" -Pattern "hat"`


Filter directory by size: `Get-ChildItem | Where-Object -Property Length -gt 100`
