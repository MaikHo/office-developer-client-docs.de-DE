---
title: Kanonische Pidlidrecurrencetype (-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidRecurrenceType
api_type:
- COM
ms.assetid: 81ad2e8a-661f-4fc7-bee4-848db3285e31
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 7a0ea0dfe236341815fe94fb570908d7034fc83e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315911"
---
# <a name="pidlidrecurrencetype-canonical-property"></a>Kanonische Pidlidrecurrencetype (-Eigenschaft

  
  
**Gilt für**: Outlook 2013 | Outlook 2016 
  
Gibt den Serientyp der wiederkehrenden Serie an.
  
|||
|:-----|:-----|
|Zugeordnete Eigenschaften:  <br/> |dispidRecurType  <br/> |
|Eigenschaftensatz:  <br/> |PSETID_Appointment  <br/> |
|Long-ID (Deckel):  <br/> |0x00008231  <br/> |
|Datentyp:  <br/> |PT_LONG  <br/> |
|Bereich:  <br/> |Kalender  <br/> |
   
## <a name="remarks"></a>Bemerkungen

Diese Eigenschaft gibt den Serientyp der wiederkehrenden Serie mithilfe eines der unten aufgeführten Werte an.
  
|**Status**|**Wert**|**Beschreibung**|
|:-----|:-----|:-----|
|rectypeNone  <br/> |0  <br/> |Ein Termin für eine Instanz.  <br/> |
|rectypeDaily  <br/> |1  <br/> |Ein tägliches Serienmuster.  <br/> |
|rectypeWeekly  <br/> |2  <br/> |Ein wöchentliches Serienmuster.  <br/> |
|rectypeMonthly  <br/> |3  <br/> |Ein monatliches Serienmuster.  <br/> |
|rectypeYearly  <br/> |4  <br/> |Ein jährliches Serienmuster.  <br/> |
   
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

