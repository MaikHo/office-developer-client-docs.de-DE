---
title: SortDirection-Eigenschaft (RDS)
TOCTitle: SortDirection Property (RDS)
ms:assetid: 33de0dce-f371-6a54-d179-0627939f5b14
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249106(v=office.15)
ms:contentKeyID: 48544119
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 256e6a878e9c3f382bcd65b9138df7a440bf118c
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2018
ms.locfileid: "25475400"
---
# <a name="sortdirection-property-rds"></a>SortDirection-Eigenschaft (RDS)


**Betrifft**: Access 2013 | Office 2013


Gibt eine aufsteigende oder absteigende Sortierreihenfolge an.

## <a name="syntax"></a>Syntax

*DataControl*. SortDirection = *Wert*

## <a name="parameters"></a>Parameter

  - *DataControl*

  - Eine Objektvariable, die ein [RDS.DataControl](datacontrol-object-rds.md)-Objekt darstellt.

  - *Wert*

  - Ein **Boolean** -Wert, der eine aufsteigende Sortierreihenfolge angibt, wenn er auf **True** festgelegt ist. **False** gibt eine absteigende Reihenfolge an.

## <a name="remarks"></a>Hinweise

Die Eigenschaften [SortColumn](sortcolumn-property-rds.md), **SortDirection**, [FilterValue](filtervalue-property-rds.md), [FilterCriterion](filtercriterion-property-rds.md) und [FilterColumn](filtercolumn-property-rds.md) ermöglichen die Sortier- und Filterfunktionalität für den clientbasierten Cache. Mit der Sortierfunktionalität werden Datensätze nach den Werten einer Spalte angeordnet. Mit der Filterfunktionalität werden Teilmengen von Datensätzen anhand von Suchkriterien angezeigt, während das vollständige [Recordset](recordset-object-ado.md)-Objekt im Cache bleibt. Die **Reset** -Methode führt die Kriterien aus und ersetzt das aktuelle **Recordset** -Objekt durch ein aktualisierbares **Recordset** -Objekt.
