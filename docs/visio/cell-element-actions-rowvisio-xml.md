---
title: Cell-Element (Actions Row) (Visio XML)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 5ae2b4db-03f4-1b8a-1274-7eb1521f2f59
description: Gibt eine Eigenschaft einer Aktion an, die einem benutzerdefinierten Befehl in einem Kontext-oder Aktionstags Menü zugeordnet ist.
ms.openlocfilehash: 8cce85bdfb7d0ce54d968e00cda56e4e6c2455bc
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "34538781"
---
# <a name="cell-element-actions-row-visio-xml"></a>Cell-Element (Actions Row) (Visio XML)

Gibt eine Eigenschaft einer Aktion an, die einem benutzerdefinierten Befehl in einem Kontext-oder Aktionstags Menü zugeordnet ist.
  
## <a name="element-information"></a>Informationen zum Element

|||
|:-----|:-----|
|**Elementtyp** <br/> |[Cell_Type](cell_type-complextypevisio-xml.md) <br/> |
|**Namespace** <br/> |http://schemas.microsoft.com/office/visio/2012/main  <br/> |
|**Schemadatei** <br/> |VisioSchema15. xsd  <br/> |
|**Dokumentteile** <br/> |Masters. XML, Master #. XML, Pages. XML, Page #. XML  <br/> |
   
## <a name="definition"></a>Definition

```XML
< xs:element name="Cell" type="Cell_Type" minOccurs="0" maxOccurs="unbounded" >
</xs:element >
```

## <a name="elements-and-attributes"></a>Elemente und Attribute

Wenn das Schema bestimmte Anforderungen wie **Sequence**, **minOccurs**, **maxOccurs**und **Choice**definiert, lesen Sie den Abschnitt Definition. 
  
### <a name="parent-elements"></a>Übergeordnete Elemente

|**Element**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|[Row-Element (Actions section)](row-element-actions-sectionvisio-xml.md) <br/> |[ActionsRow_Type](actionsrow_type-complextypevisio-xml.md) <br/> |Gibt eine Eigenschaft einer Aktion an, die einem benutzerdefinierten Befehl in einem Kontext-oder Aktionstags Menü zugeordnet ist.  <br/> |
   
### <a name="child-elements"></a>Untergeordnete Elemente

|**Element**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|[RefBy](refby-element-cell_type-complextypevisio-xml.md) <br/> |[RefBy_Type](refby_type-complextypevisio-xml.md) <br/> |Gibt einen Verweis auf ein Zeichenblatt an.  <br/> |
   
### <a name="attributes"></a>Attribute

|**Attribut**|**Typ**|**Erforderlich**|**Beschreibung**|**Mögliche Werte**|
|:-----|:-----|:-----|:-----|:-----|
|E  <br/> |XSD: Zeichenfolge  <br/> |Optional  <br/> |Gibt an, dass die Formel zu einem Fehler ausgewertet wird. Der Wert von **E** ist der aktuelle Wert (eine Fehler Meldungszeichenfolge); der Wert des **V** -Attributs ist der letzte gültige Wert.  <br/> |Eine Fehler Meldungszeichenfolge.  <br/> |
|F  <br/> |XSD: Zeichenfolge  <br/> |Optional  <br/> | Stellt die Formel des Elements dar. Dieses Attribut kann eine der folgenden Zeichenfolgen enthalten:  <br/>  "(eine Formel)", wenn die Formel lokal vorhanden ist  <br/>  `No Formula`Wenn die Formel lokal gelöscht oder blockiert wird  <br/>  `Inh`, wenn die Formel vererbt wird.  <br/> |Eine Formel.  <br/> |
|N  <br/> |XSD: Zeichenfolge  <br/> |erforderlich  <br/> |Stellt den Namen der ShapeSheet-Zelle dar.  <br/> |Der Name der ShapeSheet-Zelle.  <br/> Weitere Informationen finden Sie im Abschnitt "Hinweise" weiter unten.  <br/> |
|U  <br/> |XSD: Zeichenfolge  <br/> |Optional  <br/> |Stellt eine Maßeinheit dar, bei der es sich bei der Standardeinstellung um DL handelt.  <br/> |Die Einheiten der Zelle.  <br/> |
|V  <br/> |XSD: Zeichenfolge  <br/> |Optional  <br/> |Stellt den Wert der Zelle dar.  <br/> |Der Wert der ShapeSheet-Zelle.  <br/> |
   
