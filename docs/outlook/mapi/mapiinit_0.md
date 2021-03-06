---
title: MAPIINIT_0
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.MAPIINIT_0
api_type:
- COM
ms.assetid: 70739711-ff43-407d-bc8b-6baf7a476fef
description: 'Letzte Änderung: Montag, 9. März 2015'
ms.openlocfilehash: de31fe7d472b143ed8f3c108dca84a019b5ce103
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357295"
---
# <a name="mapiinit0"></a>MAPIINIT_0

  
  
**Gilt für**: Outlook 2013 | Outlook 2016 
  
Vermittelt Optionen an die [MAPIInitialize](mapiinitialize.md) -Funktion. 
  
|||
|:-----|:-----|
|Headerdatei  <br/> |MAPIX. H  <br/> |
   
```cpp
typedef struct
{
  ULONG ulVersion;
  ULONG ulFlags;
} MAPIINIT_0, FAR *LPMAPIINIT_0;

```

## <a name="members"></a>Elemente

 **ulVersion**
  
> Ein ganzzahliger Wert, der die Versionsnummer der **MAPIINIT_0** -Struktur darstellt. Das **ulVersion** -Element ist für die zukünftige Erweiterung und stellt nicht die Version der MAPI-Schnittstelle dar. Derzeit muss **ulVersion** auf MAPI_INIT_VERSION festgelegt werden. 
    
 **ulFlags**
  
> Die Bitmaske der Flags, die zum Steuern der Initialisierung der MAPI-Sitzung verwendet werden. Die folgenden Flags können festgelegt werden:
    
MAPI_MULTITHREAD_NOTIFICATIONS 
  
> MAPI sollte Benachrichtigungen mithilfe eines Threads generieren, der für die Benachrichtigungs Behandlung verwendet wird, statt für den ersten Thread, der zum Aufrufen von **MAPIInitialize**verwendet wird.
    
MAPI_NT_SERVICE 
  
> Der Anrufer wird als Windows-Dienst betrieben. Anrufer, die nicht als Windows-Dienst gestartet werden, sollten dieses Flag nicht festlegen; Anrufer, die als Dienst gestartet werden, müssen dieses Flag festlegen.
    
MAPI_NO_COINIT
  
> Legen Sie das MAPI_NO_COINT-Flag so fest, dass **MAPIInitialize** nicht versucht, com mit einem [](https://msdn.microsoft.com/library/0f171cf4-87b9-43a6-97f2-80ed344fe376%28Office.15%29.aspx)Aufruf von "Initialize" zu initialisieren. Wenn eine **MAPIINIT_0** -Struktur an **MAPIInitialize** übergeben wird, wobei _ulFlags_ auf MAPI_NO_COINIT festgelegt ist, wird von MAPI angenommen, dass com bereits initialisiert wurde, und der Aufruf von **Initialize**wird umgangen.
    
## <a name="remarks"></a>Hinweise

Multithread-Clients sollten das MAPI_MULTITHREAD_NOTIFICATIONS-Flag festlegen. Wenn das Flag nicht festgelegt ist, werden Benachrichtigungen für den Thread generiert, der für den ersten Aufruf von **MAPIInitialize**verwendet wird. 
  
Weitere Informationen zum Zeitpunkt der Festlegung dieses Flags und zur Implementierung der Threadsicherheit in einem Client finden Sie unter [Threading in MAPI](threading-in-mapi.md). 
  
## <a name="see-also"></a>Siehe auch



[MAPIInitialize](mapiinitialize.md)


[MAPI-Strukturen](mapi-structures.md)

