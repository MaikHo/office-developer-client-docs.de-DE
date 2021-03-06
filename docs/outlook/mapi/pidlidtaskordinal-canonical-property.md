---
title: Kanonische Pidlidtaskordinal (-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidTaskOrdinal
api_type:
- COM
ms.assetid: 1021860e-4c40-4c22-aa68-b568d046aaf7
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: a64008da93584529916a9303176bba0aa08d3fac
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357960"
---
# <a name="pidlidtaskordinal-canonical-property"></a>Kanonische Pidlidtaskordinal (-Eigenschaft

  
  
**Gilt für**: Outlook 2013 | Outlook 2016 
  
Stellt eine Hilfe für benutzerdefinierte Sortieraufgaben bereit.
  
|||
|:-----|:-----|
|Zugeordnete Eigenschaften:  <br/> |dispidTaskOrdinal  <br/> |
|Eigenschaftensatz:  <br/> |PSETID_Task  <br/> |
|Long-ID (Deckel):  <br/> |0x00008123  <br/> |
|Datentyp:  <br/> |PT_LONG  <br/> |
|Bereich:  <br/> |Aufgabe  <br/> |
   
## <a name="remarks"></a>Bemerkungen

Diese Eigenschaft kann nicht mehr als unset bleiben. Wenn dieser Wert festgelegt ist, muss er größer sein als "0x800186A0" (-2.147.383.648) und kleiner als "0x7FFE7960" (2.147.383.648) und muss Untervorgängen im gleichen Ordner eindeutig sein.
  
Wenn der Client diese Eigenschaft auf eine Zahl kleiner als den negativen Wert der **PR_ORDINAL_MOST** ([pidtagordinalmost (](pidtagordinalmost-canonical-property.md))-Eigenschaft des Ordners festlegt, muss der Client auch **PR_ORDINAL_MOST** für den Ordner aktualisieren. 
  
Die **PR_ORDINAL_MOST** -Eigenschaft des Ordners bietet eine effiziente Möglichkeit, einen eindeutigen Wert zwischen Vorgängen im gleichen Ordner zu ermitteln. 
  
## <a name="related-resources"></a>Zugehörige Ressourcen

### <a name="protocol-specifications"></a>Protokollspezifikationen

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Stellt Eigenschaftensatz Definitionen und Verweise auf zugehörige Exchange Server-Protokollspezifikationen bereit.
    
[[MS-OXOTASK]](https://msdn.microsoft.com/library/55600ec0-6195-4730-8436-59c7931ef27e%28Office.15%29.aspx)
  
> Definiert mehrere Objekte, die das elektronische Äquivalent von Aufgaben, Vorgangszuordnungen und Vorgangsaktualisierungen modellieren. 
    
### <a name="header-files"></a>Header Dateien

Mapidefs. h
  
> Stellt Datentypdefinitionen bereit.
    
## <a name="see-also"></a>Siehe auch



[MAPI-Eigenschaften](mapi-properties.md)
  
[Kanonische MAPI-Eigenschaften](mapi-canonical-properties.md)
  
[Zuordnen von kanonischen Eigenschaftennamen zu MAPI-Namen](mapping-canonical-property-names-to-mapi-names.md)
  
[Zuordnen von MAPI-Namen zu kanonischen Eigenschaftennamen](mapping-mapi-names-to-canonical-property-names.md)

