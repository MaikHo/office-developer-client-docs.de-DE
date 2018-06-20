---
title: Informationen zum Speichern von TZDEFINITION in ein Stream-Objekt an eine binäre Eigenschaft übermittelt werden
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 0dec535d-d48f-39a5-97d5-0bd109134b3b
description: Die Eigenschaften der Zeitzone, PidLidAppointmentTimeZoneDefinitionEndDisplay, PidLidAppointmentTimeZoneDefinitionRecur und PidLidAppointmentTimeZoneDefinitionStartDisplay sind binär benannte Eigenschaften, von denen jedes enthält einen Datenstrom, der zugeordnet ist die beibehaltenen Format einer TZDEFINITION Struktur.
ms.openlocfilehash: 8e00c7203e2a0adfdf9ff3e6dadff6485c8b5111
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2018
ms.locfileid: "19790917"
---
# <a name="about-persisting-tzdefinition-to-a-stream-to-commit-to-a-binary-property"></a><span data-ttu-id="987b1-103">Informationen zum Speichern von TZDEFINITION in ein Stream-Objekt an eine binäre Eigenschaft übermittelt werden</span><span class="sxs-lookup"><span data-stu-id="987b1-103">About persisting TZDEFINITION to a stream to commit to a binary property</span></span>

<span data-ttu-id="987b1-104">Die Eigenschaften der Zeitzone, [PidLidAppointmentTimeZoneDefinitionEndDisplay](http://msdn.microsoft.com/library/7b6193cb-612b-408e-b9bc-285df313e2cc%28Office.15%29.aspx), [PidLidAppointmentTimeZoneDefinitionRecur](http://msdn.microsoft.com/library/52fd57a0-9e34-4452-9ecd-2acb454446c9%28Office.15%29.aspx)und [PidLidAppointmentTimeZoneDefinitionStartDisplay](http://msdn.microsoft.com/library/08239670-3211-420c-99d7-0056ed967cb8%28Office.15%29.aspx) sind binäre benannte Eigenschaften, von denen jedes enthält einen Datenstrom, der die beibehaltenen Format einer [TZDEFINITION](tzdefinition.md) Struktur zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="987b1-104">The time zone properties, [PidLidAppointmentTimeZoneDefinitionEndDisplay](http://msdn.microsoft.com/library/7b6193cb-612b-408e-b9bc-285df313e2cc%28Office.15%29.aspx), [PidLidAppointmentTimeZoneDefinitionRecur](http://msdn.microsoft.com/library/52fd57a0-9e34-4452-9ecd-2acb454446c9%28Office.15%29.aspx), and [PidLidAppointmentTimeZoneDefinitionStartDisplay](http://msdn.microsoft.com/library/08239670-3211-420c-99d7-0056ed967cb8%28Office.15%29.aspx) are binary named properties, each of which contains a stream that maps to the persisted format of a [TZDEFINITION](tzdefinition.md) structure.</span></span> 
  
<span data-ttu-id="987b1-105">In diesem Thema wird ein little-endian-Format, die auf eine der drei binäre Eigenschaften commit für beim Speichern von **TZDEFINITION** in ein Stream-Objekt verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="987b1-105">This topic describes a little endian format that can be used when persisting **TZDEFINITION** to a stream to commit to one of three binary properties.</span></span> <span data-ttu-id="987b1-106">Verwenden Sie das gleiche endian-Format in ein Parser interpretiert einen Streamwert, der von einem der folgenden Eigenschaften abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="987b1-106">Use the same endian format in a parser to interpret a stream value obtained from one of these properties.</span></span> 
  
```cpp
BYTE  bMajorVersion;    // breaking change
BYTE  bMinorVersion;    // extensibility
WORD  cbHeader;         // size of following data until TZREG sub structure
WORD  wFlags;
if (TZDEFINITION_FLAG_VALID_GUID)
   GUID  guid;                // guid
if (TZDEFINITION_FLAG_VALID_KEYNAME)     
    WORD   cchKeyName;        // does not include null char
    WCHAR  rgchKeyName;       // not null terminated
    WORD  cRules;             // number of rules
// for each rule
   BYTE        bMajorVersion;         // breaking change
   BYTE        bMinorVersion;         // extensibility
   WORD        cbRule;                // size of following data
   WORD        wFlags;                // flags
   SYSTEMTIME  stStart;               // GMT when this rule starts
// Following are the fields of the TZREG sub structure
   long        lBias;                // offset from GMT
   long        lStandardBias;        // offset from bias during standard time
   long        lDaylightBias;        // offset from bias during daylight time
   SYSTEMTIME  stStandardDate;       // time to switch to standard time
   SYSTEMTIME  stDaylightDate;       // time to switch to daylight time
```

<span data-ttu-id="987b1-107">Die Nummer der Hauptversion wird verwendet, um stellen eine wichtige ändern.</span><span class="sxs-lookup"><span data-stu-id="987b1-107">The major version number is used to make a breaking change.</span></span> <span data-ttu-id="987b1-108">Clients, die mit die Hauptversionsnummer nicht vertraut sind, sollten die-Eigenschaft behandeln, sofern er nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="987b1-108">Clients that are unfamiliar with the major version number should treat the property as if it is not there.</span></span> <span data-ttu-id="987b1-109">Schreiben die Struktur Clients sollten die Konstante **TZ_BIN_VERSION_MAJOR**angeben.</span><span class="sxs-lookup"><span data-stu-id="987b1-109">Clients writing the structure should specify the constant **TZ_BIN_VERSION_MAJOR**.</span></span> 
  
<span data-ttu-id="987b1-110">Die Nummer der Nebenversion wird für die Erweiterbarkeit verwendet.</span><span class="sxs-lookup"><span data-stu-id="987b1-110">The minor version number is used for extensibility.</span></span> <span data-ttu-id="987b1-111">Clients, die mit der Nummer der Nebenversion nicht vertraut sind, sollten die Daten lesen, die sie verstehen, und überspringen die Daten, die jeder Regel oder in der gesamten Stream-Objekt angefügt werden soll möglicherweise.</span><span class="sxs-lookup"><span data-stu-id="987b1-111">Clients that are unfamiliar with the minor version number should read the data that they understand, and skip over the data that might be appended to each rule or to the overall stream.</span></span> <span data-ttu-id="987b1-112">Schreiben die Struktur Clients sollten die Konstante **TZ_BIN_VERSION_MINOR**angeben.</span><span class="sxs-lookup"><span data-stu-id="987b1-112">Clients writing the structure should specify the constant **TZ_BIN_VERSION_MINOR**.</span></span> 
  
<span data-ttu-id="987b1-113">Wenn ein Parser nicht die Hauptversion der Kopfzeile verstehen, muss Sie nicht den Rest der Struktur lesen und Verhalten, als ob die Daten nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="987b1-113">If a parser does not understand the major version of the header, it should not read the rest of the structure and behave as if the data is missing.</span></span> <span data-ttu-id="987b1-114">Wenn ein Parser nicht die Nebenversion der Kopfzeile verstehen, sollte **CbHeader** verwenden, um die Teile, die nicht erkannt und Advance, die Teile des Stream-Objekts lesen, die es versteht ignorieren.</span><span class="sxs-lookup"><span data-stu-id="987b1-114">If a parser does not understand the minor version of the header, it should use **cbHeader** to ignore the portions that it does not understand and advance to read the portions of the stream that it understands.</span></span> 
  
<span data-ttu-id="987b1-115">Der Wert der **wFlags** ist immer **TZDEFINITION_FLAG_VALID_KEYNAME**.</span><span class="sxs-lookup"><span data-stu-id="987b1-115">The value of **wFlags** is always **TZDEFINITION_FLAG_VALID_KEYNAME**.</span></span> <span data-ttu-id="987b1-116">Der Name des Schlüssels weist eine maximale Größe von **MAX_PATH**.</span><span class="sxs-lookup"><span data-stu-id="987b1-116">The key name has a maximum size of **MAX_PATH**.</span></span> 
  
<span data-ttu-id="987b1-117">Wenn ein Parser die Hauptversion einer Regel nicht erkannt wird, sollte der Client die Regel ignoriert und **CbRule** verwenden, um die Regel der nächsten zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="987b1-117">If a parser does not recognize the major version of a rule, the client should ignore the rule, and use **cbRule** to advance to the next rule.</span></span> <span data-ttu-id="987b1-118">Wenn ein Parser die Nebenversion einer Regel nicht erkannt wird, sollte der Client nur die Teile der Regel analysieren, die es versteht.</span><span class="sxs-lookup"><span data-stu-id="987b1-118">If a parser does not recognize the minor version of a rule, the client should only parse the parts of the rule that it understands.</span></span> 
  
<span data-ttu-id="987b1-119">Wenn eine **TZDEFINITION** -Struktur in einem Stream-Objekt gespeichert, sollten ein Parser keine Informationen zu schreiben, die nicht erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="987b1-119">When persisting a **TZDEFINITION** structure to a stream, a parser should not try to write any information that it does not understand.</span></span> 
  
<span data-ttu-id="987b1-120">Die maximale Anzahl von Regeln lautet 1024.</span><span class="sxs-lookup"><span data-stu-id="987b1-120">The maximum number of rules is 1024.</span></span>
  
<span data-ttu-id="987b1-121">Beachten Sie, dass die Struktur [TZREG](tzreg.md) hier anders beibehalten wird, als wenn alleine beibehalten, also desselben Codes verwendet werden kann, es zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="987b1-121">Note that the [TZREG](tzreg.md) structure is persisted here differently than when persisted alone, so the same code cannot be used to parse it.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="987b1-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="987b1-122">See also</span></span>

- [<span data-ttu-id="987b1-123">Konstanten (Outlook exportierter APIs)</span><span class="sxs-lookup"><span data-stu-id="987b1-123">Constants (Outlook exported APIs)</span></span>](constants-outlook-exported-apis.md)
- [<span data-ttu-id="987b1-124">Analysieren Sie einen Datenstrom aus eine binäre Eigenschaft zum Lesen der TZDEFINITION-Struktur</span><span class="sxs-lookup"><span data-stu-id="987b1-124">Parse a stream from a binary property to read the TZDEFINITION structure</span></span>](how-to-parse-stream-from-binary-property-to-read-tzdefinition-structure.md)
- [<span data-ttu-id="987b1-125">Lesen Sie Zeitzone Eigenschaften, ausgehend von einem Termin</span><span class="sxs-lookup"><span data-stu-id="987b1-125">Read time zone properties from an appointment</span></span>](how-to-read-time-zone-properties-from-an-appointment.md)
