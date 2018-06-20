---
title: Zelle "LockThemeColors" (Abschnitt "Protection")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- vis_sdr.chm70001
localization_priority: Normal
ms.assetid: 22cedeb3-58b5-3932-9252-5c9dd3e163e3
ms.openlocfilehash: 2ca8af2c7a41259af73a111af331ce1031e5f46c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/15/2018
ms.locfileid: "19797398"
---
# <a name="lockthemecolors-cell-protection-section"></a><span data-ttu-id="b7842-102">LockThemeColors Cell (Protection Section)</span><span class="sxs-lookup"><span data-stu-id="b7842-102">LockThemeColors Cell (Protection Section)</span></span>

<span data-ttu-id="b7842-103">Verhindert, dass Designfarben auf das Shape angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="b7842-103">Prevents application of theme colors to the shape.</span></span> 
  
<span data-ttu-id="b7842-104">Der Wert der Zelle LockThemeColors entspricht der Einstellung für das Kontrollkästchen **von Designfarben** im Dialogfeld **Schutz** .</span><span class="sxs-lookup"><span data-stu-id="b7842-104">The value of the LockThemeColors cell corresponds to the **From theme colors** check box setting in the **Protection** dialog box.</span></span> 
  
<span data-ttu-id="b7842-105">Auf die Zelle LockThemeColors aus einer anderen Formel oder aus einem Programm mithilfe der **CellsU** -Eigenschaft nach Namen verweisen verwenden:</span><span class="sxs-lookup"><span data-stu-id="b7842-105">To refer to the LockThemeColors cell by name from another formula, or from a program, using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="b7842-106">Zellenname:</span><span class="sxs-lookup"><span data-stu-id="b7842-106">Cell name:</span></span>  <br/> |<span data-ttu-id="b7842-107">LockThemeColors</span><span class="sxs-lookup"><span data-stu-id="b7842-107">LockThemeColors</span></span>  <br/> |
   
<span data-ttu-id="b7842-108">Wenn Sie auf die Zelle LockThemeColors durch Index aus einem Programm verweisen möchten, verwenden Sie die **CellsSRC** -Eigenschaft mit folgenden Argumenten:</span><span class="sxs-lookup"><span data-stu-id="b7842-108">To refer to the LockThemeColors cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="b7842-109">Abschnittsindex:</span><span class="sxs-lookup"><span data-stu-id="b7842-109">Section index:</span></span>  <br/> |<span data-ttu-id="b7842-110">**Konstanten visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="b7842-110">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="b7842-111">Zeilenindex:</span><span class="sxs-lookup"><span data-stu-id="b7842-111">Row index:</span></span>  <br/> |<span data-ttu-id="b7842-112">**visRowLock**</span><span class="sxs-lookup"><span data-stu-id="b7842-112">**visRowLock**</span></span> <br/> |
|<span data-ttu-id="b7842-113">Zellenindex:</span><span class="sxs-lookup"><span data-stu-id="b7842-113">Cell index:</span></span>  <br/> |<span data-ttu-id="b7842-114">**visLockThemeColors**</span><span class="sxs-lookup"><span data-stu-id="b7842-114">**visLockThemeColors**</span></span> <br/> |
   
