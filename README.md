# AzurePipelinesPS

A PowerShell module that makes interfacing with Azure Pipelines a bit easier.

## Building

Run the build script in the root of the project to install dependent modules and start the build

    .\build.ps1

### Default Build

```Powershell
Invoke-Build
```

### Cleaning the Output

```Powershell
Invoke-Build Clean
```

## Module Data

### Setting Module Data

```Powershell
Set-APModuleData -Instance 'https://.dev.azure.com/' -Collection 'myOrganization' -PersonalAccessToken 'myToken'
```

### Removing Module Data

```Powershell
Remove-APModuleData
```

To remove just the personal access token.

```Powershell
Remove-APModuleData -PersonalAccessToken
```

## Authentication

If a personal access token is provided in the module data it will be used to autheticate by default unless a credential is supplied.
If neither a personal access token or a credential is provided the module will attempt to authenticate with default credentials.
**Default credentials only works for on premise**.