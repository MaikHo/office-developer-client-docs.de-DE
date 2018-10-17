---
title: View-Objekt (ADOX - Access-desktop-Datenbank (engl.))
TOCTitle: View Object (ADOX)
ms:assetid: 3b2e9972-8a0d-eaa3-1c93-ae0665a47f02
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249149(v=office.15)
ms:contentKeyID: 48544280
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: ca58dd83ee3d3675a4ca272e1074b8d8cc930391
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2018
ms.locfileid: "25475938"
---
# <a name="view-object-adox"></a>View-Objekt (ADOX)


**Betrifft**: Access 2013 | Office 2013

Stellt eine gefilterte Datensatzgruppe oder eine virtuelle Tabelle dar. Wenn es in Verbindung mit dem ADO-Objekt [Command](command-object-ado.md) verwendet wird, kann das **View** -Objekt zum Hinzufügen, Löschen oder Ändern von Sichten verwendet werden.

## <a name="remarks"></a>Hinweise

Eine Sicht ist eine virtuelle Tabelle, die aus anderen Datenbanktabellen oder -sichten erstellt wird. Mit dem **View** -Objekt können Sie eine Sicht erstellen, ohne die CREATE VIEW-Syntax des Anbieters zu kennen oder zu verwenden.

Die Eigenschaften eines **View** -Objekts ermöglichen Folgendes:

  - Identifizieren der Sicht, indem Sie die [Name](name-property-adox.md)-Eigenschaft verwenden.

  - Angeben des ADO-Objekts **Command**, das zum Hinzufügen, Löschen oder Ändern von Sichten verwendet werden kann, indem Sie die [Command](command-property-adox.md)-Eigenschaft verwenden.

  - Zurückgeben von Datumsinformationen, indem Sie die Eigenschaften [DateCreated](datecreated-property-adox.md) und [DateModified](datemodified-property-adox.md) verwenden.
