---
title: Source-Eigenschaft (ADO Record)
TOCTitle: Source Property (ADO Record)
ms:assetid: f36f0f5f-4493-d8c5-db4b-c72f5031bcb3
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250235(v=office.15)
ms:contentKeyID: 48548670
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: c568861b684856f14c644a4ef3341eed66afd569
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2018
ms.locfileid: "25474038"
---
# <a name="source-property-ado-record"></a>Source-Eigenschaft (ADO Record)


**Betrifft**: Access 2013 | Office 2013

Gibt die vom [Record](record-object-ado.md)-Objekt dargestellte Datenquelle oder das Objekt an.

## <a name="settings-and-return-values"></a>Einstellungen und Rückgabewerte

Legt einen **Variant** -Wert fest, der die vom **Record** -Objekt dargestellte Entität angibt, oder gibt den Wert zurück.

## <a name="remarks"></a>Hinweise

Die **Source** -Eigenschaft gibt das Argument *Source* die [Open](open-method-ado-record.md) -Methode des **Record** -Objekts zurück. Sie kann die Zeichenfolge einer absoluten oder relativen URL enthalten. Eine absolute URL kann verwendet werden, ohne dass die [ActiveConnection](activeconnection-property-ado.md)-Eigenschaft festgelegt werden muss, um das **Record** -Objekt direkt zu öffnen. In diesem Fall wird ein implizites **Connection** -Objekt erstellt.

Die **Source** -Eigenschaft kann auch einen Verweis auf ein bereits geöffnetes **Recordset** -Objekt enthalten. Dadurch wird ein **Record** -Objekt geöffnet, das die aktuelle Zeile im **Recordset** -Objekt darstellt.

Außerdem kann die **Source** -Eigenschaft einen Verweis auf ein [Command](command-object-ado.md)-Objekt enthalten, das eine einzelne Datenzeile vom Anbieter zurückgibt.

Wenn die **ActiveConnection** -Eigenschaft ebenfalls festgelegt ist, muss die **Source** -Eigenschaft auf ein Objekt verweisen, das im Bereich dieser Verbindung vorhanden ist. Wenn z. B. in einem strukturierten Namespace die **Source** -Eigenschaft eine absolute URL enthält, muss sie auf einen Knoten zeigen, der innerhalb des Knotenbereichs vorhanden ist, der durch die URL in der Verbindungszeichenfolge identifiziert wird. Enthält die **Source** -Eigenschaft eine relative URL, dann wird sie innerhalb des Kontexts überprüft, der von der **ActiveConnection** -Eigenschaft festgelegt wird.

Die **Source** -Eigenschaft ist nicht schreibgeschützt, wenn das **Record** -Objekt geschlossen ist, und schreibgeschützt, wenn das **Record** -Objekt geöffnet ist.


> [!NOTE]
> <P>[!HINWEIS] Bei URLs, die das HTTP-Schema verwenden, wird automatisch der <A href="microsoft-ole-db-provider-for-internet-publishing.md">Microsoft OLE DB-Anbieter für Internet Publishing</A> aufgerufen. Weitere Informationen finden Sie unter <A href="absolute-and-relative-urls.md">Absolute and Relative URLs</A>.</P>

