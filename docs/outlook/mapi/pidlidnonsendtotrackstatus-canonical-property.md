---
title: Kanonische Pidlidnonsendtotrackstatus (-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidNonSendToTrackStatus
api_type:
- COM
ms.assetid: 50fec332-e7df-4bc6-8c50-59b9ca545f89
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: bdfbd553e130a4e463017168a76dc94fc0df827b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331367"
---
# <a name="pidlidnonsendtotrackstatus-canonical-property"></a>Kanonische Pidlidnonsendtotrackstatus (-Eigenschaft

  
  
**Gilt für**: Outlook 2013 | Outlook 2016 
  
Enthält den Wert für jeden Teilnehmer, der in der **dispidNonSendableTo** ([pidlidnonsendableto (](pidlidnonsendableto-canonical-property.md))-Eigenschaft aufgeführt ist.
  
|||
|:-----|:-----|
|Zugeordnete Eigenschaften:  <br/> |dispidNonSendToTrackStatus  <br/> |
|Eigenschaftensatz:  <br/> |PSETID_Common  <br/> |
|Long-ID (Deckel):  <br/> |0x00008543  <br/> |
|Datentyp:  <br/> |PT_MV_LONG  <br/> |
|Bereich:  <br/> |Allgemeine Nachrichtenübermittlung  <br/> |
   
## <a name="remarks"></a>Bemerkungen

Diese Eigenschaft ist nur erforderlich, wenn die **dispidNonSendableTo** -Eigenschaft festgelegt ist. Die Anzahl der Werte in dieser Eigenschaft muss der Anzahl der Werte in **dispidNonSendableTo**entsprechen. Jeder PT_LONG-Wert in dieser Eigenschaft entspricht dem Teilnehmer in der **dispidNonSendableTo** -Eigenschaft am gleichen Index. 
  
## <a name="related-resources"></a>Zugehörige Ressourcen

### <a name="protocol-specifications"></a>Protokollspezifikationen

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Stellt die Eigenschaftensatz Definition und Verweise auf zugehörige Exchange Server-Protokollspezifikationen bereit.
    
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