## <a name="remarks"></a>Hinweise

Das **N** -Attribut dieses **Cell** -Elements muss einer der begrenzten Werte sein, die ShapeSheet-Zellen entsprechen. In der folgenden Tabelle können Sie die Werte des **N** -Attributs bestimmen, die für dieses **Zellen** Element zulässig sind. 
  
|**Wert**|**Beschreibung**|**Weitere Informationen**|
|:-----|:-----|:-----|
|Aktion  <br/> |Enthält die Formel, die ausgeführt werden soll, wenn ein Benutzer einen Befehl in einem Kontext- oder Aktionstagmenü auswählt.  <br/> |[Zelle "Action" (Abschnitt "Actions")](action-cell-actions-section.md) <br/> |
|BeginGroup  <br/> |Gibt an, ob über dieser Aktion ein Trennzeichen in das Menü eingefügt wird.  <br/> |[Zelle "BeginGroup" (Abschnitt "Actions")](begingroup-cell-actions-section.md) <br/> |
|ButtonFace  <br/> |Bestimmt das Symbol, das neben einem Element in einem Kontext- oder Aktionstagmenü angezeigt wird.  <br/> |[Zelle "ButtonFace" (Abschnitt "Actions")](buttonface-cell-actions-section.md) <br/> |
|Checked  <br/> |Gibt an, ob ein Element im Kontext- oder Aktionstagmenü aktiviert ist.  <br/> |[Zelle "Checked" (Abschnitt "Actions")](checked-cell-actions-section.md) <br/> |
|Deaktiviert  <br/> |Gibt an, ob ein Element in einem Kontext- oder Aktionstagmenü deaktiviert ist.  <br/> |[Zelle "Disabled" (Abschnitt "Actions")](disabled-cell-actions-section.md) <br/> |
|FlyoutChild  <br/> |Bestimmt, ob die Zeile ein untergeordnetes Erweiterungsmenü der letzten Zeile oberhalb befindlichen Zeile ist, bei der es sich nicht um eine untergeordnete Erweiterung handelt.  <br/> |[FlyoutChild Cell (Actions section)](flyoutchild-cell-actions-section.md) <br/> |
|Invisible  <br/> |Zeigt an, ob die Aktion im Aktionstag- oder Kontextmenü sichtbar ist.  <br/> |[Zelle "Invisible" (Abschnitt "Actions")](invisible-cell-actions-section.md) <br/> |
|Menü  <br/> |Definiert den Namen eines Menüelements, das in einem Kontext- oder Aktionstagmenü für ein Shape oder Zeichenblatt angezeigt wird.  <br/> |[Zelle "Menu" (Abschnitt "Actions")](menu-cell-actions-section.md) <br/> |
|ReadOnly  <br/> |Steuert, ob die Aktion in einem Aktionstag- oder Kontextmenü schreibgeschützt ist.  <br/> |[Zelle "ReadOnly" (Abschnitt "Actions")](readonly-cell-actions-section.md) <br/> |
|SortKey  <br/> |Eine Zahl, mit der die Reihenfolge von Aktionen bestimmt wird, die in einem Kontext- oder Aktionstagmenü angezeigt werden.  <br/> |[Zelle "SortKey" (Abschnitt "Actions") "SortKey" (Abschnitt "Actions")](sortkey-cell-actions-section.md) <br/> |
|Tagname  <br/> |Enthält den Namen des Aktionstags, mit dem diese Aktion verknüpft ist.  <br/> |[Zelle "TagName" (Abschnitt "Actions")](tagname-cell-actions-section.md) <br/> |
   

