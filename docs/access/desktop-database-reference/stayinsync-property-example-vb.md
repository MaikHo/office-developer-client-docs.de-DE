---
title: StayInSync-Eigenschaft (Beispiel) (VB)
TOCTitle: StayInSync Property Example (VB)
ms:assetid: 1b35f19a-0104-efd5-5222-55f92e08473b
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248952(v=office.15)
ms:contentKeyID: 48543535
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 0c12ca42ec30ef40c6ef1f7c943079b4db58307a
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2018
ms.locfileid: "25475612"
---
# <a name="stayinsync-property-example-vb"></a>StayInSync-Eigenschaft (Beispiel) (VB)


**Betrifft**: Access 2013 | Office 2013

Dieses Beispiel veranschaulicht, wie die [StayInSync](stayinsync-property-ado.md)-Eigenschaft den Zugriff auf Zeilen in einem hierarchischen [Recordset](recordset-object-ado.md) vereinfacht.

Die äußere Schleife zeigt für jeden Autor den Vor- und Nachnamen, den Status und die Identifikation an. Das angefügte **Recordset** -Objekt für die einzelnen Zeilen wird von der [StayInSync](fields-collection-ado.md) -Eigenschaft aus der **Fields**-Auflistung abgerufen und automatisch **rstTitleAuthor** zugeordnet, sobald das übergeordnete **Recordset** -Objekt in eine neue Zeile verschoben wird. Die innere Schleife zeigt vier Felder aus jeder Zeile im angefügten Recordset an.

```vb 
 
'BeginStayInSyncVB 
Public Sub Main() 
 On Error GoTo ErrorHandler 
 
 'To integrate this code create a DSN called Pubs 
 'with a user_id = sa and no password 
 
 Dim Cnxn As ADODB.Connection 
 Dim rst As ADODB.Recordset 
 Dim rstTitleAuthor As New ADODB.Recordset 
 Dim strCnxn As String 
 
 ' open connection with Data Shape attributes 
 Set Cnxn = New ADODB.Connection 
 strCnxn = "Provider=MSDataShape;Data Provider='sqloledb';Data Source='MySqlServer';" & _ 
 "Initial Catalog='Pubs';Integrated Security='SSPI';" 
 Cnxn.Open strCnxn 
 
 ' create recordset 
 Set rst = New ADODB.Recordset 
 rst.StayInSync = True 
 rst.Open "SHAPE {select * from Authors} " & _ 
 "APPEND ( { select * from titleauthor} AS chapTitleAuthor " & _ 
 "RELATE au_id TO au_id) ", Cnxn, , , adCmdText 
 
 Set rstTitleAuthor = rst("chapTitleAuthor").Value 
 Do Until rst.EOF 
 Debug.Print rst!au_fname & " " & rst!au_lname & " " & _ 
 rst!State & " " & rst!au_id 
 
 Do Until rstTitleAuthor.EOF 
 Debug.Print rstTitleAuthor(0) & " " & rstTitleAuthor(1) & " " & _ 
 rstTitleAuthor(2) & " " & rstTitleAuthor(3) 
 rstTitleAuthor.MoveNext 
 Loop 
 
 rst.MoveNext 
 Loop 
 
 ' clean up 
 rst.Close 
 Cnxn.Close 
 Set rst = Nothing 
 Set Cnxn = Nothing 
 Exit Sub 
 
ErrorHandler: 
 ' clean up 
 If Not rst Is Nothing Then 
 If rst.State = adStateOpen Then rst.Close 
 End If 
 Set rst = Nothing 
 
 If Not Cnxn Is Nothing Then 
 If Cnxn.State = adStateOpen Then Cnxn.Close 
 End If 
 Set Cnxn = Nothing 
 
 If Err <> 0 Then 
 MsgBox Err.Source & "-->" & Err.Description, , "Error" 
 End If 
End Sub 
'EndStayInSyncVB 
```
