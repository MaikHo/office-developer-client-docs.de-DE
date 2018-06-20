---
title: Zelle "LockGroup" (Abschnitt "Protection")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251227
localization_priority: Normal
ms.assetid: 04b0fa5b-1680-cfe2-6aaf-0502ad196027
description: Sperrt eine Gruppe, damit die Gruppierung nicht aufgehoben werden kann.
ms.openlocfilehash: 4d09d514a3fff8ada40c67eb9cd9537539a1039a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/15/2018
ms.locfileid: "19797396"
---
# <a name="lockgroup-cell-protection-section"></a><span data-ttu-id="d1433-103">LockGroup Cell (Protection Section)</span><span class="sxs-lookup"><span data-stu-id="d1433-103">LockGroup Cell (Protection Section)</span></span>

<span data-ttu-id="d1433-104">Sperrt eine Gruppe, damit die Gruppierung nicht aufgehoben werden kann.</span><span class="sxs-lookup"><span data-stu-id="d1433-104">Locks a group so that it cannot be ungrouped.</span></span>
  
|<span data-ttu-id="d1433-105">**Wert**</span><span class="sxs-lookup"><span data-stu-id="d1433-105">**Value**</span></span>|<span data-ttu-id="d1433-106">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="d1433-106">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d1433-107">TRUE</span><span class="sxs-lookup"><span data-stu-id="d1433-107">TRUE</span></span>  <br/> |<span data-ttu-id="d1433-108">Gruppierung der Gruppe kann nicht aufgehoben werden.</span><span class="sxs-lookup"><span data-stu-id="d1433-108">Group cannot be ungrouped.</span></span>  <br/> |
|<span data-ttu-id="d1433-109">FALSE</span><span class="sxs-lookup"><span data-stu-id="d1433-109">FALSE</span></span>  <br/> |<span data-ttu-id="d1433-110">Gruppierung der Gruppe kann aufgehoben werden.</span><span class="sxs-lookup"><span data-stu-id="d1433-110">Group can be ungrouped.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d1433-111">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="d1433-111">Remarks</span></span>

<span data-ttu-id="d1433-112">Wenn Sie den Wert für LockGroupCell auf TRUE festlegen, wird auch das Löschen von Shapes verhindert, die Mitglieder der Gruppe sind.</span><span class="sxs-lookup"><span data-stu-id="d1433-112">Setting the LockGroupCell value to TRUE also prevents deletion of any shapes that are members of the group.</span></span>
  
<span data-ttu-id="d1433-113">Wenn Sie einen Verweis auf die Zelle LockGroup nach Namen aus einer anderen Formel oder aus einem Programm mithilfe der **CellsU** -Eigenschaft erhalten möchten, verwenden Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="d1433-113">To get a reference to the LockGroup cell by name from another formula, or from a program using the **CellsU** property, use:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d1433-114">Zellenname:</span><span class="sxs-lookup"><span data-stu-id="d1433-114">Cell name:</span></span>  <br/> |<span data-ttu-id="d1433-115">LockGroup</span><span class="sxs-lookup"><span data-stu-id="d1433-115">LockGroup</span></span>  <br/> |
   
<span data-ttu-id="d1433-116">Wenn Sie einen Verweis auf die Zelle LockGroup aus einem Programm nach Index erhalten möchten, verwenden Sie die **CellsSRC** -Eigenschaft mit folgenden Argumenten:</span><span class="sxs-lookup"><span data-stu-id="d1433-116">To get a reference to the LockGroup cell by index from a program, use the **CellsSRC** property with the following arguments:</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d1433-117">Abschnittsindex:</span><span class="sxs-lookup"><span data-stu-id="d1433-117">Section index:</span></span>  <br/> |<span data-ttu-id="d1433-118">**Konstanten visSectionObject**</span><span class="sxs-lookup"><span data-stu-id="d1433-118">**visSectionObject**</span></span> <br/> |
|<span data-ttu-id="d1433-119">Zeilenindex:</span><span class="sxs-lookup"><span data-stu-id="d1433-119">Row index:</span></span>  <br/> |<span data-ttu-id="d1433-120">**visRowLock**</span><span class="sxs-lookup"><span data-stu-id="d1433-120">**visRowLock**</span></span> <br/> |
|<span data-ttu-id="d1433-121">Zellenindex:</span><span class="sxs-lookup"><span data-stu-id="d1433-121">Cell index:</span></span>  <br/> |<span data-ttu-id="d1433-122">**visLockGroup**</span><span class="sxs-lookup"><span data-stu-id="d1433-122">**visLockGroup**</span></span> <br/> |
   
