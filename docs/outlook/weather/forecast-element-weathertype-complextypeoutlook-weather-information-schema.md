---
title: Forecast-Element (weathertype complexType) (Outlook-Wetter Informations Schema)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 9124fa30-d58b-8354-91e9-8d2237a8251d
description: 'Gibt die zukünftigen Wetterbedingungen von mindestens drei Tagen voraus, einschließlich heute: heute, morgen, Tag nach morgen.'
ms.openlocfilehash: 5e442ee5995bbd51c5e518162286bc199a625dbd
ms.sourcegitcommit: e7b38e37a9d79becfd679e10420a19890165606d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "34540980"
---
# <a name="forecast-element-weathertype-complextype-outlook-weather-information-schema"></a>Forecast-Element (weathertype complexType) (Outlook-Wetter Informations Schema)

Gibt die zukünftigen Wetterbedingungen von mindestens drei Tagen voraus, einschließlich heute: heute, morgen, Tag nach morgen.
  
## <a name="element-information"></a>Informationen zum Element

|||
|:-----|:-----|
|**Elementtyp** <br/> |[forecasttype](forecasttype-complextype-outlook-weather-information-schema.md) <br/> |
|**Namespace** <br/> |http://schemas.microsoft.com/office/outlook/15/getweatherinfo.xsd  <br/> |
|**Schemadatei** <br/> |GetWeatherInfo. xsd  <br/> |
   
## <a name="definition"></a>Definition

```XML
<xs:element name="forecast"      type="forecastType" minOccurs="3"     maxOccurs="unbounded"    >
  </xs:element>  

```

## <a name="elements-and-attributes"></a>Elemente und Attribute

Wenn das Schema bestimmte Anforderungen wie **Sequence**, **minOccurs**, **maxOccurs**und **Choice**definiert, lesen Sie den Abschnitt Definition. 
  
### <a name="parent-elements"></a>Übergeordnete Elemente

|**Element**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|[Wetter](weather-element-weatherdata-elementoutlook-weather-information-schema.md) <br/> |[weathertype](weathertype-complextype-outlook-weather-information-schema.md) <br/> |Gibt die Wetterbedingungen eines Standorts an.  <br/> |
   
### <a name="child-elements"></a>Untergeordnete Elemente

Keine.
  
### <a name="attributes"></a>Attribute

|**Attribut**|**Typ**|**Erforderlich**|**Beschreibung**|**Mögliche Werte**|
|:-----|:-----|:-----|:-----|:-----|
|date  <br/> |xs: Datum  <br/> |erforderlich  <br/> |Gibt das Datum für die Prognose an.  <br/> |Ein Wert vom Typ xs: Date  <br/> |
|Tag  <br/> |xs: Zeichenfolge  <br/> |erforderlich  <br/> |Gibt einen Tag für die Prognose an.  <br/> |Ein Wert vom Typ xs: String  <br/> |
|hohe  <br/> |xs: Integer  <br/> |erforderlich  <br/> |Gibt die prognostizierte höchste Temperatur an.  <br/> |Ein Wert vom Typ xs: Integer  <br/> |
|niedrigen  <br/> |xs: Integer  <br/> |erforderlich  <br/> |Gibt die prognostizierte niedrigste Temperatur an.  <br/> |Ein Wert vom Typ xs: Integer  <br/> |
|Precip  <br/> |xs: Integer  <br/> |erforderlich  <br/> |Gibt den Prozentsatz der Niederschlagswahrscheinlichkeit an.  <br/> |Ein Wert vom Typ xs: Integer  <br/> |
|shortday  <br/> |xs: Zeichenfolge  <br/> |erforderlich  <br/> |Gibt einen Tag in abgekürzter Form an.  <br/> |Ein Wert vom Typ xs: String  <br/> |
|skycodeday  <br/> |xs: Integer  <br/> |erforderlich  <br/> |Gibt einen Code für die prognostizierten Bedingungen an.  <br/> |Ein Wert vom Typ xs: Integer  <br/> |
|skytextday  <br/> |xs: Zeichenfolge  <br/> |erforderlich  <br/> |Gibt ein bis zwei Wörter an, die die prognostizierten Bedingungen beschreiben.  <br/> |Ein Wert vom Typ xs: String  <br/> |
   

