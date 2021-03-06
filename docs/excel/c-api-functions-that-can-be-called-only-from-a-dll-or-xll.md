---
title: C-API-Funktionen, die nur aus einer DLL oder XLL aufgerufen werden können
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- Funktionen [Excel 2007], c-API, die von dll oder XLL aufgerufen wird
localization_priority: Normal
ms.assetid: 87c9e75b-c364-4428-a169-010886313b85
description: 'Gilt für: Excel 2013 | Office 2013 | Visual Studio'
ms.openlocfilehash: e6d2d3c824c482e3726cdaefa869393002a80f44
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423118"
---
# <a name="c-api-functions-that-can-be-called-only-from-a-dll-or-xll"></a>C-API-Funktionen, die nur aus einer DLL oder XLL aufgerufen werden können

**Gilt für**: Excel 2013 | Office 2013 | Visual Studio 
  
Die C-API bietet 15 Microsoft Excel-Rückruffunktionen, die nur mithilfe der **Excel4**-, **Excel4v**-, **Excel12**-oder **Excel12v** -Funktionen (oder durch eine dieser Funktionen indirekt mithilfe der Frameworkfunktionen Excel) aufgerufen werden können. ** **oder **Excel12f**). Das heißt, Sie können nur aus einer DLL oder XLL aufgerufen werden.
  
## <a name="in-this-section"></a>Inhalt dieses Abschnitts

[xlAbort](xlabort.md)
  
[xlAsyncReturn](xlasyncreturn.md)
  
[xlCoerce](xlcoerce.md)
  
[xlDefineBinaryName](xldefinebinaryname.md)
  
[xlDisableXLMsgs](xldisablexlmsgs.md)
  
[xlEnableXLMsgs](xlenablexlmsgs.md)
  
[xlEventRegister](xleventregister.md)
  
[xlFree](xlfree.md)
  
[xlGetBinaryName](xlgetbinaryname.md)
  
[xlGetHwnd](xlgethwnd.md)
  
[xlGetInst](xlgetinst.md)
  
[xlGetInstPtr](xlgetinstptr.md)
  
[xlGetName](xlgetname.md)
  
[xlRunningOnCluster](xlrunningoncluster.md)
  
[xlSet](xlset.md)
  
[xlSheetId](xlsheetid.md)
  
[xlSheetNm](xlsheetnm.md)
  
[xlStack](xlstack.md)
  
[xlUDF](xludf.md)
  
## <a name="see-also"></a>Siehe auch



[C-API-Rückruffunktionen Excel4, Excel12](c-api-callback-functions-excel4-excel12.md)

