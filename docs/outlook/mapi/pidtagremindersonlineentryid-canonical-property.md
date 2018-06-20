---
title: Kanonische PidTagRemindersOnlineEntryId-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRemindersOnlineEntryId
api_type:
- COM
ms.assetid: cad25cca-248d-4845-9d60-7aa60f2dda62
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: cba8de706e7262ff59abdb6367fb505a2303dcf3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19794932"
---
# <a name="pidtagremindersonlineentryid-canonical-property"></a><span data-ttu-id="9cec2-103">Kanonische PidTagRemindersOnlineEntryId-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="9cec2-103">PidTagRemindersOnlineEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="9cec2-104">**Betrifft**: Outlook</span><span class="sxs-lookup"><span data-stu-id="9cec2-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="9cec2-105">Die **EntryID** des Ordners Erinnerungen enthält.</span><span class="sxs-lookup"><span data-stu-id="9cec2-105">Contains the **EntryID** of the reminders folder.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="9cec2-106">Zugeordneten Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="9cec2-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="9cec2-107">PR_REM_ONLINE_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="9cec2-107">PR_REM_ONLINE_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="9cec2-108">Bezeichner:</span><span class="sxs-lookup"><span data-stu-id="9cec2-108">Identifier:</span></span>  <br/> |<span data-ttu-id="9cec2-109">0x36D5</span><span class="sxs-lookup"><span data-stu-id="9cec2-109">0x36D5</span></span>  <br/> |
|<span data-ttu-id="9cec2-110">Datentyp:</span><span class="sxs-lookup"><span data-stu-id="9cec2-110">Data type:</span></span>  <br/> |<span data-ttu-id="9cec2-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="9cec2-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="9cec2-112">Bereich:</span><span class="sxs-lookup"><span data-stu-id="9cec2-112">Area:</span></span>  <br/> |<span data-ttu-id="9cec2-113">MAPI-container</span><span class="sxs-lookup"><span data-stu-id="9cec2-113">MAPI container</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="9cec2-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9cec2-114">Remarks</span></span>

<span data-ttu-id="9cec2-115">Diese Eigenschaft wird im Ordner Posteingang und im Stammordner des Nachrichtenspeichers gespeichert.</span><span class="sxs-lookup"><span data-stu-id="9cec2-115">This property is stored in the Inbox folder and in the root folder of the message store.</span></span> <span data-ttu-id="9cec2-116">Zugriff auf die Eigenschaft auf eine bestimmte Nachricht Store die folgenden Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="9cec2-116">To access the property on a specific message store, do the following.</span></span> 
  
1. <span data-ttu-id="9cec2-117">Suchen Sie zunächst nach der Eigenschaft im Ordner Posteingang.</span><span class="sxs-lookup"><span data-stu-id="9cec2-117">First, look for the property in the Inbox folder.</span></span> <span data-ttu-id="9cec2-118">Verwenden Sie [IMsgStore::GetReceiveFolder](imsgstore-getreceivefolder.md) , um einen Verweis auf die **Eintrags-ID** für den Ordner Posteingang abzurufen.</span><span class="sxs-lookup"><span data-stu-id="9cec2-118">Use [IMsgStore::GetReceiveFolder](imsgstore-getreceivefolder.md) to obtain a reference to the **EntryID** for the Inbox folder.</span></span> 
    
2. <span data-ttu-id="9cec2-119">Wenn **IMsgStore::GetReceiveFolder** erfolgreich ist, verwenden Sie den Verweis auf die **EntryID** des Posteingang und [IMsgStore::OpenEntry](imsgstore-openentry.md) zum Öffnen des Posteingangs, und rufen Sie einen Verweis auf ein Objekt **IMAPIFolder** .</span><span class="sxs-lookup"><span data-stu-id="9cec2-119">If **IMsgStore::GetReceiveFolder** is successful, then use the reference to the **EntryID** of the Inbox and [IMsgStore::OpenEntry](imsgstore-openentry.md) to open the Inbox and obtain a reference to an **IMAPIFolder** object.</span></span> 
    
