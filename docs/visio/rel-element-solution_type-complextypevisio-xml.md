---
title: Rel-Element (Solution_Type complexType) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 8438fe4b-f5f7-d4e4-58b7-7ebdc1da197a
description: Gibt eine Beziehung zu einem Webpart mit der Lösungs-XML an, die dieser Lösung zugeordnet ist.
ms.openlocfilehash: 1fe48579da28501b74fedd507f3e44d59736ae87
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "34542765"
---
# <a name="rel-element-solutiontype-complextype-visio-xml"></a>Rel-Element (Solution_Type complexType) (Visio XML)

Gibt eine Beziehung zu einem Webpart mit der Lösungs-XML an, die dieser Lösung zugeordnet ist.
  
## <a name="element-information"></a>Informationen zum Element

|||
|:-----|:-----|
|**Elementtyp** <br/> |[Rel_Type](rel_type-complextypevisio-xml.md) <br/> |
|**Namespace** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**Schemadatei** <br/> |VisioSchema15. xsd  <br/> |
|**Dokumentteile** <br/> |Pages. XML, Masters. XML, Recordsets. XML, Page #. XML, Master #. XML  <br/> |
   
## <a name="definition"></a>Definition

```XML
<xs:element name="Rel" type="Rel_Type" minOccurs="1" maxOccurs="1" >
</xs:element>
```

## <a name="elements-and-attributes"></a>Elemente und Attribute

Wenn das Schema bestimmte Anforderungen wie **Sequence**, **minOccurs**, **maxOccurs**und **Choice**definiert, lesen Sie den Abschnitt Definition. 
  
### <a name="parent-elements"></a>Übergeordnete Elemente

|**Element**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|[Solution](solution-element-solutions_type-complextypevisio-xml.md) <br/> |[Solution_Type](solution_type-complextypevisio-xml.md) <br/> |Gibt eine Instanz des in der Zeichnung gespeicherten Lösungs-XML-Code an.  <br/> |
   
### <a name="child-elements"></a>Untergeordnete Elemente

Keine.
  
### <a name="attributes"></a>Attribute

|**Attribut**|**Typ**|**Erforderlich**|**Beschreibung**|**Mögliche Werte**|
|:-----|:-----|:-----|:-----|:-----|
|r:ID  <br/> |XSD: Zeichenfolge  <br/> Weitere Informationen finden Sie in der "Anmerkungen".  <br/> |erforderlich  <br/> |Gibt eine Beziehung zu einem Webpart an.  <br/> |"rId #"  <br/> Weitere Informationen finden Sie in der "Anmerkungen".  <br/> |
   
## <a name="remarks"></a>Hinweise

Der Wert des **r:ID** -Attributs muss ein **ST_RelationshipID** -Typ sein. Der **ST_RelationshipID** -Typ ist eine Zeichenfolge, die im Format "rId #" sein muss, wobei das letzte Zeichen eine Zahl sein muss. Die Zahl muss unter allen gleichgeordneten Elementen des **rel** -Elements eindeutig sein. 
  
Weitere Informationen zum ST_RelationshipID-Typ finden Sie in der [Spezifikation ISO/IEC 29500 Part 1](https://www.iso.org/iso/home/store/catalogue_tc/catalogue_detail.md?csnumber=61750).
  

