---
title: Field. DefaultValue-Eigenschaft (DAO)
TOCTitle: DefaultValue Property
ms:assetid: 8a1c558b-c8f6-757d-c595-4e50b9b6ae3f
ms:mtpsurl: https://msdn.microsoft.com/library/Ff197092(v=office.15)
ms:contentKeyID: 48546185
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 18fb4d3a4427db2b407b6a20507339fe83665c97
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32293119"
---
# <a name="fielddefaultvalue-property-dao"></a><span data-ttu-id="372f0-102">Field. DefaultValue-Eigenschaft (DAO)</span><span class="sxs-lookup"><span data-stu-id="372f0-102">Field.DefaultValue property (DAO)</span></span>


<span data-ttu-id="372f0-103">**Gilt für**: Access 2013, Office 2013</span><span class="sxs-lookup"><span data-stu-id="372f0-103">**Applies to**: Access 2013, Office 2013</span></span>


<span data-ttu-id="372f0-p101">Legt den Standardwert eines **[Field](field-object-dao.md)** -Objekts fest oder gibt den Wert zurück. Bei einem **Field**-Objekt, das der **[Fields](fields-collection-dao.md)** -Auflistung noch nicht angefügt wurde, besteht für diese Eigenschaft Lese-/Schreibzugriff (gilt nur für Microsoft Access-Arbeitsbereiche).</span><span class="sxs-lookup"><span data-stu-id="372f0-p101">Sets or returns the default value of a **[Field](field-object-dao.md)** object. For a **Field** object not yet appended to the **[Fields](fields-collection-dao.md)** collection, this property is read/write (Microsoft Access workspaces only).</span></span>

## <a name="syntax"></a><span data-ttu-id="372f0-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="372f0-106">Syntax</span></span>

<span data-ttu-id="372f0-107">*Ausdruck* . DefaultValue</span><span class="sxs-lookup"><span data-stu-id="372f0-107">*expression* .DefaultValue</span></span>

<span data-ttu-id="372f0-108">*Ausdruck* Eine Variable, die ein **Field** -Objekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="372f0-108">*expression* A variable that represents a **Field** object.</span></span>

## <a name="remarks"></a><span data-ttu-id="372f0-109">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="372f0-109">Remarks</span></span>

<span data-ttu-id="372f0-p102">Die Einstellung oder der Rückgabewert ist vom Datentyp **String** und kann maximal 255 Zeichen enthalten. Es kann sich um einen Text oder einen Ausdruck handeln. Ist die Eigenschafteneinstellung ein Ausdruck, kann er benutzerdefinierte Funktionen, SQL-Aggregatfunktionen des Microsoft Access-Datenbankmoduls oder Verweise auf Abfragen, Formulare oder andere **Field**-Objekte enthalten.</span><span class="sxs-lookup"><span data-stu-id="372f0-p102">The setting or return value is a **String** data type that can contain a maximum of 255 characters. It can be either text or an expression. If the property setting is an expression, it can't contain user-defined functions, Microsoft Access database engine SQL aggregate functions, or references to queries, forms, or other **Field** objects.</span></span>


> [!NOTE]
> <span data-ttu-id="372f0-113">[!HINWEIS] Sie können die **DefaultValue**-Eigenschaft eines **Field**-Objekts für ein [TableDef](tabledef-object-dao.md) -Objekt auch auf einen speziellen Wert, "GenUniqueID( )" genannt, festlegen.</span><span class="sxs-lookup"><span data-stu-id="372f0-113">You can also set the **DefaultValue** property of a **Field** object on a [TableDef](tabledef-object-dao.md) object to a special value called "GenUniqueID( )".</span></span> <span data-ttu-id="372f0-114">Dabei wird diesem Feld eine Zufallszahl zugewiesen, sobald ein neuer Datensatz hinzugefügt oder erstellt wird, wodurch jeder Datensatz einen eindeutigen Bezeichner erhält.</span><span class="sxs-lookup"><span data-stu-id="372f0-114">This causes a random number to be assigned to this field whenever a new record is added or created, thereby giving each record a unique identifier.</span></span> <span data-ttu-id="372f0-115">Die [Type](field-type-property-dao.md)-Eigenschaft des Felds muss ein **Long**-Wert sein.</span><span class="sxs-lookup"><span data-stu-id="372f0-115">The field's [Type](field-type-property-dao.md) property must be **Long**.</span></span>


