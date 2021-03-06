---
title: CURRENCY
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- CURRENCY
api_type:
- COM
ms.assetid: cffc05a0-95e4-4b9f-bf8f-c4272a75afa8
description: 'Letzte Änderung: Montag, 9. März 2015'
ms.openlocfilehash: dccb6b19af72d0f748a3a513b7f3d78904ebc789
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431120"
---
# <a name="currency"></a>CURRENCY

  
  
**Gilt für**: Outlook 2013 | Outlook 2016 
  
Enthält eine signierte 64-Bit-Ganzzahl, die einen Währungswert darstellt. 
  
|||
|:-----|:-----|
|Headerdatei  <br/> |Mapidefs. h  <br/> |
   
```cpp
typedef struct tagCY
{
  unsigned long Lo;
  long Hi;
} CURRENCY;

```

## <a name="members"></a>Members

 **Lo**
  
> Low-Order 32 Bits des Currency-Werts. 
    
 **Hallo**
  
> High-Order 32 Bits des Currency-Werts.
    
## <a name="remarks"></a>Bemerkungen

Die **Währungs** Struktur ist eine skalierte ganzzahlige Darstellung einer Dezimalzahl mit vier Ziffern rechts vom Dezimaltrennzeichen. Beispielsweise ist ein gespeicherter Wert von 327500 so auszulegen, dass er einen Währungswert von 32,7500 darstellt. 
  
Die **Currency** -Struktur dient zur Beschreibung einer Eigenschaft vom Typ PT_CURRENCY. Weitere Informationen zu Eigenschaftstypen finden Sie unter [MAPI property Type Overview](mapi-property-type-overview.md).
  
## <a name="see-also"></a>Siehe auch



[SPropValue](spropvalue.md)


[MAPI-Strukturen](mapi-structures.md)

