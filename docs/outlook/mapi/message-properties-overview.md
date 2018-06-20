---
title: Nachricht Eigenschaften (Übersicht)
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 447f54de-9f0d-4f73-89b6-bed9cfea9c15
description: 'Letzte �nderung: Samstag, 23. Juli 2011'
ms.openlocfilehash: 78e2f63746a866603bc2392fbe5c8bb25d3f38c5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19793264"
---
# <a name="message-properties-overview"></a><span data-ttu-id="96cfa-103">Nachricht Eigenschaften (Übersicht)</span><span class="sxs-lookup"><span data-stu-id="96cfa-103">Message Properties Overview</span></span>

  
  
<span data-ttu-id="96cfa-104">**Betrifft**: Outlook</span><span class="sxs-lookup"><span data-stu-id="96cfa-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="96cfa-105">MAPI ist Nachrichteneigenschaften in drei Typen unterteilt:</span><span class="sxs-lookup"><span data-stu-id="96cfa-105">MAPI divides message properties into three types:</span></span>
  
- <span data-ttu-id="96cfa-106">Content Nachrichteneigenschaften.</span><span class="sxs-lookup"><span data-stu-id="96cfa-106">Message content properties.</span></span>
    
- <span data-ttu-id="96cfa-107">Nachrichteneigenschaften Übertragung, oder einen Umschlag zu.</span><span class="sxs-lookup"><span data-stu-id="96cfa-107">Message transmission, or envelope, properties.</span></span>
    
- <span data-ttu-id="96cfa-108">Nachricht Empfängereigenschaften.</span><span class="sxs-lookup"><span data-stu-id="96cfa-108">Message recipient properties.</span></span>
    
<span data-ttu-id="96cfa-109">Content Nachrichteneigenschaften beschreiben den Text einer Nachricht.</span><span class="sxs-lookup"><span data-stu-id="96cfa-109">Message content properties describe the text of a message.</span></span> <span data-ttu-id="96cfa-110">Jede Nachrichtenklasse verfügt über einen eigenen Satz an Content-Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="96cfa-110">Every message class has its own set of content properties.</span></span> <span data-ttu-id="96cfa-111">MAPI definiert Content-Eigenschaften für Notizen und Bericht Nachrichten. Es ist bis zu Clients and Message-Anbieter, die diese Klassen werden Nachrichten an die Eigenschaften entsprechend ihren Implementierungen festlegen behandelt.</span><span class="sxs-lookup"><span data-stu-id="96cfa-111">MAPI defines content properties for note and report messages; it is up to the clients and message store providers that handle these classes of messages to set the properties appropriately for their implementations.</span></span> <span data-ttu-id="96cfa-112">**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) und **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) sind Beispiele für Content-Eigenschaften für Hinweis Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="96cfa-112">**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) and **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) are examples of content properties for note messages.</span></span> <span data-ttu-id="96cfa-113">**PR_BODY** enthält den unformatierten Inhalt einer Notiz **PR_RTF_COMPRESSED** die komprimierte Version der formatierte Inhalt einer Notiz.</span><span class="sxs-lookup"><span data-stu-id="96cfa-113">**PR_BODY** contains the unformatted contents of a note, while **PR_RTF_COMPRESSED** contains the compressed version of a note's formatted contents.</span></span> <span data-ttu-id="96cfa-114">Weitere Informationen zur Eigenschaft Bezeichner Bereichen finden Sie unter [Eigenschaft Bezeichner Bereiche](property-identifier-ranges.md).</span><span class="sxs-lookup"><span data-stu-id="96cfa-114">For more information about property identifier ranges, see [Property Identifier Ranges](property-identifier-ranges.md).</span></span>
  
<span data-ttu-id="96cfa-115">Für neue Nachrichtenklassen; können Clients in einem der folgenden beiden Methoden Inhalte-spezifische Eigenschaften definieren:</span><span class="sxs-lookup"><span data-stu-id="96cfa-115">For new message classes, clients can define content-specific properties in one of two ways:</span></span>
  
- <span data-ttu-id="96cfa-116">Im Bereich benutzerdefinierten Meldung Klasse-Content-Eigenschaften mithilfe von Eigenschaftenbezeichner: 0x6800 über 0x7BFF.</span><span class="sxs-lookup"><span data-stu-id="96cfa-116">By using property identifiers in the custom message class content properties range: 0x6800 through 0x7BFF.</span></span>
    
- <span data-ttu-id="96cfa-117">Mithilfe von benannten Eigenschaften mit IDs, die in der 0 x 8000 über 0xFFFE Bereich liegen.</span><span class="sxs-lookup"><span data-stu-id="96cfa-117">By using named properties that have identifiers that fall in the 0x8000 through 0xFFFE range.</span></span>
    
