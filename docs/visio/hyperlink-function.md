---
title: HYPERLINK-Funktion
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251441
localization_priority: Normal
ms.assetid: 943636a6-e135-a626-7924-11e238156548
description: Navigiert zu der angegebenen Adresse, eine Datei, UNC oder URL sein kann Pfad.
ms.openlocfilehash: 4e86fd3682d5d9e26c52839e76d2016d654b3141
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/15/2018
ms.locfileid: "19797163"
---
# <a name="hyperlink-function"></a><span data-ttu-id="0baeb-103">HYPERLINK Function</span><span class="sxs-lookup"><span data-stu-id="0baeb-103">HYPERLINK Function</span></span>

<span data-ttu-id="0baeb-104">Navigiert zu der angegebenen Adresse, eine Datei, UNC oder URL sein kann Pfad.</span><span class="sxs-lookup"><span data-stu-id="0baeb-104">Navigates to the specified address, which can be a file, UNC, or URL path.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="0baeb-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="0baeb-105">Syntax</span></span>

<span data-ttu-id="0baeb-106">HYPERLINK ("** *Adresse* **" [,"** *Subaddress* **","** *Extrainfo* **", ** *Fenster* **, "** *Frame* **"])</span><span class="sxs-lookup"><span data-stu-id="0baeb-106">HYPERLINK(" ** *address* ** "[," ** *subaddress* ** "," ** *extrainfo* ** ", ** *window* **," ** *frame* ** "])</span></span> 
  
### <a name="parameters"></a><span data-ttu-id="0baeb-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="0baeb-107">Parameters</span></span>

|<span data-ttu-id="0baeb-108">**Name**</span><span class="sxs-lookup"><span data-stu-id="0baeb-108">**Name**</span></span>|<span data-ttu-id="0baeb-109">**Erforderlich/Optional**</span><span class="sxs-lookup"><span data-stu-id="0baeb-109">**Required/Optional**</span></span>|<span data-ttu-id="0baeb-110">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="0baeb-110">**Data Type**</span></span>|<span data-ttu-id="0baeb-111">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="0baeb-111">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="0baeb-112">_Adresse_</span><span class="sxs-lookup"><span data-stu-id="0baeb-112">_address_</span></span> <br/> |<span data-ttu-id="0baeb-113">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="0baeb-113">Required</span></span>  <br/> |<span data-ttu-id="0baeb-114">**String**</span><span class="sxs-lookup"><span data-stu-id="0baeb-114">**String**</span></span> <br/> |<span data-ttu-id="0baeb-115">Ein vollständiger Pfad oder ein relativer Pfad.</span><span class="sxs-lookup"><span data-stu-id="0baeb-115">A full path or a relative path.</span></span>  <br/> |
| <span data-ttu-id="0baeb-116">_SubAddress_</span><span class="sxs-lookup"><span data-stu-id="0baeb-116">_subaddress_</span></span> <br/> |<span data-ttu-id="0baeb-117">Optional</span><span class="sxs-lookup"><span data-stu-id="0baeb-117">Optional</span></span>  <br/> |<span data-ttu-id="0baeb-118">**String**</span><span class="sxs-lookup"><span data-stu-id="0baeb-118">**String**</span></span> <br/> |<span data-ttu-id="0baeb-119">Gibt eine Position innerhalb von Address zu verknüpfenden an.</span><span class="sxs-lookup"><span data-stu-id="0baeb-119">Specifies a location within address to link to.</span></span> <span data-ttu-id="0baeb-120">Beispielsweise kann Adresse eine Microsoft Visio-Datei handelt, Subaddress ein Seitenname sein; Wenn eine Microsoft Excel-Datei kann Subaddress ein Arbeitsblatt oder einen Bereich in einem Arbeitsblatt sein; Wenn eine URL für eine HTML-Seite kann Subaddress Anker sein.</span><span class="sxs-lookup"><span data-stu-id="0baeb-120">For example, if address is a Microsoft Visio file, subaddress can be a page name; if a Microsoft Excel file, subaddress can be a worksheet or range within a worksheet; if a URL for an HTML page, subaddress can be an anchor.</span></span>  <br/> |
| <span data-ttu-id="0baeb-121">_ExtraInfo_</span><span class="sxs-lookup"><span data-stu-id="0baeb-121">_extrainfo_</span></span> <br/> |<span data-ttu-id="0baeb-122">Optional</span><span class="sxs-lookup"><span data-stu-id="0baeb-122">Optional</span></span>  <br/> |<span data-ttu-id="0baeb-123">**String**</span><span class="sxs-lookup"><span data-stu-id="0baeb-123">**String**</span></span> <br/> |<span data-ttu-id="0baeb-124">Übergibt Informationen, die bei der Auflösung der URL verwendet werden, z. B. die Koordinaten für eine Imagemap.</span><span class="sxs-lookup"><span data-stu-id="0baeb-124">Passes information used in resolving the URL, such as the coordinates of an image map.</span></span>  <br/> |
| <span data-ttu-id="0baeb-125">_Fenster_</span><span class="sxs-lookup"><span data-stu-id="0baeb-125">_window_</span></span> <br/> |<span data-ttu-id="0baeb-126">Optional</span><span class="sxs-lookup"><span data-stu-id="0baeb-126">Optional</span></span>  <br/> |<span data-ttu-id="0baeb-127">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="0baeb-127">**Boolean**</span></span> <br/> |<span data-ttu-id="0baeb-p102">Legt fest, ob der Hyperlink in einem neuen Fenster geöffnet wird. Die Standardeinstellung lautet FALSE.</span><span class="sxs-lookup"><span data-stu-id="0baeb-p102">Specifies whether the hyperlink is opened in a new window. The default value is FALSE.</span></span>  <br/> |
| <span data-ttu-id="0baeb-130">_Rahmen_</span><span class="sxs-lookup"><span data-stu-id="0baeb-130">_frame_</span></span> <br/> |<span data-ttu-id="0baeb-131">Optional</span><span class="sxs-lookup"><span data-stu-id="0baeb-131">Optional</span></span>  <br/> |<span data-ttu-id="0baeb-132">**String**</span><span class="sxs-lookup"><span data-stu-id="0baeb-132">**String**</span></span> <br/> | <span data-ttu-id="0baeb-p103">Legt den Namen eines Frames zu einem Ziel fest, wenn Visio als aktives Dokument in einem ActiveX-Browser, z. B. Microsoft Internet Explorer 3.0 oder höher, geöffnet ist. Die Standardeinstellung ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="0baeb-p103">Specifies the name of a frame to target when Visio is open as an Active document in an ActiveX browser, such as Microsoft Internet Explorer 3.0 or later. The default is an empty string.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0baeb-135">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="0baeb-135">Remarks</span></span>

