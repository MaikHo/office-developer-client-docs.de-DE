---
title: Kanonische Pidtagattachsize (-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAttachSize
api_type:
- HeaderDef
ms.assetid: 768b3215-dd9f-4aa0-b52c-178ca81a7b07
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: f3e4f19ab43a3da7c4840d762d5131813c83d996
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32361089"
---
# <a name="pidtagattachsize-canonical-property"></a>Kanonische Pidtagattachsize (-Eigenschaft

  
  
**Gilt für**: Outlook 2013 | Outlook 2016 
  
Enthält die Summe der Größen aller Eigenschaften einer Anlage in Byte. 
  
|||
|:-----|:-----|
|Zugeordnete Eigenschaften:  <br/> |PR_ATTACH_SIZE  <br/> |
|Kennung:  <br/> |0x0E20  <br/> |
|Datentyp:  <br/> |PT_LONG  <br/> |
|Bereich:  <br/> |Nachrichtenanlage  <br/> |
   
## <a name="remarks"></a>Bemerkungen

Es wird empfohlen, dass Attachment-unter Objekte die **PR_ATTACH_SIZE** -Eigenschaft verfügbar machen. Die in **PR_ATTACH_SIZE** enthaltene Summe enthält die Größe der **PR_ATTACH_DATA_BIN** ([pidtagattachdatabinary (](pidtagattachdatabinary-canonical-property.md)) oder **PR_ATTACH_DATA_OBJ** ([pidtagattachdataobject (](pidtagattachdataobject-canonical-property.md))-Eigenschaft. Dementsprechend ist **PR_ATTACH_SIZE** in der Regel größer als der Inhalt der Anlage allein. 
  
Diese Eigenschaft kann verwendet werden, um die ungefähre Größe der Anlage zu überprüfen, bevor eine Remoteübertragung per Modem durchgeführt wird und Status anzeigen beim Speichern der Anlage auf dem Datenträger angezeigt werden. Sie ist besonders nützlich bei angefügten OLE-Objekten. 
  
## <a name="related-resources"></a>Zugehörige Ressourcen

### <a name="protocol-specifications"></a>Protokollspezifikationen

[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> Verarbeitet Nachrichten-und Anlagenobjekte.
    
### <a name="header-files"></a>Header Dateien

Mapidefs. h
  
> Stellt Datentypdefinitionen bereit.
    
mapitags. h
  
> Enthält Definitionen von Eigenschaften, die als Alternative Namen aufgeführt sind.
    
## <a name="see-also"></a>Siehe auch



[Kanonische Pidtagmessagesize (-Eigenschaft](pidtagmessagesize-canonical-property.md)


[MAPI-Eigenschaften](mapi-properties.md)
  
[Kanonische MAPI-Eigenschaften](mapi-canonical-properties.md)
  
[Zuordnen von kanonischen Eigenschaftennamen zu MAPI-Namen](mapping-canonical-property-names-to-mapi-names.md)
  
[Zuordnen von MAPI-Namen zu kanonischen Eigenschaftennamen](mapping-mapi-names-to-canonical-property-names.md)

