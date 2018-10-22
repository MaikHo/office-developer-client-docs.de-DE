---
title: Senden eines E-Mail-Elements mit einer elektronischen Visitenkarte
TOCTitle: Send a mail item with an electronic business card
ms:assetid: f8aae7f2-85fc-4ed0-9f59-282ede702357
ms:mtpsurl: https://msdn.microsoft.com/library/Bb624312(v=office.15)
ms:contentKeyID: 55119839
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: 22d931832b0b12a7baa2e8d04789db03f89ac0bd
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25406218"
---
# <a name="send-a-mail-item-with-an-electronic-business-card"></a><span data-ttu-id="dda09-102">Senden eines E-Mail-Elements mit einer elektronischen Visitenkarte</span><span class="sxs-lookup"><span data-stu-id="dda09-102">Send a mail item with an electronic business card</span></span>

<span data-ttu-id="dda09-103">In diesem Beispiel wird ein E-Mail-Element erstellt, nach einer elektronischen Visitenkarte gesucht und diese ggf. in das E-Mail-Element eingefügt.</span><span class="sxs-lookup"><span data-stu-id="dda09-103">This example creates a mail item, looks for an Electronic Business Card, and if it finds one, inserts the Electronic Business Card into the mail item.</span></span>

## <a name="example"></a><span data-ttu-id="dda09-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dda09-104">Example</span></span>

<span data-ttu-id="dda09-105">Zum Einfügen einer elektronischen Visitenkarte können Sie [AddBusinessCard](https://msdn.microsoft.com/library/bb647034\(v=office.15\)) für das [MailItem](https://msdn.microsoft.com/library/bb643865\(v=office.15\))-Objekt aufrufen.</span><span class="sxs-lookup"><span data-stu-id="dda09-105">To insert an Electronic Business Card, you can call [AddBusinessCard](https://msdn.microsoft.com/library/bb647034\(v=office.15\)) on the [MailItem](https://msdn.microsoft.com/library/bb643865\(v=office.15\)) object.</span></span> <span data-ttu-id="dda09-106">Diese Methode übernimmt eine Zeichenfolgendarstellung einer E-Mail-Adresse und versucht ein [ContactItem](https://msdn.microsoft.com/library/bb644956\(v=office.15\)) -Objekt mit dieser Adresse im Standardordner für Kontakte zu finden.</span><span class="sxs-lookup"><span data-stu-id="dda09-106">This method takes a string representing an e-mail address and attempts to find a [ContactItem](https://msdn.microsoft.com/library/bb644956\(v=office.15\)) with that address in the default Contacts folder.</span></span> <span data-ttu-id="dda09-107">Ein **ContactItem**-Objekt kann bis zu drei E-Mail-Adressen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="dda09-107">A **ContactItem** can have as many as three e-mail addresses.</span></span> <span data-ttu-id="dda09-108">Wenn der Kontakt gefunden wird, ruft das Beispiel die **AddBusinessCard**-Methode auf, und zeigt dem Benutzer dann die Nachricht an.</span><span class="sxs-lookup"><span data-stu-id="dda09-108">If the contact is found, the example calls the **AddBusinessCard** method, and then displays the message to the user.</span></span>

<span data-ttu-id="dda09-109">Wenn Sie Visual Studio verwenden, um dieses Codebeispiel zu testen, müssen Sie der Microsoft Outlook 15.0-Objektbibliothekkomponente zuerst einen Verweis hinzufügen und die Outlook-Variable angeben, wenn Sie den **Microsoft.Office.Interop.Outlook**-Namespace importieren.</span><span class="sxs-lookup"><span data-stu-id="dda09-109">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="dda09-110">Die Anweisung **Imports** oder **using** darf im Codebeispiel nicht direkt vor den Funktionen stehen, sondern muss vor der öffentlichen Class-Deklaration hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="dda09-110">The Imports or using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="dda09-111">Die folgenden Codezeilen zeigen, wie Sie den Import und die Zuweisung in Visual Basic und C\# vornehmen.</span><span class="sxs-lookup"><span data-stu-id="dda09-111">The following lines of code show how to do the import and assignment in Visual Basic and C#.</span></span>

```vb
Imports Outlook = Microsoft.Office.Interop.Outlook
```


```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```


```vb
Private Sub AddBusinessCard(ByVal eMailAddress As String)
    Dim mail As Outlook.MailItem = CType(Application.CreateItem( _
        Outlook.OlItemType.olMailItem), Outlook.MailItem)
    mail.BodyFormat = Outlook.OlBodyFormat.olFormatHTML
    Dim contact As Outlook.ContactItem = _
        CType(Application.Session.GetDefaultFolder( _
        Outlook.OlDefaultFolders.olFolderContacts).Items.Find( _
        "[Email1Address]='" & eMailAddress & "'" & " OR " & _
        "[Email2Address]='" & eMailAddress & "'" + " OR " & _
        "[Email3Address]='" & eMailAddress & "'") _
        , Outlook.ContactItem)
    If (contact Is Nothing) Then
        Return
    End If
    mail.AddBusinessCard(contact)
    mail.Display(False)
End Sub
```


```csharp
private void AddBusinessCard(string eMailAddress)
{
    Outlook.MailItem mail = Application.CreateItem(
        Outlook.OlItemType.olMailItem) as Outlook.MailItem;
    mail.BodyFormat = Outlook.OlBodyFormat.olFormatHTML;
    Outlook.ContactItem contact = Application.Session.
        GetDefaultFolder(
        Outlook.OlDefaultFolders.olFolderContacts).Items.Find(
        "[Email1Address]='" + eMailAddress + "'" + " OR " +
        "[Email2Address]='" + eMailAddress + "'" + " OR " +
        "[Email3Address]='" + eMailAddress + "'")
        as Outlook.ContactItem;
    if (contact == null)
    {
        return;
    }
    mail.AddBusinessCard(contact);
    mail.Display(false);
}
```

## <a name="see-also"></a><span data-ttu-id="dda09-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dda09-112">See also</span></span>

- [<span data-ttu-id="dda09-113">Elektronische Visitenkarten</span><span class="sxs-lookup"><span data-stu-id="dda09-113">Electronic Business Cards</span></span>](electronic-business-cards.md)
