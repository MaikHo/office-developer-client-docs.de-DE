---
title: Kanonische PidTagScheduleInfoMonthsBusy-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_type:
- COM
ms.assetid: b15447d6-89aa-40ad-93fc-21fbfa5e3d0e
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 293e8648374b61784f5bda0db124506f345b2701
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19795105"
---
# <a name="pidtagscheduleinfomonthsbusy-canonical-property"></a><span data-ttu-id="d9080-103">Kanonische PidTagScheduleInfoMonthsBusy-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="d9080-103">PidTagScheduleInfoMonthsBusy Canonical Property</span></span>

  
  
<span data-ttu-id="d9080-104">**Betrifft**: Outlook</span><span class="sxs-lookup"><span data-stu-id="d9080-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="d9080-105">Enthält die Monate, für die Frei/Gebucht-Daten vom Typ beschäftigt in der Nachricht Frei/Gebucht-Informationen vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="d9080-105">Contains the months for which free/busy data of type busy is present in the free/busy message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="d9080-106">Zugeordneten Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="d9080-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d9080-107">PR_SCHDINFO_MONTHS_BUSY</span><span class="sxs-lookup"><span data-stu-id="d9080-107">PR_SCHDINFO_MONTHS_BUSY</span></span>  <br/> |
|<span data-ttu-id="d9080-108">Bezeichner:</span><span class="sxs-lookup"><span data-stu-id="d9080-108">Identifier:</span></span>  <br/> |<span data-ttu-id="d9080-109">0x6853</span><span class="sxs-lookup"><span data-stu-id="d9080-109">0x6853</span></span>  <br/> |
|<span data-ttu-id="d9080-110">Datentyp:</span><span class="sxs-lookup"><span data-stu-id="d9080-110">Data type:</span></span>  <br/> |<span data-ttu-id="d9080-111">PT_MV_LONG</span><span class="sxs-lookup"><span data-stu-id="d9080-111">PT_MV_LONG</span></span>  <br/> |
|<span data-ttu-id="d9080-112">Bereich:</span><span class="sxs-lookup"><span data-stu-id="d9080-112">Area:</span></span>  <br/> |<span data-ttu-id="d9080-113">Frei/Gebucht-Informationen</span><span class="sxs-lookup"><span data-stu-id="d9080-113">Free/Busy</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d9080-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d9080-114">Remarks</span></span>

<span data-ttu-id="d9080-115">Das Format, Berechnung und Einschränkungen dieser Eigenschaft werden die gleichen, die von **PR_SCHDINFO_MONTHS_TENTATIVE** ([PidTagScheduleInfoMonthsTentative](pidtagscheduleinfomonthstentative-canonical-property.md)), aber finden Sie unter Termine, die auf das zugehörige Calendar-Objekt gekennzeichnet sind.</span><span class="sxs-lookup"><span data-stu-id="d9080-115">The format, computation and constraints of this property are the same as those of **PR_SCHDINFO_MONTHS_TENTATIVE** ([PidTagScheduleInfoMonthsTentative](pidtagscheduleinfomonthstentative-canonical-property.md)) but refer to appointments that are marked busy on the associated calendar object.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="d9080-116">Verwandte Ressourcen</span><span class="sxs-lookup"><span data-stu-id="d9080-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="d9080-117">Protokollspezifikationen</span><span class="sxs-lookup"><span data-stu-id="d9080-117">Protocol specifications</span></span>

<span data-ttu-id="d9080-118">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d9080-118">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d9080-119">Bietet Verweise auf Verwandte Exchange Server-Spezifikationen.</span><span class="sxs-lookup"><span data-stu-id="d9080-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="d9080-120">[[MS-OXOPFFB]](http://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d9080-120">[[MS-OXOPFFB]](http://msdn.microsoft.com/library/1a527299-7211-4d27-a74c-b69bd0746320%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d9080-121">Veröffentlicht die Verfügbarkeit eines Benutzers oder einer Ressource.</span><span class="sxs-lookup"><span data-stu-id="d9080-121">Publishes the availability of a user or resource.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="d9080-122">Header-Dateien</span><span class="sxs-lookup"><span data-stu-id="d9080-122">Header files</span></span>

<span data-ttu-id="d9080-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="d9080-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="d9080-124">Enthält die Datentypdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="d9080-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="d9080-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="d9080-125">Mapitags.h</span></span>
  
> <span data-ttu-id="d9080-126">Enthält Definitionen von Eigenschaften, die als Alternative Namen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="d9080-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d9080-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d9080-127">See also</span></span>



[<span data-ttu-id="d9080-128">MAPI-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d9080-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d9080-129">Kanonische MAPI-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d9080-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d9080-130">Zuordnen von kanonischen Eigenschaftennamen zu MAPI-Namen</span><span class="sxs-lookup"><span data-stu-id="d9080-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d9080-131">Zuordnen von MAPI-Namen zu kanonische Eigenschaftennamen</span><span class="sxs-lookup"><span data-stu-id="d9080-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)
