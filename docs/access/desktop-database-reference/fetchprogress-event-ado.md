---
title: FetchProgress-Ereignis (ADO)
TOCTitle: FetchProgress event (ADO)
ms:assetid: 09145d9a-ea5e-b41c-6c54-33ec83e642a9
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248828(v=office.15)
ms:contentKeyID: 48543114
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: d863f51e7836acdc577ecd720df77114ed66f067
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32293182"
---
# <a name="fetchprogress-event-ado"></a>FetchProgress-Ereignis (ADO)

**Gilt für**: Access 2013, Office 2013

Das **FetchProgress**-Ereignis wird regelmäßig während einer langen asynchronen Operation aufgerufen, um einen Bericht darüber zu erstellen, wie viele zusätzliche Zeilen derzeit in das [Recordset](recordset-object-ado.md) abgerufen wurden.

## <a name="syntax"></a>Syntax

FetchProgress*Progress*, *MaxProgress*, *Status*, precordset **

## <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|:--------|:----------|
|*Progress* |Ein **Long** -Wert, der die Anzahl von Datensätzen angibt, die derzeit mit der Fetch-Operation abgerufen wurden.|
|*MaxProgress* |Ein **Long** -Wert, der die maximale Anzahl von Datensätzen angibt, die erwartungsgemäß abgerufen werden.|
|*adStatus* |Ein [EventStatusEnum](eventstatusenum.md)-Statuswert.|
|*precordset* |Ein **Recordset** -Objekt, das das Objekt darstellt, für das die Datensätze abgerufen werden.|

## <a name="remarks"></a>Bemerkungen

Wenn **FetchProgress** mit einem untergeordneten **Recordset**-Objekt verwendet wird, ist zu beachten, dass die *Progress*- und *MaxProgress*-Parameterwerte vom zugrunde liegenden [Microsoft Cursor Service für OLE DB](microsoft-cursor-service-for-ole-db-ado-service-component.md)-Rowset abgeleitet werden. Die zurückgegebenen Werte stellen die Gesamtanzahl von Datensätzen im zugrunde liegenden Rowset dar, nicht nur die Anzahl von Datensätzen im aktuellen Kapitel.

> [!NOTE]
> [!HINWEIS] Um **FetchProgress** mit Microsoft Visual Basic zu verwenden, ist Visual Basic 6.0 oder höher erforderlich.


