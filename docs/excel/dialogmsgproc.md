---
title: DIALOGMsgProc
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- DIALOGMsgProc
keywords:
- dialogmsgproc-Funktion [Excel 2007]
localization_priority: Normal
ms.assetid: 9a538e83-ba34-4806-bb8c-7cda3beb6b66
description: 'Gilt für: Excel 2013 | Office 2013 | Visual Studio'
ms.openlocfilehash: 1de1b73f5672067f07518ef3367d77349395a1c3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406514"
---
# <a name="dialogmsgproc"></a>DIALOGMsgProc

**Gilt für**: Excel 2013 | Office 2013 | Visual Studio 
  
Dieses Verfahren ist dem systemeigenen Windows-Dialogfeld zugeordnet, das von [fShowDialog](fshowdialog.md) angezeigt wird. Es stellt die von Windows aufgerufenen Dienstroutinen für die Ereignisse (Nachrichten) bereit, die auftreten, wenn der Benutzer eines der Schaltflächen, Eingabefelder oder Steuerelemente des Dialogfelds betreibt. 
  
```cs
BOOL CALLBACK DIALOGMsgProc(HWND hWndDlg, UINT message, WPARAM wParam, LPARAM lParam);
```

## <a name="parameters"></a>Parameter

 _hWndDlg_ (**HWND**)
  
Enthält das HWND-Windows-Handle des Dialogfelds.
  
 _Nachricht_ (**Uint**)
  
Die Nachricht, auf die geantwortet werden soll.
  
 _wParam_ (**WParam**)
  
 _LPARAM_ (**LPARAM**)
  
Von Windows übergebene Argumente.
  
## <a name="property-valuereturn-value"></a>Eigenschaftswert/Rückgabewert

 **True** , wenn die Nachricht verarbeitet, **false** , wenn nicht. 
  
### <a name="example"></a>Beispiel

Den `\SAMPLES\GENERIC\GENERIC.C` Quellcode für diese Funktion finden Sie unter. 
  
## <a name="see-also"></a>Siehe auch



[Funktionen in der generische DLL](functions-in-the-generic-dll.md)

