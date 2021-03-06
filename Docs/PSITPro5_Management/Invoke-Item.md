﻿# Invoke-Item

## SYNOPSIS
Performs the default action on the specified item.

## DESCRIPTION
The Invoke-Item cmdlet performs the default action on the specified item.
For example, it runs an executable file or opens a document file in the application associated with the document file type.
The default action depends on the type of item and is determined by the Windows PowerShell provider that provides access to the data.

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


### Include [String[]]

Performs the default action only on the specified items.
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

Specifies a path to the item.
The value of LiteralPath is used exactly as it is typed.
No characters are interpreted as wildcards.
If the path includes escape characters, enclose it in single quotation marks.
Single quotation marks tell Windows PowerShell not to interpret any characters as escape sequences.


### Path [String[]]

```powershell
[Parameter(
  Mandatory = $true,
  Position = 1,
  ValueFromPipeline = $true,
  ValueFromPipelineByPropertyName = $true,
  ParameterSetName = 'Set 1')]
```

Specifies the path to the selected item.


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

You can pipe a string that contains a path to Invoke-Item.

## OUTPUTS
### None

The command does not generate any output.
However, output might be generated by the item that it invokes.

## NOTES
The Invoke-Item cmdlet is designed to work with the data exposed by any provider.
To list the providers available in your session, type "Get-PsSProvider".
For more information, see about_Providers.


## EXAMPLES
### -------------------------- EXAMPLE 1 --------------------------

```powershell
PS C:\>invoke-item C:\Test\aliasApr04.doc

```
This command opens the file aliasApr04.doc in Microsoft Office Word.
In this case, opening in Word is the default action for .doc files.






### -------------------------- EXAMPLE 2 --------------------------

```powershell
PS C:\>invoke-item "C:\Documents and Settings\Lister\My Documents\*.xls"

```
This command opens all of the Microsoft Office Excel spreadsheets in the C:\Documents and Settings\Lister\My Documents folder.
Each spreadsheet is opened in a new instance of Excel.
In this case, opening in Excel is the default action for .xls files.







## RELATED LINKS

[Online Version:](http://go.microsoft.com/fwlink/p/?linkid=290506)

[Clear-Item]()

[Copy-Item]()

[Get-Item]()

[Invoke-Command]()

[Move-Item]()

[New-Item]()

[Remove-Item]()

[Rename-Item]()

[Set-Item]()

[about_Providers]()

