---
title: QueryDef.Prepare Property (DAO)
TOCTitle: Prepare Property
ms:assetid: d5a285c4-bd00-028b-b785-f1890db29bab
ms:mtpsurl: https://msdn.microsoft.com/library/Ff835035(v=office.15)
ms:contentKeyID: 48547968
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1101187
f1_categories:
- Office.Version=v15
ms.openlocfilehash: cec1fde6bc76438da2292ae30545337eaeea6cf4
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2018
ms.locfileid: "25474109"
---
# <a name="querydefprepare-property-dao"></a>QueryDef.Prepare Property (DAO)


**Betrifft**: Access 2013 | Office 2013

## <a name="syntax"></a>Syntax

*Ausdruck* . Vorbereiten

*Ausdruck* Eine Variable, die ein **QueryDef** -Objekt darstellt.

## <a name="remarks"></a>Bemerkungen

Sie können mit der **Prepare**-Eigenschaft festlegen, dass der Server anhand Ihrer Abfrage eine temporäre gespeicherte Prozedur erstellt und sie dann ausführt, oder die Abfrage direkt ausführen. Standardmäßig hat die **Prepare**-Eigenschaft den Wert **dbQPrepare**. Sie können für diese Eigenschaft jedoch **dbQUnprepare** festlegen, um zu verhindern, dass die Abfrage vorbereitet wird. In diesem Fall wird die Abfrage unter Verwendung der **SQLExecDirect**-API ausgeführt.

Das Erstellen einer gespeicherten Prozedur kann die erste Ausführung verlangsamen. Alle nachfolgenden Verweise auf die Abfrage werden dann jedoch schneller ausgeführt. Einige Abfragen können nicht in Form von gespeicherten Prozeduren ausgeführt werden. In diesen Fällen setzen Sie die **Prepare**-Eigenschaft auf **dbQUnprepare**.

Wenn **Vorbereiten** auf **dbExecDirect**festgelegt wird, kann dies überschrieben werden, wenn die Abfrage ausgeführt wird, indem Sie Options-Argument der **[Execute](querydef-execute-method-dao.md)** -Methode auf **DbExecDirect**festlegen.


> [!NOTE]
> <P>[!HINWEIS] Die ODBC-API <STRONG>SQLPrepare</STRONG> wird aufgerufen, sobald die DAO- <STRONG><A href="querydef-sql-property-dao.md">SQL</A></STRONG> -Eigenschaft festgelegt wird. Sie müssen daher zur Steigerung der Leistung mithilfe der <STRONG>dbQUnprepare</STRONG>-Option die <STRONG>Prepare</STRONG>-Eigenschaft festlegen, bevor Sie die <STRONG>SQL</STRONG>-Eigenschaft festlegen.</P>



## <a name="example"></a>Beispiel

In diesem Beispiel wird mit der **Prepare**-Eigenschaft festgelegt, dass eine Abfrage direkt ausgeführt wird, anstatt zuvor eine temporäre gespeicherte Prozedur auf dem Server zu erstellen.

```vb 
Sub PrepareX() 
 
 Dim wrkODBC As Workspace 
 Dim conPubs As Connection 
 Dim qdfTemp As QueryDef 
 Dim rstTemp As Recordset 
 
 ' Create ODBCDirect Workspace object and open Connection 
 ' object. 
 Set wrkODBC = CreateWorkspace("", _ 
 "admin", "", dbUseODBC) 
 
 ' Note: The DSN referenced below must be configured to 
 ' use Microsoft Windows NT Authentication Mode to 
 ' authorize user access to the Microsoft SQL Server. 
 Set conPubs = wrkODBC.OpenConnection("Publishers", , , _ 
 "ODBC;DATABASE=pubs;DSN=Publishers") 
 
 Set qdfTemp = conPubs.CreateQueryDef("") 
 
 With qdfTemp 
 ' Because you will only run this query once, specify 
 ' the ODBC SQLExecDirect API function. If you do 
 ' not set this property before you set the SQL 
 ' property, the ODBC SQLPrepare API function will 
 ' be called anyway which will nullify any 
 ' performance gain. 
 .Prepare = dbQUnprepare 
 .SQL = "UPDATE roysched " & _ 
 "SET royalty = royalty * 2 " & _ 
 "WHERE title_id LIKE 'BU____' OR " & _ 
 "title_id LIKE 'PC____'" 
 .Execute 
 End With 
 
 Debug.Print "Query results:" 
 
 ' Open recordset containing modified records. 
 Set rstTemp = conPubs.OpenRecordset( _ 
 "SELECT * FROM roysched " & _ 
 "WHERE title_id LIKE 'BU____' OR " & _ 
 "title_id LIKE 'PC____'") 
 
 ' Enumerate recordset. 
 With rstTemp 
 Do While Not .EOF 
 Debug.Print , !title_id, !lorange, _ 
 !hirange, !royalty 
 .MoveNext 
 Loop 
 .Close 
 End With 
 
 conPubs.Close 
 wrkODBC.Close 
 
```
