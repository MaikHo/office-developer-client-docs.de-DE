---
title: QueryDef.DateCreated Property (DAO)
TOCTitle: DateCreated Property
ms:assetid: f7585b34-8314-fb9f-daa6-cd1a8ad59d91
ms:mtpsurl: https://msdn.microsoft.com/library/Ff836910(v=office.15)
ms:contentKeyID: 48548763
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 62fcad68a50ac7f2a09675d9ac51734c4147d207
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2018
ms.locfileid: "25475598"
---
# <a name="querydefdatecreated-property-dao"></a>QueryDef.DateCreated Property (DAO)


**Betrifft**: Access 2013 | Office 2013

Gibt das Datum und die Uhrzeit der Objekterstellung zurück (nur Microsoft Access-Arbeitsbereiche). Schreibgeschützter **Variant**-Wert.

## <a name="syntax"></a>Syntax

*Ausdruck* . DateCreated

*Ausdruck* Eine Variable, die ein **QueryDef** -Objekt darstellt.

## <a name="remarks"></a>Bemerkungen

DateCreated und LastUpdated geben das Datum und die Uhrzeit der Erstellung oder der letzen Aktualisierung des Objekts zurück. In einer Mehrbenutzerumgebung sollten Benutzer diese Einstellungen direkt vom Dateiserver erhalten, um Diskrepanzen bei den Einstellungen der Eigenschaften DateCreated und LastUpdated zu vermeiden.
