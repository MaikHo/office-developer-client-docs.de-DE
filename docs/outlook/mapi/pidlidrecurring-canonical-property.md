---
title: Kanonische Pidlidrecurring (-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidRecurring
api_type:
- COM
ms.assetid: 3d39a053-277f-4d59-ab2e-cee81710f2ab
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 85e78695a7c4fca5a1e5cd28b0254d4559be0c13
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315918"
---
# <a name="pidlidrecurring-canonical-property"></a>Kanonische Pidlidrecurring (-Eigenschaft

  
  
**Gilt für**: Outlook 2013 | Outlook 2016 
  
Gibt an, ob eine Termin Nachricht recurrent ist.
  
|||
|:-----|:-----|
|Zugeordnete Eigenschaften:  <br/> |dispidRecurring  <br/> |
|Eigenschaftensatz:  <br/> |PSETID_Appointment  <br/> |
|Long-ID (Deckel):  <br/> |0x00008223  <br/> |
|Datentyp:  <br/> |PT_BOOLEAN  <br/> |
|Bereich:  <br/> |Kalender  <br/> |
   
## <a name="remarks"></a>Bemerkungen

Diese Eigenschaft ist TRUE, wenn der Termin eine Terminserie ist und FALSE, wenn es nicht wiederholt wird.
  
Diese Eigenschaft gibt an, ob das Objekt eine wiederkehrende Datenreihe darstellt. Der Wert TRUE gibt an, dass das Objekt eine wiederkehrende Datenreihe darstellt. Der Wert FALSE oder das Fehlen dieser Eigenschaft gibt an, dass das Objekt entweder eine einzelne Instanz oder eine Ausnahme (einschließlich einer verwaisten Instanz) darstellt. Beachten Sie den Unterschied zwischen dieser Eigenschaft und der **LID_IS_RECURRING** ([pidlidisrecurring (](pidlidisrecurring-canonical-property.md))-Eigenschaft.
  
## <a name="related-resources"></a>Zugehörige Ressourcen

### <a name="protocol-specifications"></a>Protokollspezifikationen

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Stellt Eigenschaftensatz Definitionen und Verweise auf zugehörige Exchange Server-Protokollspezifikationen bereit.
    
[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> Gibt die Eigenschaften und Vorgänge für Termin-, Besprechungs-und Antwortnachrichten an.
    
### <a name="header-files"></a>Header Dateien

Mapidefs. h
  
> Stellt Datentypdefinitionen bereit.
    
## <a name="see-also"></a>Siehe auch



[MAPI-Eigenschaften](mapi-properties.md)
  
[Kanonische MAPI-Eigenschaften](mapi-canonical-properties.md)
  
[Zuordnen von kanonischen Eigenschaftennamen zu MAPI-Namen](mapping-canonical-property-names-to-mapi-names.md)
  
[Zuordnen von MAPI-Namen zu kanonischen Eigenschaftennamen](mapping-mapi-names-to-canonical-property-names.md)

