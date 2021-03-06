---
title: Informationen zu Zeichenfolgen
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
f1_keywords:
- Vis_DSS.chm82251826
localization_priority: Normal
ms.assetid: e1174d8f-70cb-4595-7906-889da15367db
description: 'Formeln können Zeichenfolgen enthalten. Wenn Sie ausgegebene Zeichenfolgen (z. B. einen Wert in einer Eingabeaufforderungszelle), Werte für Shape-Datenelemente oder ein Textfeld formatieren möchten, geben Sie eine Formatierungsangabe an. Ausgegebene Werte können als Zahl-Einheit-Paar, Zeichenfolge, Datum-Uhrzeit, Zeitdauer oder Währung formatiert werden. Beispiel: das Format picture0 #/10 uuformats das Nummern Einheiten paar 10,9 cm AS10 9/10 Zentimeter.'
ms.openlocfilehash: aa95e11db387913edbb40292f7da6a0f4b8a5cf7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409517"
---
# <a name="about-strings"></a>Informationen zu Zeichenfolgen

Formeln können Zeichenfolgen enthalten. Wenn Sie ausgegebene Zeichenfolgen (z. B. einen Wert in einer Eingabeaufforderungszelle), Werte für Shape-Datenelemente oder ein Textfeld formatieren möchten, geben Sie eine Formatierungsangabe an. Ausgegebene Werte können als Zahl-Einheit-Paar, Zeichenfolge, Datum-Uhrzeit, Zeitdauer oder Währung formatiert werden. Mit der Formatierungsangabe "0 #/10 uu" wird beispielsweise das Zahl-Einheit-Paar 10,9 cm als "10 9/10 Zentimeter" formatiert.
  
Sie können Format Bilder in der Zelle **Format** des Abschnitts Shape-Daten und als Argument für die **Format** -oder **FORMATEX** -Funktion verwenden. Wenn Sie ein Textfeld einfügen, werden Bilder in der Liste der Formate im Dialogfeld **Feld** (Registerkarte**Einfügen** ) angezeigt. 
  
## <a name="using-functions-to-format-strings"></a>Verwenden von Funktionen zum Formatieren von Zeichenfolgen

In einer beliebigen Formel, die in eine Zeichenfolge aufgelöst wird, einschließlich benutzerdefinierter Textfeldformeln, können Sie die **Format** -oder die **FORMATEX** -Funktion verwenden. Die Funktion FORMAT gibt eine Zeichenfolge der formatierten Ausgabe zurück. Die **FORMATEX** -Funktion konvertiert nicht typisierte Eingabe in die Einheiten, die Sie für das formatierte Ergebnis auswählen. 
  
## <a name="displaying-formatted-shape-data"></a>Anzeigen formatierter Shape-Daten

Sie können den angezeigten Wert eines Shape-Datenelements formatieren, indem Sie eine Formatierungsangabe in die Zelle Format eingeben.
  
Ein Projektplan-Shape kann beispielsweise ein Shape-Datenelement enthalten, das die Kosten eines Prozesses misst. Standardmäßig ist der Wert eines Shape-Datenelements eine Zeichenfolge. Um die Zeichenfolge "1200" zu formatieren, können Sie "$###,###.00" in die Zelle "Format" eingeben, damit dem Benutzer eine Währung angezeigt wird.
  
Microsoft Visio bestimmt das anzuzeigende Währungssymbol und das 1000er-Trennzeichen anhand der Einstellungen auf der Registerkarte **Währung** im Dialogfeld **Format anpassen ** unter **Region und Sprache** in der Systemsteuerung. (Klicken Sie in der **System**Steuerung auf **Region und Sprache**, und klicken Sie dann auf **Weitere Einstellungen**.)
  
Verwenden Sie die CY-Funktion, wenn Sie eine Zeichenfolge in einen Währungswert konvertieren möchten, damit Sie Berechnungen mit diesem Wert durchführen können.
  
## <a name="using-functions-to-manipulate-text-strings"></a>Verwenden von Funktionen zum Bearbeiten von Textzeichenfolgen

Mit Funktionen können Sie Textzeichenfolgen bearbeiten, z. B. bestimmte Zeichen in einer Zeichenfolge suchen oder ersetzen. Sie können auch Informationen zur Position eines Zeichens in einer Zeichenfolge abrufen, oder Anfangs- und Endzeichen einer Zeichenfolge bestimmen. 
  

