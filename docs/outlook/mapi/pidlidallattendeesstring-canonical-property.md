---
title: Kanonische pidlidallattendeesstring (-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAllAttendeesString
api_type:
- COM
ms.assetid: 2ffc0609-341d-4e35-8f53-ed3096c6fa7f
description: 'Letzte Änderung: Montag, 9. März 2015'
ms.openlocfilehash: 96ad0727797475effd0563e4753070cb3bac4b37
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32334776"
---
# <a name="pidlidallattendeesstring-canonical-property"></a>Kanonische pidlidallattendeesstring (-Eigenschaft

  
  
**Gilt für**: Outlook 2013 | Outlook 2016 
  
Gibt eine Liste aller Teilnehmer außer dem Organisator an, einschließlich Ressourcen und nicht sendender Teilnehmer.
  
|||
|:-----|:-----|
|Zugeordnete Eigenschaften:  <br/> |dispidAllAttendeesString  <br/> |
|Eigenschaftengruppe:  <br/> |PSETID_Appointment  <br/> |
|Lange ID (LID):  <br/> |0x00008238  <br/> |
|Datentyp:  <br/> |PT_UNICODE  <br/> |
|Bereich:  <br/> |Meetings  <br/> |
   
## <a name="remarks"></a>Hinweise

Der Wert für jeden Teilnehmer ist der Anzeigename des Teilnehmers. Getrennte Einträge müssen durch ein Semikolon, gefolgt von einem Leerzeichen, abgegrenzt werden. Diese Eigenschaft ist nicht erforderlich.
  
## <a name="related-resources"></a>Verwandte Ressourcen

### <a name="protocol-specifications"></a>Protokollspezifikationen

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Stellt Eigenschaftenmengen Definitionen und Verweise auf zugehörige Exchange Server Protokollspezifikationen bereit.
    
[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> Gibt die Eigenschaften und Vorgänge für Termin-, Besprechungsanfrage-und Antwortnachrichten an.
    
### <a name="header-files"></a>Header Dateien

Mapidefs. h
  
> Stellt Definitionen von Datentypen bereit.
    
## <a name="see-also"></a>Siehe auch



[MAPI-Eigenschaften](mapi-properties.md)
  
[Kanonische MAPI-Eigenschaften](mapi-canonical-properties.md)
  
[Zuordnen von kanonischen Eigenschaftennamen zu MAPI-Namen](mapping-canonical-property-names-to-mapi-names.md)
  
[Zuordnen von MAPI-Namen zu kanonischen Eigenschaftennamen](mapping-mapi-names-to-canonical-property-names.md)

