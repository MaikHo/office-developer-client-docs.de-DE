---
title: ODER (Access Custom Web App)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: e7190523-87cf-4e04-aef4-d229776cd16b
description: Kombiniert zwei Bedingungen. Gibt TRUE zurück, wenn eine der beiden Bedingungen true ist.
ms.openlocfilehash: ffa605d2403c5aa8396d89f78d0bb7dd11343540
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414760"
---
# <a name="or-access-custom-web-app"></a>ODER (Access Custom Web App)

Kombiniert zwei Bedingungen. Gibt TRUE zurück, wenn eine der beiden Bedingungen true ist.
  
> [!IMPORTANT]
> Das Erstellen und Verwenden von Access-Web-Apps in SharePoint wird von Microsoft nicht mehr empfohlen. Alternativ sollten Sie die Verwendung von [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) für das Erstellen von Business Solutions ohne Code für das Web und für mobile Geräte in Betracht ziehen. 
  
## <a name="syntax"></a>Syntax

 *Boolean-Wert* **Oder** *Boolean-Wert* 
  
Der **or** -Operator verwendet das folgende Argument. 
  
|**Argumentname**|**Beschreibung**|
|:-----|:-----|
| *BoolescherAusdruck*  <br/> |Ein beliebiger gültiger Ausdruck, der TRUE oder FALSE zurückgibt.  <br/> |
   
## <a name="remarks"></a>Bemerkungen

Wenn mehrere logische Operatoren in einer Anweisung verwendet werden, werden Operatoren **** **und** Operatoren ausgewertet. Sie können die Reihenfolge der Auswertung jedoch mithilfe von Klammern ändern. 
  
Die folgende Tabelle zeigt das Ergebnis des **or** -Operators. 
  
||**TRUE**|**FALSE**|
|:-----|:-----|:-----|
|**TRUE** <br/> |TRUE  <br/> |TRUE  <br/> |
|**FALSE** <br/> |TRUE  <br/> |FALSE  <br/> |
   

