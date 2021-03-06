---
title: Übersicht über multidimensionale Schemas und Daten
TOCTitle: Overview of multidimensional schemas and data
ms:assetid: a963e993-b7bf-eeb4-ecd5-d6fe43cf4bb5
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249784(v=office.15)
ms:contentKeyID: 48546923
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: d65378bf964ad8c6e81a08cb653f09bf00a8431c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288154"
---
# <a name="overview-of-multidimensional-schemas-and-data"></a>Übersicht über multidimensionale Schemas und Daten

**Gilt für**: Access 2013, Office 2013

## <a name="understanding-multidimensional-schemas"></a>Grundlegendes zu multidimensionalen Schemas

Das zentrale Metadatenobjekt in ADO MD ist der *Cube*, der aus einer strukturierten Menge verwandter Dimensionen, Hierarchien, Ebenen und Elementen besteht.

Eine *Dimension* ist eine unabhängige Kategorie mit Daten aus der multidimensionalen Datenbank, die von Ihren Geschäftsentitäten abgeleitet wird. Eine Dimension enthält normalerweise Elemente, die als Abfragekriterien für die Maßeinheiten der Datenbank verwendet werden.

Eine *Hierarchie* ist ein Aggregationspfad einer Dimension. Eine Dimension kann mehrere Granularitätsebenen haben, die jeweils Beziehungen zwischen unter- und übergeordneten Elementen haben. Eine Hierarchie definiert, wie diese Ebenen miteinander verwandt sind.

Eine *Ebene* ist ein Aggregationsschritt in einer Hierarchie. Bei Dimensionen mit mehreren Informationsschichten stellt jede Schicht eine Ebene dar.

Ein *Element* ist ein Datenelement in einer Dimension. In der Regel erstellen Sie eine Beschriftung oder beschreiben Sie eine Maßeinheit der Datenbank, die Elemente verwendet.

Cubes werden durch [CubeDef](cubedef-object-ado-md.md)-Objekte in ADO MD dargestellt. Dimensionen, Hierarchien, Ebenen und Elemente werden ebenfalls durch die entsprechenden ADO MD-Objekte dargestellt: [Dimension](dimension-object-ado-md.md), [Hierarchy](hierarchy-object-ado-md.md), [Level](level-object-ado-md.md) und [Member](member-object-ado-md.md).

## <a name="dimensions"></a>Maße

Die Dimensionen eines Cubes hängen von Ihren Geschäftsentitäten und den Arten der Daten ab, die in der Datenbank dargestellt werden. In der Regel ist jede Dimension ein unabhängiger Einstiegspunkt oder Mechanismus zum Auswählen von Daten.

Ein Cube mit Verkaufsdaten enthält beispielsweise die folgenden fünf Dimensionen: Verkaufsberater, Geografie, Zeit, Artikel und Maßeinheiten. Die Dimension für Maßeinheiten enthält Werte der tatsächlichen Verkaufsdaten, während die anderen Dimensionen Möglichkeiten darstellen, die Verkaufsdatenwerte zu gruppieren und in Kategorien zu unterteilen.

Die Dimension für die Geografie enthält die folgenden Elementgruppen:

```text
 
{All, North America, Europe, Canada, USA, UK, Germany, Canada-West, 
Canada-East, USA-NW, USA-SW, USA-NE, USA-SE, England, Scotland,  
Wales,Ireland, Germany-North, Germany-South, Ottawa, Toronto,  
Vancouver, Calgary, Seattle, Boise, Los Angeles, Houston,  
Shreveport, Miami, Boston, New York, London, Dover, Glasgow,  
Edinburgh, Cardiff, Pembroke, Belfast, Berlin,  
Hamburg, Munich, Stuttgart} 
```

## <a name="hierarchies"></a>Hierarchien

Hierarchien definieren die Möglichkeiten, die Ebenen einer Dimension zusammenzufassen oder zu gruppieren. Eine Dimension kann mehrere Hierarchien enthalten.

## <a name="levels"></a>Abstufungen

Im oben dargestellten Beispiel der Dimension für die Geografie steht jedes Feld für eine Ebene in der Hierarchie.

