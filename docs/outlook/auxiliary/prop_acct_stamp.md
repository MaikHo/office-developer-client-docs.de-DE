---
title: PROP_ACCT_STAMP
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 70b6ecc8-6be3-0f05-3291-ac5b7f2ecfdb
description: Gibt den Stempel Konto zurück.
ms.openlocfilehash: ec1824d8c8c61d392b4e11cdb5213a85100d971e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/15/2018
ms.locfileid: "19791199"
---
# <a name="propacctstamp"></a><span data-ttu-id="432e2-103">PROP_ACCT_STAMP</span><span class="sxs-lookup"><span data-stu-id="432e2-103">PROP_ACCT_STAMP</span></span>

<span data-ttu-id="432e2-104">Gibt den Stempel Konto zurück.</span><span class="sxs-lookup"><span data-stu-id="432e2-104">Returns the account stamp.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="432e2-105">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="432e2-105">Quick info</span></span>

<span data-ttu-id="432e2-106">Finden Sie unter [IOlkAccount](iolkaccount.md).</span><span class="sxs-lookup"><span data-stu-id="432e2-106">See [IOlkAccount](iolkaccount.md).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="432e2-107">Bezeichner:</span><span class="sxs-lookup"><span data-stu-id="432e2-107">Identifier:</span></span>  <br/> |<span data-ttu-id="432e2-108">0x000d</span><span class="sxs-lookup"><span data-stu-id="432e2-108">0x000D</span></span>  <br/> |
|<span data-ttu-id="432e2-109">Der Eigenschaftentyp:</span><span class="sxs-lookup"><span data-stu-id="432e2-109">Property type:</span></span>  <br/> |<span data-ttu-id="432e2-110">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="432e2-110">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="432e2-111">Eigenschafts-Tag:</span><span class="sxs-lookup"><span data-stu-id="432e2-111">Property tag:</span></span>  <br/> |<span data-ttu-id="432e2-112">0x000D001F</span><span class="sxs-lookup"><span data-stu-id="432e2-112">0x000D001F</span></span>  <br/> |
|<span data-ttu-id="432e2-113">Access:</span><span class="sxs-lookup"><span data-stu-id="432e2-113">Access:</span></span>  <br/> |<span data-ttu-id="432e2-114">Schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="432e2-114">Read-only</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="432e2-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="432e2-115">Remarks</span></span>

<span data-ttu-id="432e2-116">Rufen Sie diese Eigenschaft mithilfe von [IOlkAccount::GetProp](iolkaccount-getprop.md).</span><span class="sxs-lookup"><span data-stu-id="432e2-116">Get this property by using [IOlkAccount::GetProp](iolkaccount-getprop.md).</span></span> <span data-ttu-id="432e2-117">Wenn der Client versucht, diese Eigenschaft nicht festlegen, gibt diese Eigenschaft **E_OLK_PROP_READ_ONLY**.</span><span class="sxs-lookup"><span data-stu-id="432e2-117">If the client attempts to set this property, this property returns **E_OLK_PROP_READ_ONLY**.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="432e2-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="432e2-118">See also</span></span>

- [<span data-ttu-id="432e2-119">Über die Konto-API</span><span class="sxs-lookup"><span data-stu-id="432e2-119">About the Account Management API</span></span>](about-the-account-management-api.md)  
- [<span data-ttu-id="432e2-120">Konstanten (Account Management API)</span><span class="sxs-lookup"><span data-stu-id="432e2-120">Constants (Account management API)</span></span>](constants-account-management-api.md)
