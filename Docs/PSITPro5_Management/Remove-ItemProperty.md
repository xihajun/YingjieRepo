﻿# Remove-ItemProperty

## SYNOPSIS
Deletes the property and its value from an item.

## DESCRIPTION
The Remove-ItemProperty cmdlet deletes a property and its value from an item.
You can use it to delete registry values and the data that they store.

## PARAMETERS

### Credential [PSCredential]

```powershell
[Parameter(ValueFromPipelineByPropertyName = $true)]
```

Specifies a user account that has permission to perform this action.
The default is the current user.

Type a user name, such as "User01" or "Domain01\User01", or enter a PSCredential object, such as one generated by the Get-Credential cmdlet.
If you type a user name, you will be prompted for a password.

This parameter is not supported by any providers installed with Windows PowerShell.


### Exclude [String[]]

Omits the specified items.
The value of this parameter qualifies the Path parameter.
Enter a path element or pattern, such as "*.txt".
Wildcards are permitted.


### Filter [String]

Specifies a filter in the provider's format or language.
The value of this parameter qualifies the Path parameter.
The syntax of the filter, including the use of wildcards, depends on the provider.
Filters are more efficient than other parameters, because the provider applies them when retrieving the objects rather than having Windows PowerShell filter the objects after they are retrieved.


### Force [switch]

Allows the cmdlet to remove a property of an object that cannot otherwise be accessed by the user.
Implementation varies from provider to provider.
For more information, see about_Providers.


### Include [String[]]

Deletes only the specified items.
The value of this parameter qualifies the Path parameter.
Enter a path element or pattern, such as "*.txt".
Wildcards are permitted.


### InformationAction [System.Management.Automation.ActionPreference]

```powershell
[ValidateSet(
  'SilentlyContinue',
  'Stop',
  'Continue',
  'Inquire',
  'Ignore',
  'Suspend')]
```


Type a user name, such as "User01" or "Domain01\User01", or enter a PSCredential object, such as one generated by the Get-Credential cmdlet.
If you type a user name, you will be prompted for a password.

This parameter is not supported by any providers installed with Windows PowerShell.


### InformationVariable [System.String]


Type a user name, such as "User01" or "Domain01\User01", or enter a PSCredential object, such as one generated by the Get-Credential cmdlet.
If you type a user name, you will be prompted for a password.

This parameter is not supported by any providers installed with Windows PowerShell.


### LiteralPath [String[]]

```powershell
[Parameter(
  Mandatory = $true,
  ParameterSetName = 'Set 2')]
```

Specifies a path to the item property.
The value of LiteralPath is used exactly as it is typed.
No characters are interpreted as wildcards.
If the path includes escape characters, enclose it in single quotation marks.
Single quotation marks tell Windows PowerShell not to interpret any characters as escape sequences.


### Name [String[]]

```powershell
[Parameter(
  Mandatory = $true,
  Position = 2,
  ValueFromPipelineByPropertyName = $true)]
```

Specifies the names of the properties to be retrieved.


### Path [String[]]

```powershell
[Parameter(
  Mandatory = $true,
  Position = 1,
  ValueFromPipeline = $true,
  ValueFromPipelineByPropertyName = $true,
  ParameterSetName = 'Set 1')]
```

Specifies the path to the item whose properties are being removed.
Wildcards are permitted.


### Confirm [switch]

Prompts you for confirmation before running the cmdlet.Prompts you for confirmation before running the cmdlet.


### WhatIf [switch]

Shows what would happen if the cmdlet runs.
The cmdlet is not run.Shows what would happen if the cmdlet runs.
The cmdlet is not run.


### UseTransaction [switch]

Includes the command in the active transaction.
This parameter is valid only when a transaction is in progress.
For more information, see Includes the command in the active transaction.
This parameter is valid only when a transaction is in progress.
For more information, see



## INPUTS
### System.String

You can pipe a string that contains a path (but not a literal path) to Remove-ItemProperty.

## OUTPUTS
### None

This cmdlet does not return any output.

## NOTES
You can also refer to Remove-ItemProperty by its built-in alias, "rp".
For more information, see about_Alias.

In the Windows PowerShell Registry provider, registry values are considered to be properties of a registry key or subkey.
You can use the ItemProperty cmdlets to manage these values.

The Remove-ItemProperty cmdlet is designed to work with the data exposed by any provider.
To list the providers available in your session, type "Get-PSProvider".
For more information, see about_Providers.


## EXAMPLES
### -------------------------- EXAMPLE 1 --------------------------

```powershell
PS C:\>remove-itemproperty -path HKLM:\Software\SmpApplication -name SmpProperty

```
This command deletes the SmpProperty registry value, and its data, from the SmpApplication subkey of the HKEY_LOCAL_MACHINE\Software registry key.

Because the command is issued from a file system drive (PS C:\\>), it includes the fully qualified path to the SmpApplication subkey, including the drive, HKLM:, and the Software key.

It uses the Name parameter to identify the registry value that is being deleted.






### -------------------------- EXAMPLE 2 --------------------------

```powershell
PS C:\>set-location HKCU:\Software\MyCompany\MyApp
PS HKCU:\Software\MyCompany\MyApp> remove-itemproperty -path . -Name Options -confirm

```
These commands delete the Options registry value, and its data, from the MyApp subkey of HKEY_CURRENT_USER\Software\MyCompany.

The first command uses the Set-Location cmdlet to change the current location to the HKEY_CURRENT_USER drive (HKCU:) and the Software\MyCompany\MyApp subkey.

The second command uses the Remove-Item cmdlet to remove the Options registry value, and its data, from the MyApp subkey.
Because the Path parameter is required, the command uses a dot (.) to indicate the current location.
It uses the Name parameter to specify which registry value to delete.
It uses the Confirm parameter to request a user prompt before deleting the value.






### -------------------------- EXAMPLE 3 --------------------------

```powershell
PS C:\>get-item -path HKLM:\Software\MyCompany | remove-itemproperty -name NoOfEmployees

```
This command deletes the NoOfEmployees registry value, and its data, from the HKLM\Software\MyCompany registry key.

The command uses the Get-Item cmdlet to get an item that represents the registry key.
It uses a pipeline operator (|) to send the object to the Remove-ItemProperty cmdlet.
Then, it uses the Name parameter of Remove-ItemProperty to specify the name of the registry value.







## RELATED LINKS

[Online Version:](http://go.microsoft.com/fwlink/p/?linkid=293897)

[Clear-ItemProperty]()

[Copy-ItemProperty]()

[Get-ItemProperty]()

[Move-ItemProperty]()

[New-ItemProperty]()

[Remove-Item]()

[Rename-ItemProperty]()

[Set-ItemProperty]()

[about_Providers]()

