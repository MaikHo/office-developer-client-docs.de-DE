---
title: Abrufen von primären und Anbieter Identität
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d81bb81d-1708-4a8d-a4d5-c3ba087db9b7
description: 'Letzte �nderung: Samstag, 23. Juli 2011'
ms.openlocfilehash: 2a87e32fe21aa6fb1d9296c568a74da994c146bb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19795389"
---
# <a name="retrieving-primary-and-provider-identity"></a><span data-ttu-id="59654-103">Abrufen von primären und Anbieter Identität</span><span class="sxs-lookup"><span data-stu-id="59654-103">Retrieving Primary and Provider Identity</span></span>

  
  
<span data-ttu-id="59654-104">**Betrifft**: Outlook</span><span class="sxs-lookup"><span data-stu-id="59654-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="59654-105">Dienstanbieter, die in der Regel von adressbuchanbietern implementierte, haben die Möglichkeit eine Identität, die zum Darstellen der Sitzung in einer Vielzahl von Situationen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="59654-105">Service providers, typically address book providers, have the option of supplying an identity that can be used to represent the session in a variety of situations.</span></span> <span data-ttu-id="59654-106">Drei Eigenschaften wird die Identität des Anbieters beschrieben:</span><span class="sxs-lookup"><span data-stu-id="59654-106">Three properties describe a provider's identity:</span></span>
  
