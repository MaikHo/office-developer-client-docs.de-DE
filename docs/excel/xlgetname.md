---
title: xlGetName
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlGetName
keywords:
- Xlgetname-Funktion [excel 2007]
localization_priority: Normal
ms.assetid: 72dbebc0-7436-4771-8fbf-2b445341da65
description: 'Gilt f�r: Excel 2013�| Office 2013�| Visual Studio'
ms.openlocfilehash: 069676957d280a0bf3b398bb23b27f0e654bc655
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19790602"
---
# <a name="xlgetname"></a><span data-ttu-id="5fe62-104">xlGetName</span><span class="sxs-lookup"><span data-stu-id="5fe62-104">xlGetName</span></span>

<span data-ttu-id="5fe62-105">**Gilt für**: Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5fe62-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="5fe62-106">Gibt den vollständigen Pfad und Namen der DLL in Form einer Zeichenfolge zurück.</span><span class="sxs-lookup"><span data-stu-id="5fe62-106">Returns the full path and file name of the DLL in the form of a string.</span></span>
  
```cs
Excel12(xlGetName, LPXLOPER12 pxRes, 0);
```

## <a name="parameters"></a><span data-ttu-id="5fe62-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="5fe62-107">Parameters</span></span>

<span data-ttu-id="5fe62-108">Diese Funktion hat keine Argumente.</span><span class="sxs-lookup"><span data-stu-id="5fe62-108">This function has no arguments.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="5fe62-109">Eigenschaft Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5fe62-109">Property value/Return value</span></span>

<span data-ttu-id="5fe62-110">Der Pfad und Dateiname (**XltypeStr**) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5fe62-110">Returns the path and file name (**xltypeStr**).</span></span> 
  
## <a name="example"></a><span data-ttu-id="5fe62-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5fe62-111">Example</span></span>

`\SAMPLES\EXAMPLE\EXAMPLE.C`
  
```cs
short WINAPI xlGetNameExample(void)
{
    XLOPER12 xRes;
    Excel12(xlGetName, (LPXLOPER12)&xRes, 0);
    Excel12(xlcAlert, 0, 1, (LPXLOPER12)&xRes);
    Excel12(xlFree, 0, 1, (LPXLOPER12)&xRes);
    return 1;
}
```

## <a name="see-also"></a><span data-ttu-id="5fe62-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5fe62-112">See also</span></span>

- [<span data-ttu-id="5fe62-113">C C-API-Funktionen, die nur aus einer DLL oder XLL aufgerufen werden k�nnen</span><span class="sxs-lookup"><span data-stu-id="5fe62-113">C API Functions That Can Be Called Only from a DLL or XLL</span></span>](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)
