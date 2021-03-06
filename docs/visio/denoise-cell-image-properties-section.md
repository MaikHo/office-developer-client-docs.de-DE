---
title: Zelle "Denoise" (Abschnitt "Image Properties")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm225
localization_priority: Normal
ms.assetid: e305585f-f0d8-0494-91d4-0c76929dc170
description: Entfernt Rauschen (Pixel mit wahllos verteilten Farbstufen) aus einem Bitmapbild. Der Standardwert lautet 0 %.
ms.openlocfilehash: f970fde22e864239ea3f3f9bcb704e7f4692e9cc
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415803"
---
# <a name="denoise-cell-image-properties-section"></a>Zelle "Denoise" (Abschnitt "Image Properties")

Entfernt Rauschen (Pixel mit wahllos verteilten Farbstufen) aus einem Bitmapbild. Der Standardwert lautet 0 %.
  
## <a name="remarks"></a>Bemerkungen

Wenn Sie einen Verweis auf die Zelle Denoise aus einer anderen Formel oder aus einem Programm mithilfe der **CellsU** -Eigenschaft nach Namen erhalten möchten, verwenden Sie Folgendes: 
  
|||
|:-----|:-----|
| Zellenname:  <br/> | Denoise  <br/> |
   
Wenn Sie einen Verweis auf die Zelle Denoise aus einem Programm nach Index erhalten möchten, verwenden Sie die **CellsSRC** -Eigenschaft mit folgenden Argumenten: 
  
|||
|:-----|:-----|
| Abschnittsindex:  <br/> |**Konstanten visSectionObject** <br/> |
| Zeilenindex:  <br/> |**visRowImage** <br/> |
| Zellenindex:  <br/> |**visImageDenoise** <br/> |
   

