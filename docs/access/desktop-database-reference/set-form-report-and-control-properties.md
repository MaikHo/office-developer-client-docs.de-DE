---
title: Einstellen von Formular-, Berichts- und Steuerelementeigenschaften
TOCTitle: Set form, report, and control properties
ms:assetid: 03349d86-f107-9e49-89df-62f55f3a0735
ms:mtpsurl: https://msdn.microsoft.com/library/Ff844789(v=office.15)
ms:contentKeyID: 48542977
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- vbaac10.chm12286
f1_categories:
- Office.Version=v15
ms.openlocfilehash: f839ab2e2c6dfab32c49248f1be1878bf289eb6b
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2018
ms.locfileid: "25473825"
---
# <a name="set-form-report-and-control-properties"></a>Einstellen von Formular-, Berichts- und Steuerelementeigenschaften

**Betrifft**: Access 2013 | Office 2013

Jedes Formular, jeder Bericht, jeder Bereich und jedes Steuerelement verfügt über Eigenschafteneinstellungen, mit denen Sie das Aussehen und die Funktionsweise eines Elements ändern können. Sie können die Eigenschaften im Eigenschaftenfenster, in einem Makro oder in Visual Basic anzeigen und ändern.

## <a name="set-properties"></a>Eigenschaften festlegen

1. Wählen Sie in der Formularentwurfsansicht oder Berichtsentwurfsansicht das Steuerelement, den Bereich, das Formular oder den Bericht aus, für das bzw. den Sie die Eigenschaft einstellen möchten. Sie haben folgende Auswahlmöglichkeiten:
    
   - Steuerelemente. Wenn Sie mehrere Steuerelemente auswählen möchten, klicken Sie bei gedrückter UMSCHALTTASTE auf die gewünschten Steuerelemente, oder ziehen Sie den Mauszeiger über die gewünschten Steuerelemente. Wenn Sie mehrere Steuerelemente auswählen, zeigt das Eigenschaftenfenster nur die Eigenschaften an, die alle markierten Steuerelemente gemeinsam besitzen.
    
   - Einen Bereich. Klicken Sie auf den Bereichsmarkierer des gewünschten Bereichs.
    
   - Das gesamte Formular oder den gesamten Bericht. Klicken Sie auf den Formularmarkierer oder Berichtsmarkierer in der oberen linken Ecke des Formulars bzw. Berichts.

2. Zeigen Sie das Eigenschaftenfenster an, indem Sie zuerst mit der rechten Maustaste auf das Objekt oder den Bereich und dann im Kontextmenü auf **Eigenschaften** klicken, oder indem Sie auf der Symbolleiste auf **Eigenschaften** klicken.

3. Klicken Sie auf die Eigenschaft, deren Wert Sie einstellen möchten, und führen Sie dann einen der folgenden Schritte durch:
    
   - Geben Sie im Einstellungsfeld der Eigenschaft die gewünschte Einstellung oder einen geeigneten Ausdruck ein.
    
   - Wenn das Einstellungsfeld der Eigenschaft einen Pfeil enthält, klicken Sie auf den Pfeil, und klicken Sie dann in der Liste auf einen Wert.
    
   - Wenn eine **Generator** -Schaltfläche rechts neben dem Eigenschaftenfeld angezeigt wird, klicken Sie auf einen Generator anzuzeigen oder Anzeigen eines Dialogfelds bietet Ihnen eine Auswahl von Generatoren. Beispielsweise können Sie die Code-Generators, Makro-Generator oder Abfrage-Generator verwenden, um bestimmte Eigenschaften festzulegen.

## <a name="tips"></a>Tipps

- Microsoft Access stellt ein **Zoom** -Feld für die Eingabe und die Anzeige von Ausdrücken oder anderen langen Eigenschafteneinstellungen bereit. Um das **Zoom** -Feld anzuzeigen, klicken Sie im Eigenschaftenfenster auf das Eigenschaftenfeld. Drücken Sie dann UMSCHALT+F2, oder klicken Sie zuerst mit der rechten Maustaste, und klicken Sie dann im Kontextmenü auf **Zoom**.

- Sie können die Eigenschaft **Steuerelementinhalt** für einige Steuerelemente einstellen, indem Sie die Eigenschafteneinstellung im Steuerelement selbst vornehmen.

- Durch Ändern der Standardeigenschafteneinstellungen für einen Steuerelementtyp erreichen Sie, dass später von Ihnen erstellte Steuerelemente über die neuen Standardeinstellungen verfügen.

- Die Eigenschafteneinstellungen eines gebundenen Steuerelements stimmen nicht immer mit den entsprechenden Einstellungen im Feld der zugrunde liegenden Tabelle oder Abfrage überein, an die das Steuerelement gebunden ist. In diesem Fall setzen die Einstellungen des Formulars oder Berichts in der Regel die Einstellungen der Tabelle oder Abfrage außer Kraft. Weitere Informationen über die Vererbung von Eigenschaften finden Sie in den Erklärungen zur Beziehung zwischen Steuerelementeigenschaften und Eigenschaften in den zugrunde liegenden Feldern.
