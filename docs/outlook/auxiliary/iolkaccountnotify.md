---
title: IOlkAccountNotify
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 360854bb-e9be-a784-e80b-3f18418ded1b
ms.openlocfilehash: f4b57ad1062df9aa1809e8eb422a2c983adcac4a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19791111"
---
# <a name="iolkaccountnotify"></a><span data-ttu-id="c150d-102">IOlkAccountNotify</span><span class="sxs-lookup"><span data-stu-id="c150d-102">IOlkAccountNotify</span></span>

<span data-ttu-id="c150d-103">Stellt einen Rückruf an dem Client für Änderungen an einem Konto an.</span><span class="sxs-lookup"><span data-stu-id="c150d-103">Provides a callback to the client for changes to an account.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="c150d-104">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="c150d-104">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c150d-105">Erbt:</span><span class="sxs-lookup"><span data-stu-id="c150d-105">Inherits from:</span></span>  <br/> |[<span data-ttu-id="c150d-106">IOlkErrorUnknown</span><span class="sxs-lookup"><span data-stu-id="c150d-106">IOlkErrorUnknown</span></span>](iolkerrorunknown.md) <br/> |
|<span data-ttu-id="c150d-107">Bereitgestellt von:</span><span class="sxs-lookup"><span data-stu-id="c150d-107">Provided by:</span></span>  <br/> | <span data-ttu-id="c150d-108">Client</span><span class="sxs-lookup"><span data-stu-id="c150d-108">Client</span></span>  <br/> |
|<span data-ttu-id="c150d-109">Schnittstellenbezeichner:</span><span class="sxs-lookup"><span data-stu-id="c150d-109">Interface identifier:</span></span>  <br/> |<span data-ttu-id="c150d-110">IID_IOlkAccountNotify</span><span class="sxs-lookup"><span data-stu-id="c150d-110">IID_IOlkAccountNotify</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="c150d-111">Vtable-Reihenfolge</span><span class="sxs-lookup"><span data-stu-id="c150d-111">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="c150d-112">Benachrichtigen</span><span class="sxs-lookup"><span data-stu-id="c150d-112">Notify</span></span>](iolkaccountnotify-notify.md) <br/> |<span data-ttu-id="c150d-113">Benachrichtigt den Client von Änderungen an das angegebene Konto.</span><span class="sxs-lookup"><span data-stu-id="c150d-113">Notifies the client of changes to the specified account.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c150d-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c150d-114">Remarks</span></span>

<span data-ttu-id="c150d-115">Diese Schnittstelle wird an [IOlkAccountManager::Advise](iolkaccountmanager-advise.md) übergeben, beim Einrichten von Benachrichtigungen.</span><span class="sxs-lookup"><span data-stu-id="c150d-115">This interface is passed to [IOlkAccountManager::Advise](iolkaccountmanager-advise.md) when setting up notifications.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="c150d-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c150d-116">See also</span></span>

- [<span data-ttu-id="c150d-117">Über die Konto-API</span><span class="sxs-lookup"><span data-stu-id="c150d-117">About the Account Management API</span></span>](about-the-account-management-api.md) 
- [<span data-ttu-id="c150d-118">Konstanten (Account Management API)</span><span class="sxs-lookup"><span data-stu-id="c150d-118">Constants (Account management API)</span></span>](constants-account-management-api.md)
