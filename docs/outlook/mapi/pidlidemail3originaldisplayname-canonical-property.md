---
title: Kanonische Pidlidemail3originaldisplayname (-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidEmail3OriginalDisplayName
api_type:
- COM
ms.assetid: f3fa392a-c3b1-46dd-bf9b-5ce310719542
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: e69bcde35bcfec7746893ee18423aca3a24a6c4a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338073"
---
# <a name="pidlidemail3originaldisplayname-canonical-property"></a>Kanonische Pidlidemail3originaldisplayname (-Eigenschaft

  
  
**Gilt für**: Outlook 2013 | Outlook 2016 
  
Gibt den dritten Anzeigenamen an, der der für den Kontakt angegebenen e-Mail-Adresse entspricht.
  
|||
|:-----|:-----|
|Zugeordnete Eigenschaften:  <br/> |dispidEmail3OriginalDisplayName  <br/> |
|Eigenschaftensatz:  <br/> |PSETID_Address  <br/> |
|Long-ID (Deckel):  <br/> |0x000080A4  <br/> |
|Datentyp:  <br/> |PT_UNICODE  <br/> |
|Bereich:  <br/> |Kontakt  <br/> |
   
## <a name="remarks"></a>Bemerkungen

Wenn der Wert der **dispidEmail3AddrType** ([pidlidemail3addresstype (](pidlidemail3addresstype-canonical-property.md))-Eigenschaft "SMTP" lautet, sollte der Wert der entsprechenden **dispidEmail3OriginalDisplayName** -Eigenschaft dem Wert der entsprechenden ** dispidEmail3EmailAddress** ([pidlidemail3emailaddress (](pidlidemail3emailaddress-canonical-property.md)). Der Zweck dieser Eigenschaft ist es, eine Alternative benutzerfreundliche Adresse anzuzeigen, die dem in der **dispidEmail3EmailAddress**entspricht.
  
## <a name="related-resources"></a>Zugehörige Ressourcen

### <a name="protocol-specifications"></a>Protokollspezifikationen

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Stellt Eigenschaftensatz Definitionen und Verweise auf zugehörige Exchange Server-Protokollspezifikationen bereit.
    
[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)
  
> Gibt die Eigenschaften und Vorgänge an, die für Kontakte und persönliche Verteilerlisten zulässig sind.
    
### <a name="header-files"></a>Header Dateien

Mapidefs. h
  
> Stellt Datentypdefinitionen bereit.
    
## <a name="see-also"></a>Siehe auch



[MAPI-Eigenschaften](mapi-properties.md)
  
[Kanonische MAPI-Eigenschaften](mapi-canonical-properties.md)
  
[Zuordnen von kanonischen Eigenschaftennamen zu MAPI-Namen](mapping-canonical-property-names-to-mapi-names.md)
  
[Zuordnen von MAPI-Namen zu kanonischen Eigenschaftennamen](mapping-mapi-names-to-canonical-property-names.md)

