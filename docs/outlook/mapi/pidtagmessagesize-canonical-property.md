---
title: Kanonische Pidtagmessagesize (-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagMessageSize
api_type:
- HeaderDef
ms.assetid: c67fb54b-8cc7-4fbc-8204-36fcddfa6192
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: 3a49c6d70cc47ff726a7a99860b5e81a400be0bf
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32355650"
---
# <a name="pidtagmessagesize-canonical-property"></a>Kanonische Pidtagmessagesize (-Eigenschaft

  
  
**Gilt für**: Outlook 2013 | Outlook 2016 
  
Enthält die Summe der Größen aller Eigenschaften eines Nachrichtenobjekts in Bytes. 
  
|||
|:-----|:-----|
|Zugeordnete Eigenschaften:  <br/> |PR_MESSAGE_SIZE  <br/> |
|Kennung:  <br/> |0x0E08  <br/> |
|Datentyp:  <br/> |PT_LONG  <br/> |
|Bereich:  <br/> |Allgemeine Nachrichtenübermittlung  <br/> |
   
## <a name="remarks"></a>Bemerkungen

Es wird empfohlen, dass Nachrichtenobjekte diese Eigenschaft verfügbar machen. Die Größe der Nachricht gibt die ungefähre Anzahl von Bytes an, die beim Verschieben der Nachricht von einem Nachrichtenspeicher zu einem anderen übertragen werden. Als Summe der Größen aller Eigenschaften des Message-Objekts ist es in der Regel erheblich größer als der Nachrichtentext allein. 
  
Die meisten Nachrichtenspeicher Anbieter berechnen diese Eigenschaft für Nachrichten, die Sie verarbeiten. Einige Nachrichtenspeicher Anbieter unterstützen diese Eigenschaft jedoch nicht. Diese Eigenschaft ist in jedem Fall erst verfügbar, wenn die [IMAPIProp:: SaveChanges](imapiprop-savechanges.md) -oder [IMessage:: SubmitMessage](imessage-submitmessage.md) -Methode aufgerufen wurde. 
  
## <a name="related-resources"></a>Zugehörige Ressourcen

### <a name="protocol-specifications"></a>Protokollspezifikationen

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Enthält Verweise auf zugehörige Exchange Server-Protokollspezifikationen.
    
[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> Verarbeitet Nachrichten-und Anlagenobjekte.
    
[[MS-OXCFOLD]](https://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)
  
> Behandelt Ordner Vorgänge.
    
[[MS-OXCSTOR]](https://msdn.microsoft.com/library/d42ed1e0-3e77-4264-bd59-7afc583510e2%28Office.15%29.aspx)
  
> Gibt zulässige Vorgänge für die wichtigsten Nachrichtenspeicher Objekte an.
    
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

