---
title: Kanonische PidTagNextSendAcct-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagNextSendAcct
api_type:
- HeaderDef
ms.assetid: b7429c2e-0d9d-4921-9f56-9ecad817f8cb
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 517d0900e968ea55cedf6b17b31d97795fcf61c0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19794638"
---
# <a name="pidtagnextsendacct-canonical-property"></a><span data-ttu-id="ca25c-103">Kanonische PidTagNextSendAcct-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="ca25c-103">PidTagNextSendAcct Canonical Property</span></span>

  
  
<span data-ttu-id="ca25c-104">**Betrifft**: Outlook</span><span class="sxs-lookup"><span data-stu-id="ca25c-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ca25c-105">Gibt den Server, den ein Client derzeit versucht, Senden von e-Mails zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ca25c-105">Specifies the server that a client is currently attempting to use to send email.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ca25c-106">Zugeordneten Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="ca25c-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ca25c-107">PR_NEXT_SEND_ACCT</span><span class="sxs-lookup"><span data-stu-id="ca25c-107">PR_NEXT_SEND_ACCT</span></span>  <br/> |
|<span data-ttu-id="ca25c-108">Bezeichner:</span><span class="sxs-lookup"><span data-stu-id="ca25c-108">Identifier:</span></span>  <br/> |<span data-ttu-id="ca25c-109">0x0E29</span><span class="sxs-lookup"><span data-stu-id="ca25c-109">0x0E29</span></span>  <br/> |
|<span data-ttu-id="ca25c-110">Datentyp:</span><span class="sxs-lookup"><span data-stu-id="ca25c-110">Data type:</span></span>  <br/> |<span data-ttu-id="ca25c-111">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="ca25c-111">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="ca25c-112">Bereich:</span><span class="sxs-lookup"><span data-stu-id="ca25c-112">Area:</span></span>  <br/> |<span data-ttu-id="ca25c-113">Outlook-Anwendung</span><span class="sxs-lookup"><span data-stu-id="ca25c-113">Outlook application</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ca25c-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ca25c-114">Remarks</span></span>

<span data-ttu-id="ca25c-115">Das Format dieser Eigenschaft ist die Implementierung ab.</span><span class="sxs-lookup"><span data-stu-id="ca25c-115">The format of this property is implementation dependent.</span></span> <span data-ttu-id="ca25c-116">Diese Eigenschaft kann zum Ermitteln des Servers, leiten Sie die e-Mail vom Client verwendet werden, jedoch ist optional, und der Wert hat keine Bedeutung für den Server.</span><span class="sxs-lookup"><span data-stu-id="ca25c-116">This property can be used by the client to determine which server to direct the email to, but is optional and the value has no meaning to the server.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="ca25c-117">Verwandte Ressourcen</span><span class="sxs-lookup"><span data-stu-id="ca25c-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="ca25c-118">Protokollspezifikationen</span><span class="sxs-lookup"><span data-stu-id="ca25c-118">Protocol specifications</span></span>

<span data-ttu-id="ca25c-119">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ca25c-119">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ca25c-120">Bietet Verweise auf Verwandte Exchange Server-Spezifikationen.</span><span class="sxs-lookup"><span data-stu-id="ca25c-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="ca25c-121">[[MS-OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ca25c-121">[[MS-OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ca25c-122">Konvertiert zwischen IETF RFC2445, RFC2446, RFC2447, und Termine und meeting-Objekte.</span><span class="sxs-lookup"><span data-stu-id="ca25c-122">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
<span data-ttu-id="ca25c-123">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="ca25c-123">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="ca25c-124">Gibt die Eigenschaften und Operationen, die für e-Mail-Nachrichtenobjekte zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="ca25c-124">Specifies the properties and operations that are permissible for email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="ca25c-125">Header-Dateien</span><span class="sxs-lookup"><span data-stu-id="ca25c-125">Header files</span></span>

<span data-ttu-id="ca25c-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ca25c-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="ca25c-127">Enthält die Datentypdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="ca25c-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="ca25c-128">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="ca25c-128">Mapitags.h</span></span>
  
> <span data-ttu-id="ca25c-129">Enthält Definitionen von Eigenschaften, die als Alternative Namen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="ca25c-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ca25c-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca25c-130">See also</span></span>



[<span data-ttu-id="ca25c-131">MAPI-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="ca25c-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ca25c-132">Kanonische MAPI-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="ca25c-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ca25c-133">Zuordnen von kanonischen Eigenschaftennamen zu MAPI-Namen</span><span class="sxs-lookup"><span data-stu-id="ca25c-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ca25c-134">Zuordnen von MAPI-Namen zu kanonische Eigenschaftennamen</span><span class="sxs-lookup"><span data-stu-id="ca25c-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)
