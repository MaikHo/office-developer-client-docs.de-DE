---
title: Row_Type ComplexType ("Visio XML")
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 5e5c420e-f384-7b62-c862-35aea16e6d55
ms.openlocfilehash: ebd3b666590e6144d2a3cb6e0059b64eb6e8dab5
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25391577"
---
# <a name="rowtype-complextype-visio-xml"></a><span data-ttu-id="98afd-102">Row_Type ComplexType ("Visio XML")</span><span class="sxs-lookup"><span data-stu-id="98afd-102">Row_Type complexType ('Visio XML')</span></span>

## <a name="type-information"></a><span data-ttu-id="98afd-103">Informationen zum Typ</span><span class="sxs-lookup"><span data-stu-id="98afd-103">Type information</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="98afd-104">**Namespace**</span><span class="sxs-lookup"><span data-stu-id="98afd-104">**Namespace**</span></span> <br/> |https://schemas.microsoft.com/office/visio/2011/1/core  <br/> |
|<span data-ttu-id="98afd-105">**Schemadatei**</span><span class="sxs-lookup"><span data-stu-id="98afd-105">**Schema file**</span></span> <br/> |<span data-ttu-id="98afd-106">VisioSchema15-2012-06-05.xsd</span><span class="sxs-lookup"><span data-stu-id="98afd-106">VisioSchema15-2012-06-05.xsd</span></span>  <br/> |
|<span data-ttu-id="98afd-107">**Erweiterungsbasis**</span><span class="sxs-lookup"><span data-stu-id="98afd-107">**Extension base**</span></span> <br/> |<span data-ttu-id="98afd-108">Keine</span><span class="sxs-lookup"><span data-stu-id="98afd-108">None</span></span>  <br/> |
   
## <a name="definition"></a><span data-ttu-id="98afd-109">Definition</span><span class="sxs-lookup"><span data-stu-id="98afd-109">Definition</span></span>

```XML
          <xs:complexType name="Row_Type">
          
          <xs:sequence>
    <xs:element name="Cell"  type="Cell_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
    <xs:element name="Trigger"  type="Trigger_Type"
     minOccurs="0"
     maxOccurs="unbounded"
    >
    </xs:element>
    
      </xs:sequence>
    <xs:attribute name="N"
  type="xsd:string"
    />
    <xs:attribute name="LocalName"
  type="xsd:string"
    />
    <xs:attribute name="IX"
  type="xsd:unsignedInt"
    />
    <xs:attribute name="T"
  type="xsd:string"
    />
    <xs:attribute name="Del"
  type="xsd:boolean"
    />
      </xs:complexType>
      
```

## <a name="elements-and-attributes"></a><span data-ttu-id="98afd-110">Elemente und Attribute</span><span class="sxs-lookup"><span data-stu-id="98afd-110">Elements and attributes</span></span>

<span data-ttu-id="98afd-111">Wenn das Schema spezifische Anforderungen, beispielsweise **Abfolge**, **MinOccurs**, **MaxOccurs**und **Wahl**, definiert finden Sie im Definitionsabschnitt.</span><span class="sxs-lookup"><span data-stu-id="98afd-111">If the schema defines specific requirements, such as **sequence**, **minOccurs**, **maxOccurs**, and **choice**, see the definition section.</span></span> 
  
### <a name="child-elements"></a><span data-ttu-id="98afd-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="98afd-112">Child elements</span></span>

|<span data-ttu-id="98afd-113">**Element**</span><span class="sxs-lookup"><span data-stu-id="98afd-113">**Element**</span></span>|<span data-ttu-id="98afd-114">**Typ**</span><span class="sxs-lookup"><span data-stu-id="98afd-114">**Type**</span></span>|<span data-ttu-id="98afd-115">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="98afd-115">**Description**</span></span>|
|:-----|:-----|:-----|
|[<span data-ttu-id="98afd-116">Cell</span><span class="sxs-lookup"><span data-stu-id="98afd-116">Cell</span></span>](cell-elementvisio-xml.md) <br/> |[<span data-ttu-id="98afd-117">Cell_Type</span><span class="sxs-lookup"><span data-stu-id="98afd-117">Cell_Type</span></span>](cell_type-complextypevisio-xml.md) <br/> ||
|[<span data-ttu-id="98afd-118">Trigger</span><span class="sxs-lookup"><span data-stu-id="98afd-118">Trigger</span></span>](trigger-elementvisio-xml.md) <br/> |[<span data-ttu-id="98afd-119">Trigger_Type</span><span class="sxs-lookup"><span data-stu-id="98afd-119">Trigger_Type</span></span>](trigger_type-complextypevisio-xml.md) <br/> ||
   
