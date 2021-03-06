---
title: IConverterSessionMAPIToMIMEStm
ms.date: 9/20/2017
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IConverterSession.MAPIToMIMEStm
api_type:
- COM
ms.assetid: 8660c701-f7f4-8d92-7984-5dae7f677783
description: 'Letzte Änderung: 20. September 2017'
ms.openlocfilehash: 55c547c4dae1acc3e9874edc7778f53a5d34f957
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326944"
---
# <a name="iconvertersessionmapitomimestm"></a>IConverterSession::MAPIToMIMEStm
 
  
**Gilt für**: Outlook 2013 | Outlook 2016 
  
Konvertiert eine MAPI-Nachricht in einen MIME-Stream.
  
```cpp
HRESULT IConverterSession::MAPIToMIMEStm( 
    LPMESSAGE pmsg, 
    LPSTREAM pstm, 
    ULONG ulFlags 
);
```

## <a name="parameters"></a>Parameter

 _pmsg_
  
> in Zeiger auf die zu konvertierende Nachricht. Weitere Informationen finden Sie unter mapidefs. h für die Typdefinition von **LPMESSAGE**.
    
 _pstm_
  
> Out [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) -Schnittstelle zum Ausgeben des Streams. 
    
 _ulFlags_
  
>  in Flags, die bestimmte Aktionen für den Konverter kennzeichnen: 
    
CCSF_8BITHEADERS
  
> Der Konverter sollte 8-Bit-Kopfzeilen zulassen.
    
CCSF_EMBEDDED_MESSAGE
  
> Gesendete/nicht gesendete Informationen werden in X-unsent gespeichert.
    
CCSF_GLOBAL_MESSAGE
  
> Der Konverter sollte eine internationale Nachricht (EAI/RFC6530) erstellen.
    
CCSF_INCLUDE_BCC
  
> BCC-Empfänger der MAPI-Nachricht sollten im MIME-Stream enthalten sein.
    
CCSF_NO_MSGID
  
> In ausgehenden Nachrichten keine Nachricht-ID-Felder einbeziehen.
    
CCSF_NOHEADERS
  
> Der Konverter sollte die Kopfzeilen der externen Nachricht ignorieren.
    
CCSF_PLAIN_TEXT_ONLY
  
> Der Konverter sollte nur nur-Text senden.
    
CCSF_SMTP
  
> Der Konverter wird an eine SMTP-Nachricht übergeben. Dieses Flag muss immer festgelegt werden.
    
CCSF_USE_RTF
  
> Der Konverter sollte in der MIME-Nachricht vom HTML-in das RTF-Format konvertieren.
    
CCSF_USE_TNEF
  
> Der Konverter sollte das TNEF-Format (Transport Neutral Encapsulation Format) in der MIME-Nachricht verwenden.
    
## <a name="return-values"></a>Rückgabewerte

E_INVALIDARG
  
> Ungültige Flags wurden übergeben, oder *pmsg* oder *pstm* ist NULL. 
    
## <a name="remarks"></a>Bemerkungen

Wird nur für standardmäßige Outlook-Nachrichtentypen unterstützt.
  
## <a name="mfcmapi-reference"></a>MFCMAPI-Referenz

Einen MFCMAP-Beispielcode finden Sie in der folgenden Tabelle.
  
|**Datei**|**Funktion**|**Comment**|
|:-----|:-----|:-----|
|MapiMime. cpp  <br/> |ImportEMLToIMessage  <br/> |MFCMAPI verwendet MimeToMAPI, um eine EML-Datei in eine MAPI-Nachricht umzuwandeln.  <br/> |
|MapiMime. cpp  <br/> |ExportIMessageToEML  <br/> |MFCMAPI verwendet MAPIToMIMEStm, um eine MAPI-Nachricht in eine EML-Datei umzuwandeln.  <br/> |
   
## <a name="see-also"></a>Siehe auch



[IConverterSession : IUnknown](iconvertersessioniunknown.md)
  
[IConverterSession::MAPIToMIMEStm](iconvertersession-mapitomimestm.md)
  
[IConverterSession::MIMEToMAPI](iconvertersession-mimetomapi.md)
  
[IConverterSession::SetAdrBook](iconvertersession-setadrbook.md)
  
[IConverterSession::SetCharSet](iconvertersession-setcharset.md)
  
[IConverterSession::SetEncoding](iconvertersession-setencoding.md)
  
[IConverterSession::SetSaveFormat](iconvertersession-setsaveformat.md)
  
[IConverterSession::SetTextWrapping](iconvertersession-settextwrapping.md)
  
[Kanonische Pidtagmessageeditorformat (-Eigenschaft](pidtagmessageeditorformat-canonical-property.md)
  
[Kanonische PidLidUseTnef-Eigenschaft](pidlidusetnef-canonical-property.md)


[MAPI-Konstanten](mapi-constants.md)

