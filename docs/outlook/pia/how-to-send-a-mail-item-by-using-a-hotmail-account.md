---
title: Senden eines E-Mail-Elements mithilfe eines Hotmail-Kontos
TOCTitle: Send a mail item by using a Hotmail account
ms:assetid: f25853a7-67c0-46a3-a298-5cdf72ebc53f
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184652(v=office.15)
ms:contentKeyID: 55119797
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: f95d5202f17c21e1c4be4545687f2eee96a00da3
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25407303"
---
# <a name="send-a-mail-item-by-using-a-hotmail-account"></a><span data-ttu-id="3937b-102">Senden eines E-Mail-Elements mithilfe eines Hotmail-Kontos</span><span class="sxs-lookup"><span data-stu-id="3937b-102">Send a mail item by using a Hotmail account</span></span>

<span data-ttu-id="3937b-103">In diesem Beispiel wird die [SendUsingAccount](https://msdn.microsoft.com/library/bb623679\(v=office.15\))-Eigenschaft verwendet, um ein E-Mail-Element mithilfe eines Windows Live Hotmail-Kontos zu senden.</span><span class="sxs-lookup"><span data-stu-id="3937b-103">This example uses the [SendUsingAccount](https://msdn.microsoft.com/library/bb623679\(v=office.15\)) property to send a mail item by using a Windows Live Hotmail account.</span></span>

## <a name="example"></a><span data-ttu-id="3937b-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3937b-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="3937b-105">Das folgende Codebeispiel ist ein Auszug aus [Programming Applications für Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493).</span><span class="sxs-lookup"><span data-stu-id="3937b-105">The following code example is an excerpt from  [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)  , from Microsoft Press (ISBN 9780735622494, copyright Microsoft Press 2007, all rights reserved).</span></span>

<span data-ttu-id="3937b-106">In einem Profil sind ein oder mehrere E-Mail-Konten definiert, die jeweils einem Server eines bestimmten Typs, wie Microsoft Exchange Server oder POP3 (Post Office Protocol 3), zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="3937b-106">A profile defines one or more e-mail accounts, and each e-mail account is associated with a server of a specific type, such as Microsoft Exchange Server or Post Office Protocol 3 (POP3).</span></span> <span data-ttu-id="3937b-107">Da ein Profil mehrere Konten enthalten kann, müssen Sie angeben, mit welchem E-Mail-Konto Sie das Element senden möchten, und dann ein [Account](https://msdn.microsoft.com/library/bb645103\(v=office.15\)) -Objekt zu seiner Darstellung abrufen.</span><span class="sxs-lookup"><span data-stu-id="3937b-107">Because you may have multiple accounts in your profile, you must specify which e-mail account you want to use to send the item, and then obtain an [Account](https://msdn.microsoft.com/library/bb645103\(v=office.15\)) object to represent it.</span></span>

<span data-ttu-id="3937b-108">Im nachstehenden Codebeispiel wird eine Nachricht mit einer angefügten Reiseroute erstellt und dann mit einem Windows Live Hotmail-Konto gesendet.</span><span class="sxs-lookup"><span data-stu-id="3937b-108">In the following code example, a message is created with an attached itinerary and then sent by using a Windows Live Hotmail account.</span></span> <span data-ttu-id="3937b-109">Das Hotmail-E-Mail-Konto wird als **Account**-Objekt im Profil des Benutzers verwendet.</span><span class="sxs-lookup"><span data-stu-id="3937b-109">The Hotmail e-mail account is used as the **Account** object in the user's profile.</span></span> <span data-ttu-id="3937b-110">Das Codebeispiel legt dann die SendUsingAccount-Eigenschaft auf dieses Konto fest und ruft die [Send()](https://msdn.microsoft.com/library/bb644139\(v=office.15\))-Methode aus dem [MailItem](https://msdn.microsoft.com/library/bb643865\(v=office.15\))-Objekt auf.</span><span class="sxs-lookup"><span data-stu-id="3937b-110">The code example then sets the SendUsingAccount property to that Account and calls the [Send()](https://msdn.microsoft.com/library/bb644139\(v=office.15\)) method from the [MailItem](https://msdn.microsoft.com/library/bb643865\(v=office.15\)) object.</span></span>

<span data-ttu-id="3937b-111">Wenn Sie Visual Studio verwenden, um dieses Codebeispiel zu testen, müssen Sie der Microsoft Outlook 15.0-Objektbibliothekkomponente zuerst einen Verweis hinzufügen und die Outlook-Variable angeben, wenn Sie den **Microsoft.Office.Interop.Outlook**-Namespace importieren.</span><span class="sxs-lookup"><span data-stu-id="3937b-111">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="3937b-112">Die **using**-Anweisung darf im Codebeispiel nicht direkt vor den Funktionen stehen, sondern muss vor der öffentlichen Class-Deklaration hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="3937b-112">The using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="3937b-113">Die folgende Codezeile zeigt, wie Sie den Import und die Zuweisung in C\# vornehmen.</span><span class="sxs-lookup"><span data-stu-id="3937b-113">The following line of code shows how to do the import and assignment in C#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```

```csharp
private void SendUsingAccountExample()
{
    Outlook.MailItem mail = Application.CreateItem(
        Outlook.OlItemType.olMailItem) as Outlook.MailItem;
    mail.Subject = "Our itinerary";
    mail.Attachments.Add(@"c:\travel\itinerary.doc",
        Outlook.OlAttachmentType.olByValue,
        Type.Missing, Type.Missing);
    Outlook.Account account =
        Application.Session.Accounts["Hotmail"];
    mail.SendUsingAccount = account;
    mail.Send();
}
```

## <a name="see-also"></a><span data-ttu-id="3937b-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3937b-114">See also</span></span>

- [<span data-ttu-id="3937b-115">Konten</span><span class="sxs-lookup"><span data-stu-id="3937b-115">Accounts</span></span>](accounts.md)
