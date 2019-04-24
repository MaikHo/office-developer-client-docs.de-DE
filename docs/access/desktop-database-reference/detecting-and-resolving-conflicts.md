---
title: Erkennen und Lösen von Konflikten
TOCTitle: Detecting and resolving conflicts
ms:assetid: 8299745b-e595-21d5-26c1-a078d00a1c0c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249566(v=office.15)
ms:contentKeyID: 48545983
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: ddd7566be2581fe449872eb576bf7f11e5a806fb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32293924"
---
# <a name="detecting-and-resolving-conflicts"></a><span data-ttu-id="03507-102">Erkennen und Lösen von Konflikten</span><span class="sxs-lookup"><span data-stu-id="03507-102">Detecting and resolving conflicts</span></span>

<span data-ttu-id="03507-103">**Gilt für**: Access 2013, Office 2013</span><span class="sxs-lookup"><span data-stu-id="03507-103">**Applies to**: Access 2013, Office 2013</span></span>

## <a name="detecting-and-resolving-conflicts"></a><span data-ttu-id="03507-104">Erkennen und Lösen von Konflikten</span><span class="sxs-lookup"><span data-stu-id="03507-104">Detecting and Resolving Conflicts</span></span>

<span data-ttu-id="03507-p101">Wenn Sie das **Recordset** -Objekt im sofortigen Aktualisierungsmodus verwenden, ist die Wahrscheinlichkeit von Parallelitätsproblemen wesentlich geringer. Wenn die Anwendung andererseits den Batchaktualisierungsmodus verwendet, besteht eine relativ hohe Wahrscheinlichkeit, dass ein Benutzer einen Datensatz ändert, bevor Änderungen eines anderen Benutzers, der denselben Datensatz bearbeitet, gespeichert werden. In diesem Fall sollte der Konflikt von der Anwendung problemlos behoben werden. Möglicherweise möchten Sie, dass die letzte Person, die eine Aktualisierung an den Server sendet, "gewinnt". Oder Sie möchten, dass der letzte Benutzer entscheidet, welche Aktualisierung Vorrang haben soll, indem Sie ihm die Wahl zwischen den miteinander in Konflikt stehenden Werten lassen.</span><span class="sxs-lookup"><span data-stu-id="03507-p101">If you are dealing with your **Recordset** in immediate mode, there is much less chance for concurrency problems to arise. On the other hand, if your application uses batch mode updating, there may be a good chance that one user will change a record before changes made by another user editing the same record are saved. In such a case, you will want your application to gracefully handle the conflict. It may be your wish that the last person to send an update to the server "wins." Or you may want to let the most recent user to decide which update should take precedence by providing him with a choice between the two conflicting values.</span></span>

<span data-ttu-id="03507-p102">In jedem Fall stellt ADO die Eigenschaften **UnderlyingValue** und **OriginalValue** des **Field** -Objekts für diese Art von Konflikten bereit. Verwenden Sie diese Eigenschaften in Kombination mit der **Resync** -Methode und der **Filter** -Eigenschaft des **Recordset** -Objekts.</span><span class="sxs-lookup"><span data-stu-id="03507-p102">Whatever the case, ADO provides the **UnderlyingValue** and **OriginalValue** properties of the **Field** object in order to handle these types of conflicts. Use these properties in combination with the **Resync** method and **Filter** property of the **Recordset**.</span></span>

## <a name="detecting-errors"></a><span data-ttu-id="03507-112">Erkennen von Fehlern</span><span class="sxs-lookup"><span data-stu-id="03507-112">Detecting Errors</span></span>

<span data-ttu-id="03507-p103">Wenn ADO während einer Batchaktualisierung einen Konflikt findet, wird der **Errors**-Auflistung eine Warnung hinzugefügt. Deshalb sollten Sie unmittelbar nach dem Aufrufen von **BatchUpdate** stets auf Fehler überprüfen. Falls Sie Fehler finden, sollten Sie testen, ob ein Konflikt vorliegt. Im ersten Schritt sollten Sie die **Filter**-Eigenschaft im **Recordset**-Objekt auf **adFilterConflictingRecords** festlegen (die **Filter**-Eigenschaft wird im vorherigen Kapitel behandelt). Dadurch werden im **Recordset**-Objekt nur die Datensätze angezeigt, die einen Konflikt verursachen. Falls die **RecordCount**-Eigenschaft nach diesem Schritt gleich Null ist, wissen Sie, dass der Fehler nicht durch einen Konflikt verursacht wurde.</span><span class="sxs-lookup"><span data-stu-id="03507-p103">When ADO encounters a conflict during a batch update, a warning will be placed in the **Errors** collection. Therefore, you should always check for errors immediately after calling **BatchUpdate**, and if you find them, begin testing the assumption that you have encountered a conflict. The first step is to set the **Filter** property on the **Recordset** equal to **adFilterConflictingRecords** (the **Filter** property is discussed in the preceding chapter). This limits the view on your **Recordset** to only those records that are in conflict. If the **RecordCount** property is equal to zero after this step, you know the error was raised by something other than a conflict.</span></span>

