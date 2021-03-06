---
title: Starten eines neuen Formulars zum verFassen
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: ffceaa03-76f2-42e0-b28d-226f1f9cc889
description: 'Letzte Änderung: Samstag, 23. Juli 2011'
ms.openlocfilehash: 29d53ba1242014a501a01d161c19dade164f393a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32270056"
---
# <a name="launching-a-new-compose-form"></a>Starten eines neuen Formulars zum verFassen

  
  
**Gilt für**: Outlook 2013 | Outlook 2016 
  
Formularserver Implementierer sollten die folgende Abfolge von Methoden aufrufen zu ihren Formularserver-und Form-Objekten erwarten, wenn eine Clientanwendung eine neue Nachricht zum Verfassen öffnet:
  
1. Die Clientanwendung Ruft die [IMAPIFormMgr:: ResolveMessageClass](imapiformmgr-resolvemessageclass.md) -Methode auf, um Klasseninformationen zur Nachrichtenklasse des Formular Servers abzurufen. 
    
2. Die Clientanwendung Ruft [IMAPIFormMgr:: CreateForm](imapiformmgr-createform.md) auf, um ein neues Form-Objekt abzurufen. 
    
3. Der MAPI-Formular-Manager lädt den Formularserver, falls er sich nicht bereits im Arbeitsspeicher befindet, und ruft eine [IMAPIForm](imapiformiunknown.md) -Schnittstelle vom Formularserver ab. 
    
4. Die Clientanwendung verwendet die resultierende **IMAPIForm** -Schnittstelle und ruft die [IUnknown:: QueryInterface](https://msdn.microsoft.com/library/54d5ff80-18db-43f2-b636-f93ac053146d%28Office.15%29.aspx) -Methode auf, um die [IPersistMessage](ipersistmessageiunknown.md) -Schnittstelle des Objekts abzurufen. 
    
5. Die Clientanwendung Ruft die [IPersistMessage:: InitNew](ipersistmessage-initnew.md) -Methode auf, um das Form-Objekt mit [IMessage](imessageimapiprop.md)-, View Context-und Advise-Objekten zu verbinden.
    
6. Die Clientanwendung Ruft die [IMAPIForm::D overb](imapiform-doverb.md) -Methode auf, um das geöffnete Verb aufzurufen. 
    
## <a name="see-also"></a>Siehe auch



[Formular Server interAktionen](form-server-interactions.md)

