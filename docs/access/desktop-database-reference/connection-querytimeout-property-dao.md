---
title: Connection.QueryTimeout Property (DAO)
TOCTitle: QueryTimeout Property
ms:assetid: 97853412-d5ae-7a71-ccaa-595c68919654
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197804(v=office.15)
ms:contentKeyID: 48546471
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1052905
f1_categories:
- Office.Version=v15
ms.openlocfilehash: 51f2f51743a8f92b77fafacebbc18e11eb77fe8a
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2018
ms.locfileid: "25473348"
---
# <a name="connectionquerytimeout-property-dao"></a>Connection.QueryTimeout Property (DAO)


**Betrifft**: Access 2013 | Office 2013

Mit dieser Eigenschaft wird ein Wert festgelegt oder zurückgegeben, der angibt, wie viele Sekunden beim Ausführen einer Abfrage zu einer ODBC-Datenquelle gewartet wird, bevor ein Timeoutfehler auftritt.

## <a name="syntax"></a>Syntax

*Ausdruck* . QueryTimeout

*Ausdruck* Eine Variable, die ein **Connection** -Objekt darstellt.

## <a name="remarks"></a>Bemerkungen

Der Standardwert beträgt 60.

Bei einer ODBC-Datenbank, wie z. B. Microsoft SQL Server, können aufgrund des Netzwerkverkehrs oder einer hohen Belastung des ODBC-Servers Verzögerungen auftreten. Um eine unbegrenzte Wartezeit zu vermeiden, können Sie die Zeit festlegen.

Wenn Sie **QueryTimeout** mit einem **[Connection](connection-object-dao.md)** - oder **[Database](database-object-dao.md)** -Objekt verwenden, wird ein globaler Wert für alle Abfragen festgelegt, die der Datenbank zugeordnet sind. Sie können diesen Wert für eine bestimmte Abfrage außer Kraft setzen, indem Sie die **ODBCTimeout**-Eigenschaft für das betreffende **[QueryDef](querydef-object-dao.md)** -Objekt festlegen.
