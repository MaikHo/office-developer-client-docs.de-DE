---
title: Öffnen eine Beschreibung der Ansicht
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 1940feb0-9e0f-4d96-9fb9-b9a35a0aa661
description: 'Letzte �nderung: Samstag, 23. Juli 2011'
ms.openlocfilehash: 525c817cfc3bdcf96455d35025e85486ec8b5b42
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19793305"
---
# <a name="opening-a-view-descriptor"></a><span data-ttu-id="3cb24-103">Öffnen eine Beschreibung der Ansicht</span><span class="sxs-lookup"><span data-stu-id="3cb24-103">Opening a view descriptor</span></span>
  
<span data-ttu-id="3cb24-104">**Betrifft**: Outlook</span><span class="sxs-lookup"><span data-stu-id="3cb24-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="3cb24-105">Viele Ordner können mit einer Normalansicht, eine Standardansicht oder eine beliebige Anzahl von personalisierte Ansichten geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="3cb24-105">Many folders can be opened with a normal view, a default view, or any number of personalized views.</span></span> <span data-ttu-id="3cb24-106">Eine Ansicht wird beschrieben, wie der Inhalt eines Ordners angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="3cb24-106">A view describes how to display the contents of a folder.</span></span> <span data-ttu-id="3cb24-107">Die Normalansicht wird verwendet, wenn keine alternativen Ansicht vorhanden ist und wenn Sie den Ordner zum ersten Mal öffnen.</span><span class="sxs-lookup"><span data-stu-id="3cb24-107">The normal view is used when there is no alternative view and when you are opening the folder for the first time.</span></span> <span data-ttu-id="3cb24-108">Wenn Sie eine alternative Ansicht vorhanden ist, müssen Sie es zum Öffnen des Ordners verwenden.</span><span class="sxs-lookup"><span data-stu-id="3cb24-108">When an alternative view does exist, you must use it to open the folder.</span></span>
  
<span data-ttu-id="3cb24-109">Eine Ansicht wird in einer Nachricht als ein Deskriptor Ansicht bezeichnet beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3cb24-109">A view is described in a message known as a view descriptor.</span></span> <span data-ttu-id="3cb24-110">Ansicht Deskriptoren werden in der Regel als zugeordneten Nachrichten erstellt und in den allgemeinen oder persönliche Ansicht-Ordnern oder in einem Ordner IPM können angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3cb24-110">View descriptors are typically created as associated messages and can appear in either the common or personal view folders or in any IPM folder.</span></span>
  
### <a name="to-open-a-view-descriptor"></a><span data-ttu-id="3cb24-111">Eine Beschreibung der Ansicht öffnen</span><span class="sxs-lookup"><span data-stu-id="3cb24-111">To open a view descriptor</span></span>
  
1. <span data-ttu-id="3cb24-112">Rufen Sie [IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md) zum Abrufen des zugehörigen Inhaltsverzeichnisses für den Ordner.</span><span class="sxs-lookup"><span data-stu-id="3cb24-112">Call [IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md) to retrieve the associated contents table for the folder.</span></span> 
    
2. <span data-ttu-id="3cb24-113">Erstellen Sie eine Beschränkung, der nur Nachrichten mit der Nachrichtenklasse für die Ansicht Deskriptoren reserviert ermittelt und rufen Sie die [Methode IMAPITable:: Restrict](imapitable-restrict.md) zur Begrenzung der Tabelle und [IMAPITable::QueryRows](imapitable-queryrows.md) zum Abrufen der entsprechenden Zeilen, oder...</span><span class="sxs-lookup"><span data-stu-id="3cb24-113">Create a restriction that locates only messages with the message class reserved for view descriptors and call [IMAPITable::Restrict](imapitable-restrict.md) to limit the table and [IMAPITable::QueryRows](imapitable-queryrows.md) to retrieve the appropriate rows, or...</span></span>
    
   <span data-ttu-id="3cb24-114">Rufen Sie den Ordner [IMAPIProp::GetProps](imapiprop-getprops.md) -Methode zum Abrufen der Eigenschaft **PR_DEFAULT_VIEW_ENTRYID** ([PidTagDefaultViewEntryId](pidtagdefaultviewentryid-canonical-property.md)).</span><span class="sxs-lookup"><span data-stu-id="3cb24-114">Call the folder's [IMAPIProp::GetProps](imapiprop-getprops.md) method to retrieve its **PR_DEFAULT_VIEW_ENTRYID** ([PidTagDefaultViewEntryId](pidtagdefaultviewentryid-canonical-property.md)) property.</span></span> <span data-ttu-id="3cb24-115">**PR_DEFAULT_VIEW_ENTRYID** enthält die Eintrags-ID für die Nachricht mit der standardmäßigen Ansicht Deskriptor für einen Ordner.</span><span class="sxs-lookup"><span data-stu-id="3cb24-115">**PR_DEFAULT_VIEW_ENTRYID** contains the entry identifier for the message containing the default view descriptor for a folder.</span></span> <span data-ttu-id="3cb24-116">Dieser Aufruf erfolgreich, wenn der Ordner die Verwendung des MAPI_ASSOCIATED-Flags für Aufrufe von [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) und [IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md)unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3cb24-116">This call will succeed if the folder supports the use of the MAPI_ASSOCIATED flag on calls to [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) and [IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md).</span></span>
    
3. <span data-ttu-id="3cb24-117">Rufen Sie [IMsgStore::OpenEntry](imsgstore-openentry.md) , wobei die Eintrags-ID der Ansicht Deskriptor zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="3cb24-117">Call [IMsgStore::OpenEntry](imsgstore-openentry.md) with the entry identifier of the view descriptor to open it.</span></span> 
    
