---
title: Kanonische PidLidLogFlags-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidLogFlags
api_type:
- COM
ms.assetid: 3174d931-e045-44db-a203-a27c9c00f4fc
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 7b2dd30511927f8df8a8bc587a6b1fedd5854810
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19793654"
---
# <a name="pidlidlogflags-canonical-property"></a><span data-ttu-id="d995d-103">Kanonische PidLidLogFlags-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="d995d-103">PidLidLogFlags Canonical Property</span></span>

  
  
<span data-ttu-id="d995d-104">**Betrifft**: Outlook</span><span class="sxs-lookup"><span data-stu-id="d995d-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="d995d-105">Enthält Metadaten zur Erfassung.</span><span class="sxs-lookup"><span data-stu-id="d995d-105">Contains metadata about the journal.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="d995d-106">Zugeordneten Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="d995d-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d995d-107">dispidLogFlags</span><span class="sxs-lookup"><span data-stu-id="d995d-107">dispidLogFlags</span></span>  <br/> |
|<span data-ttu-id="d995d-108">-Eigenschaft festgelegt:</span><span class="sxs-lookup"><span data-stu-id="d995d-108">Property set:</span></span>  <br/> |<span data-ttu-id="d995d-109">PSETID_Log</span><span class="sxs-lookup"><span data-stu-id="d995d-109">PSETID_Log</span></span>  <br/> |
|<span data-ttu-id="d995d-110">Long-ID (Abdeckung):</span><span class="sxs-lookup"><span data-stu-id="d995d-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="d995d-111">0x0000870C</span><span class="sxs-lookup"><span data-stu-id="d995d-111">0x0000870C</span></span>  <br/> |
|<span data-ttu-id="d995d-112">Datentyp:</span><span class="sxs-lookup"><span data-stu-id="d995d-112">Data type:</span></span>  <br/> |<span data-ttu-id="d995d-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="d995d-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="d995d-114">Bereich:</span><span class="sxs-lookup"><span data-stu-id="d995d-114">Area:</span></span>  <br/> |<span data-ttu-id="d995d-115">Journal</span><span class="sxs-lookup"><span data-stu-id="d995d-115">Journal</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d995d-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d995d-116">Remarks</span></span>

<span data-ttu-id="d995d-117">Das Bit dar, das Metadaten für die Erfassung enthält muss entweder 0 (null) oder "0 x 40000000".</span><span class="sxs-lookup"><span data-stu-id="d995d-117">The bit field that contains metadata about the journal must be either zero or "0x40000000".</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="d995d-118">Verwandte Ressourcen</span><span class="sxs-lookup"><span data-stu-id="d995d-118">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="d995d-119">Protokollspezifikationen</span><span class="sxs-lookup"><span data-stu-id="d995d-119">Protocol specifications</span></span>

<span data-ttu-id="d995d-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d995d-120">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d995d-121">Enthält Eigenschaftendefinitionen und Verweise auf Verwandte Exchange Server-Spezifikationen.</span><span class="sxs-lookup"><span data-stu-id="d995d-121">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="d995d-122">[[MS-OXOJRNL]](http://msdn.microsoft.com/library/2aa04fd2-0f36-4ce4-9178-c0fc70aa8d43%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d995d-122">[[MS-OXOJRNL]](http://msdn.microsoft.com/library/2aa04fd2-0f36-4ce4-9178-c0fc70aa8d43%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d995d-123">Gibt die Eigenschaften und Operationen, die für Journale zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="d995d-123">Specifies the properties and operations that are permissible for journals.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="d995d-124">Header-Dateien</span><span class="sxs-lookup"><span data-stu-id="d995d-124">Header files</span></span>

<span data-ttu-id="d995d-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="d995d-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="d995d-126">Enthält die Datentypdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="d995d-126">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d995d-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d995d-127">See also</span></span>



[<span data-ttu-id="d995d-128">MAPI-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d995d-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d995d-129">Kanonische MAPI-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d995d-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d995d-130">Zuordnen von kanonischen Eigenschaftennamen zu MAPI-Namen</span><span class="sxs-lookup"><span data-stu-id="d995d-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d995d-131">Zuordnen von MAPI-Namen zu kanonische Eigenschaftennamen</span><span class="sxs-lookup"><span data-stu-id="d995d-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)
