---
title: Ordinal-Eigenschaft (ADO MD Cell)
TOCTitle: Ordinal Property (ADO MD Cell)
ms:assetid: be705823-6c5e-0c8f-f780-87df19423a72
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249924(v=office.15)
ms:contentKeyID: 48547462
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 284e2cac2c1a86d87e39d9913a262fbafb435ece
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2018
ms.locfileid: "25473397"
---
# <a name="ordinal-property-ado-md-cell"></a>Ordinal-Eigenschaft (ADO MD Cell)


**Betrifft**: Access 2013 | Office 2013

Identifiziert eine Zelle eindeutig durch ihre Position innerhalb einer Zellmenge.

## <a name="return-values"></a>Rückgabewerte

Gibt einen schreibgeschützten, ganzzahligen **Long** -Wert zurück.

## <a name="remarks"></a>Hinweise

Durch den Ordnungswert einer Zelle wird die Zelle innerhalb einer Zellmenge eindeutig identifiziert. Bei diesem Konzept sind die Zellen in einer Zellmenge nummeriert, als wäre die Zellmenge ein *p*-dimensionales Array, wobei *p* die Anzahl der [Achsen](axes-collection-ado-md.md) darstellt. Zellen sind zeilenweise nummeriert (beginnend bei 0).

Der Ordnungswert der Zelle kann mit der [Item](item-property-ado-md-cellset.md)-Eigenschaft des [Cellset](cellset-object-ado-md.md)-Objekts verwendet werden, um die [Zelle](cell-object-ado-md.md) schnell abzurufen.
