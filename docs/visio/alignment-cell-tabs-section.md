---
title: Zelle "Alignment" (Abschnitt "Tabs")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm35
localization_priority: Normal
ms.assetid: 84234177-a2df-6acc-2761-230bc5d12627
description: Legt die Tabausrichtung fest.
ms.openlocfilehash: 461357c9c838fb4c0e5b0159bf027dd6adce26f9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425540"
---
# <a name="alignment-cell-tabs-section"></a>Zelle "Alignment" (Abschnitt "Tabs")

Legt die Tabausrichtung fest.
  
|**Wert**|**Alignment**|**Automatisierungskonstante**|
|:-----|:-----|:-----|
| 0  <br/> | Left  <br/> |**visTabStopLeft** <br/> |
| 1  <br/> | Zentriert  <br/> |**visTabStopCenter** <br/> |
| 2  <br/> | Nach rechts  <br/> |**visTabStopRight** <br/> |
| 3  <br/> | Decimal  <br/> |**visTabStopDecimal** <br/> |
| 4  <br/> | Komma  <br/> |**visTabStopComma** <br/> |
   
## <a name="remarks"></a>Bemerkungen

Wenn Sie einen Verweis auf die Zelle Alignment aus einer anderen Formel oder aus einem Programm mithilfe der **CellsU** -Eigenschaft nach Namen erhalten möchten, verwenden Sie Folgendes: 
  
|||
|:-----|:-----|
| Zellenname:  <br/> | Registerkarten.  *IJ* , wobei *i und j =* <1>, 2, 3  <br/> |
   
Wenn Sie einen Verweis auf die Zelle Alignment aus einem Programm nach Index erhalten möchten, verwenden Sie die **CellsSRC** -Eigenschaft mit folgenden Argumenten: 
  
|||
|:-----|:-----|
| Abschnittsindex:  <br/> |**visSectionTab** <br/> |
| Zeilenindex:  <br/> |**visRowTab +** *i* wobei *i* = 0, 1, 2...  <br/> |
| Zellenindex:  <br/> | (*j* * 3) **+ visTabAlign** <br/> |
   

