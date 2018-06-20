---
title: Kanonische PidTagFreeBusyPublishEnd-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagFreeBusyPublishEnd
api_type:
- HeaderDef
ms.assetid: df239741-6a63-4cd4-9bbb-42c0f5c668a5
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 1f7f439b211b60f7acad3a9dd19c50a21923c1cc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19794409"
---
# <a name="pidtagfreebusypublishend-canonical-property"></a><span data-ttu-id="e4baa-103">Kanonische PidTagFreeBusyPublishEnd-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="e4baa-103">PidTagFreeBusyPublishEnd Canonical Property</span></span>

  
  
<span data-ttu-id="e4baa-104">**Betrifft**: Outlook</span><span class="sxs-lookup"><span data-stu-id="e4baa-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="e4baa-105">Die Endzeit des publishing Bereichs enthält.</span><span class="sxs-lookup"><span data-stu-id="e4baa-105">Contains the end time of the publishing range.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="e4baa-106">Zugeordneten Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="e4baa-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="e4baa-107">PR_FREEBUSY_PUBLISH_END</span><span class="sxs-lookup"><span data-stu-id="e4baa-107">PR_FREEBUSY_PUBLISH_END</span></span>  <br/> |
|<span data-ttu-id="e4baa-108">Bezeichner:</span><span class="sxs-lookup"><span data-stu-id="e4baa-108">Identifier:</span></span>  <br/> |<span data-ttu-id="e4baa-109">0x6848</span><span class="sxs-lookup"><span data-stu-id="e4baa-109">0x6848</span></span>  <br/> |
|<span data-ttu-id="e4baa-110">Datentyp:</span><span class="sxs-lookup"><span data-stu-id="e4baa-110">Data type:</span></span>  <br/> |<span data-ttu-id="e4baa-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="e4baa-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="e4baa-112">Bereich:</span><span class="sxs-lookup"><span data-stu-id="e4baa-112">Area:</span></span>  <br/> |<span data-ttu-id="e4baa-113">Frei/Gebucht-Informationen</span><span class="sxs-lookup"><span data-stu-id="e4baa-113">Free/Busy</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e4baa-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e4baa-114">Remarks</span></span>

<span data-ttu-id="e4baa-115">Der Wert für diese Eigenschaft wird auf den Anfangstermin des publishing Bereichs durch Hinzufügen des Werts der **PR_FREEBUSY_COUNT_MONTHS** ([PidTagFreeBusyCountMonths](pidtagfreebusycountmonths-canonical-property.md)) berechnet.</span><span class="sxs-lookup"><span data-stu-id="e4baa-115">The value for this property is computed by adding the value of **PR_FREEBUSY_COUNT_MONTHS** ([PidTagFreeBusyCountMonths](pidtagfreebusycountmonths-canonical-property.md)) to the start date of the publishing range.</span></span> <span data-ttu-id="e4baa-116">Dieser Wert wird als die Anzahl der Minuten seit Mitternacht, 1. Januar 1601 in koordinierter Weltzeit (UTC) ausgedrückt.</span><span class="sxs-lookup"><span data-stu-id="e4baa-116">This value is expressed as the number of minutes since midnight, January 1, 1601 in Coordinated Universal Time (UTC).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="e4baa-117">Verwandte Ressourcen</span><span class="sxs-lookup"><span data-stu-id="e4baa-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="e4baa-118">Protokollspezifikationen</span><span class="sxs-lookup"><span data-stu-id="e4baa-118">Protocol specifications</span></span>

<span data-ttu-id="e4baa-119">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e4baa-119">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e4baa-120">Bietet Verweise auf Verwandte Exchange Server-Spezifikationen.</span><span class="sxs-lookup"><span data-stu-id="e4baa-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="e4baa-121">[[MS-OXOPFFB]](http://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="e4baa-121">[[MS-OXOPFFB]](http://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="e4baa-122">Veröffentlicht die Verfügbarkeit eines Benutzers oder einer Ressource.</span><span class="sxs-lookup"><span data-stu-id="e4baa-122">Publishes the availability of a user or resource.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="e4baa-123">Header-Dateien</span><span class="sxs-lookup"><span data-stu-id="e4baa-123">Header files</span></span>

<span data-ttu-id="e4baa-124">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e4baa-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="e4baa-125">Enthält die Datentypdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="e4baa-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="e4baa-126">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="e4baa-126">Mapitags.h</span></span>
  
> <span data-ttu-id="e4baa-127">Enthält Definitionen von Eigenschaften, die als Alternative Namen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="e4baa-127">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e4baa-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e4baa-128">See also</span></span>



[<span data-ttu-id="e4baa-129">MAPI-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="e4baa-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="e4baa-130">Kanonische MAPI-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="e4baa-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="e4baa-131">Zuordnen von kanonischen Eigenschaftennamen zu MAPI-Namen</span><span class="sxs-lookup"><span data-stu-id="e4baa-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="e4baa-132">Zuordnen von MAPI-Namen zu kanonische Eigenschaftennamen</span><span class="sxs-lookup"><span data-stu-id="e4baa-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)
