---
title: Hinzufügen von und verweisen auf benutzerdefinierte Assemblys
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- InfoPath 2003-kompatible Formularvorlagen verwenden benutzerdefinierter Assemblys, Assemblys [InfoPath 2007], Hinzufügen benutzerdefinierter mithilfe des InfoPath 2003-Objektmodell
localization_priority: Normal
ms.assetid: 20e1f43e-8279-48fc-8f34-16a2729dbc9b
description: Wenn Sie in einem Formularvorlagenprojekt mit verwaltetem Code einen Verweis auf eine benutzerdefinierte Assembly hinzufügen, wird diese beim Kompilieren und Veröffentlichen des Projekts in die Formularvorlagendatei (XSN) einbezogen.
ms.openlocfilehash: e182930ebe14b6f64d1b90509fe400cc1fb1b26e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19790730"
---
# <a name="add-and-reference-custom-assemblies"></a><span data-ttu-id="bc693-104">Hinzufügen von und verweisen auf benutzerdefinierte Assemblys</span><span class="sxs-lookup"><span data-stu-id="bc693-104">Add and Reference Custom Assemblies</span></span>

<span data-ttu-id="bc693-105">Wenn Sie in einem Formularvorlagenprojekt mit verwaltetem Code einen Verweis auf eine benutzerdefinierte Assembly hinzufügen, wird diese beim Kompilieren und Veröffentlichen des Projekts in die Formularvorlagendatei (XSN) einbezogen.</span><span class="sxs-lookup"><span data-stu-id="bc693-105">When you add a reference to a custom assembly in a managed-code form template project, that assembly is included within the form template file (.xsn) when your project is compiled and published.</span></span>
  
## <a name="add-and-reference-a-custom-assembly"></a><span data-ttu-id="bc693-106">Hinzufügen einer benutzerdefinierten Assembly und Verweisen darauf</span><span class="sxs-lookup"><span data-stu-id="bc693-106">Add and Reference a Custom Assembly</span></span>

<span data-ttu-id="bc693-107">Kopieren Sie zum Vermeiden von eines Konflikts mit wie das InfoPath-Projektsystem Dateien verwaltet wird, die die Formularvorlagendatei hinzugefügt werden, keine benutzerdefinierte Assemblys, die Sie in den Ordner der obersten Ebene des ein Formularvorlagenprojekt verweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="bc693-107">To avoid a conflict with how the InfoPath project system manages files that are added to the form template file, do not copy any custom assemblies that you want to reference into the top-level folder of a form template project.</span></span> <span data-ttu-id="bc693-108">Standardmäßig wird dies einen Pfad in folgendem Format sein: < *Laufwerk* >: \Users\ *UserName* \Documents\InfoPath Projects\ *Projektname*</span><span class="sxs-lookup"><span data-stu-id="bc693-108">By default, this will be a path in the following format: < *drive*  >:\Users\  *UserName*  \Documents\InfoPath Projects\  *ProjectName*</span></span> 
  
<span data-ttu-id="bc693-p102">Wenn Sie benutzerdefinierte Assemblys verschieben möchten, die Sie auf einen Speicherort im Projektordner verweisen, müssen Sie einen Unterordner unter dem Projekthauptordner erstellen und anschließend die benutzerdefinierten Assemblys aus dem Unterordnerkopieren und darauf verweisen. Beachten Sie jedoch, dass das Erstellen eines Unterordners für Assemblys, auf die verwiesen wird, nicht erforderlich ist. Sofern sich eine Assembly, auf die verwiesen wird, nicht im Ordner auf der höchsten Ebene des Projekts befindet, wird sie vom InfoPath-Projektsystem beim Kompilieren und Veröffentlichen des Projekts automatisch in die Formularvorlagendatei (XSN) kopiert.</span><span class="sxs-lookup"><span data-stu-id="bc693-p102">If you do want to move custom assemblies that you reference to a location within the project folder, you must create a subfolder under the main project folder, and then copy and reference custom assemblies from that subfolder. However, be aware that creating a subfolder for referenced assemblies is not necessary. As long as a referenced assembly is not located within the project's top-level folder, the InfoPath project system will copy the assembly into the form template file (.xsn) when the project is compiled and published.</span></span>
  
### <a name="reference-a-custom-assembly-from-its-default-location"></a><span data-ttu-id="bc693-112">Verweisen auf eine benutzerdefinierte Assembly von ihrem Standardspeicherort aus</span><span class="sxs-lookup"><span data-stu-id="bc693-112">Reference a custom assembly from its default location</span></span>

1. <span data-ttu-id="bc693-113">Öffnen Sie das Formularvorlagenprojekt in Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="bc693-113">Open the form template project in Visual Studio 2012.</span></span>
    
2. <span data-ttu-id="bc693-114">On the **Project** menu, click **Add Reference**.</span><span class="sxs-lookup"><span data-stu-id="bc693-114">On the **Project** menu, click **Add Reference**.</span></span>
    
3. <span data-ttu-id="bc693-115">Klicken Sie auf die Registerkarte **Durchsuchen** , suchen Sie und geben Sie die Assembly, und klicken Sie dann auf **OK** , um den Verweis hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="bc693-115">Click the **Browse** tab, locate and specify the assembly, and then click **OK** to add the reference.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="bc693-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bc693-116">See also</span></span>

#### <a name="tasks"></a><span data-ttu-id="bc693-117">Aufgaben</span><span class="sxs-lookup"><span data-stu-id="bc693-117">Tasks</span></span>

[<span data-ttu-id="bc693-118">Erstellen einer Formularvorlage mit dem InfoPath 2003-Objektmodell</span><span class="sxs-lookup"><span data-stu-id="bc693-118">Create a Form Template Using the InfoPath 2003 Object Model</span></span>](how-to-create-a-form-template-using-the-infopath-2003-object-model.md)
