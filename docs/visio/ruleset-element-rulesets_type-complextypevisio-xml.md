---
title: RuleSet-Element (RuleSets_Type complexType) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 5ca63b8a-782e-211f-be7a-8e177b61d8fc
description: Stellt einen Satz von Diagramm Validierungsregeln dar.
ms.openlocfilehash: c6fc8df6d9c84f44496d69207dfb9cfb878659e3
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "34541638"
---
# <a name="ruleset-element-rulesetstype-complextype-visio-xml"></a>RuleSet-Element (RuleSets_Type complexType) (Visio XML)

Stellt einen Satz von Diagramm Validierungsregeln dar.
  
## <a name="element-information"></a>Informationen zum Element

|||
|:-----|:-----|
|**Elementtyp** <br/> |[RuleSet_Type](ruleset_type-complextypevisio-xml.md) <br/> |
|**Namespace** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**Schemadatei** <br/> |VisioSchema15. xsd  <br/> |
|**Dokumentteile** <br/> |Validation. XML  <br/> |
   
## <a name="definition"></a>Definition

```XML
< xs:element name="RuleSet" type="RuleSet_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>Elemente und Attribute

Wenn das Schema bestimmte Anforderungen wie **Sequence**, **minOccurs**, **maxOccurs**und **Choice**definiert, lesen Sie den Abschnitt Definition. 
  
### <a name="parent-elements"></a>Übergeordnete Elemente

|**Element**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|[RuleSets](rulesets-element-validation_type-complextypevisio-xml.md) <br/> |[RuleSets_Type](rulesets_type-complextypevisio-xml.md) <br/> |Enthält ein **RuleSet** -Element für jeden Überprüfungsregel Satz im Dokument.  <br/> |
   
### <a name="child-elements"></a>Untergeordnete Elemente

|**Element**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|[Rule](rule-element-ruleset_type-complextypevisio-xml.md) <br/> |[Rule_Type](rule_type-complextypevisio-xml.md) <br/> |Repräsentiert eine einzelne Überprüfungsregel in einem Regelsatz für die Diagrammüberprüfung.  <br/> |
|[RuleSetFlags](rulesetflags-element-ruleset_type-complextypevisio-xml.md) <br/> |[RuleSetFlags_Type](rulesetflags_type-complextypevisio-xml.md) <br/> |Gibt Regel festgelegte Eigenschaften an.  <br/> |
   
### <a name="attributes"></a>Attribute

|**Attribut**|**Typ**|**Erforderlich**|**Beschreibung**|**Mögliche Werte**|
|:-----|:-----|:-----|:-----|:-----|
|Beschreibung  <br/> |XSD: Zeichenfolge  <br/> |Optional  <br/> |Gibt die Beschreibung an, die auf der Benutzeroberfläche des Validierungsregel Satzes angezeigt wird. Der Standardwert ist eine leere Zeichenfolge.  <br/> |Werte des Typs XSD: String.  <br/> |
|Aktiviert  <br/> |XSD: Boolean  <br/> |Optional  <br/> |Gibt an, ob die Regeln im angegebenen Überprüfungsregel Satz überprüft werden, wenn die Validierung für das aktuelle Dokument ausgelöst wird. Der Standardwert ist True.  <br/> |Werte des XSD: Boolean-Typs.  <br/> |
|ID  <br/> |XSD: unsignedInt  <br/> |erforderlich  <br/> |Gibt den eindeutigen Bezeichner des Überprüfungsregel Satzes an.  <br/> |Werte des XSD: unsignedInt-Typs.  <br/> |
|Name  <br/> |XSD: Zeichenfolge  <br/> |Optional  <br/> |Gibt den lokalen Namen des Überprüfungsregel Satzes an. Standardwert NameU-Attribut.  <br/> |Werte des Typs XSD: String.  <br/> |
|NameU  <br/> |XSD: Zeichenfolge  <br/> |erforderlich  <br/> |Gibt den universellen Namen des Überprüfungsregel Satzes an.  <br/> |Werte des Typs XSD: String.  <br/> |
   

