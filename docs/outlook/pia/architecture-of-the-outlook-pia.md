---
title: Architektur der Outlook PIA
TOCTitle: Architecture of the Outlook PIA
ms:assetid: 89577d14-e6e2-4270-8e72-b0adba378667
ms:mtpsurl: https://msdn.microsoft.com/library/office/bb646255(v=office.15)
ms:contentKeyID: 55119777
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 759e01b7ea032f53e3afeeaccaff687afc3735b3
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25406148"
---
# <a name="architecture-of-the-outlook-pia"></a><span data-ttu-id="655e3-102">Architektur der Outlook-PIA</span><span class="sxs-lookup"><span data-stu-id="655e3-102">Architecture of the Outlook PIA</span></span>

<span data-ttu-id="655e3-103">Die primäre Interopassembly (PIA) von Outlook unterstützt uneingeschränkt die Entwicklung für das Outlook-Objektmodell in verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="655e3-103">The Microsoft Outlook 2010 Primary Interop Assembly (PIA) fully supports developing against the Outlook object model in managed code.</span></span> <span data-ttu-id="655e3-104">Wenn Sie die PIA jedoch erstmalig in einem Objektkatalog anzeigen, sind Sie möglicherweise überrascht von den vielen enthaltenen zusätzlichen Schnittstellen und davon, dass nicht alle Methoden-, Eigenschaften- und Ereignismember eines Objekts durch dieselbe Objektschnittstelle verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="655e3-104">However, when you look at the PIA in an object browser for the first time, you may be surprised by the many extra interfaces that the PIA contains, and the fact that not all method, property, and event members of an object are exposed by the same object interface.</span></span> <span data-ttu-id="655e3-105">Die Themen in diesem Abschnitt enthalten Richtlinien für den Zugriff auf Objektmember in Code und für die Suche nach Hilfe zu Objekten, Methoden, Eigenschaften und Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="655e3-105">The topics in this section describe guidelines for how to access object members in code, and where to look for help for objects, methods, properties, and events.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="655e3-106">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="655e3-106">In this section</span></span>

|<span data-ttu-id="655e3-107">Thema</span><span class="sxs-lookup"><span data-stu-id="655e3-107">Topic</span></span>|<span data-ttu-id="655e3-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="655e3-108">Description</span></span>|
|:----|:----------|
|[<span data-ttu-id="655e3-109">Zuordnen der Outlook-PIA zum Objektmodell</span><span class="sxs-lookup"><span data-stu-id="655e3-109">Relating the Outlook PIA with the Object Model</span></span>](relating-the-outlook-pia-with-the-object-model.md) |<span data-ttu-id="655e3-110">Beschreibt, wie Objekte und Member im COM-basierten Outlook-Objektmodell entsprechenden verwalteten Schnittstellen und Klassen in der PIA zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="655e3-110">Describes how objects and members in the COM-based Outlook object model are mapped to corresponding managed interfaces and classes in the PIA.</span></span>|
|[<span data-ttu-id="655e3-111">Objekte in der Outlook-PIA</span><span class="sxs-lookup"><span data-stu-id="655e3-111">Objects in the Outlook PIA</span></span>](objects-in-the-outlook-pia.md) |<span data-ttu-id="655e3-112">Beschreibt die typischen einem COM-Objekt zugeordneten .NET-Schnittstellen, Klassen und Delegate sowie den Zugriff auf ein Objekt in der PIA.</span><span class="sxs-lookup"><span data-stu-id="655e3-112">Describes the typical .NET interfaces, classes, and delegates that are mapped to a COM object, and describes how to access an object in the PIA.</span></span>|
|[<span data-ttu-id="655e3-113">Methoden und Eigenschaften in der Outlook-PIA</span><span class="sxs-lookup"><span data-stu-id="655e3-113">Methods and Properties in the Outlook PIA</span></span>](methods-and-properties-in-the-outlook-pia.md) |<span data-ttu-id="655e3-114">Beschreibt, wie mithilfe der PIA auf Methoden und Eigenschaften eines Objekts in verwaltetem Code zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="655e3-114">Describes how to access methods and properties of an object in managed code by using the PIA.</span></span>|
|[<span data-ttu-id="655e3-115">Ereignisse in der Outlook-PIA</span><span class="sxs-lookup"><span data-stu-id="655e3-115">Events in the Outlook PIA</span></span>](events-in-the-outlook-pia.md) |<span data-ttu-id="655e3-116">Beschreibt ereignisabhängige Schnittstellen, Stellvertretungen und Senkenhilfsklassen in der PIA.</span><span class="sxs-lookup"><span data-stu-id="655e3-116">Describes event-related interfaces, delegates, and sink helper classes in the PIA.</span></span>|

## <a name="see-also"></a><span data-ttu-id="655e3-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="655e3-117">See also</span></span>

- [<span data-ttu-id="655e3-118">Einrichten der Outlook-PIA</span><span class="sxs-lookup"><span data-stu-id="655e3-118">Setting Up to Use the Outlook PIA</span></span>](setting-up-to-use-the-outlook-pia.md)
- [<span data-ttu-id="655e3-119">Entwickeln von verwalteten Outlook-Add-Ins mithilfe der Outlook-PIA</span><span class="sxs-lookup"><span data-stu-id="655e3-119">Developing Managed Outlook Add-ins Using the Outlook PIA</span></span>](developing-managed-outlook-add-ins-using-the-outlook-pia.md)
- [<span data-ttu-id="655e3-120">Gewusst wie... (Outlook 2013 PIA-Referenz)</span><span class="sxs-lookup"><span data-stu-id="655e3-120">How Do I... (Outlook 2013 PIA Reference)</span></span>](how-do-i-outlook-2013-pia-reference.md)
