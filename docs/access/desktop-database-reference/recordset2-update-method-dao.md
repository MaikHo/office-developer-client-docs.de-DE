---
title: Recordset2. Update-Methode (DAO)
TOCTitle: Update Method
ms:assetid: 1b47606a-e79c-23f1-b120-46d1429bc167
ms:mtpsurl: https://msdn.microsoft.com/library/Ff845700(v=office.15)
ms:contentKeyID: 48543537
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052882
f1_categories:
- Office.Version=v15
localization_priority: Normal
ms.openlocfilehash: 4259da0eb48e7ff13e246b326cc6e96d7a916ea7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32307168"
---
# <a name="recordset2update-method-dao"></a>Recordset2. Update-Methode (DAO)

**Gilt für**: Access 2013, Office 2013

## <a name="syntax"></a>Syntax

*Ausdruck* . Update (***UpdateType***, ***Force***)

*Ausdruck* Eine Variable, die ein **Recordset2** -Objekt darstellt.

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
<td><p><em>Aktualisierungstyp</em></p></td>
<td><p>Optional</p></td>
<td><p><strong>Long</strong></p></td>
<td><p>Eine <strong><a href="updatetypeenum-enumeration-dao.md">UpdateTypeEnum</a></strong> -Konstante, die den Aktualisierungstyp so angibt, wie er in den Einstellungen angegeben ist (nur ODBCDirect-Arbeitsbereiche).</p></td>
</tr>
<tr class="even">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p><strong>Boolean</strong></p></td>
<td><p>Ein <strong>Boolean</strong>-Wert, der angibt, ob die Änderungen in der Datenbank erzwungen werden sollen, unabhängig davon, ob die zugrunde liegenden Daten seit dem <strong><a href="recordset-addnew-method-dao.md">AddNew</a></strong>-, <strong><a href="fields-delete-method-dao.md">Delete</a></strong>- oder <strong><a href="recordset2-edit-method-dao.md">Edit</a></strong>-Aufruf von einem anderen Benutzer geändert wurden. Ist <strong>True</strong> festgelegt, werden die Änderungen erzwungen, und die von anderen Benutzern vorgenommenen Änderungen werden einfach überschrieben. Bei <strong>False</strong> (Standard) verursachen Änderungen, die andere Benutzer vorgenommen haben, während die Aktualisierung ausstand, ein Fehlschlagen der Aktualisierung für die Änderungen, bei denen Konflikte bestehen. Es tritt kein Fehler auf, aber die <strong><a href="recordset-batchcollisioncount-property-dao.md">BatchCollisionCount</a></strong> -und <strong>BatchCollisions</strong> -Eigenschaften geben die Anzahl von Konflikten und die von Konflikten betroffenen Zeilen an (nur ODBCDirect-Arbeitsbereiche).</p></td>
</tr>
</tbody>
</table>


## <a name="remarks"></a>Bemerkungen

Verwenden Sie **Update**, um den aktuellen Datensatz und alle Änderungen, die Sie daran vorgenommen haben, zu speichern.

> [!IMPORTANT]
> [!WICHTIG] Änderungen an dem aktuellen Datensatz gehen in folgenden Fällen verloren:
> - Sie verwenden die **Edit**- oder **AddNew**-Methode und wechseln dann zu einem anderen Datensatz, ohne zuvor **Update** zu verwenden.
> - Sie verwenden **Edit** oder **AddNew** und dann erneut **Edit** oder **AddNew**, ohne zuvor **Update** zu verwenden.
> - Sie legen die **[Bookmark](recordset2-bookmark-property-dao.md)** -Eigenschaft auf einen anderen Datensatz fest.
> - Sie schließen das **Recordset**, ohne zuvor **Update** zu verwenden.
> - Sie brechen den **Edit**-Vorgang ab, indem Sie **[CancelUpdate](recordset2-cancelupdate-method-dao.md)** verwenden.

Wenn Sie einen Datensatz bearbeiten möchten, verwenden Sie die **Edit**-Methode, um den Inhalt des aktuellen Datensatzes in den Kopierpuffer zu kopieren. Ohne vorheriges Anwenden von **Edit** tritt ein Fehler auf, sobald Sie **Update** verwenden oder versuchen, den Wert eines Felds zu ändern.

In einem ODBCDirect-Arbeitsbereich können Sie Batchaktualisierungen vornehmen, wenn die Cursor-Bibliothek dies unterstützt und das **Recordset** mit der Option der optimistischen Batchsperre geöffnet wurde.

Ist in einem Microsoft Access-Arbeitsbereich die **LockEdits**-Eigenschafteneinstellung eines **Recordset**-Objekts in einer Mehrbenutzerumgebung auf **True** festgelegt (pessimistisch gesperrt), bleibt der Datensatz ab dem Moment gesperrt, in dem **Edit** verwendet wird, bis zu dem Zeitpunkt, zu dem die **Update**-Methode ausgeführt oder die Bearbeitung abgebrochen wird. Wenn die **LockEdits**-Eigenschafteneinstellung auf **False** festgelegt ist (optimistisch gesperrt), wird der Datensatz gesperrt und mit dem vorab bearbeiteten Datensatz verglichen, bevor er in der Datenbank aktualisiert wird. Wurde der Datensatz nach dem Verwenden der **Edit**-Methode geändert, schlägt der **Update**-Vorgang fehl. Die mit einem Microsoft Access-Datenbankmodul verbundenen ODBC- und installierbaren ISAM-Datenbanken verwenden immer optimistische Sperren. Verwenden Sie erneut die **Update**-Methode, um den **Update**-Vorgang mit Ihren Änderungen fortzusetzen. Um den Datensatz auf die Änderung des anderen Benutzers zurückzusetzen, aktualisieren Sie den aktuellen Datensatz mit Move 0.

> [!NOTE]
> [!HINWEIS] Es muss ein eindeutiger Index für den Datensatz in der zugrunde liegenden Datenquelle vorhanden sein, damit ein Datensatz hinzugefügt, bearbeitet oder gelöscht werden kann. Andernfalls tritt im Methodenaufruf **AddNew**, **Delete** oder **Edit** in einem Microsoft Access-Arbeitsbereich ein Fehler vom Typ "Berechtigung verweigert" auf, oder im **Update**-Aufruf in einem ODBCDirect-Arbeitsbereich tritt ein Fehler vom Typ "Ungültiges Argument" auf.


