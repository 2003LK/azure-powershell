---
external help file:
Module Name: Az.Databricks
online version: https://learn.microsoft.com/powershell/module/az.databricks/update-azdatabricksworkspace
schema: 2.0.0
---

# Update-AzDatabricksWorkspace

## SYNOPSIS
Updates a workspace.

## SYNTAX

### UpdateExpanded (Default)
```
Update-AzDatabricksWorkspace -Name <String> -ResourceGroupName <String> [-SubscriptionId <String>]
 [-AccessConnectorId <String>] [-AccessConnectorIdentityType <IdentityType>]
 [-AccessConnectorUserAssignedIdentityId <String>] [-AmlWorkspaceId <String>]
 [-Authorization <IWorkspaceProviderAuthorization[]>] [-AutomaticClusterUpdate <AutomaticClusterUpdateValue>]
 [-ComplianceStandard <ComplianceStandard[]>] [-DefaultCatalogInitialType <InitialType>]
 [-DefaultStorageFirewall <DefaultStorageFirewall>] [-EnableNoPublicIP] [-EncryptionKeyName <String>]
 [-EncryptionKeySource <KeySource>] [-EncryptionKeyVaultUri <String>] [-EncryptionKeyVersion <String>]
 [-EnhancedSecurityCompliance <ComplianceSecurityProfileValue>]
 [-EnhancedSecurityMonitoring <EnhancedSecurityMonitoringValue>] [-KeyVaultKeyName <String>]
 [-KeyVaultKeyVersion <String>] [-KeyVaultUri <String>] [-ManagedDiskKeySource <EncryptionKeySource>]
 [-ManagedDiskKeyVaultPropertiesKeyName <String>] [-ManagedDiskKeyVaultPropertiesKeyVaultUri <String>]
 [-ManagedDiskKeyVaultPropertiesKeyVersion <String>] [-ManagedDiskRotationToLatestKeyVersionEnabled]
 [-ManagedServiceKeySource <EncryptionKeySource>] [-ManagedServicesKeyVaultPropertiesKeyName <String>]
 [-ManagedServicesKeyVaultPropertiesKeyVaultUri <String>]
 [-ManagedServicesKeyVaultPropertiesKeyVersion <String>] [-PrepareEncryption]
 [-PublicNetworkAccess <PublicNetworkAccess>] [-RequiredNsgRule <RequiredNsgRules>] [-SkuTier <String>]
 [-Tag <Hashtable>] [-UiDefinitionUri <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm]
 [-WhatIf] [<CommonParameters>]
```

### UpdateViaIdentityExpanded
```
Update-AzDatabricksWorkspace -InputObject <IDatabricksIdentity> [-AccessConnectorId <String>]
 [-AccessConnectorIdentityType <IdentityType>] [-AccessConnectorUserAssignedIdentityId <String>]
 [-AmlWorkspaceId <String>] [-Authorization <IWorkspaceProviderAuthorization[]>]
 [-AutomaticClusterUpdate <AutomaticClusterUpdateValue>] [-ComplianceStandard <ComplianceStandard[]>]
 [-DefaultCatalogInitialType <InitialType>] [-DefaultStorageFirewall <DefaultStorageFirewall>]
 [-EnableNoPublicIP] [-EncryptionKeyName <String>] [-EncryptionKeySource <KeySource>]
 [-EncryptionKeyVaultUri <String>] [-EncryptionKeyVersion <String>]
 [-EnhancedSecurityCompliance <ComplianceSecurityProfileValue>]
 [-EnhancedSecurityMonitoring <EnhancedSecurityMonitoringValue>] [-KeyVaultKeyName <String>]
 [-KeyVaultKeyVersion <String>] [-KeyVaultUri <String>] [-ManagedDiskKeySource <EncryptionKeySource>]
 [-ManagedDiskKeyVaultPropertiesKeyName <String>] [-ManagedDiskKeyVaultPropertiesKeyVaultUri <String>]
 [-ManagedDiskKeyVaultPropertiesKeyVersion <String>] [-ManagedDiskRotationToLatestKeyVersionEnabled]
 [-ManagedServiceKeySource <EncryptionKeySource>] [-ManagedServicesKeyVaultPropertiesKeyName <String>]
 [-ManagedServicesKeyVaultPropertiesKeyVaultUri <String>]
 [-ManagedServicesKeyVaultPropertiesKeyVersion <String>] [-PrepareEncryption]
 [-PublicNetworkAccess <PublicNetworkAccess>] [-RequiredNsgRule <RequiredNsgRules>] [-SkuTier <String>]
 [-Tag <Hashtable>] [-UiDefinitionUri <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm]
 [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Updates a workspace.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```powershell
