---
title: Anzeigen der an einen Empfänger gesendeten Aufgabeanfragenelemente
TOCTitle: Display the task request items sent to a recipient
ms:assetid: 167c3d52-67b5-467c-a7b6-e8cc96002b63
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184591(v=office.15)
ms:contentKeyID: 55119930
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: f26e8d1402b75272e79c6244b7bd2875d783c1f1
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25406638"
---
# <a name="display-the-task-request-items-sent-to-a-recipient"></a><span data-ttu-id="259f6-102">Anzeigen der an einen Empfänger gesendeten Aufgabeanfragenelemente</span><span class="sxs-lookup"><span data-stu-id="259f6-102">Display the task request items sent to a recipient</span></span>

<span data-ttu-id="259f6-103">In diesem Beispiel wird veranschaulicht, wie alle Elemente der Aufgabenanforderung angezeigt werden, die sich im Postfach eines Empfängers befinden.</span><span class="sxs-lookup"><span data-stu-id="259f6-103">This example shows how to display all of the task request items that are in a recipient's Inbox.</span></span>

## <a name="example"></a><span data-ttu-id="259f6-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="259f6-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="259f6-105">Das folgende Codebeispiel ist ein Auszug aus [Programming Applications für Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493).</span><span class="sxs-lookup"><span data-stu-id="259f6-105">The following code example is an excerpt from  [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)  , from Microsoft Press (ISBN 9780735622494, copyright Microsoft Press 2007, all rights reserved).</span></span>

<span data-ttu-id="259f6-106">Ein [TaskRequestItem](https://msdn.microsoft.com/library/bb610737\(v=office.15\))-Objekt stellt eine Anforderung dar, eine Aufgabe einem anderen Benutzer zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="259f6-106">A [TaskRequestItem](https://msdn.microsoft.com/library/bb610737\(v=office.15\)) object represents a request to assign a task to another user.</span></span> <span data-ttu-id="259f6-107">Das **TaskRequestItem**-Objekt wird erstellt, wenn das Element im Posteingang des Empfängers eingeht.</span><span class="sxs-lookup"><span data-stu-id="259f6-107">The **TaskRequestItem** is created when the item is received in the recipient's Inbox.</span></span> <span data-ttu-id="259f6-108">Im nachstehenden Codebeispiel filtert ShowTaskRequests den Posteingang eines Empfängers, erstellt ein [Table](https://msdn.microsoft.com/library/bb652856\(v=office.15\))-Objekt und fügt eine Zeile für jeden Eintrag ein, für den Wert der[MessageClass](https://msdn.microsoft.com/library/bb610592\(v=office.15\))-Eigenschaft gleich **IPM.TaskRequest** ist.</span><span class="sxs-lookup"><span data-stu-id="259f6-108">In the following code example, ShowTaskRequests filters through a recipient’s Inbox, creates a [Table](https://msdn.microsoft.com/library/bb652856\(v=office.15\)) object, and inserts a row for each item for which the value of the [MessageClass](https://msdn.microsoft.com/library/bb610592\(v=office.15\)) property equals **IPM.TaskRequest**.</span></span> <span data-ttu-id="259f6-109">Der Betreff jeder Aufgabe im Posteingangsordner des Empfängers wird dann in die Ablaufverfolgungslistener der [Listener](https://msdn.microsoft.com/library/system.diagnostics.debug.listeners.aspx)-Auflistung geschrieben.</span><span class="sxs-lookup"><span data-stu-id="259f6-109">The subject of each task in the recipient’s Inbox folder is then written to the trace listeners of the [Listeners](https://msdn.microsoft.com/library/system.diagnostics.debug.listeners.aspx) collection.</span></span>

<span data-ttu-id="259f6-110">Wenn Sie Visual Studio verwenden, um dieses Codebeispiel zu testen, müssen Sie der Microsoft Outlook 15.0-Objektbibliothekkomponente zuerst einen Verweis hinzufügen und die Outlook-Variable angeben, wenn Sie den **Microsoft.Office.Interop.Outlook**-Namespace importieren.</span><span class="sxs-lookup"><span data-stu-id="259f6-110">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="259f6-111">Die **using**-Anweisung darf im Codebeispiel nicht direkt vor den Funktionen stehen, sondern muss vor der öffentlichen Class-Deklaration hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="259f6-111">The using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="259f6-112">Die folgende Codezeile zeigt, wie Sie den Import und die Zuweisung in C\# vornehmen.</span><span class="sxs-lookup"><span data-stu-id="259f6-112">The following line of code shows how to do the import and assignment in C#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void ShowTaskRequests()
{
    string filter = "[MessageClass] = 'IPM.TaskRequest'";
    Outlook.Table table =
        Application.Session.GetDefaultFolder
        (Outlook.OlDefaultFolders.olFolderInbox).GetTable
        (filter, Outlook.OlTableContents.olUserItems);
    while (!table.EndOfTable)
    {
        Outlook.Row nextRow = table.GetNextRow();
        Debug.WriteLine(nextRow["Subject"]);
    }
}
```

## <a name="see-also"></a><span data-ttu-id="259f6-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="259f6-113">See also</span></span>

- [<span data-ttu-id="259f6-114">Aufgaben</span><span class="sxs-lookup"><span data-stu-id="259f6-114">Tasks</span></span>](tasks.md)