<span data-ttu-id="372f0-116">Die Verfügbarkeit der **DefaultValue**-Eigenschaft hängt vom Objekt ab, in dem die **Fields**-Auflistung enthalten ist (siehe folgende Tabelle).</span><span class="sxs-lookup"><span data-stu-id="372f0-116">The availability of the **DefaultValue** property depends on the object that contains the **Fields** collection, as shown in the following table.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="372f0-117">Zugehörigkeit der Fields-Auflistung</span><span class="sxs-lookup"><span data-stu-id="372f0-117">If the Fields collection belongs to an</span></span></p></th>
<th><p><span data-ttu-id="372f0-118">Verfügbarkeit von DefaultValue</span><span class="sxs-lookup"><span data-stu-id="372f0-118">Then DefaultValue is</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="372f0-119">Index-Objekt</span><span class="sxs-lookup"><span data-stu-id="372f0-119">Index object</span></span></p></td>
<td><p><span data-ttu-id="372f0-120">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="372f0-120">Not supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="372f0-121">QueryDef-Objekt</span><span class="sxs-lookup"><span data-stu-id="372f0-121">QueryDef object</span></span></p></td>
<td><p><span data-ttu-id="372f0-122">Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="372f0-122">Read-only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="372f0-123">Recordset-Objekt</span><span class="sxs-lookup"><span data-stu-id="372f0-123">Recordset object</span></span></p></td>
<td><p><span data-ttu-id="372f0-124">Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="372f0-124">Read-only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="372f0-125">Relation-Objekt</span><span class="sxs-lookup"><span data-stu-id="372f0-125">Relation object</span></span></p></td>
<td><p><span data-ttu-id="372f0-126">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="372f0-126">Not supported</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="372f0-127">TableDef-Objekt</span><span class="sxs-lookup"><span data-stu-id="372f0-127">TableDef object</span></span></p></td>
<td><p><span data-ttu-id="372f0-128">Lesen/Schreiben</span><span class="sxs-lookup"><span data-stu-id="372f0-128">Read/write</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="372f0-p104">Beim Erstellen eines neuen Datensatzes wird die Einstellung der **DefaultValue**-Eigenschaft automatisch als Wert für das Feld eingegeben. Sie können den Feldwert ändern, indem Sie seine **[Value](field-value-property-dao.md)** -Eigenschaft festlegen.</span><span class="sxs-lookup"><span data-stu-id="372f0-p104">When a new record is created, the **DefaultValue** property setting is automatically entered as the value for the field. You can change the field value by setting its **[Value](field-value-property-dao.md)** property.</span></span>

<span data-ttu-id="372f0-131">Die **DefaultValue**-Eigenschaft wird nicht auf Felder vom Datentyp **AutoNumber** oder **Long Binary** angewendet.</span><span class="sxs-lookup"><span data-stu-id="372f0-131">The **DefaultValue** property doesn't apply to **AutoNumber** and **Long Binary** fields.</span></span>

## <a name="example"></a><span data-ttu-id="372f0-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="372f0-132">Example</span></span>

<span data-ttu-id="372f0-p105">This example uses the **DefaultValue** property to alert the user of a field's normal value while prompting for input. In addition, it demonstrates how new records will be filled using **DefaultValue** in the absence of any other input. The DefaultPrompt function is required for this procedure to run.</span><span class="sxs-lookup"><span data-stu-id="372f0-p105">This example uses the **DefaultValue** property to alert the user of a field's normal value while prompting for input. In addition, it demonstrates how new records will be filled using **DefaultValue** in the absence of any other input. The DefaultPrompt function is required for this procedure to run.</span></span>

```vb
    Sub DefaultValueX() 
     
     Dim dbsNorthwind As Database 
     Dim tdfEmployees As TableDef 
     Dim strOldDefault As String 
     Dim rstEmployees As Recordset 
     Dim strMessage As String 
     Dim strCode As String 
     
     Set dbsNorthwind = OpenDatabase("Northwind.mdb") 
     Set tdfEmployees = dbsNorthwind.TableDefs!Employees 
     
     ' Store original DefaultValue information and set the 
     ' property to a new value. 
     strOldDefault = _ 
     tdfEmployees.Fields!PostalCode.DefaultValue 
     tdfEmployees.Fields!PostalCode.DefaultValue = "98052" 
     
     Set rstEmployees = _ 
     dbsNorthwind.OpenRecordset("Employees", _ 
     dbOpenDynaset) 
     
     With rstEmployees 
     ' Add a new record to the Recordset. 
     .AddNew 
     !FirstName = "Bruce" 
     !LastName = "Oberg" 
     
     ' Get user input. If user enters something, the field 
     ' will be filled with that data; otherwise, it will be 
     ' filled with the DefaultValue information. 
     strMessage = "Enter postal code for " & vbCr & _ 
     !FirstName & " " & !LastName & ":" 
     strCode = DefaultPrompt(strMessage, !PostalCode) 
     If strCode <> "" Then !PostalCode = strCode 
     .Update 
     
     ' Go to new record and print information. 
     .Bookmark = .LastModified 
     Debug.Print " FirstName = " & !FirstName 
     Debug.Print " LastName = " & !LastName 
     Debug.Print " PostalCode = " & !PostalCode 
     
     ' Delete new record because this is a demonstration. 
     .Delete 
     .Close 
     End With 
     
     ' Restore original DefaultValue property because this is a 
     ' demonstration. 
     tdfEmployees.Fields!PostalCode.DefaultValue = _ 
     strOldDefault 
     
     dbsNorthwind.Close 
     
    End Sub 
     
    Function DefaultPrompt(strPrompt As String, _ 
     fldTemp As Field) As String 
     
     Dim strFullPrompt As String 
     
     ' Ask user for new DefaultValue setting for the specified 
     ' Field object. 
     strFullPrompt = strPrompt & vbCr & _ 
     "[Default = " & fldTemp.DefaultValue & _ 
     ", Cancel - use default]" 
     DefaultPrompt = InputBox(strFullPrompt) 
     
    End Function
```
