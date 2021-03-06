---
title: Kanonische pidlidaddressbookprovideremaillist (-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidAddressBookProviderEmailList
api_type:
- COM
ms.assetid: 9c0527ea-e922-4514-b913-d3520350c452
description: 'Letzte Änderung: Montag, 9. März 2015'
ms.openlocfilehash: 053ec531f69ff7734872466b7a661beff3177b2c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348482"
---
# <a name="pidlidaddressbookprovideremaillist-canonical-property"></a>Kanonische pidlidaddressbookprovideremaillist (-Eigenschaft

  
  
**Gilt für**: Outlook 2013 | Outlook 2016 
  
Gibt an, welche elektronischen Adresseigenschaften für den Kontakt festgelegt werden. 
  
|||
|:-----|:-----|
|Zugeordnete Eigenschaften:  <br/> |dispidABPEmailList  <br/> |
|Eigenschaftengruppe:  <br/> |PSETID_Address  <br/> |
|Lange ID (LID):  <br/> |0x00008028  <br/> |
|Datentyp:  <br/> |PT_MV_LONG  <br/> |
|Bereich:  <br/> |Kontakt  <br/> |
   
## <a name="remarks"></a>Hinweise

Jeder PT_LONG-Wert in dieser Eigenschaft muss in der-Eigenschaft eindeutig sein und muss auf einen der Werte in der folgenden Tabelle festgelegt werden. Wenn diese Eigenschaft festgelegt ist, muss auch die **dispidABPArrayType** ([pidlidaddressbookproviderarraytype (](pidlidaddressbookproviderarraytype-canonical-property.md))-Eigenschaft festgelegt werden. Diese beiden Eigenschaften müssen miteinander synchronisiert bleiben. Wenn beispielsweise einer der Werte in **dispidABPEmailList** "0x00000000" ist, muss **dispidABPArrayType** das Bit "0x00000001" festgelegt haben. 
  
|**Wert**|**Beschreibung**|
|:-----|:-----|
|0x00000000  <br/> |Mail1 ist für den Kontakt definiert.  <br/> |
|0x00000001  <br/> |Mail2 ist für den Kontakt definiert.  <br/> |
|0x00000002  <br/> |Email3 ist für den Kontakt definiert.  <br/> |
|0x00000003  <br/> |Business Fax ist für den Kontakt definiert.  <br/> |
|0x00000004  <br/> |Home Fax ist für den Kontakt definiert.  <br/> |
|0x00000005  <br/> |Primäres Fax ist für den Kontakt definiert.  <br/> |
   
## <a name="related-resources"></a>Verwandte Ressourcen

### <a name="protocol-specifications"></a>Protokollspezifikationen

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Stellt Eigenschaftenmengen Definitionen und Verweise auf zugehörige Exchange Server Protokollspezifikationen bereit.
    
[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)
  
> Gibt die Eigenschaften und Vorgänge an, die für Kontakte und persönliche Verteilerlisten zulässig sind.
    
### <a name="header-files"></a>Header Dateien

Mapidefs. h
  
> Stellt Definitionen von Datentypen bereit.
    
## <a name="see-also"></a>Siehe auch



[MAPI-Eigenschaften](mapi-properties.md)
  
[Kanonische MAPI-Eigenschaften](mapi-canonical-properties.md)
  
[Zuordnen von kanonischen Eigenschaftennamen zu MAPI-Namen](mapping-canonical-property-names-to-mapi-names.md)
  
[Zuordnen von MAPI-Namen zu kanonischen Eigenschaftennamen](mapping-mapi-names-to-canonical-property-names.md)

