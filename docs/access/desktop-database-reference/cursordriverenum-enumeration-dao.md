---
title: CursorDriverEnum Enumeration (DAO)
TOCTitle: CursorDriverEnum Enumeration
ms:assetid: d0312ece-c30a-7d61-d5f3-75edf0d0afc8
ms:mtpsurl: https://msdn.microsoft.com/library/Ff834707(v=office.15)
ms:contentKeyID: 48547832
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: bcce8eefad7fcad7dee7e46274ffc45125dc36c9
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2018
ms.locfileid: "25475005"
---
# <a name="cursordriverenum-enumeration-dao"></a>CursorDriverEnum Enumeration (DAO)


**Betrifft**: Access 2013 | Office 2013

Gibt den Typ des Cursortreibers an.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Name</p></th>
<th><p>Wert</p></th>
<th><p>Beschreibung</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>dbUseClientBatchCursor</p></td>
<td><p>3</p></td>
<td><p>Verwendet immer die FoxPro-Cursorbibliothek. Diese Option ist für Batchaktualisierungen erforderlich.</p></td>
</tr>
<tr class="even">
<td><p>dbUseDefaultCursor</p></td>
<td><p>-1</p></td>
<td><p>(Standard) Verwendet serverseitige Cursor, wenn diese vom Server unterstützt werden; andernfalls wird die ODBC-Cursorbibliothek verwendet.</p></td>
</tr>
<tr class="odd">
<td><p>dbUseNoCursor</p></td>
<td><p>4</p></td>
<td><p>Öffnet alle Cursor (d. h., <strong>Recordset</strong> -Objekte) als Vorwärtscursor Typ schreibgeschützt, mit der Größe eines Rowsets 1 an. Auch bekannt als &quot;Abfragen ohne Cursor.&quot;</p></td>
</tr>
<tr class="even">
<td><p>dbUseODBCCursor</p></td>
<td><p>1</p></td>
<td><p>Verwendet immer die ODBC-Cursorbibliothek. Diese Option bietet für kleine Resultsets eine bessere Leistung, aber bei umfangreichen Resultsets wird die Leistung schnell beeinträchtigt.</p></td>
</tr>
<tr class="odd">
<td><p>dbUseServerCursor</p></td>
<td><p>2</p></td>
<td><p>Verwendet immer serverseitige Cursor. Für die meisten umfangreichen Vorgänge bietet diese Option eine bessere Leistung; sie kann jedoch mehr Netzwerkverkehr verursachen.</p></td>
</tr>
</tbody>
</table>
