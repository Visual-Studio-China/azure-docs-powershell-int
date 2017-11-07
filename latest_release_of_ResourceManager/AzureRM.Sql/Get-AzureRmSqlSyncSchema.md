---
external help file: Microsoft.Azure.Commands.Sql.dll-Help.xml
online version:
schema: 2.0.0
content_git_url: https://github.com/Visual-Studio-China/azure-powershell/blob/preview/src/ResourceManager/Sql/Commands.Sql/help/Get-AzureRmSqlSyncSchema.md
original_content_git_url: https://github.com/Visual-Studio-China/azure-powershell/blob/preview/src/ResourceManager/Sql/Commands.Sql/help/Get-AzureRmSqlSyncSchema.md
---

# Get-AzureRmSqlSyncSchema

## SYNOPSIS
Returns information about the sync schema of a member database or a hub database.

## SYNTAX

```
Get-AzureRmSqlSyncSchema [-SyncGroupName] <String> [-SyncMemberName <String>] [-ServerName] <String>
 [-DatabaseName] <String> [-ResourceGroupName] <String>
```

## DESCRIPTION
The **Get-AzureRmSqlSyncSchema** cmdlet returns information about the sync schema of a member database or a hub database.

## EXAMPLES

### Example 1.1: Get the sync schema for a hub database
```
PS C:\>Get-AzureRmSqlSyncSchema -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -DatabaseName "database01" -SyncGroupName "syncGroup01"
Tables                     LastUpdateTime
------                     --------------
{dbo.Table_1, dbo.Table_2} 6/13/2017 10:03:44 AM
```

This command gets the sync schema for the hub database in the sync group syncGroup01.


### Example 1.2: Get the sync schema for a hub database, and expand Tables
```
PS C:\>Get-AzureRmSqlSyncSchema -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -DatabaseName "database01" -SyncGroupName "syncGroup01"  | select -ExpandProperty Tables
Columns    : {column1, column2}
ErrorId    : Schema_TableHasNoPrimaryKey
HasError   : True
Name       : dbo.Table_1
QuotedName : [dbo].[Table_1]

Columns    : {column2, column4}
ErrorId    : Schema_TableHasNoPrimaryKey
HasError   : True
Name       : dbo.Table_2
QuotedName : [dbo].[Table_2]
```

This command gets the sync schema for the hub database in the sync group syncGroup01 and expand Tables property.


### Example 2: Get the sync schema for a member database
```
PS C:\>Get-AzureRmSqlSyncSchema -ResourceGroupName "ResourceGroup01" -ServerName "Server01" -DatabaseName "database01" -SyncGroupName "syncGroup01" -SyncMemberName "syncMember01"
The schema payload is the same as Example 1.
```
This command gets the sync schema for the member database in the sync member syncMember01.


## PARAMETERS

### -DatabaseName
The name of the Azure SQL Database.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
The name of the resource group.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerName
The name of the Azure SQL Server.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SyncGroupName
The sync group name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SyncMemberName
The sync member name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

### Microsoft.Azure.Commands.Sql.DataSync.Model.AzureSqlSyncFullSchemaModel

### Tables: Microsoft.Azure.Commands.Sql.DataSync.Model.AzureSqlSyncFullSchemaTableModel

### Columns: Microsoft.Azure.Commands.Sql.DataSync.Model.AzureSqlSyncFullSchemaColumnModel

## NOTES

## RELATED LINKS