<span data-ttu-id="0baeb-p104">Wenn das Dokument keinen Basispfad besitzt, navigiert Visio relativ zum Dokumentpfad. Wenn das Dokument noch nicht gespeichert wurde, bleibt der Hyperlink undefiniert.</span><span class="sxs-lookup"><span data-stu-id="0baeb-p104">If the document has no base path, Visio navigates according to the document path. If the document has not been saved, the hyperlink is undefined.</span></span> 
  
<span data-ttu-id="0baeb-138">Relative Pfade basieren auf dem Feld **Hyperlinkbasis** im Dialogfeld **Visio Eigenschaften** angegeben.</span><span class="sxs-lookup"><span data-stu-id="0baeb-138">Relative paths are based on the **Hyperlink base** field specified in the **Visio Properties** dialog box.</span></span> 
  
<span data-ttu-id="0baeb-139">Sie können die GOTOPAGE-Funktion nutzen, um zu den Zeichenblättern eines Dokuments zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="0baeb-139">You can use the GOTOPAGE function to navigate to pages of a document.</span></span> 
  
## <a name="example-1"></a><span data-ttu-id="0baeb-140">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="0baeb-140">Example 1</span></span>

 `HYPERLINK("C:\My Documents\Drawing1.vsdx")`
  
## <a name="example-2"></a><span data-ttu-id="0baeb-141">Beispiel 2</span><span class="sxs-lookup"><span data-stu-id="0baeb-141">Example 2</span></span>

 `HYPERLINK("\\Server\Share\Drawing1.vsdx")`
  
## <a name="example-3"></a><span data-ttu-id="0baeb-142">Beispiel 3</span><span class="sxs-lookup"><span data-stu-id="0baeb-142">Example 3</span></span>

 `HYPERLINK("http://www.microsoft.com")`
  
## <a name="example-4"></a><span data-ttu-id="0baeb-143">Beispiel 4</span><span class="sxs-lookup"><span data-stu-id="0baeb-143">Example 4</span></span>

 `HYPERLINK("..\data.xlsx","sheet1!A1")`
  
