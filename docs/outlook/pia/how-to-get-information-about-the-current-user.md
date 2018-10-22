---
title: Abrufen von Informationen über den aktuellen Benutzer
TOCTitle: Get information about the current user
ms:assetid: 3802523a-3ccf-4cca-a348-abe2645a0d9c
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184601(v=office.15)
ms:contentKeyID: 55119840
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 7ac10c01d205f4f4590183bcef8006e8f1344cbd
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25406974"
---
# <a name="get-information-about-the-current-user"></a><span data-ttu-id="61ca1-102">Abrufen von Informationen über den aktuellen Benutzer</span><span class="sxs-lookup"><span data-stu-id="61ca1-102">Get information about the current user</span></span>

<span data-ttu-id="61ca1-103">Dieses Beispiel zeigt, wie Sie Informationen des aktuellen Benutzers, z. B. Name, berufliche Position und Telefonnummer, abrufen.</span><span class="sxs-lookup"><span data-stu-id="61ca1-103">This example shows how to get the current user’s information, such as name, job title, and telephone number.</span></span>

## <a name="example"></a><span data-ttu-id="61ca1-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="61ca1-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="61ca1-105">Das folgende Codebeispiel ist ein Auszug aus [Programming Applications für Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493).</span><span class="sxs-lookup"><span data-stu-id="61ca1-105">The following code example is an excerpt from  [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)  , from Microsoft Press (ISBN 9780735622494, copyright Microsoft Press 2007, all rights reserved).</span></span>

<span data-ttu-id="61ca1-106">Um ein [ExchangeUser](https://msdn.microsoft.com/library/bb609574\(v=office.15\))-Objekt aus einem [AddressEntry](https://msdn.microsoft.com/library/bb609728\(v=office.15\))-Objekt abzurufen, rufen Sie die [GetExchangeUser()](https://msdn.microsoft.com/library/bb611808\(v=office.15\))-Methode im **AddressEntry**-Objekt auf.</span><span class="sxs-lookup"><span data-stu-id="61ca1-106">To obtain an [ExchangeUser](https://msdn.microsoft.com/library/bb609574\(v=office.15\)) object from an [AddressEntry](https://msdn.microsoft.com/library/bb609728\(v=office.15\)) object, call the [GetExchangeUser()](https://msdn.microsoft.com/library/bb611808\(v=office.15\)) method on the **AddressEntry** object.</span></span> <span data-ttu-id="61ca1-107">Im folgenden Verfahren ruft GetCurrentUserInfo die [AddressEntry](https://msdn.microsoft.com/library/bb644359\(v=office.15\))-Eigenschaft für das [Recipient](https://msdn.microsoft.com/library/bb624370\(v=office.15\))-Objekt mithilfe der [CurrentUser](https://msdn.microsoft.com/library/bb622574\(v=office.15\))-Eigenschaft ab.</span><span class="sxs-lookup"><span data-stu-id="61ca1-107">In the following procedure,   gets the AddressEntry property for the Recipient object by using the CurrentUser property.</span></span> <span data-ttu-id="61ca1-108">Wenn das **AddressEntry**-Objekt dem Benutzer eines Exchange-Postfachs entspricht, ruft GetCurrentUserInfo die **GetExchangeUser**-Methode auf, und es wird ein **ExchangeUser**-Objekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="61ca1-108">If the AddressEntry object represents an Exchange mailbox user,   calls the GetExchangeUser method and an ExchangeUser object is returned.</span></span> <span data-ttu-id="61ca1-109">Die Eigenschaften [Name](https://msdn.microsoft.com/library/bb622941\(v=office.15\)), [PrimarySmtpAddress](https://msdn.microsoft.com/library/bb645506\(v=office.15\)), [JobTitle](https://msdn.microsoft.com/library/bb645451\(v=office.15\)), [Department](https://msdn.microsoft.com/library/bb623789\(v=office.15\)), [OfficeLocation](https://msdn.microsoft.com/library/bb611429\(v=office.15\)), [BusinessTelephoneNumber](https://msdn.microsoft.com/library/bb612294\(v=office.15\)) und [MobileTelephoneNumber](https://msdn.microsoft.com/library/bb609292\(v=office.15\)) werden in den Ablaufverfolgungslistenern der [Listeners](https://msdn.microsoft.com/library/system.diagnostics.debug.listeners.aspx)-Auflistung aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="61ca1-109">The [Name](https://msdn.microsoft.com/library/bb622941\(v=office.15\)) , [PrimarySmtpAddress](https://msdn.microsoft.com/library/bb645506\(v=office.15\)) , [JobTitle](https://msdn.microsoft.com/library/bb645451\(v=office.15\)) , [Department](https://msdn.microsoft.com/library/bb623789\(v=office.15\)) , [OfficeLocation](https://msdn.microsoft.com/library/bb611429\(v=office.15\)) , [BusinessTelephoneNumber](https://msdn.microsoft.com/library/bb612294\(v=office.15\)) , and [MobileTelephoneNumber](https://msdn.microsoft.com/library/bb609292\(v=office.15\)) properties are written to the trace listeners of the [Listeners](https://msdn.microsoft.com/library/system.diagnostics.debug.listeners.aspx) collection.</span></span>

<span data-ttu-id="61ca1-110">Wenn Sie Visual Studio verwenden, um dieses Codebeispiel zu testen, müssen Sie der Microsoft Outlook 15.0-Objektbibliothekkomponente zuerst einen Verweis hinzufügen und die Outlook-Variable angeben, wenn Sie den **Microsoft.Office.Interop.Outlook**-Namespace importieren.</span><span class="sxs-lookup"><span data-stu-id="61ca1-110">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="61ca1-111">Die **using**-Anweisung darf im Codebeispiel nicht direkt vor den Funktionen stehen, sondern muss vor der öffentlichen Class-Deklaration hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="61ca1-111">The using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="61ca1-112">Die folgende Codezeile zeigt, wie Sie den Import und die Zuweisung in C\# vornehmen.</span><span class="sxs-lookup"><span data-stu-id="61ca1-112">The following line of code shows how to do the import and assignment in C#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```csharp
private void GetCurrentUserInfo()
{
    Outlook.AddressEntry addrEntry =
        Application.Session.CurrentUser.AddressEntry;
    if (addrEntry.Type == "EX")
    {
        Outlook.ExchangeUser currentUser =
            Application.Session.CurrentUser.
            AddressEntry.GetExchangeUser();
        if (currentUser != null)
        {
            StringBuilder sb = new StringBuilder();
            sb.AppendLine("Name: "
                + currentUser.Name);
            sb.AppendLine("STMP address: "
                + currentUser.PrimarySmtpAddress);
            sb.AppendLine("Title: "
                + currentUser.JobTitle);
            sb.AppendLine("Department: "
                + currentUser.Department);
            sb.AppendLine("Location: "
                + currentUser.OfficeLocation);
            sb.AppendLine("Business phone: "
                + currentUser.BusinessTelephoneNumber);
            sb.AppendLine("Mobile phone: "
                + currentUser.MobileTelephoneNumber);
            Debug.WriteLine(sb.ToString());
        }
    }
}
```

## <a name="see-also"></a><span data-ttu-id="61ca1-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="61ca1-113">See also</span></span>

- [<span data-ttu-id="61ca1-114">Exchange-Benutzer</span><span class="sxs-lookup"><span data-stu-id="61ca1-114">Exchange Users</span></span>](exchange-users.md)
