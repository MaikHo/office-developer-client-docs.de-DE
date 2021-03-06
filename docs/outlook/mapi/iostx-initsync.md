---
title: IOSTXInitSync
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IOSTX.InitSync
api_type:
- COM
ms.assetid: e22244a2-ac5f-910a-501f-4483ea0667c2
description: 'Letzte Änderung: Samstag, 23. Juli 2011'
ms.openlocfilehash: b9086383b45d40d5839284ac785d72438be60e00
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413353"
---
# <a name="iostxinitsync"></a>IOSTX::InitSync

  
  
**Gilt für**: Outlook 2013 | Outlook 2016 
  
Informiert den lokalen Nachrichtenspeicher über die Synchronisierung, die gestartet werden soll.
  
```cpp
HRESULT InitSync( 
    ULONG ulFlags 
);
```

## <a name="parameters"></a>Parameter

 _ulFlags_
  
> in Flags zum Bestimmen des geeigneten Verhaltens während der Synchronisierung. Outlook verwendet diese Flags in jedem Status des Replikationsstatus Computers, um die Informationen zu ermitteln, die für den Client bereitgestellt werden sollen. Wenn der Client beispielsweise **SYNC_ONLY_ASSOCIATED**übergibt, gibt Outlook nur Informationen zurück, die sich auf zugeordnete (oder ausgeblendete) Elemente beziehen. 
    
## <a name="see-also"></a>Siehe auch



[IOSTX::GetLastError](iostx-getlasterror.md)
  
[IOSTX::SetSyncResult](iostx-setsyncresult.md)
  
[IOSTX::SyncBeg](iostx-syncbeg.md)
  
[IOSTX::SyncEnd](iostx-syncend.md)
  
[IOSTX::SyncHdrBeg](iostx-synchdrbeg.md)
  
[IOSTX::SyncHdrEnd](iostx-synchdrend.md)
  
[IOSTX : IUnknown](iostxiunknown.md)


[MAPI-Konstanten](mapi-constants.md)