<span data-ttu-id="03507-p104">Wenn Sie **BatchUpdate** aufrufen, generieren ADO und der Anbieter SQL-Anweisungen, um Aktualisierungen in der Datenquelle auszuführen. Beachten Sie, dass für bestimmte Datenquellen Einschränkungen bezüglich der Spaltentypen gelten, die in einer WHERE-Klausel verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="03507-p104">When you call **BatchUpdate**, ADO and the provider are generating SQL statements to perform updates on the data source. Remember that certain data sources have limitations on which types of columns can be used in a WHERE clause.</span></span>

<span data-ttu-id="03507-p105">Rufen Sie anschließend die **Resync**-Methode für das **Recordset**-Objekt auf, wobei das Argument *AffectRecords* auf **adAffectGroup** sowie das Argument *ResyncValues* auf **adResyncUnderlyingValues** festgelegt sind. Die **Resync**-Methode aktualisiert die Daten im aktuellen **Recordset**-Objekt in der zugrunde liegenden Datenbank. Mithilfe von **adAffectGroup** stellen Sie sicher, dass nur die Datensätze, die mit der aktuellen Filtereinstellung angezeigt werden (also nur die miteinander in Konflikt stehenden Datensätze), erneut mit der Datenbank synchronisiert werden. Dies könnte bei einem umfangreichen **Recordset**-Objekt einen erheblichen Unterschied hinsichtlich der Leistung ausmachen. Wenn Sie beim Aufrufen von **Resync** das Argument *ResyncValues* auf **adResyncUnderlyingValues** festlegen, stellen Sie sicher, dass die **UnderlyingValue**-Eigenschaft den Wert (der den Konflikt verursacht) aus der Datenbank enthält, dass die **Value**-Eigenschaft den vom Benutzer eingegebenen Wert beibehält und dass die **OriginalValue**-Eigenschaft den ursprünglichen Wert für das Feld enthält (der Wert, der vor dem letzten erfolgreichen **UpdateBatch**-Aufruf vorhanden war). Anschließend können Sie mithilfe dieser Werte den Konflikt programmgesteuert lösen oder den Benutzer auffordern, den gewünschten Wert auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="03507-p105">Next, call the **Resync** method on the **Recordset** with the *AffectRecords* argument set equal to **adAffectGroup** and the *ResyncValues* argument set equal to **adResyncUnderlyingValues**. The **Resync** method refreshes the data in the current **Recordset** object from the underlying database. By using **adAffectGroup**, you are ensuring that only the records visible with the current filter setting, that is, only the conflicting records, are resynchronized with the database. This could make a significant performance difference if you are dealing with a large **Recordset**. By setting the *ResyncValues* argument to **adResyncUnderlyingValues** when calling **Resync**, you ensure that the **UnderlyingValue** property will contain the (conflicting) value from the database, that the **Value** property will maintain the value entered by the user, and that the **OriginalValue** property will hold the original value for the field (the value it had before the last successful **UpdateBatch** call was made). You can then use these values to resolve the conflict programmatically or require the user to choose the value that will be used.</span></span>

<span data-ttu-id="03507-p106">Diese Technik wird im folgenden Codebeispiel dargestellt. In diesem Beispiel wird künstlich ein Konflikt erzeugt, indem mithilfe eines separaten **Recordset** -Objekts ein Wert in der zugrunde liegenden Tabelle geändert wird, bevor **UpdateBatch** aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="03507-p106">This technique is shown in the code example below. The example artificially creates a conflict by using a separate **Recordset** to change a value in the underlying table before **UpdateBatch** is called.</span></span>

