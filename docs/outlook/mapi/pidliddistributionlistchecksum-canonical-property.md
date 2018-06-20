---
title: Kanonische PidLidDistributionListChecksum-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidLidDistributionListChecksum
api_type:
- COM
ms.assetid: bd50ab34-caae-4258-8afc-769e3cbc5220
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: bba1e78d79800b1c8e56ad50ce1abb144d4c9aae
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19793496"
---
# <a name="pidliddistributionlistchecksum-canonical-property"></a><span data-ttu-id="8f7d3-103">Kanonische PidLidDistributionListChecksum-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="8f7d3-103">PidLidDistributionListChecksum Canonical Property</span></span>

  
  
<span data-ttu-id="8f7d3-104">**Betrifft**: Outlook</span><span class="sxs-lookup"><span data-stu-id="8f7d3-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="8f7d3-105">Gibt die 32-Bit-CRC polynomial Prüfsumme für eine persönliche Verteilerliste Kontrollkästchen (CRC-32).</span><span class="sxs-lookup"><span data-stu-id="8f7d3-105">Specifies the 32-bit cyclic redundancy check (CRC-32) polynomial checksum for a personal distribution list.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="8f7d3-106">Zugeordneten Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="8f7d3-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="8f7d3-107">dispidDLChecksum</span><span class="sxs-lookup"><span data-stu-id="8f7d3-107">dispidDLChecksum</span></span>  <br/> |
|<span data-ttu-id="8f7d3-108">-Eigenschaft festgelegt:</span><span class="sxs-lookup"><span data-stu-id="8f7d3-108">Property set:</span></span>  <br/> |<span data-ttu-id="8f7d3-109">PSETID_Address</span><span class="sxs-lookup"><span data-stu-id="8f7d3-109">PSETID_Address</span></span>  <br/> |
|<span data-ttu-id="8f7d3-110">Long-ID (Abdeckung):</span><span class="sxs-lookup"><span data-stu-id="8f7d3-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="8f7d3-111">0x0000804C</span><span class="sxs-lookup"><span data-stu-id="8f7d3-111">0x0000804C</span></span>  <br/> |
|<span data-ttu-id="8f7d3-112">Datentyp:</span><span class="sxs-lookup"><span data-stu-id="8f7d3-112">Data type:</span></span>  <br/> |<span data-ttu-id="8f7d3-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="8f7d3-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="8f7d3-114">Bereich:</span><span class="sxs-lookup"><span data-stu-id="8f7d3-114">Area:</span></span>  <br/> |<span data-ttu-id="8f7d3-115">Kontakt</span><span class="sxs-lookup"><span data-stu-id="8f7d3-115">Contact</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8f7d3-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8f7d3-116">Remarks</span></span>

<span data-ttu-id="8f7d3-117">Der Wert dieser Eigenschaft kann verwendet werden, zu erkennen, wann die **DispidDLMembers** ([PidLidDistributionListMembers](pidliddistributionlistmembers-canonical-property.md))-Eigenschaft aktualisiert wurde, ohne die Aktualisierung der anderen persönlichen Verteilerliste Liste Elementeigenschaften durch den CRC-32 auf dem vorhandenen computing der Wert der **DispidDLMembers** und diese mit dem Wert der Eigenschaft **DispidDLChecksum** zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="8f7d3-117">The value of this property can be used to detect when the **dispidDLMembers** ([PidLidDistributionListMembers](pidliddistributionlistmembers-canonical-property.md)) property was updated without updating the other personal distribution list member properties by computing the CRC-32 on the existing value of **dispidDLMembers** and comparing it with the value of the **dispidDLChecksum** property.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="8f7d3-118">Verwandte Ressourcen</span><span class="sxs-lookup"><span data-stu-id="8f7d3-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="8f7d3-119">Protokollspezifikationen</span><span class="sxs-lookup"><span data-stu-id="8f7d3-119">Protocol specifications</span></span>

<span data-ttu-id="8f7d3-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8f7d3-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8f7d3-121">Enthält Eigenschaftendefinitionen und Verweise auf Verwandte Exchange Server-Spezifikationen.</span><span class="sxs-lookup"><span data-stu-id="8f7d3-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="8f7d3-122">[[MS-OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8f7d3-122">[[MS-OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8f7d3-123">Gibt die Eigenschaften und Operationen, die für Kontakte und persönliche Verteilerlisten zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="8f7d3-123">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="8f7d3-124">Header-Dateien</span><span class="sxs-lookup"><span data-stu-id="8f7d3-124">Header files</span></span>

<span data-ttu-id="8f7d3-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="8f7d3-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="8f7d3-126">Enthält die Datentypdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="8f7d3-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8f7d3-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f7d3-127">See also</span></span>



[<span data-ttu-id="8f7d3-128">MAPI-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="8f7d3-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="8f7d3-129">Kanonische MAPI-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="8f7d3-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="8f7d3-130">Zuordnen von kanonischen Eigenschaftennamen zu MAPI-Namen</span><span class="sxs-lookup"><span data-stu-id="8f7d3-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="8f7d3-131">Zuordnen von MAPI-Namen zu kanonische Eigenschaftennamen</span><span class="sxs-lookup"><span data-stu-id="8f7d3-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)
