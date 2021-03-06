---
title: Konten
TOCTitle: Accounts
ms:assetid: 28df6dbd-4d24-42f3-91c1-fd8b3a4ea722
ms:mtpsurl: https://msdn.microsoft.com/library/office/ff184597(v=office.15)
ms:contentKeyID: 55119790
ms.date: 07/24/2014
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: d539f38419a8eaac60cd3054da6283a49bf4cc00
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331185"
---
# <a name="accounts"></a>Konten 

In diesem Abschnitt werden Beispielaufgaben bereitgestellt, die sich auf E-Mail-Konten beziehen. Beispiele von E-Mail-Konten sind Microsoft Exchange Server-, Post Office Protocol 3 (POP3)-, Internet Message Access Protocol (IMAP)- und Hypertext Transfer Protocol (HTTP)-Konten. Ein Konto für das aktuelle Profil wird durch ein [Account](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.account?view=outlook-pia)-Objekt dargestellt.


|Thema|Beschreibung|
|:----|:----------|
|[Abrufen von Kontoinformationen](how-to-get-account-information.md) | Verwendet als Eingabeargument ein vertrauenswürdiges Microsoft Outlook [Application](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook.application?view=outlook-pia) -Objekt und zeigt mithilfe des **Account**-Objekts die Details aller Konten an, die für das aktuelle Outlook-Profil zur Verfügung stehen.|
|[Erstellen eines sendbaren Elements für ein bestimmtes Konto auf der Basis des aktuellen Ordners](how-to-create-a-sendable-item-for-a-specific-account-based-on-the-current-folder.md) | Enthält zwei Codebeispiele, die zeigen, wie ein versendbares E-Mail-Element und eine Besprechungsanfrage erstellt werden, und wie sie mithilfe eines bestimmten Kontos, das auf dem aktuellen Ordner basiert, gesendet werden.|
|[Abrufen des Kontos für einen Ordner](how-to-get-the-account-for-a-folder.md) | Ruft das Konto ab, das einem Ordner in der aktuellen Sitzung zugeordnet ist.|
|[Abrufen von Informationen über mehrere Konten](how-to-get-information-about-multiple-accounts.md) | Ruft verschiedene Informationen zu jedem Konto im aktuellen Profil ab und zeigt diese an.|
|[Senden eines E-Mail-Elements mithilfe eines Hotmail-Kontos](how-to-send-a-mail-item-by-using-a-hotmail-account.md) | Verwendet die [SendUsingAccount](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.outlook._mailitem.sendusingaccount?view=outlook-pia) -Eigenschaft, um ein E-Mail-Element mithilfe eines Windows Live Hotmail-Kontos zu senden.|

## <a name="see-also"></a>Siehe auch

- [Exchange-Benutzer](exchange-users.md)
- [Mail](mail.md)
- [Empfänger](recipients.md)
- [Gewusst wie... (Outlook 2013 PIA-Referenz)](how-do-i-outlook-2013-pia-reference.md)

