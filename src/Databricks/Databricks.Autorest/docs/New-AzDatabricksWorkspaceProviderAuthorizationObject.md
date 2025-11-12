---
external help file:
Module Name: Az.Databricks
online version: https://learn.microsoft.com/powershell/module/Az.Databricks/new-AzDatabricksWorkspaceProviderAuthorizationObject
schema: 2.0.0
---

# New-AzDatabricksWorkspaceProviderAuthorizationObject

## SYNOPSIS
Create an in-memory object for WorkspaceProviderAuthorization.

## SYNTAX

```
New-AzDatabricksWorkspaceProviderAuthorizationObject -PrincipalId <String> -RoleDefinitionId <String>
 [<CommonParameters>]
```

## DESCRIPTION
Create an in-memory object for WorkspaceProviderAuthorization.

## EXAMPLES

### Example 1: {{ Add title here }}
```powershell
{{ Add code here }}
```

```output
{{ Add output here }}
```

{{ Add description here }}

### Example 2: {{ Add title here }}
```powershell
{{ Add code here }}
```

```output
{{ Add output here }}
```

{{ Add description here }}

## PARAMETERS

### -PrincipalId
The provider's principal identifier.
This is the identity that the provider will use to call ARM to manage the workspace resources.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RoleDefinitionId
The provider's role definition identifier.
This role will define all the permissions that the provider must have on the workspace's container resource group.
This role definition cannot have permission to delete the resource group.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Databricks.Models.Api20251001Preview.WorkspaceProviderAuthorization

## NOTES

## RELATED LINKS

