---
title: Kanonische PidTagOriginalDisplayCc-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginalDisplayCc
api_type:
- COM
ms.assetid: f48d723c-3ad8-4617-952a-ba5216b2129c
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: c4fc8ef6dd67eb5187bbc0bac8c4f4f9bee13826
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19794690"
---
# <a name="pidtagoriginaldisplaycc-canonical-property"></a><span data-ttu-id="ce26e-103">Kanonische PidTagOriginalDisplayCc-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="ce26e-103">PidTagOriginalDisplayCc Canonical Property</span></span>

  
  
<span data-ttu-id="ce26e-104">**Betrifft**: Outlook</span><span class="sxs-lookup"><span data-stu-id="ce26e-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ce26e-105">Enthält die Anzeigenamen der Empfänger Carbon Copy, Kopie (CC) der ursprünglichen Nachricht.</span><span class="sxs-lookup"><span data-stu-id="ce26e-105">Contains the display names of any carbon copy (CC) recipients of the original message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ce26e-106">Zugeordneten Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="ce26e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ce26e-107">PR_ORIGINAL_DISPLAY_CC, PR_ORIGINAL_DISPLAY_CC_A, PR_ORIGINAL_DISPLAY_CC_W</span><span class="sxs-lookup"><span data-stu-id="ce26e-107">PR_ORIGINAL_DISPLAY_CC, PR_ORIGINAL_DISPLAY_CC_A, PR_ORIGINAL_DISPLAY_CC_W</span></span>  <br/> |
|<span data-ttu-id="ce26e-108">Bezeichner:</span><span class="sxs-lookup"><span data-stu-id="ce26e-108">Identifier:</span></span>  <br/> |<span data-ttu-id="ce26e-109">0x0073</span><span class="sxs-lookup"><span data-stu-id="ce26e-109">0x0073</span></span>  <br/> |
|<span data-ttu-id="ce26e-110">Datentyp:</span><span class="sxs-lookup"><span data-stu-id="ce26e-110">Data type:</span></span>  <br/> |<span data-ttu-id="ce26e-111">PT_STRING8, PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="ce26e-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="ce26e-112">Bereich:</span><span class="sxs-lookup"><span data-stu-id="ce26e-112">Area:</span></span>  <br/> |<span data-ttu-id="ce26e-113">Allgemeine messaging</span><span class="sxs-lookup"><span data-stu-id="ce26e-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ce26e-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ce26e-114">Remarks</span></span>

<span data-ttu-id="ce26e-115">Diese Eigenschaften enthalten eine durch Semikolons getrennte Liste.</span><span class="sxs-lookup"><span data-stu-id="ce26e-115">These properties contain a list separated by semicolons.</span></span> <span data-ttu-id="ce26e-116">Es MAPI bereitgestellten und wird direkt aus **PR_DISPLAY_CC** ([PidTagDisplayCc](pidtagdisplaycc-canonical-property.md)) bei einer Übermittlung kopiert oder Unzustellbarkeitsbericht oder einem Lese- oder nonread Bericht wird generiert.</span><span class="sxs-lookup"><span data-stu-id="ce26e-116">It is furnished by MAPI and is copied directly from **PR_DISPLAY_CC** ([PidTagDisplayCc](pidtagdisplaycc-canonical-property.md)) when a delivery or nondelivery report or a read or nonread report is generated.</span></span> <span data-ttu-id="ce26e-117">Diese Eigenschaft kann auf andere Nachrichten durch ihre Nachrichtenklassen definierten vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="ce26e-117">This property may be present on other messages as defined by their message classes.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="ce26e-118">Verwandte Ressourcen</span><span class="sxs-lookup"><span data-stu-id="ce26e-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="ce26e-119">Protokollspezifikationen</span><span class="sxs-lookup"><span data-stu-id="ce26e-119">Protocol specifications</span></span>

<span data-ttu-id="ce26e-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ce26e-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ce26e-121">Bietet Verweise auf Verwandte Exchange Server-Spezifikationen.</span><span class="sxs-lookup"><span data-stu-id="ce26e-121">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="ce26e-122">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ce26e-122">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ce26e-123">Gibt die Eigenschaften und Operationen, die für Objekte, die e-Mail-Nachricht zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="ce26e-123">Specifies the properties and operations that are permissible on email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="ce26e-124">Header-Dateien</span><span class="sxs-lookup"><span data-stu-id="ce26e-124">Header files</span></span>

<span data-ttu-id="ce26e-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ce26e-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="ce26e-126">Enthält die Datentypdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="ce26e-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="ce26e-127">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="ce26e-127">Mapitags.h</span></span>
  
> <span data-ttu-id="ce26e-128">Enthält Definitionen von Eigenschaften, die als Alternative Namen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="ce26e-128">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ce26e-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce26e-129">See also</span></span>



[<span data-ttu-id="ce26e-130">MAPI-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="ce26e-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ce26e-131">Kanonische MAPI-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="ce26e-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ce26e-132">Zuordnen von kanonischen Eigenschaftennamen zu MAPI-Namen</span><span class="sxs-lookup"><span data-stu-id="ce26e-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ce26e-133">Zuordnen von MAPI-Namen zu kanonische Eigenschaftennamen</span><span class="sxs-lookup"><span data-stu-id="ce26e-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)
