---
title: DbEngine. Idle-Methode (DAO)
TOCTitle: Idle Method
ms:assetid: c90b565e-626e-139d-102a-0386601ce0c8
ms:mtpsurl: https://msdn.microsoft.com/library/Ff823202(v=office.15)
ms:contentKeyID: 48547666
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052978
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 7a84e3cc4b35886a12b2e6b4cf92b7483fea293a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32294330"
---
# <a name="dbengineidle-method-dao"></a>DbEngine. Idle-Methode (DAO)

**Gilt für**: Access 2013, Office 2013

Unterbricht die Datenverarbeitung und ermöglicht es dem Microsoft Access-Datenbankmodul, anstehende Aufgaben auszuführen, z. B. Speicheroptimierung oder Timeouts von Seiten (gilt nur für Microsoft Access-Arbeitsbereiche).

## <a name="syntax"></a>Syntax

*Ausdruck* . Leerlauf (***Aktion***)

*Ausdruck* Eine Variable, die ein **DBEngine** -Objekt darstellt.

## <a name="parameters"></a>Parameter

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Name</p></th>
<th><p>Erforderlich/optional</p></th>
<th><p>Datentyp</p></th>
<th><p>Beschreibung</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>Action</em></p></td>
<td><p>Optional</p></td>
<td><p><strong>Variant</strong></p></td>
<td><p>Gibt die auszuführende Aktion an. Dies kann eine der <strong><a href="idleenum-enumeration-dao.md">IdleEnum</a></strong> -Konstanten sein.</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>Bemerkungen

Mit der **Idle**-Methode kann das Microsoft Access-Datenbankmodul Hintergrundaufgaben ausführen, die wegen der umfangreichen Datenverarbeitung möglicherweise nicht mehr aktuell sind. Dies kommt oft in Multitaskingumgebungen mit mehreren Benutzern vor, in denen die Hintergrundverarbeitungszeit nicht ausreicht, um alls Datensätze in einem **[Recordset](recordset-object-dao.md)** auf dem aktuellen Stand zu halten.

Usually, read locks are removed and data in local dynaset-type **Recordset** objects are updated only when no other actions (including mouse movements) occur. If you periodically use the **Idle** method, the Microsoft Access database engine can catch up on background processing tasks by releasing unneeded read locks.

Durch Angabe des optionalen Arguments **dbRefreshCache** wird der Speicher nur mit den aktuellsten Daten aus der Datenbank aktualisiert.

Sie müssen diese Methode nur dann in Einzelbenutzerumgebungen anrwenden, wenn mehrere Instanzen einer Anwendung ausgeführt werden. Durch die **Idle**-Methode kann die Leistung in einer Mehrbenutzerumgebung verbessert werden, da das Datenbankmodul gezwungen wird, Daten auf einen Datenträger zu schreiben und Sperren im Speicher freizugeben.


> [!NOTE]
> [!HINWEIS] Sie können Lesesperren auch dadurch freigeben, dass Sie Operationen zum Bestandteil einer Transaktion machen.

## <a name="example"></a>Beispiel

This example uses the **Idle** method to ensure that an output procedure is accessing the most current data available from the database. The IdleOutput procedure is required for this procedure to run.

```vb 
Sub IdleX() 
 
 Dim dbsNorthwind As Database 
 Dim strCountry As String 
 Dim strSQL As String 
 Dim rstOrders As Recordset 
 
 Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
 
 ' Get name of country from user and build SQL statement 
 ' with it. 
 strCountry = Trim(InputBox("Enter country:")) 
 strSQL = "SELECT * FROM Orders WHERE ShipCountry = '" & _ 
 strCountry & "' ORDER BY OrderID" 
 
 ' Open Recordset object with SQL statement. 
 Set rstOrders = dbsNorthwind.OpenRecordset(strSQL) 
 
 ' Display contents of Recordset object. 
 IdleOutput rstOrders, strCountry 
 
 rstOrders.Close 
 dbsNorthwind.Close 
 
End Sub 
 
Sub IdleOutput(rstTemp As Recordset, strTemp As String) 
 
 ' Call the Idle method to release unneeded locks, force 
 ' pending writes, and refresh the memory with the current 
 ' data in the .mdb file. 
 DBEngine.Idle dbRefreshCache 
 
 ' Enumerate the Recordset object. 
 With rstTemp 
 Debug.Print "Orders from " & strTemp & ":" 
 Debug.Print , "OrderID", "CustomerID", "OrderDate" 
 Do While Not .EOF 
 Debug.Print , !OrderID, !CustomerID, !OrderDate 
 .MoveNext 
 Loop 
 End With 
 
End Sub 
 
```

