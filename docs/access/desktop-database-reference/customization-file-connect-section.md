---
title: Anpassungsdatei – Verbindungsabschnitt
TOCTitle: Customization File Connect section
ms:assetid: 037abfb4-798d-4b09-6133-356969aee95c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248802(v=office.15)
ms:contentKeyID: 48542985
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 8652aa2c028350aab79cdf101cba189026b9a5ae
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32295142"
---
# <a name="customization-file-connect-section"></a>Anpassungsdatei – Verbindungsabschnitt

**Gilt für**: Access 2013, Office 2013

Das Verweigern aller Verbindungen ist das Standardverhalten des Handlers. Im **connect** -Abschnitt werden Ausnahmen für dieses Verhalten angegeben. Wenn z. B. alle **connect** -Abschnitte nicht vorhanden oder leer sind, können standardmäßig keine Verbindungen hergestellt werden.

Der **connect** -Abschnitt kann Folgendes enthalten:

- Einen Standardzugriffseintrag, in dem die für diese Verbindung zulässigen Standardlese- und -schreiboperationen angegeben werden. Wenn im Abschnitt kein Standardzugriffseintrag vorhanden ist, wird der Abschnitt ignoriert.

- Eine neue Verbindungszeichenfolge, durch die die Clientverbindungszeichenfolge ersetzt wird.

## <a name="syntax"></a>Syntax

Ein Standardzugriffseintrag hat folgendes Format:

`Access=accessRight`

Ein Eintrag für eine Ersetzungsverbindungszeichenfolge hat folgendes Format:

`Connect=connectionString`

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Teil</p></th>
<th><p>Beschreibung</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Connect</strong></p></td>
<td><p>Eine literale Zeichenfolge, durch die angegeben wird, dass es sich um einen Verbindungszeichenfolgeneintrag handelt.</p></td>
</tr>
<tr class="even">
<td><p><strong><em>connectionString</em></strong></p></td>
<td><p>Eine Zeichenfolge, durch die die gesamte Clientverbindungszeichenfolge ersetzt wird.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Access</strong></p></td>
<td><p>Eine literale Zeichenfolge, durch die angegeben wird, dass es sich um einen Zugriffseintrag handelt.</p></td>
</tr>
<tr class="even">
<td><p><strong><em>accessRight</em></strong></p></td>
<td><p>Eines der folgenden Zugriffsrechte:</p>
<p></p>
<ul>
<li><p><strong>NoAccess</strong> - Benutzer kann nicht auf die Datenquelle zugreifen.</p></li>
<li><p><strong>ReadOnly</strong> - Benutzer kann die Datenquelle lesen.</p></li>
<li><p><strong>ReadWrite</strong> - Benutzer kann in der Datenquelle lesen oder schreiben.</p></li>
</ul>
<p></p></td>
</tr>
</tbody>
</table>


Wenn Sie eine Verbindung zulassen möchten (in der Tat das standardmäßige Handler-Verhalten deaktivieren), legen Sie den Zugriffseintrag im **Standardabschnitt Connect** auf fest, und löschen oder kommentieren Sie einen anderen Abschnitt **Connect** *Identifier* aus.

