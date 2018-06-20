---
title: Kanonische PidTagTransmittableDisplayName-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagTransmittableDisplayName
api_type:
- COM
ms.assetid: aadd9086-b936-4067-bf7d-f54fc50e3c83
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 96eaf6c3f9ddc9d4bf6bc16ddc28a6f38bc311f2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19795257"
---
# <a name="pidtagtransmittabledisplayname-canonical-property"></a><span data-ttu-id="781ce-103">Kanonische PidTagTransmittableDisplayName-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="781ce-103">PidTagTransmittableDisplayName Canonical Property</span></span>

  
  
<span data-ttu-id="781ce-104">**Betrifft**: Outlook</span><span class="sxs-lookup"><span data-stu-id="781ce-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="781ce-105">Enthält den Namen eines Empfängers Anzeige in einem sicheren Formular, das nicht geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="781ce-105">Contains a recipient's display name in a secure form that cannot be changed.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="781ce-106">Zugeordneten Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="781ce-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="781ce-107">PR_TRANSMITABLE_DISPLAY_NAME, PR_TRANSMITABLE_DISPLAY_NAME_A, PR_TRANSMITABLE_DISPLAY_NAME_W</span><span class="sxs-lookup"><span data-stu-id="781ce-107">PR_TRANSMITABLE_DISPLAY_NAME, PR_TRANSMITABLE_DISPLAY_NAME_A, PR_TRANSMITABLE_DISPLAY_NAME_W</span></span>  <br/> |
|<span data-ttu-id="781ce-108">Bezeichner:</span><span class="sxs-lookup"><span data-stu-id="781ce-108">Identifier:</span></span>  <br/> |<span data-ttu-id="781ce-109">0x3A20</span><span class="sxs-lookup"><span data-stu-id="781ce-109">0x3A20</span></span>  <br/> |
|<span data-ttu-id="781ce-110">Datentyp:</span><span class="sxs-lookup"><span data-stu-id="781ce-110">Data type:</span></span>  <br/> |<span data-ttu-id="781ce-111">PT_UNICODE PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="781ce-111">PT_UNICODE, PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="781ce-112">Bereich:</span><span class="sxs-lookup"><span data-stu-id="781ce-112">Area:</span></span>  <br/> |<span data-ttu-id="781ce-113">Adresse</span><span class="sxs-lookup"><span data-stu-id="781ce-113">Address</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="781ce-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="781ce-114">Remarks</span></span>

<span data-ttu-id="781ce-115">Diese Eigenschaften sollte von allen adressbuchanbietern implementierte implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="781ce-115">These properties should be implemented by all address book providers.</span></span> <span data-ttu-id="781ce-116">Sie enthalten die Version der Anzeigename den Namen des Empfängers, der mit der Meldung übertragen wird.</span><span class="sxs-lookup"><span data-stu-id="781ce-116">They contain the version of the recipient's display name that is transmitted with the message.</span></span> <span data-ttu-id="781ce-117">Für die meisten adressbuchanbietern implementierte müssen diese Eigenschaften denselben Wert wie die Eigenschaft **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)).</span><span class="sxs-lookup"><span data-stu-id="781ce-117">For most address book providers these properties have the same value as the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property.</span></span> <span data-ttu-id="781ce-118">Anbieter, die nicht über einen sicheren Anzeigenamen PT_ERROR und MAPI-Änderungen der angezeigte Name zurückgegeben, durch den Namen in Anführungszeichen hinzufügen verfügen.</span><span class="sxs-lookup"><span data-stu-id="781ce-118">Providers that do not have a secure display name return PT_ERROR and MAPI changes the display name by adding quotation marks around the name.</span></span>
  
<span data-ttu-id="781ce-119">Eine Clientanwendung kann diese Eigenschaft verwenden, um Änderung oder "spoofing" von Einträgen zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="781ce-119">A client application can use this property to prevent alteration or "spoofing" of entries.</span></span> <span data-ttu-id="781ce-120">Ein Beispiel für spoofing überträgt John Doe als (was ein Guy) John Doe.</span><span class="sxs-lookup"><span data-stu-id="781ce-120">An example of spoofing is transmitting John Doe as John (What a Guy) Doe.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="781ce-121">Verwandte Ressourcen</span><span class="sxs-lookup"><span data-stu-id="781ce-121">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="781ce-122">Protokollspezifikationen</span><span class="sxs-lookup"><span data-stu-id="781ce-122">Protocol specifications</span></span>

<span data-ttu-id="781ce-123">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="781ce-123">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="781ce-124">Bietet Verweise auf Verwandte Exchange Server-Spezifikationen.</span><span class="sxs-lookup"><span data-stu-id="781ce-124">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="781ce-125">[[MS-OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="781ce-125">[[MS-OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="781ce-126">Gibt die Eigenschaften und Operationen für Listen der Benutzer, Kontakte, Gruppen und Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="781ce-126">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
<span data-ttu-id="781ce-127">[[MS-NSPI]](http://msdn.microsoft.com/library/6dd0a3ea-b4d4-4a73-a857-add03a89a543%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="781ce-127">[[MS-NSPI]](http://msdn.microsoft.com/library/6dd0a3ea-b4d4-4a73-a857-add03a89a543%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="781ce-128">Verarbeitet ein Client-Kommunikation mit einem Server (NSPI = Name Service Provider Interface).</span><span class="sxs-lookup"><span data-stu-id="781ce-128">Handles a client's communications with a Name Service Provider Interface (NSPI) server.</span></span>
    
<span data-ttu-id="781ce-129">[[MS-OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="781ce-129">[[MS-OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="781ce-130">Verarbeitet die Reihenfolge und den Fluss für Datenübertragungen zwischen einem Client und Server.</span><span class="sxs-lookup"><span data-stu-id="781ce-130">Handles the order and flow for data transfers between a client and server.</span></span>
    
<span data-ttu-id="781ce-131">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="781ce-131">[[MS-OXCMSG]](http://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="781ce-132">Nachrichten und Anlagen Objekte behandelt.</span><span class="sxs-lookup"><span data-stu-id="781ce-132">Handles message and attachment objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="781ce-133">Header-Dateien</span><span class="sxs-lookup"><span data-stu-id="781ce-133">Header files</span></span>

<span data-ttu-id="781ce-134">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="781ce-134">Mapidefs.h</span></span>
  
> <span data-ttu-id="781ce-135">Enthält die Datentypdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="781ce-135">Provides data type definitions.</span></span>
    
<span data-ttu-id="781ce-136">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="781ce-136">Mapitags.h</span></span>
  
> <span data-ttu-id="781ce-137">Enthält Definitionen von Eigenschaften, die als zugeordneten Eigenschaften aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="781ce-137">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="781ce-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="781ce-138">See also</span></span>



[<span data-ttu-id="781ce-139">MAPI-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="781ce-139">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="781ce-140">Kanonische MAPI-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="781ce-140">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="781ce-141">Zuordnen von kanonischen Eigenschaftennamen zu MAPI-Namen</span><span class="sxs-lookup"><span data-stu-id="781ce-141">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="781ce-142">Zuordnen von MAPI-Namen zu kanonische Eigenschaftennamen</span><span class="sxs-lookup"><span data-stu-id="781ce-142">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)
