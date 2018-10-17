---
title: Error.Source Property (DAO)
TOCTitle: Source Property
ms:assetid: 3c101cac-278e-025e-55a4-8a9d1ee7db3c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff192677(v=office.15)
ms:contentKeyID: 48544302
ms.date: 09/18/2015
mtps_version: v=office.15
f1_keywords:
- dao360.chm1053360
f1_categories:
- Office.Version=v15
ms.openlocfilehash: b9aafe1b16b3d989a81ff21f97bd4b6d10f79de3
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2018
ms.locfileid: "25474914"
---
# <a name="errorsource-property-dao"></a>Error.Source Property (DAO)


**Betrifft**: Access 2013 | Office 2013


Gibt den Namen des Objekts zurück, das den Fehler ursprünglich erzeugt hat.

## <a name="syntax"></a>Syntax

*Ausdruck* . Quelle

*Ausdruck* Eine Variable, die ein **Error** -Objekt darstellt.

## <a name="remarks"></a>Bemerkungen

Der Wert der **Source**-Eigenschaft ist gewöhnlich der Klassenname oder die Programm-ID des Objekts. Mit der **Source**-Eigenschaft können Sie dem Benutzer Informationen darüber liefern, ob der Code Fehler behandeln kann, die von einem Objekt in einer anderen Anwendung erzeugt wurden.

Angenommen, wenn Sie auf Microsoft Excel zugreifen und ein "Division durch Null"-Fehler generiert, Microsoft Excel legt **Error.Number** auf die Microsoft Excel-Code für diesen Fehler und die **Source** -Eigenschaft auf Excel.Application. Beachten Sie, dass, wenn der Fehler in ein anderes Objekt von Microsoft Excel aufgerufen, generiert wird, wird Microsoft Excel den Fehler abfängt und **Error.Number** weiterhin auf die Microsoft Excel-Code festgelegt. Die anderen **Fehler** Objekteigenschaften (einschließlich **Quelle**) behalten die Werte als Satz durch das Objekt jedoch, die den Fehler verursacht hat. Die **Source** -Eigenschaft enthält immer den Namen des Objekts, das den Fehler ursprünglich erzeugt hat.

Basierend auf der gesamten Fehlerdokumentation können Sie Code schreiben, der den Fehler angemessen behandelt. Wenn Ihre Fehlerbehandlung fehlschlägt, können Sie den Fehler mithilfe der Informationen des **[Error](error-object-dao.md)** -Objekts für den Benutzer beschreiben. Hierzu können Sie die **Source**-Eigenschaft und die anderen **Error**-Eigenschaften verwenden, um den Benutzer darüber zu informieren, welches Objekt den Fehler ursprünglich verursacht hat, eine Fehlerbeschreibung zu liefern usw.


> [!NOTE]
> <P>Das <STRONG>On Error Resume Next</STRONG>-Konstrukt ist möglicherweise <STRONG>On Error GoTo</STRONG> vorzuziehen, wenn Fehler behandelt werden, die während des Zugriffs auf andere Objekte erzeugt wurden. Wenn das <STRONG>Error</STRONG>-Objekt nach jeder Interaktion mit einem Objekt überprüft wird, kann jeder Zweifel darüber aus dem Weg geräumt werden, auf welches Objekt der Code beim Auftreten des Fehlers zugegriffen hat. Auf diese Weise wissen Sie, welches Objekt den Fehlercode in <STRONG>Error.Number</STRONG> geschrieben und welches Objekt den Fehler ursprünglich erzeugt hat (<STRONG>Error.Source</STRONG>).</P>



## <a name="example"></a>Beispiel

Dieses Beispiel löst einen Fehler aus, fängt ihn auf und zeigt die Eigenschaften **Description**, **Number**, **Source**, **HelpContext** und **HelpFile** des resultierenden **Error**-Objekts an.

```vb
    Sub DescriptionX() 
     
     Dim dbsTest As Database 
     
     On Error GoTo ErrorHandler 
     
     ' Intentionally trigger an error. 
     Set dbsTest = OpenDatabase("NoDatabase") 
     
     Exit Sub 
     
    ErrorHandler: 
     Dim strError As String 
     Dim errLoop As Error 
     
     ' Enumerate Errors collection and display properties of 
     ' each Error object. 
     For Each errLoop In Errors 
     With errLoop 
     strError = _ 
     "Error #" & .Number & vbCr 
     strError = strError & _ 
     " " & .Description & vbCr 
     strError = strError & _ 
     " (Source: " & .Source & ")" & vbCr 
     strError = strError & _ 
     "Press F1 to see topic " & .HelpContext & vbCr 
     strError = strError & _ 
     " in the file " & .HelpFile & "." 
     End With 
     MsgBox strError 
     Next 
     
     Resume Next 
     
    End Sub
```