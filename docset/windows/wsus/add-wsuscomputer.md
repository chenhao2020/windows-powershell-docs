---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: brianlic
author: brianlic-msft
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.UpdateServices.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Add-WsusComputer
ms.assetid: 6CFD1224-CEC5-47D9-93F7-89B236146FF6
---

# Add-WsusComputer

## SYNOPSIS
Adds a client computer to a target group.

## SYNTAX

```
Add-WsusComputer -Computer <WsusComputer> -TargetGroupName <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-WsusComputer** cmdlet adds the specified computer to the specified target group on the local server or a specified server.
You can invoke this command by using the pipeline operator for the results of the [Get-WsusComputer](./Get-WsusComputer.md) cmdlet.
Calling the **Get-WsusComputer** cmdlet and passing the results into this cmdlet enables you to leverage the filtering capabilities of the **Get-WsusComputer** cmdlet in moving the desired computers to the specified target group.
The server used in the **Get-WsusComputer** cmdlet is also used in this cmdlet.

## EXAMPLES

### Example 1: Add computers to a target group
```
PS C:\> Get-WsusServer -Name "contoso" | Get-WsusComputer -NameIncludes "winvm" | Add-WsusComputer -TargetGroupName "Windows Virtual Machines"
```

This command adds all computers with winvm in the name to the target group named Windows Virtual Machines on the server named contoso.

## PARAMETERS

### -Computer
Specifies the object that contains the client computer to be added.
This value is obtained by running the **Get-WsusComputer** cmdlet and piping the resulting **WsusComputer** object into this cmdlet.

```yaml
Type: WsusComputer
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetGroupName
Specifies the name of the computer target group for which to run this cmdlet.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.UpdateServices.Commands.WsusComputer

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Get-WsusComputer](./Get-WsusComputer.md)

[Get-WsusServer](./Get-WsusServer.md)
