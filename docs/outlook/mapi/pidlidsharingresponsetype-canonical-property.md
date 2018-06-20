---
title: Kanonische PidLidSharingResponseType-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidSharingResponseType
api_type:
- COM
ms.assetid: c27b1239-3612-4bb3-9f22-4b89ee9900cd
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: a645ee26b56355c6594f5667585becbcff2e3eec
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19793803"
---
# <a name="pidlidsharingresponsetype-canonical-property"></a><span data-ttu-id="51868-103">Kanonische PidLidSharingResponseType-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="51868-103">PidLidSharingResponseType Canonical Property</span></span>

  
  
<span data-ttu-id="51868-104">**Betrifft**: Outlook</span><span class="sxs-lookup"><span data-stu-id="51868-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="51868-105">Gibt den Typ der Antwort mit dem der Empfänger die Freigabeanfrage geantwortet.</span><span class="sxs-lookup"><span data-stu-id="51868-105">Specifies the type of response with which the recipient of the sharing request responded.</span></span> <span data-ttu-id="51868-106">Dies ist eine Eigenschaft eines eine Freigabenachricht.</span><span class="sxs-lookup"><span data-stu-id="51868-106">This is a property of a sharing message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="51868-107">Zugeordneten Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="51868-107">Associated properties:</span></span>  <br/> |<span data-ttu-id="51868-108">dispidSharingResponseType</span><span class="sxs-lookup"><span data-stu-id="51868-108">dispidSharingResponseType</span></span>  <br/> |
|<span data-ttu-id="51868-109">-Eigenschaft festgelegt:</span><span class="sxs-lookup"><span data-stu-id="51868-109">Property set:</span></span>  <br/> |<span data-ttu-id="51868-110">PSETID_Sharing</span><span class="sxs-lookup"><span data-stu-id="51868-110">PSETID_Sharing</span></span>  <br/> |
|<span data-ttu-id="51868-111">Long-ID (Abdeckung):</span><span class="sxs-lookup"><span data-stu-id="51868-111">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="51868-112">0x00008A27</span><span class="sxs-lookup"><span data-stu-id="51868-112">0x00008A27</span></span>  <br/> |
|<span data-ttu-id="51868-113">Datentyp:</span><span class="sxs-lookup"><span data-stu-id="51868-113">Data type:</span></span>  <br/> |<span data-ttu-id="51868-114">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="51868-114">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="51868-115">Bereich:</span><span class="sxs-lookup"><span data-stu-id="51868-115">Area:</span></span>  <br/> |<span data-ttu-id="51868-116">Freigabe</span><span class="sxs-lookup"><span data-stu-id="51868-116">Sharing</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="51868-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="51868-117">Remarks</span></span>

<span data-ttu-id="51868-118">Der Wert dieser Eigenschaft muss auf einen der folgenden Werte festgelegt werden:</span><span class="sxs-lookup"><span data-stu-id="51868-118">The value of this property must be set to one of the following values:</span></span>
  
|<span data-ttu-id="51868-119">**Wert**</span><span class="sxs-lookup"><span data-stu-id="51868-119">**Value**</span></span>|<span data-ttu-id="51868-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="51868-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="51868-121">0x00000000</span><span class="sxs-lookup"><span data-stu-id="51868-121">0x00000000</span></span>  <br/> |<span data-ttu-id="51868-122">Keine Antwort</span><span class="sxs-lookup"><span data-stu-id="51868-122">No response</span></span>  <br/> |
|<span data-ttu-id="51868-123">0x00000001</span><span class="sxs-lookup"><span data-stu-id="51868-123">0x00000001</span></span>  <br/> |<span data-ttu-id="51868-124">Akzeptiert</span><span class="sxs-lookup"><span data-stu-id="51868-124">Accepted</span></span>  <br/> |
|<span data-ttu-id="51868-125">0x00000002</span><span class="sxs-lookup"><span data-stu-id="51868-125">0x00000002</span></span>  <br/> |<span data-ttu-id="51868-126">Verweigert</span><span class="sxs-lookup"><span data-stu-id="51868-126">Denied</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="51868-127">Verwandte Ressourcen</span><span class="sxs-lookup"><span data-stu-id="51868-127">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="51868-128">Protokollspezifikationen</span><span class="sxs-lookup"><span data-stu-id="51868-128">Protocol specifications</span></span>

<span data-ttu-id="51868-129">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="51868-129">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="51868-130">Enthält Eigenschaftendefinitionen und Verweise auf Verwandte Exchange Server-Spezifikationen.</span><span class="sxs-lookup"><span data-stu-id="51868-130">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="51868-131">[[MS-OXSHARE]](http://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="51868-131">[[MS-OXSHARE]](http://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="51868-132">Teilt Postfachordner zwischen Clients.</span><span class="sxs-lookup"><span data-stu-id="51868-132">Shares mailbox folders between clients.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="51868-133">Header-Dateien</span><span class="sxs-lookup"><span data-stu-id="51868-133">Header files</span></span>

<span data-ttu-id="51868-134">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="51868-134">Mapidefs.h</span></span>
  
> <span data-ttu-id="51868-135">Enthält die Datentypdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="51868-135">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="51868-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="51868-136">See also</span></span>



[<span data-ttu-id="51868-137">MAPI-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="51868-137">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="51868-138">Kanonische MAPI-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="51868-138">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="51868-139">Zuordnen von kanonischen Eigenschaftennamen zu MAPI-Namen</span><span class="sxs-lookup"><span data-stu-id="51868-139">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="51868-140">Zuordnen von MAPI-Namen zu kanonische Eigenschaftennamen</span><span class="sxs-lookup"><span data-stu-id="51868-140">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)
