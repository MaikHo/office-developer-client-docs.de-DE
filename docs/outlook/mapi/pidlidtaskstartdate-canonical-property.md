---
title: Kanonische PidLidTaskStartDate-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskStartDate
api_type:
- COM
ms.assetid: fe87eb3d-21d1-45bb-b848-e141ce1be6a0
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 486b1f913e7c3c76886232c48fa842e25e1f7905
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19793854"
---
# <a name="pidlidtaskstartdate-canonical-property"></a><span data-ttu-id="45266-103">Kanonische PidLidTaskStartDate-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="45266-103">PidLidTaskStartDate Canonical Property</span></span>

  
  
<span data-ttu-id="45266-104">**Betrifft**: Outlook</span><span class="sxs-lookup"><span data-stu-id="45266-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="45266-105">Das Datum, wenn der Benutzer für den Task erwartet.</span><span class="sxs-lookup"><span data-stu-id="45266-105">The date when the user expects to begin the task.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="45266-106">Zugeordneten Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="45266-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="45266-107">dispidTaskStartDate</span><span class="sxs-lookup"><span data-stu-id="45266-107">dispidTaskStartDate</span></span>  <br/> |
|<span data-ttu-id="45266-108">-Eigenschaft festgelegt:</span><span class="sxs-lookup"><span data-stu-id="45266-108">Property set:</span></span>  <br/> |<span data-ttu-id="45266-109">PSETID_Task</span><span class="sxs-lookup"><span data-stu-id="45266-109">PSETID_Task</span></span>  <br/> |
|<span data-ttu-id="45266-110">Long-ID (Abdeckung):</span><span class="sxs-lookup"><span data-stu-id="45266-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="45266-111">0x00008104</span><span class="sxs-lookup"><span data-stu-id="45266-111">0x00008104</span></span>  <br/> |
|<span data-ttu-id="45266-112">Datentyp:</span><span class="sxs-lookup"><span data-stu-id="45266-112">Data type:</span></span>  <br/> |<span data-ttu-id="45266-113">PT_SYSTIME</span><span class="sxs-lookup"><span data-stu-id="45266-113">PT_SYSTIME</span></span>  <br/> |
|<span data-ttu-id="45266-114">Bereich:</span><span class="sxs-lookup"><span data-stu-id="45266-114">Area:</span></span>  <br/> |<span data-ttu-id="45266-115">Aufgabe</span><span class="sxs-lookup"><span data-stu-id="45266-115">Task</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="45266-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="45266-116">Remarks</span></span>

<span data-ttu-id="45266-117">Wenn der Wert dieser Eigenschaft nicht festgelegt lassen, hat die Aufgabe ein Startdatum keinen.</span><span class="sxs-lookup"><span data-stu-id="45266-117">If this property value is left unset, the task does not have a start date.</span></span> <span data-ttu-id="45266-118">Der Wert "0x5AE980E0" (1,525,252,320) bedeutet auch, dass die Aufgabe ein Startdatum nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="45266-118">A value of "0x5AE980E0" (1,525,252,320) also means that the task does not have a start date.</span></span> <span data-ttu-id="45266-119">Wenn der Vorgang ein Startdatum hat, der Wert muss eine Zeitkomponente Mitternacht haben, und die **DispidTaskDueDate** ([PidLidTaskDueDate](pidlidtaskduedate-canonical-property.md)) und **DispidCommonStart** ([PidLidCommonStart](pidlidcommonstart-canonical-property.md)) Eigenschaften müssen ebenfalls festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="45266-119">If the task has a start date, the value must have a time component of midnight, and the **dispidTaskDueDate** ([PidLidTaskDueDate](pidlidtaskduedate-canonical-property.md)) and **dispidCommonStart** ([PidLidCommonStart](pidlidcommonstart-canonical-property.md)) properties must also be set.</span></span>
  
<span data-ttu-id="45266-120">Diese Eigenschaft wird von der Informationszwecken kennzeichnen Protokollspezifikation gemeinsam genutzt und Task-Related Object Protokoll Specification befindet sich in [[MS-OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="45266-120">This property is shared by the Informational Flagging Protocol Specification and Task-Related Object Protocol Specification located in [[MS-OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="45266-121">Verwandte Ressourcen</span><span class="sxs-lookup"><span data-stu-id="45266-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="45266-122">Protokollspezifikationen</span><span class="sxs-lookup"><span data-stu-id="45266-122">Protocol specifications</span></span>

<span data-ttu-id="45266-123">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="45266-123">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="45266-124">Enthält Eigenschaftendefinitionen und Verweise auf Verwandte Exchange Server-Spezifikationen.</span><span class="sxs-lookup"><span data-stu-id="45266-124">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="45266-125">[[MS-OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="45266-125">[[MS-OXOTASK]](http://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="45266-126">Gibt die Eigenschaften und Operationen, die auf Kontakte und persönliche Verteilerlisten zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="45266-126">Specifies the properties and operations that are permissible on contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="45266-127">Header-Dateien</span><span class="sxs-lookup"><span data-stu-id="45266-127">Header files</span></span>

<span data-ttu-id="45266-128">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="45266-128">Mapidefs.h</span></span>
  
> <span data-ttu-id="45266-129">Enthält die Datentypdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="45266-129">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="45266-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="45266-130">See also</span></span>



[<span data-ttu-id="45266-131">Kanonische PidLidTaskDueDate-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="45266-131">PidLidTaskDueDate Canonical Property</span></span>](pidlidtaskduedate-canonical-property.md)
  
[<span data-ttu-id="45266-132">Kanonische PidLidCommonStart-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="45266-132">PidLidCommonStart Canonical Property</span></span>](pidlidcommonstart-canonical-property.md)


[<span data-ttu-id="45266-133">MAPI-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="45266-133">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="45266-134">Kanonische MAPI-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="45266-134">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="45266-135">Zuordnen von kanonischen Eigenschaftennamen zu MAPI-Namen</span><span class="sxs-lookup"><span data-stu-id="45266-135">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="45266-136">Zuordnen von MAPI-Namen zu kanonische Eigenschaftennamen</span><span class="sxs-lookup"><span data-stu-id="45266-136">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)
