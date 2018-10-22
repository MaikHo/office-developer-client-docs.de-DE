---
title: Angeben verschiedener Empfängertypen für ein Terminelement
TOCTitle: Specify different recipient types for an appointment item
ms:assetid: 83aedc8f-adc0-453d-8e71-1bb9aacc7993
ms:mtpsurl: https://msdn.microsoft.com/library/Ff184622(v=office.15)
ms:contentKeyID: 55119807
ms.date: 07/24/2014
mtps_version: v=office.15
ms.openlocfilehash: c1f9e1d8e7b4c884853dda9b5c37cd7357d48b6c
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25405686"
---
# <a name="specify-different-recipient-types-for-an-appointment-item"></a><span data-ttu-id="12363-102">Angeben verschiedener Empfängertypen für ein Terminelement</span><span class="sxs-lookup"><span data-stu-id="12363-102">Uses the OlMeetingRecipientType enumeration to specify different recipient types for an appointment item.</span></span>

<span data-ttu-id="12363-103">In diesem Beispiel werden mithilfe der [OlMeetingRecipientType](https://msdn.microsoft.com/library/bb623431\(v=office.15\))-Auflistung verschiedene Empfängertypen für ein Terminelement angegeben.</span><span class="sxs-lookup"><span data-stu-id="12363-103">This example shows how to use the [OlMeetingRecipientType](https://msdn.microsoft.com/library/bb623431\(v=office.15\)) enumeration to specify different recipient types for an appointment item.</span></span>

## <a name="example"></a><span data-ttu-id="12363-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="12363-104">Example</span></span>

> [!NOTE] 
> <span data-ttu-id="12363-105">Das folgende Codebeispiel ist ein Auszug aus [Programming Applications für Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493).</span><span class="sxs-lookup"><span data-stu-id="12363-105">The following code example is an excerpt from  [Programming Applications for Microsoft Office Outlook 2007](https://www.amazon.com/gp/product/0735622493?ie=UTF8&tag=msmsdn-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=0735622493)  , from Microsoft Press (ISBN 9780735622494, copyright Microsoft Press 2007, all rights reserved).</span></span>

<span data-ttu-id="12363-106">Zum Hinzufügen von Empfängern zu einem [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) -Objekt, das eine Besprechungsanfrage darstellt, geben Sie mit der OlMeetingRecipientType-Aufzählung an, ob es sich beim Empfänger der Nachricht um einen erforderlichen oder optionalen Teilnehmer oder um eine Ressource (wie einen Raum oder eine bestimmte Ausstattung) handelt.</span><span class="sxs-lookup"><span data-stu-id="12363-106">To add recipients to an [AppointmentItem](https://msdn.microsoft.com/library/bb645611\(v=office.15\)) object that represents a meeting request, use the OlMeetingRecipientType enumeration to specify whether the recipient of the message is a required or optional attendee, or a resource (such as a room or equipment).</span></span>

<span data-ttu-id="12363-107">Im folgenden Codebeispiel erstellt SetRecipientTypeForAppt ein **AppointmentItem**-Objekt, legt Eigenschaften für dieses Objekt fest und fügt erforderliche und optionale Teilnehmer hinzu.</span><span class="sxs-lookup"><span data-stu-id="12363-107">In the following code example, SetRecipientTypeForAppt creates an **AppointmentItem** object, sets properties for that object, and adds required and optional attendees.</span></span> <span data-ttu-id="12363-108">Es wird auch ein Konferenzraum für die Besprechung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="12363-108">It also adds a conference room for the meeting.</span></span> <span data-ttu-id="12363-109">Beachten Sie, dass die [MeetingStatus](https://msdn.microsoft.com/library/bb611417\(v=office.15\))-Eigenschaft auf [olMeeting](https://msdn.microsoft.com/library/bb644590\(v=office.15\)) festgelegt wird, wodurch angegeben wird, dass der Termin eine Besprechungsanfrage ist.</span><span class="sxs-lookup"><span data-stu-id="12363-109">Note that the [MeetingStatus](https://msdn.microsoft.com/library/bb611417\(v=office.15\)) property is set to [olMeeting](https://msdn.microsoft.com/library/bb644590\(v=office.15\)), indicating that the appointment is a meeting request.</span></span>

<span data-ttu-id="12363-110">Wenn Sie Visual Studio verwenden, um dieses Codebeispiel zu testen, müssen Sie der Microsoft Outlook 15.0-Objektbibliothekkomponente zuerst einen Verweis hinzufügen und die Outlook-Variable angeben, wenn Sie den **Microsoft.Office.Interop.Outlook**-Namespace importieren.</span><span class="sxs-lookup"><span data-stu-id="12363-110">If you use Visual Studio to test this code example, you must first add a reference to the Microsoft Outlook 15.0 Object Library component and specify the   variable when you import the Microsoft.Office.Interop.Outlook namespace.</span></span> <span data-ttu-id="12363-111">Die **using**-Anweisung darf im Codebeispiel nicht direkt vor den Funktionen stehen, sondern muss vor der öffentlichen Class-Deklaration hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="12363-111">The using statement must not occur directly before the functions in the code example but must be added before the public   declaration.</span></span> <span data-ttu-id="12363-112">Die folgende Codezeile zeigt, wie Sie den Import und die Zuweisung in C\# vornehmen.</span><span class="sxs-lookup"><span data-stu-id="12363-112">The following line of code shows how to do the import and assignment in C#.</span></span>

```csharp
using Outlook = Microsoft.Office.Interop.Outlook;
```

```csharp
private void SetRecipientTypeForAppt()
{
    Outlook.AppointmentItem appt =
        Application.CreateItem(
        Outlook.OlItemType.olAppointmentItem)
        as Outlook.AppointmentItem;
    appt.Subject = "Customer Review";
    appt.MeetingStatus = Outlook.OlMeetingStatus.olMeeting;
    appt.Location = "36/2021";
    appt.Start = DateTime.Parse("10/20/2006 10:00 AM");
    appt.End = DateTime.Parse("10/20/2006 11:00 AM");
    Outlook.Recipient recipRequired =
        appt.Recipients.Add("Ryan Gregg");
    recipRequired.Type =
        (int)Outlook.OlMeetingRecipientType.olRequired;
    Outlook.Recipient recipOptional =
        appt.Recipients.Add("Peter Allenspach");
    recipOptional.Type =
        (int)Outlook.OlMeetingRecipientType.olOptional;
    Outlook.Recipient recipConf =
        appt.Recipients.Add("Conf Room 36/2021 (14) AV");
    recipConf.Type =
        (int)Outlook.OlMeetingRecipientType.olResource;
    appt.Recipients.ResolveAll();
    appt.Display(false);
}
```

## <a name="see-also"></a><span data-ttu-id="12363-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="12363-113">See also</span></span>

- [<span data-ttu-id="12363-114">Termine</span><span class="sxs-lookup"><span data-stu-id="12363-114">Appointments</span></span>](appointments.md)