<span data-ttu-id="96cfa-118">Der Bezeichner Bereich für benutzerdefinierte Meldung Klasseneigenschaften Content steht jeder Client, der eine benutzerdefinierte Nachrichtenklasse erstellt.</span><span class="sxs-lookup"><span data-stu-id="96cfa-118">The identifier range for custom message class content properties is available to any client that creates a custom message class.</span></span> <span data-ttu-id="96cfa-119">Aus diesem Grund kann ein Bezeichner in diesem Bereich für mehrere Nachrichtenklassen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="96cfa-119">Therefore, one property identifier in this range can be used for multiple message classes.</span></span> <span data-ttu-id="96cfa-120">Benutzer von Eigenschaften in diesem Bereich Annahmen über das Verhalten der Eigenschaften nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="96cfa-120">Users of properties in this range cannot make assumptions as to the behavior of the properties.</span></span> 
  
<span data-ttu-id="96cfa-121">Clients erstellen für benannte Eigenschaften einen Namen, der einen Eigenschaftensatz und eine Zeichenfolge oder einen numerischen Wert für jede neue Eigenschaft angibt.</span><span class="sxs-lookup"><span data-stu-id="96cfa-121">For named properties, clients create a name that specifies a property set and either a character string or a numeric value for each new property.</span></span> <span data-ttu-id="96cfa-122">Clients ordnen Sie dann die-Eigenschaft einen Bezeichner in der benannten Eigenschaftsbereich.</span><span class="sxs-lookup"><span data-stu-id="96cfa-122">Clients then associate the property with an identifier in the named property range.</span></span> <span data-ttu-id="96cfa-123">Benutzer von benannten Eigenschaften, die sie durch den Namen oder Bezeichner über die Methoden [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) und [IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md) zugreifen.</span><span class="sxs-lookup"><span data-stu-id="96cfa-123">Users of named properties access them by name or identifier through the [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) and [IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md) methods.</span></span> 
  
<span data-ttu-id="96cfa-124">Umschlageigenschaften enthalten Informationen, die verwendet wird, um eine Nachricht von einem Empfänger in eine andere zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="96cfa-124">Envelope properties provide information that is used to transmit a message from one recipient to another.</span></span> <span data-ttu-id="96cfa-125">Wie bei Content Nachrichteneigenschaften, ist es möglich, dass Clients oder Dienstanbieter eigene Umschlageigenschaften definieren, die zu ergänzen, die MAPI definiert.</span><span class="sxs-lookup"><span data-stu-id="96cfa-125">As with message content properties, it is possible for clients or service providers to define their own envelope properties to supplement those that MAPI defines.</span></span> <span data-ttu-id="96cfa-126">Clients und Transportanbieter Umschlageigenschaften festlegen, die MAPI definiert basierend auf der Definition, die MAPI bietet.</span><span class="sxs-lookup"><span data-stu-id="96cfa-126">Clients and transport providers set the envelope properties that MAPI defines based on the definition that MAPI provides.</span></span> <span data-ttu-id="96cfa-127">Transportanbieter, die spezielle Features implementieren können ihre eigenen Umschlageigenschaften, um die Features für Clients verfügbar machen definieren.</span><span class="sxs-lookup"><span data-stu-id="96cfa-127">Transport providers that implement special features can define their own envelope properties to expose those features to clients.</span></span> <span data-ttu-id="96cfa-128">MAPI reserviert einen Bereich von eigenschaftskennungen, die für diese speziellen vom Anbieter definiertes Eigenschaften verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="96cfa-128">MAPI sets aside a range of property identifiers that can be used for these special provider-defined properties.</span></span> <span data-ttu-id="96cfa-129">Transportanbieter implementieren in der Regel eine spezielle Eigenschaftenseite um diese Eigenschaften anzuzeigen, und Aktivieren von Clients, sie zu ändern.</span><span class="sxs-lookup"><span data-stu-id="96cfa-129">Transport providers typically implement a special property page to display these properties and enable clients to change them.</span></span> <span data-ttu-id="96cfa-130">**PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) und **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) sind Beispiele für Eigenschaften von Umschlägen.</span><span class="sxs-lookup"><span data-stu-id="96cfa-130">**PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) and **PR_MESSAGE_CLASS** ([PidTagMessageClass](pidtagmessageclass-canonical-property.md)) are examples of envelope properties.</span></span> <span data-ttu-id="96cfa-131">Weitere Informationen finden Sie unter [Eigenschaft Bezeichner Bereiche](property-identifier-ranges.md).</span><span class="sxs-lookup"><span data-stu-id="96cfa-131">For more information, see [Property Identifier Ranges](property-identifier-ranges.md).</span></span>
  
