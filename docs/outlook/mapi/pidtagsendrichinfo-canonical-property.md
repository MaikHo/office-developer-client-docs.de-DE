---
title: Kanonische Pidtagsendrichinfo (-Eigenschaft
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagSendRichInfo
api_type:
- COM
ms.assetid: e85fc766-197a-484f-b600-68cd28a052a2
description: 'Letzte �nderung: Montag, 9. M�rz 2015'
ms.openlocfilehash: a7ad27d757d4ed6df58c597bf17d9e5412f83457
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342518"
---
# <a name="pidtagsendrichinfo-canonical-property"></a>Kanonische Pidtagsendrichinfo (-Eigenschaft

  
  
**Gilt für**: Outlook 2013 | Outlook 2016 
  
Enthält TRUE, wenn der Empfänger alle Nachrichteninhalte empfangen kann, einschließlich Rich-Text-Format (RTF) und Objekt Verknüpfungs-und Einbettungs Objekte (OLE). 
  
|||
|:-----|:-----|
|Zugeordnete Eigenschaften:  <br/> |PR_SEND_RICH_INFO  <br/> |
|Kennung:  <br/> |0x3A40  <br/> |
|Datentyp:  <br/> |PT_BOOLEAN  <br/> |
|Bereich:  <br/> |Adresse  <br/> |
   
## <a name="remarks"></a>Bemerkungen

Es wird empfohlen, dass Verteilerlisten-und Messaging-Benutzerobjekte diese Eigenschaft verfügbar machen. 
  
Diese Eigenschaft gibt an, ob der Absender der Ansicht ist, dass der Empfänger MAPI-fähig ist. 
  
Wenn diese Eigenschaft auf TRUE festgelegt ist, können Transport und Gateway den vollständigen Inhalt der Nachricht übertragen, einschließlich RTF-und OLE-Objekten. Transport-und Gateway sollten Transport Neutral Encapsulation Format (TNEF) verwenden, um alle Eigenschaften einzukapseln, die nicht für alle Beteiligten Messagingsysteme systemeigen sind. 
  
Wenn diese Eigenschaft auf FALSE festgelegt ist, können Transportanbieter und Gateway Nachrichten verwerfen, die von ihren systemeigenen Clients nicht verwendet werden können. Wenn die Clients beispielsweise RTF nicht unterstützen, kann der Transportanbieter nur nur-Text senden. 
  
Wenn diese Eigenschaft nicht festgelegt ist, wird das Standardverhalten durch die Implementierung des Transportanbieters, MTA (Message Transfer Agent) oder Gateways bestimmt. Adressbuchanbieter müssen diese Eigenschaft nicht unterstützen. Ein eng gekoppelter Adressbuch-und Transportanbieter kann beispielsweise TNEF senden, aber nie RTF verwenden. 
  
Der Client sollte nicht davon ausgehen, dass der Transportanbieter und das Gateway TNEF aus eigener Initiative verwenden. Einige Transportanbieter und Gateways, die TNEF unterstützen, übertragen Sie ohne Rücksicht auf den Wert dieser Eigenschaft, andere jedoch ablehnen, TNEF zu erstellen oder zu senden, wenn Sie nicht auf TRUE festgelegt ist. 
  
> [!NOTE]
> Die Einstellung dieser Eigenschaft und die Entscheidungen, die auf ihrem Wert basieren, sind pro Empfänger. 
  
Standardmäßig wird der Wert von MAPI auf TRUE festgelegt. Ein Client, der [IAddrBook:: CreateOneOff](iaddrbook-createoneoff.md) oder einen Anbieter aufruft, der [IMAPISupport:: CreateOneOff](imapisupport-createoneoff.md) aufgerufen hat, kann das **MAPI_SEND_NO_RICH_INFO** -Bit im Parameter _ulFlags_ festlegen, wodurch MAPI diese Eigenschaft auf false festgelegt wird. Von der Benutzeroberfläche erstellte einmaliges verwenden den von der Erstellungs Vorlage angegebenen Wert. 
  
Bei Aufrufen der [IAddrBook::](iaddrbook-resolvename.md) ResolveName-Methode, wenn der Name nicht aufgelöst, aber als Internet Adresse (SMTP) interpretiert werden kann, wird diese Eigenschaft auf false festgelegt. Um als Internet Adresse interpretiert werden zu können, muss der Anzeigename des nicht aufgelösten Eintrags im Format X @ Y liegen. Z, beispielsweise "pete@pinecone.com". 
  
## <a name="related-resources"></a>Zugehörige Ressourcen

### <a name="protocol-specifications"></a>Protokollspezifikationen

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> Enthält Verweise auf zugehörige Exchange Server-Protokollspezifikationen.
    
[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)
  
> Gibt die Eigenschaften und Vorgänge für Listen von Benutzern, Kontakten, Gruppen und Ressourcen an.
    
[[MS-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> Gibt die Eigenschaften und Vorgänge an, die für e-Mail-Nachrichtenobjekte zulässig sind.
    
[[MS-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)
  
> von Internet Standard-e-Mail-Konventionen zu Nachrichtenobjekten.
    
### <a name="header-files"></a>Header Dateien

Mapidefs. h
  
> Stellt Datentypdefinitionen bereit.
    
Mapitags. h
  
> Enthält Definitionen von Eigenschaften, die als zugeordnete Eigenschaften aufgelistet sind.
    
## <a name="see-also"></a>Siehe auch



[Kanonische Pidtagattachdataobject (-Eigenschaft](pidtagattachdataobject-canonical-property.md)


[MAPI-Eigenschaften](mapi-properties.md)
  
[Kanonische MAPI-Eigenschaften](mapi-canonical-properties.md)
  
[Zuordnen von kanonischen Eigenschaftennamen zu MAPI-Namen](mapping-canonical-property-names-to-mapi-names.md)
  
[Zuordnen von MAPI-Namen zu kanonischen Eigenschaftennamen](mapping-mapi-names-to-canonical-property-names.md)