Jede Ebene enthält eine Gruppe von Elementen:

  - Welt = {All}


  - Kontinente = {Nordamerika, Europa}

  - Länder = {Canada, USA, UK, Deutschland}

  - Regionen = {Canada-East, Canada-West, USA-NE, USA-NW, USA-SE, USA-SW, England, Irland, Schottland, Wales, Deutschland-Nord, Deutschland-Süd}

  - Städte = {Ottawa, Toronto, Vancouver, Calgary, Seattle, Boise, Los Angeles, Houston, Shreveport, Miami, Boston, New York, London, Dover, Glasgow, Edinburgh, Cardiff, Pembroke, Belfast, Hamburg, Berlin

## <a name="members"></a>Elemente

Elemente auf der Blattebene einer Hierarchie haben keine untergeordneten Elemente, und Elemente auf der Stammebene haben keine übergeordneten Elemente. Alle anderen Elemente haben mindestens ein über- und ein untergeordnetes Element. Wenn beispielsweise die Hierarchiestruktur in der Dimension für die Geografie teilweise durchquert wird, werden folgende Beziehungen zwischen unter- und übergeordneten Elementen gefunden:

- Alle (übergeordnetes Element von) {Europa, Nordamerika}
- {Nordamerika} (übergeordnetes Element von) {Kanada, USA}
- USA (übergeordnetes Element von) {USA-NE, USA-NW, USA-SE, USA-SW}
- {USA-NW} (übergeordnetes Element von) {Boise, Seattle}

Elemente können entlang einer oder mehrerer Hierarchien pro Dimension konsolidiert werden.

In diesem Beispiel wird auch ein weiteres Merkmal veranschaulicht: einige Elemente der Wochenebene der Year-Week-Hierarchie werden nicht auf einer beliebigen Ebene der Year-Quarter-Hierarchie angezeigt. Eine Hierarchie muss also nicht alle Elemente einer Dimension enthalten.

## <a name="understanding-multidimensional-schemas"></a>Grundlegendes zu multidimensionalen Schemas

Das zentrale Metadatenobjekt in ADO MD ist der *Cube*, der aus einer strukturierten Menge verwandter Dimensionen, Hierarchien, Ebenen und Elementen besteht.

Eine *Dimension* ist eine unabhängige Kategorie mit Daten aus der multidimensionalen Datenbank, die von Ihren Geschäftsentitäten abgeleitet wird. Eine Dimension enthält normalerweise Elemente, die als Abfragekriterien für die Maßeinheiten der Datenbank verwendet werden.

Eine *Hierarchie* ist ein Aggregationspfad einer Dimension. Eine Dimension kann mehrere Granularitätsebenen haben, die jeweils Beziehungen zwischen unter- und übergeordneten Elementen haben. Eine Hierarchie definiert, wie diese Ebenen miteinander verwandt sind.

Eine *Ebene* ist ein Aggregationsschritt in einer Hierarchie. Bei Dimensionen mit mehreren Informationsschichten stellt jede Schicht eine Ebene dar.

Ein *Element* ist ein Datenelement in einer Dimension. In der Regel erstellen Sie eine Beschriftung oder beschreiben Sie eine Maßeinheit der Datenbank, die Elemente verwendet.

Cubes werden durch [CubeDef](cubedef-object-ado-md.md)-Objekte in ADO MD dargestellt. Dimensionen, Hierarchien, Ebenen und Elemente werden ebenfalls durch die entsprechenden ADO MD-Objekte dargestellt: [Dimension](dimension-object-ado-md.md), [Hierarchy](hierarchy-object-ado-md.md), [Level](level-object-ado-md.md) und [Member](member-object-ado-md.md).

## <a name="dimensions"></a>Maße

Die Dimensionen eines Cubes hängen von Ihren Geschäftsentitäten und den Arten der Daten ab, die in der Datenbank dargestellt werden. In der Regel ist jede Dimension ein unabhängiger Einstiegspunkt oder Mechanismus zum Auswählen von Daten.

Ein Cube mit Verkaufsdaten enthält beispielsweise die folgenden fünf Dimensionen: Verkaufsberater, Geografie, Zeit, Artikel und Maßeinheiten. Die Dimension für Maßeinheiten enthält Werte der tatsächlichen Verkaufsdaten, während die anderen Dimensionen Möglichkeiten darstellen, die Verkaufsdatenwerte zu gruppieren und in Kategorien zu unterteilen.

Die Dimension für die Geografie enthält die folgenden Elementgruppen:

```text 
 
{All, North America, Europe, Canada, USA, UK, Germany, Canada-West, 
Canada-East, USA-NW, USA-SW, USA-NE, USA-SE, England, Scotland,  
Wales,Ireland, Germany-North, Germany-South, Ottawa, Toronto,  
Vancouver, Calgary, Seattle, Boise, Los Angeles, Houston,  
Shreveport, Miami, Boston, New York, London, Dover, Glasgow,  
Edinburgh, Cardiff, Pembroke, Belfast, Berlin,  
Hamburg, Munich, Stuttgart} 
```

## <a name="hierarchies"></a>Hierarchien

Hierarchien definieren die Möglichkeiten, die Ebenen einer Dimension zusammenzufassen oder zu gruppieren. Eine Dimension kann mehrere Hierarchien enthalten.

## <a name="levels"></a>Abstufungen

Im oben dargestellten Beispiel der Dimension für die Geografie steht jedes Feld für eine Ebene in der Hierarchie.

Jede Ebene enthält eine Gruppe von Elementen:

- Welt = {All}


- Kontinente = {Nordamerika, Europa}

- Länder = {Canada, USA, UK, Deutschland}

- Regionen = {Canada-East, Canada-West, USA-NE, USA-NW, USA-SE, USA-SW, England, Irland, Schottland, Wales, Deutschland-Nord, Deutschland-Süd}

- Städte = {Ottawa, Toronto, Vancouver, Calgary, Seattle, Boise, Los Angeles, Houston, Shreveport, Miami, Boston, New York, London, Dover, Glasgow, Edinburgh, Cardiff, Pembroke, Belfast, Hamburg, Berlin

## <a name="members"></a>Elemente

Elemente auf der Blattebene einer Hierarchie haben keine untergeordneten Elemente, und Elemente auf der Stammebene haben keine übergeordneten Elemente. Alle anderen Elemente haben mindestens ein über- und ein untergeordnetes Element. Wenn beispielsweise die Hierarchiestruktur in der Dimension für die Geografie teilweise durchquert wird, werden folgende Beziehungen zwischen unter- und übergeordneten Elementen gefunden:

- Alle (übergeordnetes Element von) {Europa, Nordamerika}

- {Nordamerika} (übergeordnetes Element von) {Kanada, USA}

- USA (übergeordnetes Element von) {USA-NE, USA-NW, USA-SE, USA-SW}

- {USA-NW} (übergeordnetes Element von) {Boise, Seattle}

Elemente können entlang einer oder mehrerer Hierarchien pro Dimension konsolidiert werden.

In diesem Beispiel wird auch ein weiteres Merkmal veranschaulicht: einige Elemente der Wochenebene der Year-Week-Hierarchie werden nicht auf einer beliebigen Ebene der Year-Quarter-Hierarchie angezeigt. Eine Hierarchie muss also nicht alle Elemente einer Dimension enthalten.

