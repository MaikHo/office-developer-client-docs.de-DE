---
title: Project-Clientprogrammierung
manager: soliver
ms.date: 08/10/2016
ms.audience: Developer
f1_keywords:
- object model
- Project object model
- Project VBA
- VBA
keywords:
- VBA, Projektobjektmodell, Projekt, Programmierbarkeit, Programmierbarkeit, Projekt VBA, Visual Basic for Applications, Project-Objektmodell, VBA, Objektmodell, VBA, Visual Basic für Applikationen
localization_priority: Normal
ms.assetid: 0ad49ff6-8dff-4379-a52c-d292c53c2bc0
description: Die Project 2013-Desktopclientanwendungen – Project Standard 2013 und Project Professional 2013 – können angepasst und erweitert werden, indem VBA zum Schreiben von Makros verwendet wird. Sie können Visual Studio 2012 verwenden, um die Menüband-Benutzeroberfläche anzupassen und komplexe Add-Ins zu erstellen. Office-Add-ins ermöglicht ein neues Erweiterbarkeitsmodell für Aufgabenbereiche in Project, die auf einer gemeinsamen Office 2013-Plattform aufbauen. Project Standard 2013 und Project Professional 2013 können allgemeine Office-Add-Ins ausführen und Aufgabenbereich-Add-Ins verwenden, die speziell für die Integration in SharePoint, andere Websites und Webanwendungen sowie externe Daten entwickelt wurden.
ms.openlocfilehash: cc345f0ff91dfb573dd86c256e89df478edd4924
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32301512"
---
# <a name="project-client-programming"></a>Project-Clientprogrammierung

Die Project 2013-Desktopclientanwendungen – Project Standard 2013 und Project Professional 2013 – können angepasst und erweitert werden, indem VBA zum Schreiben von Makros verwendet wird. Sie können Visual Studio 2012 verwenden, um die Menüband-Benutzeroberfläche anzupassen und komplexe Add-Ins zu erstellen. Office-Add-ins ermöglicht ein neues Erweiterbarkeitsmodell für Aufgabenbereiche in Project, die auf einer gemeinsamen Office 2013-Plattform aufbauen. Project Standard 2013 und Project Professional 2013 können allgemeine Office-Add-Ins ausführen und Aufgabenbereich-Add-Ins verwenden, die speziell für die Integration in SharePoint, andere Websites und Webanwendungen sowie externe Daten entwickelt wurden.
  
 **Wechseln zu Visual Studio** VBA eignet sich für die Aufzeichnung von Makros und die Entwicklung relativ einfacher Automatisierungslösungen. Es wird empfohlen, Visual Studio 2012 zu verwenden, um Aufgabenbereich-Add-Ins, Add-Ins und komplexere, sichere, skalierbare und einfach bereitgestellte Lösungen zu entwickeln. Microsoft .NET Framework 4,0 und die primäre Interop-Assembly von Project 2013 bieten zahlreiche Vorteile beim entwickeln und Bereitstellen von Lösungen, mit denen die Project 2013-Desktop Clients automatisiert und integriert werden. 
  
> [!NOTE]
> Sie können Visual Studio 2010 zum Entwickeln von Project-Add-Ins verwenden. Visual Studio 2012 enthält jedoch Vorlagen und Erweiterungen, die für die Erstellung von Office-Add-ins-Clients vorgesehen sind. 
  
Das **MSProject** -Objektmodell für VBA in Project 2013 ist im Wesentlichen identisch mit dem **Microsoft. Office. Interop. MSProject** -Objektmodell für Lösungen mit verwaltetem Code mit Office Developer Tools für Visual Studio 2013 (auch bekannt als VSTO). Visual Studio 2012 enthält Vorlagen zum Entwickeln von Add-Ins auf Anwendungsebene für Project 2010 und für Project 2013 (entweder die Project Standard-oder Project Professional-Versionen). VSTO und Office Developer Tools für Visual Studio 2012 vereinfachen das entwickeln, testen und Bereitstellen erweiterter Integrationslösungen, die den Project-Desktop Client und andere Office 2013-Anwendungen verwenden können, und die Integration in SharePoint-Websites,-Listen und Workflows. 
  
Aufgabenbereich-Add-Ins und andere Add-Ins für Office und SharePoint können im Office Store (siehe [https://office.microsoft.com/store/](https://office.microsoft.com/en-us/store/)) für die Verwendung mit Project Online-und lokalen Installationen verkauft werden. VBA-Makros und VSTO-Add-Ins können nicht im Office Store verteilt werden. Sie sind für die lokale Verwendung mit Project Standard und Project Professional konzipiert. Sie können VBA-Makros in einem Projekt verteilen. MPP-Datei, installieren Sie Sie in der Datei Global. MPT auf Ihrem Computer, oder verteilen Sie Sie in der Enterprise-Global-Projektvorlage in Project Server 2013. VSTO-Add-Ins können sicherer über die [ClickOnce](https://msdn.microsoft.com/library/t71a733d.aspx) -Bereitstellung verteilt werden, was einfache Updates ermöglicht. 
  
## <a name="reference"></a>Referenz

[Projekt-VBA-Entwicklerreferenz](https://msdn.microsoft.com/library/ee861523%28office.15%29.aspx) Enthält Einführungs-und VBA-Hilfeartikel. 
  
## <a name="related-sections"></a>Verwandte Abschnitte

[Project Server 2013-Architektur](project-server-2013-architecture.md) Zeigt, wie die Projekt Clients mit Project Server interagieren. 
  
## <a name="see-also"></a>Siehe auch

- [Project für Entwickler](https://msdn.microsoft.com/office/aa905469)
- [Office Developer Center](https://dev.office.com)
- [Visual Studio Developer Center](https://msdn.microsoft.com/vstudio/aa718325.aspx)
- [ClickOnce-Sicherheit und-Bereitstellung](https://msdn.microsoft.com/library/t71a733d.aspx)
- [Referenz: Verfügbare Felder](https://support.office.com/en-us/article/available-fields-reference-615a4563-1cc3-40f4-b66f-1b17e793a460)