```vb 
 
'BeginConflicts 
    On Error GoTo ErrHandler: 
     
    Dim objRs1 As New ADODB.Recordset 
    Dim objRs2 As New ADODB.Recordset 
    Dim strSQL As String 
    Dim strMsg As String 
     
    strSQL = "SELECT * FROM Shippers WHERE ShipperID = 2" 
                  
    'Open Rs and change a value 
    objRs1.CursorLocation = adUseClient 
    objRs1.Open strSQL, strConn, adOpenStatic, adLockBatchOptimistic, adCmdText 
    objRs1("Phone") = "(111) 555-1111" 
     
    'Introduce a conflict at the db... 
    objRs2.Open strSQL, strConn, adOpenKeyset, adLockOptimistic, adCmdText 
    objRs2("Phone") = "(999) 555-9999" 
    objRs2.Update 
    objRs2.Close 
    Set objRs2 = Nothing 
     
    On Error Resume Next 
    objRs1.UpdateBatch 
     
    If objRs1.ActiveConnection.Errors.Count <> 0 Then 
        Dim intConflicts As Integer 
         
        intConflicts = 0 
         
        objRs1.Filter = adFilterConflictingRecords 
         
        intConflicts = objRs1.RecordCount 
         
        'Resync so we can see the UnderlyingValue and offer user a choice. 
        'This sample only displays all three values and resets to original. 
        objRs1.Resync adAffectGroup, adResyncUnderlyingValues 
         
        If intConflicts > 0 Then 
            strMsg = "A conflict occurred with updates for " & intConflicts & _ 
                     " record(s)." & vbCrLf & "The values will be restored" & _ 
                     " to their original values." & vbCrLf & vbCrLf 
                      
            objRs1.MoveFirst 
            While Not objRs1.EOF 
                strMsg = strMsg & "SHIPPER = " & objRs1("CompanyName") & vbCrLf 
                strMsg = strMsg & "Value = " & objRs1("Phone").Value & vbCrLf 
                strMsg = strMsg & "UnderlyingValue = " & _ 
                                   objRs1("Phone").UnderlyingValue & vbCrLf 
                strMsg = strMsg & "OriginalValue = " & _ 
                                   objRs1("Phone").OriginalValue & vbCrLf 
                strMsg = strMsg & vbCrLf & "Original value has been restored." 
                   
                MsgBox strMsg, vbOKOnly, _ 
                      "Conflict " & objRs1.AbsolutePosition & _ 
                      " of " & intConflicts 
                   
                objRs1("Phone").Value = objRs1("Phone").OriginalValue 
                objRs1.MoveNext 
            Wend 
             
            objRs1.UpdateBatch adAffectGroup 
        Else 
            'Other error occurred. Minimal handling in this example. 
             strMsg = "Errors occurred during the update. " & _ 
                        objRs1.ActiveConnection.Errors(0).Number & " " & _ 
                        objRs1.ActiveConnection.Errors(0).Description 
        End If 
         
        On Error GoTo 0 
    End If 
     
    objRs1.MoveFirst 
     
    'Clean up 
    objRs1.Close 
    Set objRs1 = Nothing 
    Exit Sub 
     
ErrHandler: 
    
    If Not objRs1 Is Nothing Then 
        If objRs1.State = adStateOpen Then objRs1.Close 
        Set objRs1 = Nothing 
    End If 
     
    If Not objRs2 Is Nothing Then 
        If objRs2.State = adStateOpen Then objRs2.Close 
        Set objRs2 = Nothing 
    End If 
     
    If Err <> 0 Then 
        MsgBox Err.Source & "-->" & Err.Description, , "Error" 
    End If 
     
'EndConflicts 
```

<span data-ttu-id="03507-128">Mit der **Status** -Eigenschaft des aktuellen **Record** -Objekts oder eines bestimmten **Field** -Objekts können Sie ermitteln, welche Art von Konflikt aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="03507-128">You can use the **Status** property of the current **Record** or of a specific **Field** to determine what kind of a conflict has occurred.</span></span>

<span data-ttu-id="03507-129">Ausführlichere Informationen zur Fehlerbehandlung finden Sie in [Kapitel 6: Fehlerbehandlung](chapter-6-error-handling.md).</span><span class="sxs-lookup"><span data-stu-id="03507-129">For more detailed information on error handling, see [Chapter 6: Error Handling](chapter-6-error-handling.md).</span></span>

