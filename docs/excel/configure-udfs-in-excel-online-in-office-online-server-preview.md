---
title: Konfigurieren von UDFs in Excel online auf Office Online Server
manager: lindalu
ms.date: 12/03/2019
ms.audience: ITPro
localization_priority: Normal
ms.assetid: 3e0ca274-e9cd-48a1-8cfc-9d5053738972
description: Verwenden Sie benutzerdefinierte Funktionen (User-Defined Functions, UDFs) in Excel online auf Office Online-Server, um benutzerdefinierte Funktionen aufzurufen.
ms.openlocfilehash: e1b005079c03ae3028ba6bf9ee1156c6ae2eae80
ms.sourcegitcommit: 007aa2ceb4f569201c3f4372de5c83b6c61f8875
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2020
ms.locfileid: "43102933"
---
# <a name="configure-udfs-in-excel-online-in-office-online-server"></a>Konfigurieren von UDFs in Excel online auf Office Online Server

Verwenden Sie benutzerdefinierte Funktionen (User-Defined Functions, UDFs) in Excel online auf Office Online-Server, um benutzerdefinierte Funktionen aufzurufen. 
  
Über UDFs (User-defined Functions, benutzerdefinierte Funktionen) in Excel Online können Sie in verwaltetem Code geschriebene benutzerdefinierte Funktionen mithilfe von Formeln in Zellen aufrufen. Sie können UDFs zu folgenden Zwecken verwenden:
  
- Call custom mathematical functions.
    
- Abrufen von Daten aus benutzerdefinierten Datenquellen in Arbeitsblättern
    
- Aufrufen von Webdiensten
    
UDF-Binärdateien können in einem von zwei Speicherorten installiert werden:
  
- In einem lokalen Verzeichnis. Beispiel: 
    
    C:\UDFs\MySampleUdf.dll
    
- Im globalen Assemblycache. Beispiel: 
    
    CompanyName.Hierarchichal.MyUdfNamespace.MyUdfClassName.dll, Version=1.1.0.0, Culture=en, PublicKeyToken=e8123117d7ba9ae38
    
Verweisen Sie beim Erstellen einer **New-OfficeWebAppsExcelUserDefinedFunction-** Definition auf dem Office Online Server auf den Speicherort. 
  
> [!NOTE]
> Auf Office Online Server werden keine UDFs unterstützt, die sich auf Netzwerkfreigaben befinden. 
  
## <a name="enable-udfs-on-office-online-server"></a>Aktivieren von UDFs auf Office Online Server 

Wenn ein Administrator mithilfe des Cmdlets [New-OfficeWebAppsFarm](https://docs.microsoft.com/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps) Windows PowerShell eine neue Office-webapps-Server Farm erstellt, sind UDF-Assemblys standardmäßig deaktiviert. Der Standardwert des **ExcelUdfsAllowed**-Flags lautet "False". 
  
Um UDFs zu aktivieren, führen Sie den folgenden Befehl Windows PowerShell auf dem Office Online Server aus, nachdem die Office-webapps-Serverfarm erstellt wurde.
  
`Set-OfficeWebAppsFarm - ExcelUdfsAllowed:$true`
  
## <a name="create-udf-definitions-on-office-online-server"></a>Erstellen von UDF-Definitionen auf Office Online Server

Nach dem Aktivieren von UDFs müssen Sie eine Definition für die Binärdatei mit den UDFs erstellen. Verwenden Sie das **New-OfficeWebAppsExcelUserDefinedFunction-** Cmdlet, um eine Definition für Ihre UDF-Binärdatei auf dem Office Online Server zu erstellen. Dieses Cmdlet umfasst die folgenden Parameter: 
  
- **Assembly**
    
- **AssemblyLocation**
    
- **Enable** (standardmäßig auf False festgelegt) 
    
- **Beschreibung**
    
Die folgenden Beispiele zeigen, wie die UDF-Definitionen erstellt werden.
  
`New-OfficeWebAppsExcelUserDefinedFunction -Assembly c:\myudf.dll -AssemblyLocation LocalFile -Enable:$true -Description "My Server UDFs"`
  
`New-OfficeWebAppsExcelUserDefinedFunction -Assembly "CompanyName.Hierarchichal.MyUdfNamespace.MyUdfClassName.dll, Version=1.1.0.0, Culture=en, PublicKeyToken=e8123117d7ba9ae38" -AssemblyLocation GAC -Enable:$true -Description "My GAC Server UDFs"`
  
Führen Sie nach dem Erstellen des neuen UDF-Verweises **iisreset** auf dem Server aus, um den Verweis sofort zu übernehmen. 
  
## <a name="additional-office-online-server-udf-windows-powershell-commands"></a>Zusätzliche Office Online-Server-UDF Windows PowerShell-Befehle

Verwenden Sie die folgenden Windows PowerShell-Cmdlets zum Arbeiten mit UDFs:
  
- **Get-OfficeWebAppsExcelUserDefinedFunction** (keine erforderlichen Parameter) – gibt eine Liste von UDF-Definitionen zurück, die auf dem Office Online Server konfiguriert sind. 
    
- **Set- OfficeWebAppsExcelUserDefinedFunction** (Identity-Parameter erforderlich) – Legt Eigenschaften für vorhandene UDF-Definitionen fest. 
    
- **Remove-OfficeWebAppsExcelUserDefinedFunction** (Identity-Parameter erforderlich) – Entfernt Eigenschaften von vorhandenen UDF-Definitionen. 
    
## <a name="udf-sample"></a>UDF-Beispiel

Die folgende Beispieldatei stellt eine Beispielarbeitsmappe bereit, die ein UDF und das UDF-Binary verwendet:
  
- [BooleanDataType. xlsx](https://download.microsoft.com/download/6/7/F/67F724FD-1186-4209-BFF1-FBFD99E959D9/User%20Defined%20Function%20Assemblies/BooleanDataType.xlsx): eine Beispielarbeitsmappe, die eine UDF verwendet  
    
## <a name="see-also"></a>Weitere Informationen

- [Konfigurieren von administrativen Einstellungen für Excel Online ](https://docs.microsoft.com/officeonlineserver/configure-excel-online-administrative-settings)  
- [Office Online Server](https://docs.microsoft.com/officeonlineserver/office-online-server)
    

