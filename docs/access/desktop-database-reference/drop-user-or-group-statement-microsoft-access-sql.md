---
title: DROP USER-oder GROUP-Anweisung (Microsoft Access SQL)
TOCTitle: DROP USER or GROUP statement (Microsoft Access SQL)
ms:assetid: 46bc5916-556b-17df-2f4c-8fd7bbd21ef7
ms:mtpsurl: https://msdn.microsoft.com/library/Ff193192(v=office.15)
ms:contentKeyID: 48544575
ms.date: 10/18/2018
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 995f935ceea5af3b740215c5a4137e02e7ebb1b2
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32293644"
---
# <a name="drop-user-or-group-statement-microsoft-access-sql"></a>DROP USER-oder GROUP-Anweisung (Microsoft Access SQL)

**Gilt für**: Access 2013, Office 2013

Löscht einen oder mehrere vorhandene *Benutzer* oder *Gruppen*oder entfernt einen oder mehrere vorhandene *Benutzer* aus einer vorhandenen *Gruppe*.

## <a name="syntax"></a>Syntax

### <a name="delete-one-or-more-users-or-remove-one-or-more-users-from-a-group"></a>Löschen eines oder mehrerer Benutzer oder Entfernen eines oder mehrerer Benutzer aus einer Gruppe

Benutzer Benutzer **\[, Benutzer **,... \] \[ **\]

### <a name="delete-one-or-more-groups"></a>Löschen einer oder mehrerer Gruppen

Drop Group *Group*\[, *Group*,...\]

Die DROP USER- oder GROUP-Anweisung besteht aus folgenden Komponenten:

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
<td><p><em>user</em></p></td>
<td><p>Der Name eines Benutzers, der aus der Informationsdatei für die Arbeitsgruppe entfernt werden soll.</p></td>
</tr>
<tr class="even">
<td><p><em>group</em></p></td>
<td><p>Der Name einer Gruppe, die aus der Informationsdatei für die Arbeitsgruppe entfernt werden soll.</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>Bemerkungen

Wenn das FROM-Schlüsselwort in der DROP USER-Anweisung verwendet wird, werden alle in der Anweisung aufgeführten *Benutzer* aus der nach dem Schlüsselwort from angegebenen *Gruppe* entfernt. Die *Benutzer* selbst werden jedoch nicht gelöscht.

Die DROP GROUP-Anweisung dient zum Löschen der angegebenen *Grupppe*(n). Die *Benutzer* , die Mitglieder der *Gruppe*(n) sind, sind nicht betroffen, Sie sind jedoch nicht mehr Mitglied der gelöschten *Gruppe*(n).

