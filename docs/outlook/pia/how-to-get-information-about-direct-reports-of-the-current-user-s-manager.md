---
title: Abrufen von Informationen zu direkten Mitarbeitern des Vorgesetzten des aktuellen Benutzers
TOCTitle: Get information about direct reports of the current user's manager
ms:assetid: 768bf573-1b10-4776-8947-a7f8dc3ebde0
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184617(v=office.15)
ms:contentKeyID: 55119842
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 6237b3455eea449460133fb52a79ef87bcaebc1f
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25406701"
---
# <a name="get-information-about-direct-reports-of-the-current-users-manager"></a><span data-ttu-id="e0947-102">Abrufen von Informationen zu direkten Mitarbeitern des Vorgesetzten des aktuellen Benutzers</span><span class="sxs-lookup"><span data-stu-id="e0947-102">Get information about direct reports of the current user's manager</span></span>

<span data-ttu-id="e0947-103">In diesem Beispiel werden ggf. die Mitarbeiter des Managers des aktuellen Benutzers abgerufen und Informationen zu jedem Mitarbeiter des Managers angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e0947-103">This example gets the direct reports of the current user’s manager, if any, and then displays information about each of the manager’s direct reports.</span></span>

## <a name="example"></a><span data-ttu-id="e0947-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e0947-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="e0947-105">Das folgende Codebeispiel ist ein Auszug aus [Programming Applications für Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493).</span><span class="sxs-lookup"><span data-stu-id="e0947-105">The following code example is an excerpt from  [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)  , from Microsoft Press (ISBN 9780735622494, copyright Microsoft Press 2007, all rights reserved).</span></span>

<span data-ttu-id="e0947-106">Im folgenden Beispiel ruft die GetManagerDirectReports-Prozedur die [GetExchangeUserManager()](https://msdn.microsoft.com/library/bb646656\(v=office.15\))-Methode auf, um den Manager des Benutzers abzurufen, der durch ein [ExchangeUser](https://msdn.microsoft.com/library/bb609574\(v=office.15\))-Objekt dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="e0947-106">In the following example, the   procedure calls the GetExchangeUserManager() method to get the user's manager, represented by an ExchangeUser object.</span></span> <span data-ttu-id="e0947-107">Wenn der aktuelle Benutzer über einen Vorgesetzten verfügt, wird [GetDirectReports()](https://msdn.microsoft.com/library/bb647204\(v=office.15\)) aufgerufen, um eine [AddressEntries](https://msdn.microsoft.com/library/bb647650\(v=office.15\))-Auflistung zurückzugeben, die die Adresseinträge für alle Mitarbeiter des Managers des Benutzers darstellt.</span><span class="sxs-lookup"><span data-stu-id="e0947-107">If the current user has a manager, [GetDirectReports()](https://msdn.microsoft.com/library/bb647204\(v=office.15\)) is called to return an [AddressEntries](https://msdn.microsoft.com/library/bb647650\(v=office.15\)) collection that represents the address entries for all the direct reports of user's manager.</span></span> <span data-ttu-id="e0947-108">Wenn der Vorgesetzte keine direkten Mitarbeiter hat, gibt **GetDirectReports** eine **AddressEntries**-Auflistung mit der Anzahl 0 zurück.</span><span class="sxs-lookup"><span data-stu-id="e0947-108">If the manager has no direct reports, **GetDirectReports** returns an **AddressEntries** collection that has a count of zero.</span></span> <span data-ttu-id="e0947-109">Nachdem die Mitarbeiter eines Managers abgerufen wurden, schreibt GetManagerDirectReports Informationen zu jedem Mitarbeiter des Managers in die Ablaufverfolgungslistener der [Listeners](https://msdn.microsoft.com/library/system.diagnostics.debug.listeners.aspx)-Auflistung.</span><span class="sxs-lookup"><span data-stu-id="e0947-109">Once the manager's direct reports are obtained,   writes information about each of the manager's direct reports to the trace listeners of the Listeners collection.</span></span>


> [!NOTE]
> <span data-ttu-id="e0947-110">Der angemeldeten Benutzers muss online sein, damit diese Methode eine **AddressEntries**-Auflistung zurückgibt; andernfalls gibt **GetDirectReports** einen NULL-Verweis zurück.</span><span class="sxs-lookup"><span data-stu-id="e0947-110">The signed-in user must be online for this method to return an **AddressEntries** collection; otherwise, **GetDirectReports** returns a null reference.</span></span> <span data-ttu-id="e0947-111">Bei Produktionscode müssen Sie Tests durchführen, wenn der Benutzer offline sind, indem Sie die [\_NameSpace.ExchangeConnectionMode](https://msdn.microsoft.com/library/bb647638(v=office.15)) -Eigenschaft oder die [\_Account.ExchangeConnectionMode](https://msdn.microsoft.com/library/ff185249(v=office.15))-Eigenschaft für mehrere Exchange-Szenarien verwenden.</span><span class="sxs-lookup"><span data-stu-id="e0947-111">The logged-on user must be online for this method to return an AddressEntries collection; otherwise, GetDirectReports returns a null reference. For production code, you must test for the user being offline by using the _NameSpace.ExchangeConnectionMode property, or the _Account.ExchangeConnectionMode property for multiple Exchange scenarios.</span></span>

<span data-ttu-id="e0947-112">Wenn Sie Visual Studio verwenden, um dieses Codebeispiel zu testen, müssen Sie der Microsoft Outlook 15.0-Objektbibliothekkomponente zuerst einen Verweis hinzufügen und die Outlook-Variable angeben, wenn Sie den **Microsoft.Office.Interop.Outlook**-Namespace importieren.</span><span class="sxs-lookup"><span data-stu-id="e0947-112">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="e0947-113">Die **using**-Anweisung darf im Codebeispiel nicht direkt vor den Funktionen stehen, sondern muss vor der öffentlichen Class-Deklaration hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="e0947-113">The using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="e0947-114">Die folgende Codezeile zeigt, wie Sie den Import und die Zuweisung in C\# vornehmen.</span><span class="sxs-lookup"><span data-stu-id="e0947-114">The following line of code shows how to do the import and assignment in C#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void GetManagerDirectReports()
{
    Outlook.AddressEntry currentUser =
        Application.Session.CurrentUser.AddressEntry;
    if (currentUser.Type == "EX")
    {
        Outlook.ExchangeUser manager =
            currentUser.GetExchangeUser().GetExchangeUserManager();
        if (manager != null)
        {
            Outlook.AddressEntries addrEntries =
                manager.GetDirectReports();
            if (addrEntries != null)
            {
                foreach (Outlook.AddressEntry addrEntry
                    in addrEntries)
                {
                    Outlook.ExchangeUser exchUser =
                        addrEntry.GetExchangeUser();
                    StringBuilder sb = new StringBuilder();
                    sb.AppendLine("Name: "
                        + exchUser.Name);
                    sb.AppendLine("Title: "
                        + exchUser.JobTitle);
                    sb.AppendLine("Department: "
                        + exchUser.Department);
                    sb.AppendLine("Location: "
                        + exchUser.OfficeLocation);
                    Debug.WriteLine(sb.ToString());
                }
            }
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="e0947-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e0947-115">See also</span></span>

- [<span data-ttu-id="e0947-116">Exchange-Benutzer</span><span class="sxs-lookup"><span data-stu-id="e0947-116">Exchange Users</span></span>](exchange-users.md)
