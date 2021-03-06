---
title: Kanonische Pidtagrecipienttrackstatus (-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagRecipientTrackStatus
api_type:
- COM
ms.assetid: d619b5e7-2867-44fc-9b42-123bb1bf7bde
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 074bcf7c051b78bc32caf66502747e7fb1ab6b79
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355286"
---
# <a name="pidtagrecipienttrackstatus-canonical-property"></a>Kanonische Pidtagrecipienttrackstatus (-Eigenschaft

  
  
**Gilt für**: Outlook 2013 | Outlook 2016 
  
Gibt den vom Teilnehmer zurückgegebenen Antwortstatus an.
  
|||
|:-----|:-----|
|Zugeordnete Eigenschaften:  <br/> |PR_RECIPIENT_TRACKSTATUS  <br/> |
|Kennung:  <br/> |0x5FFF  <br/> |
|Datentyp:  <br/> |PT_LONG  <br/> |
|Bereich:  <br/> |Transport Empfänger  <br/> |
   
## <a name="remarks"></a>Bemerkungen

Wenn dieser Wert nicht festgelegt ist, muss davon ausgegangen werden, dass respNone. Andernfalls muss es eine der folgenden sein:
  
|**Antwortstatus**|**Wert**|**Beschreibung**|
|:-----|:-----|:-----|
|respNone  <br/> |0x00000000  <br/> |Für dieses Objekt ist keine Antwort erforderlich. Dies gilt für Terminobjekte und Besprechungsantwort Objekte.  <br/> |
|respTentative  <br/> |0x00000002  <br/> |Dieser Wert im Meeting-Objekt des Teilnehmers gibt an, dass der Teilnehmer das Besprechungsanfrage Objekt vorläufig akzeptiert hat.  <br/> |
|respAccepted  <br/> |0x00000003  <br/> |Dieser Wert im Meeting-Objekt des Teilnehmers gibt an, dass der Teilnehmer das Besprechungsanfrage Objekt akzeptiert hat.  <br/> |
|respDeclined  <br/> |0x00000004  <br/> |Dieser Wert im Meeting-Objekt des Teilnehmers gibt an, dass der Teilnehmer das Besprechungsanfrage Objekt abgelehnt hat.  <br/> |
   
## <a name="related-resources"></a>Zugehörige Ressourcen

### <a name="protocol-specifications"></a>Protokollspezifikationen

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Enthält Verweise auf zugehörige Exchange Server-Protokollspezifikationen.
    
[[MS-OXOCAL]](https://msdn.microsoft.com/library/09861fde-c8e4-4028-9346-e7c214cfdba1%28Office.15%29.aspx)
  
> Gibt die Eigenschaften und Vorgänge für Termin-, Besprechungs-und Antwortnachrichten an.
    
[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> Verarbeitet Nachrichten-und Anlagenobjekte.
    
### <a name="header-files"></a>Header Dateien

Mapidefs. h
  
> Stellt Datentypdefinitionen bereit.
    
Mapitags. h
  
> Enthält Definitionen von Eigenschaften, die als Alternative Namen aufgeführt sind.
    
## <a name="see-also"></a>Siehe auch



[MAPI-Eigenschaften](mapi-properties.md)
  
[Kanonische MAPI-Eigenschaften](mapi-canonical-properties.md)
  
[Zuordnen von kanonischen Eigenschaftennamen zu MAPI-Namen](mapping-canonical-property-names-to-mapi-names.md)
  
[Zuordnen von MAPI-Namen zu kanonischen Eigenschaftennamen](mapping-mapi-names-to-canonical-property-names.md)