3. <span data-ttu-id="9cec2-120">Wenn **IMsgStore::OpenEntry** erfolgreich ist, müssen verwenden Sie den zurückgegebenen Verweis auf das **IMAPIFolder** -Objekt und [IMAPIProp::GetProps](imapiprop-getprops.md) dann, um die gewünschte Eigenschaft abzurufen.</span><span class="sxs-lookup"><span data-stu-id="9cec2-120">If **IMsgStore::OpenEntry** is successful, then use the returned reference to the **IMAPIFolder** object and [IMAPIProp::GetProps](imapiprop-getprops.md) to obtain the desired property.</span></span> 
    
4. <span data-ttu-id="9cec2-121">Wenn Schritt 1, 2 oder 3 fehlschlägt, suchen Sie nach der-Eigenschaft im Stammordner gespeichert.</span><span class="sxs-lookup"><span data-stu-id="9cec2-121">If Step 1, 2, or 3 fails, look for the property in the root folder.</span></span> <span data-ttu-id="9cec2-122">Verwenden Sie hierzu **IMsgStore::OpenEntry**, Angeben von NULL für die **LpEntryID**, um den Stammordner des Nachrichtenspeichers öffnen, und rufen Sie einen Verweis auf das **IMAPIFolder** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="9cec2-122">To do that, use **IMsgStore::OpenEntry**, specifying NULL for **lpEntryID**, to open the root folder of the message store and obtain a reference to the **IMAPIFolder** object.</span></span> 
    
5. <span data-ttu-id="9cec2-123">Wenn Stammordner öffnen erfolgreich ist, müssen verwenden Sie den zurückgegebenen Verweis auf das **IMAPIFolder** -Objekt und **IMAPIProp::GetProps** dann, um die gewünschte Eigenschaft abzurufen.</span><span class="sxs-lookup"><span data-stu-id="9cec2-123">If opening the root folder is successful, then use the returned reference to the **IMAPIFolder** object and **IMAPIProp::GetProps** to obtain the desired property.</span></span> 
    
## <a name="related-resources"></a><span data-ttu-id="9cec2-124">Verwandte Ressourcen</span><span class="sxs-lookup"><span data-stu-id="9cec2-124">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="9cec2-125">Protokollspezifikationen</span><span class="sxs-lookup"><span data-stu-id="9cec2-125">Protocol specifications</span></span>

<span data-ttu-id="9cec2-126">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9cec2-126">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="9cec2-127">Bietet Verweise auf Verwandte Exchange Server-Spezifikationen.</span><span class="sxs-lookup"><span data-stu-id="9cec2-127">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="9cec2-128">[[MS-OXOSFLD]](http://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="9cec2-128">[[MS-OXOSFLD]](http://msdn.microsoft.com/library/a60e9c16-2ba8-424b-b60c-385a8a2837cb%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="9cec2-129">Gibt die Eigenschaften und Operationen für das Erstellen und Ordner mit Sonderfunktion in einem Postfach suchen.</span><span class="sxs-lookup"><span data-stu-id="9cec2-129">Specifies the properties and operations for creating and locating the special folders in a mailbox.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="9cec2-130">Header-Dateien</span><span class="sxs-lookup"><span data-stu-id="9cec2-130">Header files</span></span>

<span data-ttu-id="9cec2-131">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="9cec2-131">Mapidefs.h</span></span>
  
> <span data-ttu-id="9cec2-132">Enthält die Datentypdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="9cec2-132">Provides data type definitions.</span></span>
    
<span data-ttu-id="9cec2-133">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="9cec2-133">Mapitags.h</span></span>
  
> <span data-ttu-id="9cec2-134">Enthält Definitionen von Eigenschaften, die als Alternative Namen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="9cec2-134">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="9cec2-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9cec2-135">See also</span></span>



[<span data-ttu-id="9cec2-136">MAPI-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9cec2-136">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="9cec2-137">Kanonische MAPI-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9cec2-137">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="9cec2-138">Zuordnen von kanonischen Eigenschaftennamen zu MAPI-Namen</span><span class="sxs-lookup"><span data-stu-id="9cec2-138">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="9cec2-139">Zuordnen von MAPI-Namen zu kanonische Eigenschaftennamen</span><span class="sxs-lookup"><span data-stu-id="9cec2-139">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)
