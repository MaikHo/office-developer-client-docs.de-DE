---
title: SDoubleArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SDoubleArray
api_type:
- COM
ms.assetid: b63b26de-faf9-453c-ab8b-fb703ed09ae8
description: 'Letzte Änderung: Montag, 9. März 2015'
ms.openlocfilehash: 91440d619c8ad8a64b2bac7463a26d9c196a3c0f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439268"
---
# <a name="sdoublearray"></a>SDoubleArray

  
  
**Gilt für**: Outlook 2013 | Outlook 2016 
  
Enthält ein Array von Doubles, die zum Beschreiben einer Eigenschaft vom Typ PT_MV_DOUBLE verwendet werden.
  
|||
|:-----|:-----|
|Headerdatei  <br/> |Mapidefs. h  <br/> |
   
```cpp
typedef struct _SDoubleArray
{
  ULONG cValues;
  double FAR *lpdbl;
} SDoubleArray;

```

## <a name="members"></a>Members

 **cValues**
  
> Die Anzahl der Werte im Array, auf die durch das **lpdbl** -Element verwiesen wird. 
    
 **lpdbl**
  
> Zeiger auf ein Array von Double-Werten.
    
## <a name="remarks"></a>Bemerkungen

Weitere Informationen zu PT_MV_DOUBLE finden Sie unter [Liste der Eigenschaftstypen](property-types.md).
  
## <a name="see-also"></a>Siehe auch



[SPropValue](spropvalue.md)


[MAPI-Strukturen](mapi-structures.md)

