---
title: Refresh-Methode (ADO)
TOCTitle: Refresh Method (ADO)
ms:assetid: f1c8829f-9c7d-12b6-7470-727ff38d663e
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250227(v=office.15)
ms:contentKeyID: 48548631
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 1ea277f83c39bde4b5309a26b87961ff2325b145
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2018
ms.locfileid: "25472885"
---
# <a name="refresh-method-ado"></a>Refresh-Methode (ADO)


**Betrifft**: Access 2013 | Office 2013

Die Objekte in einer Auflistung werden aktualisiert, um Objekte widerzuspiegeln, die vom Anbieter verfügbar sind und spezifisch für diesen sind.

## <a name="syntax"></a>Syntax

*Auflistung*. Aktualisieren

## <a name="remarks"></a>Hinweise

Abhängig von der Auflistung, aus der Sie die **Refresh** -Methode aufrufen, werden unterschiedliche Tasks ausgeführt.

## <a name="parameters"></a>Parameter

Durch Verwenden der **Refresh** -Methode für die [Parameters](command-object-ado.md)-Auflistung eines [Command](parameters-collection-ado.md)-Objekts werden anbieterseitige Parameterinformationen für die im **Command** -Objekt angegebene gespeicherte Prozedur oder parametrisierte Abfrage abgerufen. Für Anbieter, die Aufrufe gespeicherter Prozeduren oder parametrisierte Abfragen nicht unterstützen, ist die Auflistung leer.

Legen Sie die [ActiveConnection](activeconnection-property-ado.md)-Eigenschaft des **Command** -Objekts auf ein gültiges [Connection](connection-object-ado.md)-Objekt, die [CommandText](commandtext-property-ado.md)-Eigenschaft auf einen gültigen Befehl und die [CommandType](commandtype-property-ado.md)-Eigenschaft auf **adCmdStoredProc** fest, bevor Sie die **Refresh** -Methode aufrufen.

Wenn Sie vor dem Aufrufen der **Refresh** -Methode auf die **Parameters** -Auflistung zugreifen, wird die Methode automatisch von ADO aufgerufen, und die Auflistung wird aufgefüllt.


> [!NOTE]
> <P>Wenn Sie die Refresh-Methode zum Abrufen von Parameterinformationen vom Anbieter verwenden und mindestens ein Parameter-Objekt mit dem variable-length-Datentyp zurückgegeben wird, wird der Speicher für die Parameter von ADO möglicherweise basierend auf der potenziellen Maximalgröße zugeordnet. Dies verursacht einen Fehler bei der Ausführung. Legen Sie die Size-Eigenschaft für diese Parameter vor dem Aufrufen der Execute-Methode explizit fest, um Fehler zu verhindern.</P>



**Fields**

Das Verwenden der **Refresh** -Methode für die **Fields** -Auflistung hat keine sichtbare Auswirkung. Zum Abrufen von Änderungen aus der zugrunde liegenden Datenbankstruktur müssen Sie entweder die [Requery](requery-method-ado.md)-Methode oder, wenn Textmarken vom [Recordset](recordset-object-ado.md)-Objekt nicht unterstützt werden, die [MoveFirst](movefirst-movelast-movenext-and-moveprevious-methods-ado.md)-Methode verwenden.

**Eigenschaften**

Durch Verwenden der **Refresh** -Methode für eine **Properties** -Auflistung mancher Objekte wird die Auflistung mit den vom Anbieter verfügbar gemachten dynamischen Eigenschaften aufgefüllt. Durch diese Eigenschaften werden Informationen zu anbieterspezifischer Funktionalität bereitgestellt, die über die von ADO unterstützten integrierten Eigenschaften hinausgeht.
