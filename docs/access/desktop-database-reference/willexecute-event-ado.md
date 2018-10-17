---
title: WillExecute-Ereignis (ADO)
TOCTitle: WillExecute Event (ADO)
ms:assetid: 9f516bfd-246d-9817-4ca3-64598ab466f7
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249732(v=office.15)
ms:contentKeyID: 48546686
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 8a5c739ffd408a1f53539c88a3bdc4169eb4cebe
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2018
ms.locfileid: "25472981"
---
# <a name="willexecute-event-ado"></a>WillExecute-Ereignis (ADO)


**Betrifft**: Access 2013 | Office 2013


Das **WillExecute** -Ereignis wird unmittelbar vor dem Ausführen eines ausstehenden Befehls für eine Verbindung aufgerufen.

## <a name="syntax"></a>Syntax

WillExecute*Source*, *CursorType*, *LockType*, *Optionen*, *AdStatus*, *pCommand*, *pCommand*, *pConnection*

## <a name="parameters"></a>Parameter

  - *Source*

  - Ein **String** -Wert, der einen SQL-Befehl oder den Namen einer gespeicherten Prozedur enthält.

  - *CursorType*

  - Ein [CursorTypeEnum](cursortypeenum.md)-Wert, der den Cursortyp für das **Recordset** -Objekt angibt, dass geöffnet wird. Mit diesem Parameter können Sie den Cursor während ein Vorgang zum [Öffnen](open-method-ado-recordset.md) des **Recordset-Objekt** für jede Art ändern. *CursorType* wird für alle anderen Vorgänge ignoriert.

  - *LockType*

  - Ein [LockTypeEnum](locktypeenum.md)-Wert, der den Sperrtyp für das **Recordset** -Objekt enthält, das geöffnet wird. Mit diesem Parameter können Sie beim **Open** -Vorgang des **Recordset** -Objekts die Sperre in einen beliebigen Typ ändern. *LockType* wird für alle anderen Vorgänge ignoriert.

  - *Options*

  - Ein **Long** -Wert, der die Optionen angibt, die zum Ausführen des Befehls oder zum Öffnen des **Recordset** -Objekts verwendet werden können.

  - *adStatus*

  - [EventStatusEnum](eventstatusenum.md)
    
    Legen Sie diesen Parameter vor Rückgabe des Ereignisses auf **adStatusUnwantedEvent** fest, um nachfolgende Benachrichtigungen zu verhindern. Oder legen Sie ihn auf **adStatusCancel** fest, um den Abbruch des das Ereignis verursachenden Vorgangs anzufordern.

  - *pCommand*

  - Das [Command](command-object-ado.md)-Objekt, für das diese Ereignisbenachrichtigung gilt.

  - *pCommand*

  - Das [Recordset](recordset-object-ado.md)-Objekt, für das diese Ereignisbenachrichtigung gilt.

  - *pConnection*

  - Das [Connection](connection-object-ado.md)-Objekt, für das diese Ereignisbenachrichtigung gilt.

## <a name="remarks"></a>Hinweise

**WillExecute** -Ereignis kann aufgrund von Auftreten einer **Verbindung.** [Führen Sie](https://msdn.microsoft.com/library/jj249832\(v=office.15\)) **Befehl.** Wird [ausgeführt](https://msdn.microsoft.com/library/jj248785\(v=office.15\)), oder **Recordset.** [Open](open-method-ado-recordset.md) -Methode *eintreten* sollte immer einen gültigen Verweis auf ein **Connection** -Objekt enthalten. Wenn das Ereignis aufgrund der **Methoden Connection.Execute**, werden die Parameter *pCommand* und *pCommand* auf **Nothing**festgelegt. Ist das Ereignis aufgrund **Recordset.Open**, der *pCommand* -Parameter wird das **Recordset** -Objekt verweisen, und der Parameter *pCommand* auf **Nothing**festgelegt ist. Ist das Ereignis aufgrund von **Command.Execute**, Parameters *pCommand* verweist auf das **Command** -Objekt, und der Parameter *pCommand* auf **Nothing**festgelegt ist.

Mit **WillExecute** können Sie die ausstehenden Ausführungsparameter untersuchen und ändern. Dieses Ereignis kann eine Anforderung zurückgeben, dass der ausstehende Befehl abgebrochen wird.
