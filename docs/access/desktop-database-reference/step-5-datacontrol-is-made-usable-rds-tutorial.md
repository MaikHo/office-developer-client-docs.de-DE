---
title: 'Schritt 5: Verwendbarmachen des DataControl-Objekts (RDS-Lernprogramm)'
TOCTitle: 'Step 5: DataControl is Made Usable (RDS Tutorial)'
ms:assetid: 9eff5732-2743-6891-dfa6-0991645e17ad
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249728(v=office.15)
ms:contentKeyID: 48546672
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 1d9bd24d0aff1134a6af77862fd8f011d4ddff9f
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2018
ms.locfileid: "25475415"
---
# <a name="step-5-datacontrol-is-made-usable-rds-tutorial"></a>Schritt 5: Verwendbarmachen des DataControl-Objekts (RDS-Lernprogramm)


**Betrifft**: Access 2013 | Office 2013

Das zurückgegebene **Recordset** -Objekt kann verwendet werden. Sie können es wie jedes andere **Recordset** -Objekt überprüfen, bearbeiten oder darin navigieren. Die Bearbeitungsmöglichkeiten des **Recordset** -Objekts hängen von der Umgebung ab. Visual Basic und Visual C++ besitzen visuelle Steuerelemente, die ein **Recordset** -Objekt direkt oder indirekt mithilfe eines aktivierenden Datensteuerelements verwenden können.

Beim Anzeigen einer Webseite in Microsoft Internet Explorer z. B. möchten Sie das **Recordset** -Objekt vermutlich in einem visuellen Steuerelement anzeigen. Visuelle Steuerelemente auf einer Webseite können nicht direkt auf ein **Recordset** -Objekt zugreifen. Der Zugriff auf das **Recordset** ist jedoch über das [RDS.DataControl](datacontrol-object-rds.md)-Objekt möglich. Das **RDS.DataControl** -Objekt kann von einem visuellen Steuerelement verwendet werden, wenn seine [SourceRecordset](recordset-sourcerecordset-properties-rds.md)-Eigenschaft auf das **Recordset** -Objekt festgelegt ist.

Der **DATASRC** -Parameter eines visuellen Steuerelements muss auf **RDS.DataControl** und seine **DATAFLD** -Eigenschaft auf ein **Recordset** -Objektfeld (Spalte) festgelegt sein.

In diesem Lernprogramm legen Sie die **SourceRecordset** -Eigenschaft fest:

```vb 
 
Sub RDSTutorial5() 
 Dim DS as New RDS.DataSpace 
 Dim RS as ADODB.Recordset 
 Dim DC as New RDS.DataControl 
 Dim DF as Object 
 Set DF = DS.CreateObject("RDSServer.DataFactory", "https://yourServer") 
 Set RS = DF.Query ("DSN=Pubs", "SELECT * FROM Authors") 
 DC.SourceRecordset = RS ' Visual controls can now bind to DC. 
... 
```
