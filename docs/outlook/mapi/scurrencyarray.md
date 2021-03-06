---
title: SCurrencyArray
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SCurrencyArray
api_type:
- COM
ms.assetid: d28852ab-b542-40e1-b2ec-85d20a2eddfd
description: 'Letzte Änderung: Montag, 9. März 2015'
ms.openlocfilehash: e9468d0c7fc7e46475afe19f12f225e53196639e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439401"
---
# <a name="scurrencyarray"></a>SCurrencyArray

  
  
**Gilt für**: Outlook 2013 | Outlook 2016 
  
Enthält ein Array von Currency-Werten, die zum Beschreiben einer Eigenschaft vom Typ PT_MV_CURRENCY verwendet werden. 
  
|||
|:-----|:-----|
|Headerdatei  <br/> |Mapidefs. h  <br/> |
   
```cpp
typedef struct _SCurrencyArray
{
  ULONG         cValues;
  CURRENCY FAR *lpcur;
} SCurrencyArray;

```

## <a name="members"></a>Members

 **cValues**
  
> Die Anzahl der Werte im Array, auf die durch das **lpcur** -Element verwiesen wird. 
    
 **lpcur**
  
> Zeiger auf ein Array von [Währungs](currency.md) Strukturen, die die Währungswerte enthalten. 
    
## <a name="remarks"></a>Bemerkungen

Weitere Informationen zu PT_MV_CURRENCY finden Sie unter [Liste der Eigenschaftentypen](property-types.md). 
  
## <a name="see-also"></a>Siehe auch



[CURRENCY](currency.md)
  
[SPropValue](spropvalue.md)


[MAPI-Strukturen](mapi-structures.md)

