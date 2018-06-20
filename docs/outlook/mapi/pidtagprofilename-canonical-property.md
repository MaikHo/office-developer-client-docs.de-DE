---
title: Kanonische PidTagProfileName-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagProfileName
api_type:
- COM
ms.assetid: 13ca726d-ae7a-4da9-9c8e-3db3c479f839
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 6ecd84e4ffa0959a037574998b5ff12d8f539c95
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19794820"
---
# <a name="pidtagprofilename-canonical-property"></a><span data-ttu-id="cb84a-103">Kanonische PidTagProfileName-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="cb84a-103">PidTagProfileName Canonical Property</span></span>

  
  
<span data-ttu-id="cb84a-104">**Betrifft**: Outlook</span><span class="sxs-lookup"><span data-stu-id="cb84a-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="cb84a-105">Enthält den Namen des Profils an.</span><span class="sxs-lookup"><span data-stu-id="cb84a-105">Contains the name of the profile.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="cb84a-106">Zugeordneten Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="cb84a-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="cb84a-107">PR_PROFILE_NAME, PR_PROFILE_NAME_A, PR_PROFILE_NAME_W</span><span class="sxs-lookup"><span data-stu-id="cb84a-107">PR_PROFILE_NAME, PR_PROFILE_NAME_A, PR_PROFILE_NAME_W</span></span>  <br/> |
|<span data-ttu-id="cb84a-108">Bezeichner:</span><span class="sxs-lookup"><span data-stu-id="cb84a-108">Identifier:</span></span>  <br/> |<span data-ttu-id="cb84a-109">0x3D12</span><span class="sxs-lookup"><span data-stu-id="cb84a-109">0x3D12</span></span>  <br/> |
|<span data-ttu-id="cb84a-110">Datentyp:</span><span class="sxs-lookup"><span data-stu-id="cb84a-110">Data type:</span></span>  <br/> |<span data-ttu-id="cb84a-111">PT_STRING8, PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="cb84a-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="cb84a-112">Bereich:</span><span class="sxs-lookup"><span data-stu-id="cb84a-112">Area:</span></span>  <br/> |<span data-ttu-id="cb84a-113">MAPI-Profil-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="cb84a-113">MAPI profile configuration</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="cb84a-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cb84a-114">Remarks</span></span>

<span data-ttu-id="cb84a-115">Diese Eigenschaften werden von Dienstanbietern berechnet.</span><span class="sxs-lookup"><span data-stu-id="cb84a-115">These properties are computed by service providers.</span></span> <span data-ttu-id="cb84a-116">Implementierung der Funktion **ServiceEntry** eines Anbieters kann diese Eigenschaften verwenden, um den Profilnamen zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="cb84a-116">A provider's implementation of the **ServiceEntry** function can use these properties to discover the profile name.</span></span> 
  
<span data-ttu-id="cb84a-117">Clientanwendungen können diese Eigenschaften als eine praktische Alternative zum Abrufen von den Namen des Profils durch Untersuchen der Eigenschaft **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) in der MAPI-Subsystems Status Tabellenzeile.</span><span class="sxs-lookup"><span data-stu-id="cb84a-117">Client applications can use these properties as a convenient alternative to obtaining the profile name by examining the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property in the MAPI subsystem's status table row.</span></span>
  
<span data-ttu-id="cb84a-118">Diese Eigenschaften möglicherweise nicht eindeutig über die Zeit, zum Beispiel, in dem ein Profil gelöscht und später erneut mit dem gleichen Namen erstellt.</span><span class="sxs-lookup"><span data-stu-id="cb84a-118">These properties may not be unique across time, for example where a profile is deleted and later recreated with the same name.</span></span> <span data-ttu-id="cb84a-119">MAPI stellt eine vollständig eindeutige **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md))-Eigenschaft im Profilabschnitt hartcodierte bereit **MUID_PROFILE_INSTANCE.**</span><span class="sxs-lookup"><span data-stu-id="cb84a-119">MAPI furnishes a totally unique **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) property in a hard-coded profile section called **MUID_PROFILE_INSTANCE.**</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="cb84a-120">Verwandte Ressourcen</span><span class="sxs-lookup"><span data-stu-id="cb84a-120">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="cb84a-121">Header-Dateien</span><span class="sxs-lookup"><span data-stu-id="cb84a-121">Header files</span></span>

<span data-ttu-id="cb84a-122">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="cb84a-122">Mapidefs.h</span></span>
  
> <span data-ttu-id="cb84a-123">Enthält die Datentypdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="cb84a-123">Provides data type definitions.</span></span>
    
<span data-ttu-id="cb84a-124">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="cb84a-124">Mapitags.h</span></span>
  
> <span data-ttu-id="cb84a-125">Enthält Definitionen von Eigenschaften, die als Alternative Namen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="cb84a-125">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="cb84a-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cb84a-126">See also</span></span>



[<span data-ttu-id="cb84a-127">MAPI-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="cb84a-127">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="cb84a-128">Kanonische MAPI-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="cb84a-128">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="cb84a-129">Zuordnen von kanonischen Eigenschaftennamen zu MAPI-Namen</span><span class="sxs-lookup"><span data-stu-id="cb84a-129">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="cb84a-130">Zuordnen von MAPI-Namen zu kanonische Eigenschaftennamen</span><span class="sxs-lookup"><span data-stu-id="cb84a-130">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)
