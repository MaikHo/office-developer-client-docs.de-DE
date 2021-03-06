---
title: Die ADO-Bibliotheks Familie
TOCTitle: The ADO family of libraries
ms:assetid: 9e794509-d0a8-2e5b-02a8-65e26f059c4e
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249724(v=office.15)
ms:contentKeyID: 48546656
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 296e05118054ec045c23cd92a399afdc3cddd9a1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32313972"
---
# <a name="the-ado-family-of-libraries"></a>Die ADO-Bibliotheks Familie

**Gilt für**: Access 2013, Office 2013

Die ADO-Familie besteht aus drei Hauptbibliotheken: ADO (einschließlich RDS), ADO MD und ADOX.

## <a name="ado"></a>ADO

Mit ADO können Clientanwendungen über einen OLE DB-Anbieter auf Daten auf einem Datenbankserver zugreifen und diese bearbeiten. Die wichtigsten Vorteile von ADO sind einfache Handhabung, hohe Geschwindigkeit sowie geringer Arbeitsspeicher- und Speicherplatzbedarf. ADO unterstützt die wichtigsten Features für die Erstellung von Client/Server-und webbasierten Anwendungen.

ADO verfügt außerdem über Remote Data Service (RDS), mit dem Sie Daten von einem Server in eine Clientanwendung oder Webseite verschieben, die Daten auf dem Client bearbeiten und Aktualisierungen an den Server in einem einzelnen Roundtrip zurückgeben können.

## <a name="ado-md"></a>ADO MD

Microsoft ActiveX Data Objects (Multidimensional) (ADO MD) ermöglicht den einfachen Zugriff auf multidimensionale Daten in Sprachen wie z. B. Microsoft Visual Basic, Microsoft Visual C++ und Microsoft Visual J++. ADO MD erweitert ADO um Objekte speziell für multidimensionale Daten, wie z. B. die Objekte **CubeDef** und **Cellset**. Mit ADO MD können Sie ein multidimensionales Schema durchsuchen, einen Cube abfragen und die Ergebnisse abrufen.

ADO MD verwendet wie ADO einen zugrunde liegenden OLE DB-Anbieter für den Zugriff auf Daten. Der Anbieter muss gemäß der OLE DB für OLAP-Spezifikation ein multidimensionaler Datenprovider (MDP) sein, um mit ADO MD arbeiten zu können. MDPs stellen Daten in multidimensionalen Ansichten dar. Tabulare Datenprovider (TDP) stellen Daten dagegen in tabularen Ansichten dar. In der Dokumentation zu Ihrem OLE DB für OLAP-Anbieter finden Sie ausführlichere Information zur Syntax und zu den Funktionen, die von Ihrem Anbieter unterstützt werden.

## <a name="adox"></a>ADOX

Microsoft ActiveX Data Objects Extensions für Datendefinitionssprache und Sicherheit (ADOX) ist eine Erweiterung der ADO-Objekte und des Programmiermodells. ADOX enthält Objekte zum Erstellen und Ändern von Schemas sowie zur Sicherheit. Da es sich um einen objektbasierten Ansatz zur Schemabearbeitung handelt, können Sie Code erstellen, der für verschiedene Datenquellen verwendet werden kann, ungeachtet der Unterschiede in der jeweiligen Syntax.

ADOX ist eine Begleitbibliothek zu ADO-Kernobjekten. Hiermit werden zusätzliche Objekte für das Erstellen, Ändern und Löschen von Schemaobjekten wie Tabellen und Prozeduren verfügbar gemacht. Außerdem enthält dieses Element Sicherheitsobjekte, um Benutzer und Gruppen zu warten und um Berechtigungen für Objekte zu erteilen und aufzuheben.