### <a name="attributes"></a><span data-ttu-id="98afd-120">Attribute</span><span class="sxs-lookup"><span data-stu-id="98afd-120">Attributes</span></span>

|<span data-ttu-id="98afd-121">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="98afd-121">**Attribute**</span></span>|<span data-ttu-id="98afd-122">**Typ**</span><span class="sxs-lookup"><span data-stu-id="98afd-122">**Type**</span></span>|<span data-ttu-id="98afd-123">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="98afd-123">**Required**</span></span>|<span data-ttu-id="98afd-124">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="98afd-124">**Description**</span></span>|<span data-ttu-id="98afd-125">**Mögliche Werte**</span><span class="sxs-lookup"><span data-stu-id="98afd-125">**Possible values**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="98afd-126">ENTF</span><span class="sxs-lookup"><span data-stu-id="98afd-126">Del</span></span>  <br/> |<span data-ttu-id="98afd-127">XSD: Boolean</span><span class="sxs-lookup"><span data-stu-id="98afd-127">xsd:boolean</span></span>  <br/> |<span data-ttu-id="98afd-128">Optional</span><span class="sxs-lookup"><span data-stu-id="98afd-128">optional</span></span>  <br/> ||<span data-ttu-id="98afd-129">Werte des Typs xsd: Boolean.</span><span class="sxs-lookup"><span data-stu-id="98afd-129">Values of the xsd:boolean type.</span></span>  <br/> |
|<span data-ttu-id="98afd-130">IX</span><span class="sxs-lookup"><span data-stu-id="98afd-130">IX</span></span>  <br/> |<span data-ttu-id="98afd-131">XSD:unsignedInt</span><span class="sxs-lookup"><span data-stu-id="98afd-131">xsd:unsignedInt</span></span>  <br/> |<span data-ttu-id="98afd-132">Optional</span><span class="sxs-lookup"><span data-stu-id="98afd-132">optional</span></span>  <br/> ||<span data-ttu-id="98afd-133">Werte des Typs Xsd:unsignedInt.</span><span class="sxs-lookup"><span data-stu-id="98afd-133">Values of the xsd:unsignedInt type.</span></span>  <br/> |
|<span data-ttu-id="98afd-134">LocalName</span><span class="sxs-lookup"><span data-stu-id="98afd-134">LocalName</span></span>  <br/> |<span data-ttu-id="98afd-135">XSD: String</span><span class="sxs-lookup"><span data-stu-id="98afd-135">xsd:string</span></span>  <br/> |<span data-ttu-id="98afd-136">Optional</span><span class="sxs-lookup"><span data-stu-id="98afd-136">optional</span></span>  <br/> ||<span data-ttu-id="98afd-137">Werte des Typs xsd: String.</span><span class="sxs-lookup"><span data-stu-id="98afd-137">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="98afd-138">N</span><span class="sxs-lookup"><span data-stu-id="98afd-138">N</span></span>  <br/> |<span data-ttu-id="98afd-139">XSD: String</span><span class="sxs-lookup"><span data-stu-id="98afd-139">xsd:string</span></span>  <br/> |<span data-ttu-id="98afd-140">Optional</span><span class="sxs-lookup"><span data-stu-id="98afd-140">optional</span></span>  <br/> ||<span data-ttu-id="98afd-141">Werte des Typs xsd: String.</span><span class="sxs-lookup"><span data-stu-id="98afd-141">Values of the xsd:string type.</span></span>  <br/> |
|<span data-ttu-id="98afd-142">T</span><span class="sxs-lookup"><span data-stu-id="98afd-142">T</span></span>  <br/> |<span data-ttu-id="98afd-143">XSD: String</span><span class="sxs-lookup"><span data-stu-id="98afd-143">xsd:string</span></span>  <br/> |<span data-ttu-id="98afd-144">Optional</span><span class="sxs-lookup"><span data-stu-id="98afd-144">optional</span></span>  <br/> ||<span data-ttu-id="98afd-145">Werte des Typs xsd: String.</span><span class="sxs-lookup"><span data-stu-id="98afd-145">Values of the xsd:string type.</span></span>  <br/> |
   

