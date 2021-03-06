---
title: HELP-Funktion
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251436
localization_priority: Normal
ms.assetid: 5b358c38-6ed1-3fbe-c1d1-1a56ebbaa870
description: Öffnet eine HTML-Hilfedatei mit dem Schlüsselwort angegebene im Suchfeld.
ms.openlocfilehash: 639d10bf489d1ad09aef1522d3cbc743bbe66f6f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "33431337"
---
# <a name="help-function"></a>HELP-Funktion

Öffnet eine HTML-Hilfedatei mit dem *Schlüsselwort* angegebene im **Suchfeld** . 
  
## <a name="syntax"></a>Syntax

HELP ("* * *filename. chm!-Schlüsselwort* * *") 
  
### <a name="parameters"></a>Parameter

|**Name**|**Erforderlich/Optional**|**Datentyp**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
| _filename. chm!-Schlüsselwort_ <br/> |Erforderlich  <br/> |**String** <br/> | Der Name der Hilfedatei und das Stichwort, nach dem gesucht werden soll.  <br/> |
   
## <a name="remarks"></a>Bemerkungen

Wenn kein *Schlüsselwort* angegeben wird, wird die Seite Inhalt der Hilfedatei geöffnet. 
  
## <a name="example"></a>Beispiel

Hilfe ("Visio. chm! ShapeSheet") 
  
Öffnet die Visio-Hilfedatei und zeigt eine Liste der Themen zum Stichwort "Shapesheet" an. 
  

