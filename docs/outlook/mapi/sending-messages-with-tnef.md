---
title: Senden von Nachrichten mit TNEF
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 6e2df265-b9dd-4e19-8ca5-3e31804e9120
description: 'Letzte �nderung: Samstag, 23. Juli 2011'
ms.openlocfilehash: fb26d854b47894d8f37763b17e5ba0b26fd25ff6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19795506"
---
# <a name="sending-messages-with-tnef"></a><span data-ttu-id="fc35f-103">Senden von Nachrichten mit TNEF</span><span class="sxs-lookup"><span data-stu-id="fc35f-103">Sending Messages with TNEF</span></span>

  
  
<span data-ttu-id="fc35f-104">**Betrifft**: Outlook</span><span class="sxs-lookup"><span data-stu-id="fc35f-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="fc35f-105">Viele Transportanbieter senden automatisch alle ausgehende Nachrichten mit Transport Neutral Encapsulation Format (TNEF).</span><span class="sxs-lookup"><span data-stu-id="fc35f-105">Many transport providers automatically send all outgoing messages with the Transport Neutral Encapsulation Format (TNEF).</span></span> <span data-ttu-id="fc35f-106">TNEF wird verwendet, um der formatierte Text zu übertragen, den viele Clients und Message-Anbieter in ihre Nachrichten, die Anlagen verschiedene Arten von benutzerdefinierten Eigenschaften für benutzerdefinierte Nachrichtenklassen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="fc35f-106">TNEF is used to transmit the formatted text that many clients and message store providers support in their messages, attachments of various types, and custom properties for custom message classes.</span></span> <span data-ttu-id="fc35f-107">Zwar der Standardmodus für die meisten Transportanbieter zum Senden von ausgehender Nachrichten mit TNEF, Sie einige Transportanbieter nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fc35f-107">Although the default mode for most transport providers is to send outgoing messages with TNEF, some transport providers do not support it.</span></span> <span data-ttu-id="fc35f-108">Die fehlende Unterstützung für TNEF ist kein Problem für standard messaging-Clients, die IPM Nachrichten senden und empfangen.</span><span class="sxs-lookup"><span data-stu-id="fc35f-108">The lack of support for TNEF is not an issue for standard messaging clients that send and receive IPM messages.</span></span> <span data-ttu-id="fc35f-109">Jedoch ist die Verwendung von TNEF für formularbasierte oder Clients, die benutzerdefinierte Eigenschaften erfordern, entscheidend.</span><span class="sxs-lookup"><span data-stu-id="fc35f-109">However, for form-based clients or clients that require custom properties, the use of TNEF is essential.</span></span> <span data-ttu-id="fc35f-110">Designer von Clients, die auf Formularen oder benutzerdefinierte Eigenschaften basieren müssen die Funktionen der Transportanbieter beachten, die sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="fc35f-110">Designers of clients that rely on forms or custom properties must be aware of the capabilities of the transport providers that they use.</span></span>
  
<span data-ttu-id="fc35f-111">Empfänger der Nachricht können steuern, ob ein Transportdienstes Nachrichten mit TNEF durch Festlegen der Eigenschaft **PR_SEND_RICH_INFO** überträgt.</span><span class="sxs-lookup"><span data-stu-id="fc35f-111">Message recipients can control whether or not a transport provider transmits messages with TNEF by setting the **PR_SEND_RICH_INFO** property.</span></span> <span data-ttu-id="fc35f-112">Weitere Informationen finden Sie unter **PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)).</span><span class="sxs-lookup"><span data-stu-id="fc35f-112">For more information, see **PR_SEND_RICH_INFO** ([PidTagSendRichInfo](pidtagsendrichinfo-canonical-property.md)).</span></span> <span data-ttu-id="fc35f-113">Wenn eines Empfängers **PR_SEND_RICH_INFO** -Eigenschaft auf TRUE festgelegt ist, überträgt ein Transportdienstes, das TNEF unterstützt es mit der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="fc35f-113">When a recipient's **PR_SEND_RICH_INFO** property is set to TRUE, a transport provider that supports TNEF transmits it with the message.</span></span> <span data-ttu-id="fc35f-114">Wenn die Eigenschaft auf FALSE festgelegt ist, wird die Formatierung verworfen.</span><span class="sxs-lookup"><span data-stu-id="fc35f-114">When the property is set to FALSE, the formatting is discarded.</span></span> <span data-ttu-id="fc35f-115">Wenn **PR_SEND_RICH_INFO** nicht vorhanden ist, ist es bis zu der Adressbuchhierarchie eine standardmäßige Vorgehensweise auswählen.</span><span class="sxs-lookup"><span data-stu-id="fc35f-115">When **PR_SEND_RICH_INFO** does not exist, it is up to the transport provider to choose a default course of action.</span></span> 
  
<span data-ttu-id="fc35f-116">Wenn Clients und Dienstanbieter einen benutzerdefinierten Empfänger erstellen, können diese den Wert der Eigenschaft **PR_SEND_RICH_INFO** beeinflussen, indem Sie die Kennzeichen MAPI_SEND_NO_RICH_INFO zur **IAddrBook::CreateOneOff** oder **im _UlFlags_ -Parameter übergeben IMAPISupport::CreateOneOff** aufrufen.</span><span class="sxs-lookup"><span data-stu-id="fc35f-116">When clients and service providers create a custom recipient, they can affect the value of its **PR_SEND_RICH_INFO** property by passing the MAPI_SEND_NO_RICH_INFO flag in the  _ulFlags_ parameter to the **IAddrBook::CreateOneOff** or **IMAPISupport::CreateOneOff** call.</span></span> <span data-ttu-id="fc35f-117">Weitere Informationen finden Sie unter [IAddrBook::CreateOneOff](iaddrbook-createoneoff.md) und [IMAPISupport::CreateOneOff](imapisupport-createoneoff.md).</span><span class="sxs-lookup"><span data-stu-id="fc35f-117">For more information, see [IAddrBook::CreateOneOff](iaddrbook-createoneoff.md) and [IMAPISupport::CreateOneOff](imapisupport-createoneoff.md).</span></span> <span data-ttu-id="fc35f-118">Übergeben von MAPI_SEND_NO_RICH_INFO bewirkt, dass MAPI, um den benutzerdefinierten Empfänger **PR_SEND_RICH_INFO** -Eigenschaft auf FALSE festgelegt. in den meisten Fällen wird durch das übergeben nicht das Flag MAPI, um die Eigenschaft auf TRUE festgelegt.</span><span class="sxs-lookup"><span data-stu-id="fc35f-118">Passing MAPI_SEND_NO_RICH_INFO causes MAPI to set the custom recipient's **PR_SEND_RICH_INFO** property to FALSE; in most cases not passing the flag causes MAPI to set the property to TRUE.</span></span> <span data-ttu-id="fc35f-119">Die einzige Ausnahme ist, wenn der benutzerdefinierten Empfängeradresse interpretiert wird, eine IP-Adresse sein.</span><span class="sxs-lookup"><span data-stu-id="fc35f-119">The one exception is if the custom recipient's address is interpreted to be an Internet address.</span></span> <span data-ttu-id="fc35f-120">In diesem Fall eine wird MAPI **PR_SEND_RICH_INFO** auf false festgelegt.</span><span class="sxs-lookup"><span data-stu-id="fc35f-120">In this one situation, MAPI sets **PR_SEND_RICH_INFO** to FALSE.</span></span> 
  
