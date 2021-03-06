---
title: Verwenden des Java-Typbibliotheks-Assistenten
TOCTitle: Using the Java Type Library Wizard
ms:assetid: 96af770c-c7c2-c905-3c3e-383a5b99cab2
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249670(v=office.15)
ms:contentKeyID: 48546455
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: a27491acabd19f688eca4159a36dcfcfc486a026
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32312082"
---
# <a name="using-the-java-type-library-wizard"></a>Verwenden des Java-Typbibliotheksassistenten


**Gilt für**: Access 2013, Office 2013

Der Java-Typbibliotheks-Assistent ist ein Feature von Visual J++ 1.x, das in das Menü **Extras** der Entwicklungsumgebung integriert ist. Er dient zum Durchsuchen einer Typbibliothek und zum Erstellen einer Java-Schnittstelle, die den Zugriff auf COM-Objekte ermöglicht. Für Visual J++ 6.0 wurde der Java-Typbibliotheks-Assistent ersetzt durch [ADO für Windows Foundation Classes](ado-wfc-programming.md).

Die mit dem Java-Typbibliotheks-Assistenten erzeugten Ergebnisse ähneln denen der Befehlszeilentools, die im [Microsoft SDK für Java](using-the-microsoft-sdk-for-java.md) enthalten sind. Sie können jedoch im Gegensatz zu den vom Microsoft SDK für Java generierten Klassenwrappern nicht in die vom Assistenten generierten Klassenwrapper springen.

Der Java-Typbibliotheks-Assistent generiert die Klassen an folgendem Speicherort\>\\:\\ \\ \<Windows\\Directory Java Trustlib MSADO15. The Summary.txt file, located in the directory where the classes were generated, shows the class definitions it generated.

Durch den Java-Typbibliotheks-Assistenten werden Aufzählungstypen aus beliebigen Typbibliotheken in den INT-Typ (Ganzzahl) konvertiert. Außerdem wird eine Schnittstelle definiert, die den einzelnen Aufzählungstypen in der Typbibliothek entspricht. Sie können mit der folgenden Syntax auf die Werte eines ADO-Aufzählungstyps verweisen:

```vb 
 
msado15.<Enum Name>.<constant Name> 
```

Ein Beispiel hierfür wird im folgenden Codefragment für das Festlegen der **CommandType** -Eigenschaft eines **Command** -Objekts gezeigt:

```vb 
 
Cmd1.putCommandType( msado15.CommandTypeEnum.adCmdStoredProc ); 
```

Alternately, you could inherit from the enumerated type wrapper generated by the Java Type Library Wizard. If so, you could remove "msado15." from the syntax. However, your class would need to inherit from each Java object and enumerated type interface that it references to completely eliminate the need to reference msado15.\* in front of all ADO objects and enumerated values.

Weiteren Beispielcode finden Sie unter [ADO-Java-Klassenwrapper](ado-java-class-wrappers.md).

**So führen Sie den Java-typBibliotheks-Assistenten in Visual J++, Version 1. * x aus***

1.  Wählen Sie im Menü **Extras** die Option **Java-Typbibliotheks-Assistent** aus.

2.  Select "Microsoft ActiveX Data Objects Library" and click **OK**. Dadurch werden nun Dateien \\im Trustlib-Verzeichnis für ADO (standardmäßig bei c:\\WinNT\\Java\\Trustlib\\MsADO15) generiert. If you used the Microsoft SDK for Java to already generate classes for ADO, they will be replaced with those from the Java Type Library Wizard.

3.  To use these files, open your project in Visual J++. From the **Project** menu, choose **Add To Project**. Wählen Sie **Dateien**aus, und fügen Sie alle. JAVA-Dateien, die \\im Trustlib-Verzeichnis (standardmäßig in\\c\\:\\WinNT\\Java Trustlib MsADO15) für Ihr Projekt generiert werden.