<span data-ttu-id="96cfa-132">Empfängereigenschaften beschreiben das Ziel für eine gesendete Nachricht.</span><span class="sxs-lookup"><span data-stu-id="96cfa-132">Recipient properties describe the destination for a sent message.</span></span> <span data-ttu-id="96cfa-133">Ein Empfänger kann ein messaging-Benutzer, Verteilerliste oder einem Computer sein.</span><span class="sxs-lookup"><span data-stu-id="96cfa-133">A recipient can be a messaging user, distribution list, or a computer.</span></span> <span data-ttu-id="96cfa-134">Empfängereigenschaften werden von MAPI definierten und vom Dienstanbieter festgelegt.</span><span class="sxs-lookup"><span data-stu-id="96cfa-134">Recipient properties are defined by MAPI and set by service providers.</span></span> <span data-ttu-id="96cfa-135">Einige Empfängereigenschaften werden von adressbuchanbietern implementierte für ihre messaging-Benutzer und Verteilung List-Objekten unterstützt. andere Empfängereigenschaften werden von Clients, Nachricht Store oder Transportanbieter unterstützt.</span><span class="sxs-lookup"><span data-stu-id="96cfa-135">Some recipient properties are supported by address book providers for their messaging user and distribution list objects; other recipient properties are supported by clients, message store providers, or transport providers.</span></span> <span data-ttu-id="96cfa-136">Beispielsweise erfordern alle Empfänger eine Adresse und einen Adresstyp. Dies sind die Eigenschaften, die vom Adressbuch-Dienstanbieter verwaltet werden, wenn der Empfänger in einem von den Containern gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="96cfa-136">For example, all recipients require an address and an address type; these are properties maintained by an address book provider when the recipient is stored in one of its containers.</span></span> <span data-ttu-id="96cfa-137">Empfänger können auch einen Typ, **PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)), die einen Empfänger als Primär, Carbon Copy, Blindkopie oder Bcc-Empfänger identifiziert.</span><span class="sxs-lookup"><span data-stu-id="96cfa-137">Recipients also have a type, **PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)), which identifies a recipient as either a primary, carbon copy, or blind carbon copy recipient.</span></span>
  
<span data-ttu-id="96cfa-138">Viele Nachrichteneigenschaften sind optional, d. h., dass Clients verfügbar oder festgelegten erwartet können nicht auf gültige Werte.</span><span class="sxs-lookup"><span data-stu-id="96cfa-138">Many message properties are optional, meaning that clients cannot expect them to be available or set to valid values.</span></span> <span data-ttu-id="96cfa-139">Einige Nachrichteneigenschaften sind erforderlich, aber verfügbar, nur, wenn eine Nachricht in einem bestimmten Zustand befindet.</span><span class="sxs-lookup"><span data-stu-id="96cfa-139">Some message properties are required but available only when a message is in a particular state.</span></span> <span data-ttu-id="96cfa-140">Eine neu erstellte Nachricht ist beispielsweise nicht erforderlich, um einen Eintrag Bezeichner bis haben, nachdem die Nachricht wurde gespeichert, und es nicht erforderlich ist, um eine Nachrichtenklasse haben, bis die Nachricht gesendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="96cfa-140">For example, a newly created message is not required to have an entry identifier until after the message has been saved, and it is not required to have a message class until the message is ready to be submitted.</span></span> <span data-ttu-id="96cfa-141">Clients sollte immer überprüfen Sie die Ergebnisse der ihre Anrufe [IMAPIProp::GetProps](imapiprop-getprops.md) und [IMAPIProp::OpenProperty](imapiprop-openproperty.md) und haben die Standardwerte bereit als Sicherung für den Fall, dass eine angeforderte Eigenschaft nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="96cfa-141">Clients should always check the results of their [IMAPIProp::GetProps](imapiprop-getprops.md) and [IMAPIProp::OpenProperty](imapiprop-openproperty.md) calls and have default values ready as a backup in case a requested property is unavailable.</span></span> 
  
<span data-ttu-id="96cfa-142">Die meisten Nachrichteneigenschaften, die Dienstanbieter festgelegt sind, an die Clients schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="96cfa-142">Most message properties that service providers set are read-only to clients.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="96cfa-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="96cfa-143">See also</span></span>



[<span data-ttu-id="96cfa-144">MAPI-Nachrichten</span><span class="sxs-lookup"><span data-stu-id="96cfa-144">MAPI Messages</span></span>](mapi-messages.md)
