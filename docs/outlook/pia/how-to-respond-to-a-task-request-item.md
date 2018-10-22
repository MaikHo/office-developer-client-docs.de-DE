---
title: Antworten auf ein Aufgabenanfragenelement
TOCTitle: Respond to a task request item
ms:assetid: 573c98ef-4d15-4fd1-bccd-25a22c9a63f0
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184608(v=office.15)
ms:contentKeyID: 55119896
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: ca85ee701b26f5ae896f9f4d012f93fea42930ec
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25406729"
---
# <a name="respond-to-a-task-request-item"></a><span data-ttu-id="9c48a-102">Antworten auf ein Aufgabenanfragenelement</span><span class="sxs-lookup"><span data-stu-id="9c48a-102">Respond to a task request item</span></span>

<span data-ttu-id="9c48a-103">In diesem Beispiel wird veranschaulicht, wie ein Aufgabenanfragenelement abgerufen und darauf geantwortet wird.</span><span class="sxs-lookup"><span data-stu-id="9c48a-103">This example shows how to get and respond to a task request item.</span></span>

## <a name="example"></a><span data-ttu-id="9c48a-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9c48a-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="9c48a-105">Das folgende Codebeispiel ist ein Auszug aus [Programming Applications für Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493).</span><span class="sxs-lookup"><span data-stu-id="9c48a-105">The following code example is an excerpt from  [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)  , from Microsoft Press (ISBN 9780735622494, copyright Microsoft Press 2007, all rights reserved).</span></span>

<span data-ttu-id="9c48a-106">Im folgenden Codebeispiel verwendet AcceptTaskRequest die [GetAssociatedTask(Boolean)](https://msdn.microsoft.com/library/bb645779\(v=office.15\))-Methode des [TaskRequestItem](https://msdn.microsoft.com/library/bb610737\(v=office.15\))-Objekts zum Abrufen des [TaskItem](https://msdn.microsoft.com/library/bb624227\(v=office.15\))-Objekts.</span><span class="sxs-lookup"><span data-stu-id="9c48a-106">In the following code example,   uses the GetAssociatedTask(Boolean) method of the TaskRequestItem object to get the TaskItem object.</span></span> <span data-ttu-id="9c48a-107">Anschließend ruft das Beispiel die [Respond(OlTaskResponse, Object, Object)](https://msdn.microsoft.com/library/bb644188\(v=office.15\))-Methode, wobei der Parameter auf [olTaskAccept](https://msdn.microsoft.com/library/bb624484\(v=office.15\)) festgelegt ist, um die Aufgabenanfrage anzunehmen.</span><span class="sxs-lookup"><span data-stu-id="9c48a-107">The example then calls the [Respond(OlTaskResponse, Object, Object)](https://msdn.microsoft.com/library/bb644188\(v=office.15\)) method with the parameter set to [olTaskAccept](https://msdn.microsoft.com/library/bb624484\(v=office.15\)) to accept the task request.</span></span>

<span data-ttu-id="9c48a-108">Wenn Sie Visual Studio verwenden, um dieses Codebeispiel zu testen, müssen Sie der Microsoft Outlook 15.0-Objektbibliothekkomponente zuerst einen Verweis hinzufügen und die Outlook-Variable angeben, wenn Sie den **Microsoft.Office.Interop.Outlook**-Namespace importieren.</span><span class="sxs-lookup"><span data-stu-id="9c48a-108">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="9c48a-109">Die **using**-Anweisung darf im Codebeispiel nicht direkt vor den Funktionen stehen, sondern muss vor der öffentlichen Class-Deklaration hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="9c48a-109">The using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="9c48a-110">Die folgende Codezeile zeigt, wie Sie den Import und die Zuweisung in C\# vornehmen.</span><span class="sxs-lookup"><span data-stu-id="9c48a-110">The following line of code shows how to do the import and assignment in C#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void AcceptTaskRequest()
{
    string filter = "[MessageClass] = 'IPM.TaskRequest'";
    Outlook.Items items =
        Application.Session.GetDefaultFolder
        (Outlook.OlDefaultFolders.olFolderInbox).
        Items.Restrict(filter);
    if (items.Count > 0)
    {
        Outlook.TaskRequestItem taskRequest =
            (Outlook.TaskRequestItem)items[1];
        Outlook.TaskItem task =
            taskRequest.GetAssociatedTask(false);
        Outlook.TaskItem taskResponse = task.Respond(
            Outlook.OlTaskResponse.olTaskAccept, true, false);
        taskResponse.Send();
    }
}
```

## <a name="see-also"></a><span data-ttu-id="9c48a-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9c48a-111">See also</span></span>

- [<span data-ttu-id="9c48a-112">Aufgaben</span><span class="sxs-lookup"><span data-stu-id="9c48a-112">Tasks</span></span>](tasks.md)
