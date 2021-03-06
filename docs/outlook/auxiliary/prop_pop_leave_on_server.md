---
title: PROP_POP_LEAVE_ON_SERVER
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 22d7c1e8-48b9-4768-b4de-9a9f32a3aabb
description: Gibt an, dass eine Kopie einer Nachricht auf dem Server für ein POP-Konto hinterlassen werden soll.
ms.openlocfilehash: e1bbddea0f10c07d630676960d1b330f6055e137
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410945"
---
# <a name="proppopleaveonserver"></a>PROP_POP_LEAVE_ON_SERVER

Gibt an, dass eine Kopie einer Nachricht auf dem Server für ein POP-Konto hinterlassen werden soll.
  
## <a name="quick-info"></a>QuickInfo

|||
|:-----|:-----|
|Kennung:  <br/> |0x1000  <br/> |
|Eigenschafts:  <br/> |PT_DWORD  <br/> |
|Property-Tag:  <br/> |0x10000003  <br/> |
|Access  <br/> |Schreibgeschützt  <br/> |
   
## <a name="remarks"></a>Bemerkungen

In der folgenden Tabelle sind die möglichen Werte aufgeführt. Weitere Informationen zu den Konstanten finden Sie unter [Constants (Account Management API)](constants-account-management-api.md) . 
  
|**Mögliche Werte**|**Beschreibung**|
|:-----|:-----|
|**LEAVE_ON_SERVER** <br/> |HinTerlässt eine Kopie der Nachricht auf dem POP-Server nach dem Herunterladen der Nachricht auf ein Gerät.  <br/> |
|**REMOVE_AFTER** <br/> |Entfernt die Nachricht vom POP-Server, nachdem Sie Sie auf ein Gerät heruntergeladen hat.  <br/> |
|**REMOVE_ON_NUKE** <br/> |Entfernt die Nachricht erst vom POP-Server, nachdem der Benutzer die Nachricht aus dem Ordner Gelöschte Elemente gelöscht hat.  <br/> |
|**GET_REMOVE_AFTER_DAYS** ( _UL_)  <br/> |Ruft die Anzahl der Tage ab, nach denen die Nachricht vom POP-Server entfernt wird.  <br/> |
|**SET_REMOVE_AFTER_DAYS** ( _Tage_)  <br/> |Legt die Anzahl der Tage fest, nach denen die Nachricht vom POP-Server entfernt wird.  <br/> |
   
## <a name="see-also"></a>Siehe auch

- [Verwalten des Nachrichtendownloads für POP3-Konten](managing-message-downloads-for-pop3-accounts.md) 
- [Konstanten (Account Management API)](constants-account-management-api.md)

