---
title: Kanonische pidlidcleanglobalobjectid (-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidCleanGlobalObjectId
api_type:
- COM
ms.assetid: 59b85997-7972-492e-9786-3f0f367dc3e3
description: 'Letzte Änderung: Montag, 9. März 2015'
ms.openlocfilehash: c48fa333d407492b69da5287fa75c565bfd10e11
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32349217"
---
# <a name="pidlidcleanglobalobjectid-canonical-property"></a>Kanonische pidlidcleanglobalobjectid (-Eigenschaft

  
  
**Gilt für**: Outlook 2013 | Outlook 2016 
  
Gibt die globale "Clean"- **objectID**an.
  
|||
|:-----|:-----|
|Zugeordnete Eigenschaften:  <br/> |dispidCleanGlobalObjId  <br/> |
|Eigenschaftengruppe:  <br/> |PSETID_Meeting  <br/> |
|Lange ID (LID):  <br/> |0x00000023  <br/> |
|Datentyp:  <br/> |PT_BINARY  <br/> |
|Bereich:  <br/> |Meetings  <br/> |
   
## <a name="remarks"></a>Hinweise

Das Format dieser Eigenschaft ist identisch mit der von **LID_GLOBAL_OBJID** ([pidlidglobalobjectid (](pidlidglobalobjectid-canonical-property.md)). Der Wert dieser Eigenschaft muss dem Wert von **LID_GLOBAL_OBJID**entsprechen, mit der Ausnahme, dass die Felder YH, YL, M und D gleich NULL sein müssen. Alle Objekte, die auf eine Instanz einer wiederkehrenden Datenreihe (einschließlich einer verwaisten Instanz) sowie die wiederkehrende Datenreihe selbst referenzieren, haben denselben Wert für diese Eigenschaft.
  
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

