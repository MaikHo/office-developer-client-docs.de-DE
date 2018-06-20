---
title: Nachricht Empfang Modell
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d85d269e-2251-4399-9159-a2f47a85e3d1
description: 'Letzte �nderung: Samstag, 23. Juli 2011'
ms.openlocfilehash: cecdb2c30d6c9df2aafbeed43714269b863ebc48
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/15/2018
ms.locfileid: "19793257"
---
# <a name="message-reception-model"></a><span data-ttu-id="21335-103">Nachricht Empfang Modell</span><span class="sxs-lookup"><span data-stu-id="21335-103">Message Reception Model</span></span>

  
  
<span data-ttu-id="21335-104">**Betrifft**: Outlook</span><span class="sxs-lookup"><span data-stu-id="21335-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="21335-105">Der Adressbuchhierarchie steuert, ob die MAPI-Warteschlange es für eingehende e-Mails Fragen muss oder führt gibt an, ob ein Rückruf an die Warteschlange MAPI, wenn neue Nachrichten eingehen.</span><span class="sxs-lookup"><span data-stu-id="21335-105">The transport provider controls whether the MAPI spooler must poll it for incoming mail or whether it performs a call back to the MAPI spooler when new mail arrives.</span></span> <span data-ttu-id="21335-106">Beenden von [IXPProvider::TransportLogon](ixpprovider-transportlogon.md) Abruf anfordern, legt der Transportdienst SP_LOGON_POLL-Flag.</span><span class="sxs-lookup"><span data-stu-id="21335-106">The transport provider sets the SP_LOGON_POLL flag when it returns from [IXPProvider::TransportLogon](ixpprovider-transportlogon.md) to request polling.</span></span> <span data-ttu-id="21335-107">Andernfalls wird der Adressbuchhierarchie [IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md) verwendet, wenn eingehende e-Mails verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="21335-107">Otherwise, the transport provider uses [IMAPISupport::SpoolerNotify](imapisupport-spoolernotify.md) when incoming mail is available.</span></span> <span data-ttu-id="21335-108">Nach dem Learning, dass eingehende e-Mails verfügbar ist, die MAPI-Warteschlange öffnet eine neue Nachricht und fordert der Adressbuchhierarchie zum Speichern von empfangenen Nachrichteneigenschaften in die Nachricht an.</span><span class="sxs-lookup"><span data-stu-id="21335-108">After learning that incoming mail is available, the MAPI spooler opens a new message and asks the transport provider to store the received message properties into the message.</span></span> 
  
<span data-ttu-id="21335-109">Dieser Prozess funktioniert folgendermaßen:</span><span class="sxs-lookup"><span data-stu-id="21335-109">This process works as follows:</span></span>
  
1. <span data-ttu-id="21335-110">Verfügbare Nachrichten werden durch entweder der Adressbuchhierarchie Aufrufen **IMAPISupport::SpoolerNotify** oder durch die MAPI-Warteschlange aufrufen [IXPLogon::Poll](ixplogon-poll.md)angegeben.</span><span class="sxs-lookup"><span data-stu-id="21335-110">Available messages are indicated by either the transport provider calling **IMAPISupport::SpoolerNotify** or by the MAPI spooler calling [IXPLogon::Poll](ixplogon-poll.md).</span></span>
    
2. <span data-ttu-id="21335-111">Die MAPI-Warteschlange ruft [IXPLogon::StartMessage](ixplogon-startmessage.md) , um den Vorgang zu initiieren.</span><span class="sxs-lookup"><span data-stu-id="21335-111">The MAPI spooler calls [IXPLogon::StartMessage](ixplogon-startmessage.md) to initiate the process.</span></span> 
    
3. <span data-ttu-id="21335-112">Der Adressbuchhierarchie Fügt einen Verweiswert an der Position, die in **StartMessage**verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="21335-112">The transport provider places a reference value in the location referenced in **StartMessage**.</span></span> <span data-ttu-id="21335-113">Diese Referenzwerte zulassen der Adressbuchhierarchie und die MAPI-Warteschlange zum Nachverfolgen der Nachricht verarbeitet wird, wenn mehrere Nachrichten übermitteln vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="21335-113">These reference values allow the transport provider and the MAPI spooler to keep track of which message is being processed when there are multiple messages to deliver.</span></span>
    
4. <span data-ttu-id="21335-114">Der Transportdienst speichert die Daten der Nachricht in den übergebenen [IMessage: IMAPIProp](imessageimapiprop.md) Instanz.</span><span class="sxs-lookup"><span data-stu-id="21335-114">The transport provider stores the message data into the passed [IMessage : IMAPIProp](imessageimapiprop.md) instance.</span></span> 
    
5. <span data-ttu-id="21335-115">Der Transportdienst Ruft die [IMAPIProp::SaveChanges](imapiprop-savechanges.md) -Methode für die Instanz **IMessage** und gibt **StartMessage**zurück.</span><span class="sxs-lookup"><span data-stu-id="21335-115">The transport provider calls the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method on the **IMessage** instance and returns from **StartMessage**.</span></span>
    
6. <span data-ttu-id="21335-116">Die MAPI-Warteschlange [IXPLogon::TransportNotify](ixplogon-transportnotify.md) aufgerufen, wenn Nachrichtenübermittlung beendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="21335-116">The MAPI spooler calls [IXPLogon::TransportNotify](ixplogon-transportnotify.md) if it must stop message delivery.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="21335-117">Wenn ein Transportdienstes eine große Anzahl von Nachrichten übermitteln muss und der Adressbuchhierarchie **IMAPISupport::SpoolerNotify** anstelle von **IXPLogon::Poll**, sollte darauf geachtet werden nicht zum Aufrufen **SpoolerNotify** zu häufig dagegen in Reihenfolge Entzieht andere Transportanbieter der CPU-Zeit.</span><span class="sxs-lookup"><span data-stu-id="21335-117">If a transport provider must deliver a large number of messages and the transport provider is using **IMAPISupport::SpoolerNotify** instead of **IXPLogon::Poll**, care should be taken not to call **SpoolerNotify** too frequently in order not to deprive other transport providers of CPU time.</span></span> <span data-ttu-id="21335-118">Die MAPI-Warteschlange hat Logik für diesen Fehler zu vermeiden, aber im Allgemeinen sollten das Intervall zwischen Aufrufen **SpoolerNotify** länger als die benötigte Zeit Ihrer Adressbuchhierarchie eine Nachricht verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="21335-118">The MAPI spooler does have logic to prevent this from happening, but in general the interval between **SpoolerNotify** calls should be longer than the time it takes your transport provider to process one message.</span></span> <span data-ttu-id="21335-119">> Darüber hinaus kann die MAPI-Warteschlange eine eingehende Nachricht nicht sofort verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="21335-119">> Also, the MAPI spooler may not process an incoming message immediately.</span></span> <span data-ttu-id="21335-120">Die MAPI-Warteschlange beantragen der Adressbuchhierarchie für andere Aufgaben, bevor er die eingehende Nachricht empfängt.</span><span class="sxs-lookup"><span data-stu-id="21335-120">The MAPI spooler may ask the transport provider to perform other tasks before it receives the incoming message.</span></span> 
  