- <span data-ttu-id="59654-107">**PR_IDENTITY_ENTRYID** ([PidTagIdentityEntryId](pidtagidentityentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="59654-107">**PR_IDENTITY_ENTRYID** ([PidTagIdentityEntryId](pidtagidentityentryid-canonical-property.md))</span></span> 
    
- <span data-ttu-id="59654-108">**PR_IDENTITY_DISPLAY** ([PidTagIdentityDisplay](pidtagidentitydisplay-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="59654-108">**PR_IDENTITY_DISPLAY** ([PidTagIdentityDisplay](pidtagidentitydisplay-canonical-property.md))</span></span> 
    
- <span data-ttu-id="59654-109">**PR_IDENTITY_SEARCH_KEY** ([PidTagIdentitySearchKey](pidtagidentitysearchkey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="59654-109">**PR_IDENTITY_SEARCH_KEY** ([PidTagIdentitySearchKey](pidtagidentitysearchkey-canonical-property.md))</span></span> 
    
<span data-ttu-id="59654-110">Diese Eigenschaften werden festgelegt, um die Eintrags-ID, Anzeigename und Suche-Schlüssel, der die entsprechenden Identitätsobjekt, das in der Regel ein messaging-Benutzer ist.</span><span class="sxs-lookup"><span data-stu-id="59654-110">These properties are set to the entry identifier, display name, and search key of the corresponding identity object, which is typically a messaging user.</span></span> <span data-ttu-id="59654-111">Anbieter, die eine Identität angeben legen Sie das STATUS_PRIMARY_IDENTITY-Flag auch in ihren **PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md))-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="59654-111">Providers that supply an identity also set the STATUS_PRIMARY_IDENTITY flag in their **PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="59654-112">Je nach Ihren Anforderungen können Sie einen bestimmten Anbieter Identität oder das primäre Identität für die Sitzung verwenden.</span><span class="sxs-lookup"><span data-stu-id="59654-112">Depending on your needs, you might use a particular provider's identity or the primary identity for the session.</span></span> <span data-ttu-id="59654-113">Sie können die Identität des Anbieters auch für die Anzeige oder zum Abrufen von Eigenschaften, wie beispielsweise **PR_RESOURCE_PATH** ([PidTagResourcePath](pidtagresourcepath-canonical-property.md)) verwenden.</span><span class="sxs-lookup"><span data-stu-id="59654-113">You can use a provider's identity also for display purposes or to retrieve properties, such as **PR_RESOURCE_PATH** ([PidTagResourcePath](pidtagresourcepath-canonical-property.md)).</span></span> <span data-ttu-id="59654-114">**PR_RESOURCE_PATH**, wenn festgelegt ist, enthält den Pfad zu den Dateien vom Anbieter erstellt oder verwendet.</span><span class="sxs-lookup"><span data-stu-id="59654-114">**PR_RESOURCE_PATH**, if set, contains the path to files used or created by the provider.</span></span> <span data-ttu-id="59654-115">Abrufen der **PR_RESOURCE_PATH** -Eigenschaft für den Anbieter für die primäre Identität angeben, wenn Sie Dateien zu suchen, die dem Benutzer der Sitzung gehören möchten.</span><span class="sxs-lookup"><span data-stu-id="59654-115">Retrieve the **PR_RESOURCE_PATH** property for the provider supplying the primary identity when you want to locate files that pertain to the user of the session.</span></span> 
  
 <span data-ttu-id="59654-116">**Um die Identität eines bestimmten Anbieters abzurufen.**</span><span class="sxs-lookup"><span data-stu-id="59654-116">**To retrieve the identity of a specific provider**</span></span>
  
1. <span data-ttu-id="59654-117">Rufen Sie [IMAPISession::GetStatusTable](imapisession-getstatustable.md) Zugriff auf die Statustabelle.</span><span class="sxs-lookup"><span data-stu-id="59654-117">Call [IMAPISession::GetStatusTable](imapisession-getstatustable.md) to access the status table.</span></span> 
    
2. <span data-ttu-id="59654-118">Erstellen Sie eine Einschränkung mithilfe einer [SPropertyRestriction](spropertyrestriction.md) Struktur entsprechend die Spalte **PR_PROVIDER_DLL_NAME** ([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md)) mit dem Namen des angegebenen Anbieters.</span><span class="sxs-lookup"><span data-stu-id="59654-118">Build a restriction using an [SPropertyRestriction](spropertyrestriction.md) structure to match the **PR_PROVIDER_DLL_NAME** ([PidTagProviderDllName](pidtagproviderdllname-canonical-property.md)) column with the name of the specified provider.</span></span> 
    
3. <span data-ttu-id="59654-119">Rufen Sie [IMAPITable](imapitable-findrow.md) , um den Anbieter Zeile zu finden.</span><span class="sxs-lookup"><span data-stu-id="59654-119">Call [IMAPITable::FindRow](imapitable-findrow.md) to locate the provider's row.</span></span> <span data-ttu-id="59654-120">Identität des Anbieters wird in der Spalte **PR_IDENTITY_ENTRYID** gespeichert werden, sofern vorhanden.</span><span class="sxs-lookup"><span data-stu-id="59654-120">The provider's identity will be stored in the **PR_IDENTITY_ENTRYID** column, if it exists.</span></span> 
    
 <span data-ttu-id="59654-121">**Um die primäre Identität für eine Sitzung abzurufen**</span><span class="sxs-lookup"><span data-stu-id="59654-121">**To retrieve the primary identity for a session**</span></span>
  
- <span data-ttu-id="59654-122">Rufen Sie [IMAPISession::QueryIdentity](imapisession-queryidentity.md).</span><span class="sxs-lookup"><span data-stu-id="59654-122">Call [IMAPISession::QueryIdentity](imapisession-queryidentity.md).</span></span> <span data-ttu-id="59654-123">**QueryIdentity** baut Sitzung Identität auf das Vorhandensein der STATUS_PRIMARY_IDENTITY Wert in der Spalte **PR_RESOURCE_FLAGS** für eine der Zeilen in der Tabelle "Status".</span><span class="sxs-lookup"><span data-stu-id="59654-123">**QueryIdentity** bases session identity on the existence of the STATUS_PRIMARY_IDENTITY value in the **PR_RESOURCE_FLAGS** column for one of the rows in the status table.</span></span> <span data-ttu-id="59654-124">Wenn keine Zeile Status dieser Wert festgelegt ist, weist **QueryIdentity** Identität zum ersten-Dienstanbieter, der die drei PR_IDENTITY Eigenschaften festlegt.</span><span class="sxs-lookup"><span data-stu-id="59654-124">If none of the status rows have this value set, **QueryIdentity** assigns identity to the first service provider that sets the three PR_IDENTITY properties.</span></span> <span data-ttu-id="59654-125">Wenn kein Dienstanbieter eine Identität bereitstellt, gibt **QueryIdentity** MAPI_W_NO_SERVICE zurück.</span><span class="sxs-lookup"><span data-stu-id="59654-125">If no service provider supplies an identity, **QueryIdentity** returns MAPI_W_NO_SERVICE.</span></span> <span data-ttu-id="59654-126">In diesem Fall sollten Sie erstellen eine Zeichenfolge, um einen allgemeinen Benutzer darstellen, der als primäre Identität verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="59654-126">When this happens, you should create a character string to represent a generic user that can serve as the primary identity.</span></span> 
    
 <span data-ttu-id="59654-127">**Die primäre Identität für eine Sitzung explizit festlegen**</span><span class="sxs-lookup"><span data-stu-id="59654-127">**To explicitly set the primary identity for a session**</span></span>
  
- <span data-ttu-id="59654-128">Rufen Sie [IMsgServiceAdmin::SetPrimaryIdentity](imsgserviceadmin-setprimaryidentity.md).</span><span class="sxs-lookup"><span data-stu-id="59654-128">Call [IMsgServiceAdmin::SetPrimaryIdentity](imsgserviceadmin-setprimaryidentity.md).</span></span> <span data-ttu-id="59654-129">Übergeben Sie die **MAPIUID** für den Ziel-Dienstanbieter.</span><span class="sxs-lookup"><span data-stu-id="59654-129">Pass the **MAPIUID** for the target service provider.</span></span> 
    
