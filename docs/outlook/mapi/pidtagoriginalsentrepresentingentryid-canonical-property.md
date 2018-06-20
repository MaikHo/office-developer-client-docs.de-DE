---
title: Kanonische PidTagOriginalSentRepresentingEntryId-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOriginalSentRepresentingEntryId
api_type:
- COM
ms.assetid: ece3df57-47f3-4d27-854f-b511c920ac75
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 92300733d32f021bb0ab8ab29a9676b740eeda12
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19794726"
---
# <a name="pidtagoriginalsentrepresentingentryid-canonical-property"></a><span data-ttu-id="d9ed3-103">Kanonische PidTagOriginalSentRepresentingEntryId-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="d9ed3-103">PidTagOriginalSentRepresentingEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="d9ed3-104">**Betrifft**: Outlook</span><span class="sxs-lookup"><span data-stu-id="d9ed3-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="d9ed3-105">Enthält die Eintrags-ID des messaging Benutzers in dessen Namen die ursprüngliche Nachricht gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="d9ed3-105">Contains the entry identifier of the messaging user on whose behalf the original message was sent.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="d9ed3-106">Zugeordneten Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="d9ed3-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d9ed3-107">PR_ORIGINAL_SENT_REPRESENTING_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="d9ed3-107">PR_ORIGINAL_SENT_REPRESENTING_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="d9ed3-108">Bezeichner:</span><span class="sxs-lookup"><span data-stu-id="d9ed3-108">Identifier:</span></span>  <br/> |<span data-ttu-id="d9ed3-109">0x005E</span><span class="sxs-lookup"><span data-stu-id="d9ed3-109">0x005E</span></span>  <br/> |
|<span data-ttu-id="d9ed3-110">Datentyp:</span><span class="sxs-lookup"><span data-stu-id="d9ed3-110">Data type:</span></span>  <br/> |<span data-ttu-id="d9ed3-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="d9ed3-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="d9ed3-112">Bereich:</span><span class="sxs-lookup"><span data-stu-id="d9ed3-112">Area:</span></span>  <br/> |<span data-ttu-id="d9ed3-113">Allgemeine messaging</span><span class="sxs-lookup"><span data-stu-id="d9ed3-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d9ed3-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d9ed3-114">Remarks</span></span>

<span data-ttu-id="d9ed3-115">Diese Eigenschaft ist eine der Adresseigenschaften für den Absender einer Nachricht dargestellt.</span><span class="sxs-lookup"><span data-stu-id="d9ed3-115">This property is one of the address properties for the original represented sender of a message.</span></span> <span data-ttu-id="d9ed3-116">Es wird in einem Thread Unterhaltung verwendet.</span><span class="sxs-lookup"><span data-stu-id="d9ed3-116">It is used in a conversation thread.</span></span>
  
<span data-ttu-id="d9ed3-117">Senden einer Nachricht im Auftrag einer anderen Client-Clientanwendung sollte diese Eigenschaft auf den Wert der Eigenschaft **PR_SENT_REPRESENTING_ENTRYID** ([PidTagSentRepresentingEntryId](pidtagsentrepresentingentryid-canonical-property.md)) auf der ersten Übermittlung der Nachricht festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d9ed3-117">A client application sending a message on behalf of another client should set this property to the value of the **PR_SENT_REPRESENTING_ENTRYID** ([PidTagSentRepresentingEntryId](pidtagsentrepresentingentryid-canonical-property.md)) property at the first submission of the message.</span></span> <span data-ttu-id="d9ed3-118">Einmal festgelegt ist, sollte es nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="d9ed3-118">Once set, it should never be changed.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="d9ed3-119">Verwandte Ressourcen</span><span class="sxs-lookup"><span data-stu-id="d9ed3-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="d9ed3-120">Protokollspezifikationen</span><span class="sxs-lookup"><span data-stu-id="d9ed3-120">Protocol specifications</span></span>

<span data-ttu-id="d9ed3-121">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d9ed3-121">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d9ed3-122">Bietet Verweise auf Verwandte Exchange Server-Spezifikationen.</span><span class="sxs-lookup"><span data-stu-id="d9ed3-122">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="d9ed3-123">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d9ed3-123">[[MS-OXOMSG]](http://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d9ed3-124">Gibt die Eigenschaften und Operationen, die für Objekte, die e-Mail-Nachricht zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="d9ed3-124">Specifies the properties and operations that are permissible on email message objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="d9ed3-125">Header-Dateien</span><span class="sxs-lookup"><span data-stu-id="d9ed3-125">Header files</span></span>

<span data-ttu-id="d9ed3-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="d9ed3-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="d9ed3-127">Enthält die Datentypdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="d9ed3-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="d9ed3-128">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="d9ed3-128">Mapitags.h</span></span>
  
> <span data-ttu-id="d9ed3-129">Enthält Definitionen von Eigenschaften, die als Alternative Namen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="d9ed3-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d9ed3-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d9ed3-130">See also</span></span>



[<span data-ttu-id="d9ed3-131">MAPI-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d9ed3-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d9ed3-132">Kanonische MAPI-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d9ed3-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d9ed3-133">Zuordnen von kanonischen Eigenschaftennamen zu MAPI-Namen</span><span class="sxs-lookup"><span data-stu-id="d9ed3-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d9ed3-134">Zuordnen von MAPI-Namen zu kanonische Eigenschaftennamen</span><span class="sxs-lookup"><span data-stu-id="d9ed3-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)