Get-AzDatabricksWorkspace -ResourceGroupName azps_test_gp_db -Name azps-databricks-workspace-t1 | Update-AzDatabricksWorkspace -Tag @{"key"="value"}
```



### -------------------------- EXAMPLE 2 --------------------------
```powershell
Update-AzDatabricksWorkspace -ResourceGroupName azps_test_gp_db -Name azps-databricks-workspace-t2 -PrepareEncryption
$updWsp = Get-AzDatabricksWorkspace -ResourceGroupName azps_test_gp_db -Name azps-databricks-workspace-t2
Set-AzKeyVaultAccessPolicy -VaultName azps-keyvault -ObjectId $updWsp.StorageAccountIdentityPrincipalId -PermissionsToKeys wrapkey,unwrapkey,get
Update-AzDatabricksWorkspace -ResourceGroupName azps_test_gp_db -Name azps-databricks-workspace-t2 -EncryptionKeySource 'Microsoft.KeyVault' -EncryptionKeyVaultUri https://azps-keyvault.vault.azure.net/ -EncryptionKeyName azps-k1 -EncryptionKeyVersion a563a8021cba47109d93bd6d690621a7
```



### -------------------------- EXAMPLE 3 --------------------------
```powershell
Update-AzDatabricksWorkspace -ResourceGroupName azps_test_gp_db -Name azps-databricks-workspace-t3 -EncryptionKeySource 'Default'
```



### -------------------------- EXAMPLE 4 --------------------------
```powershell
Update-AzDatabricksWorkspace -ResourceGroupName azps_test_gp_db -Name azps-databricks-workspace-t2 -RequiredNsgRule 'AllRules'
```



## PARAMETERS

### -AccessConnectorId
The resource ID of Azure Databricks Access Connector Resource.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AccessConnectorIdentityType
The identity type of the Access Connector Resource.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Databricks.Support.IdentityType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AccessConnectorUserAssignedIdentityId
The resource ID of the User Assigned Identity associated with the Access Connector Resource.
This is required for type 'UserAssigned' and not valid for type 'SystemAssigned'.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AmlWorkspaceId
The value which should be used for this field.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsJob
Run the command as a job

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Authorization
The workspace provider authorizations.
To construct, see NOTES section for AUTHORIZATION properties and create a hash table.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Databricks.Models.Api20251001Preview.IWorkspaceProviderAuthorization[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AutomaticClusterUpdate
Status of automated cluster updates feature.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Databricks.Support.AutomaticClusterUpdateValue
Parameter Sets: (All)
Aliases: AutomaticClusterUpdateValue

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComplianceStandard
Compliance standards associated with the workspace.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Databricks.Support.ComplianceStandard[]
Parameter Sets: (All)
Aliases: ComplianceSecurityProfileComplianceStandard

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultCatalogInitialType
Defines the initial type of the default catalog.
Possible values (case-insensitive): HiveMetastore, UnityCatalog

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Databricks.Support.InitialType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
The credentials, account, tenant, and subscription used for communication with Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultStorageFirewall
Gets or Sets Default Storage Firewall configuration information

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Databricks.Support.DefaultStorageFirewall
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableNoPublicIP
The value which should be used for this field.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EncryptionKeyName
The name of Key Vault key.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EncryptionKeySource
The encryption keySource (provider).
Possible values (case-insensitive): Default, Microsoft.Keyvault

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Databricks.Support.KeySource
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EncryptionKeyVaultUri
The URI (DNS name) of the Key Vault.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EncryptionKeyVersion
The version of KeyVault key.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnhancedSecurityCompliance
Status of Compliance Security Profile feature.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Databricks.Support.ComplianceSecurityProfileValue
Parameter Sets: (All)
Aliases: ComplianceSecurityProfileValue

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnhancedSecurityMonitoring
Status of Enhanced Security Monitoring feature.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Databricks.Support.EnhancedSecurityMonitoringValue
Parameter Sets: (All)
Aliases: EnhancedSecurityMonitoringValue

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Identity parameter.
To construct, see NOTES section for INPUTOBJECT properties and create a hash table.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Databricks.Models.IDatabricksIdentity
Parameter Sets: UpdateViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -KeyVaultKeyName
The name of KeyVault key.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyVaultKeyVersion
The version of KeyVault key.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyVaultUri
The Uri of KeyVault.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagedDiskKeySource
The encryption keySource (provider).
Possible values (case-insensitive): Microsoft.Keyvault

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Databricks.Support.EncryptionKeySource
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagedDiskKeyVaultPropertiesKeyName
The name of KeyVault key.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagedDiskKeyVaultPropertiesKeyVaultUri
The URI of KeyVault.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagedDiskKeyVaultPropertiesKeyVersion
The version of KeyVault key.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagedDiskRotationToLatestKeyVersionEnabled
Indicate whether the latest key version should be automatically used for Managed Disk Encryption.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagedServiceKeySource
The encryption keySource (provider).
Possible values (case-insensitive): Microsoft.Keyvault

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Databricks.Support.EncryptionKeySource
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagedServicesKeyVaultPropertiesKeyName
The name of KeyVault key.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagedServicesKeyVaultPropertiesKeyVaultUri
The Uri of KeyVault.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagedServicesKeyVaultPropertiesKeyVersion
The version of KeyVault key.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
The name of the workspace.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases: WorkspaceName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoWait
Run the command asynchronously

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PrepareEncryption
Prepare the workspace for encryption.
Enables the Managed Identity for managed storage account.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PublicNetworkAccess
The network access type for accessing workspace.
Set value to disabled to access workspace only via private link.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Databricks.Support.PublicNetworkAccess
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequiredNsgRule
Gets or sets a value indicating whether data plane (clusters) to control plane communication happen over private endpoint.
Supported values are 'AllRules' and 'NoAzureDatabricksRules'.
'NoAzureServiceRules' value is for internal use only.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Databricks.Support.RequiredNsgRules
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
The name of the resource group.
The name is case insensitive.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkuTier
The SKU tier.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
The ID of the target subscription.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
Resource tags.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UiDefinitionUri
The blob URI where the UI definition file is located.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Databricks.Models.IDatabricksIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Databricks.Models.Api20251001Preview.IWorkspace

## NOTES

## RELATED LINKS

