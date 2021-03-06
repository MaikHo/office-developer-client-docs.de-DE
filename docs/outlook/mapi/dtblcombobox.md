---
title: DTBLCOMBOBOX
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.DTBLCOMBOBOX
api_type:
- COM
ms.assetid: 73b68614-6aca-4669-b879-5631c5d6483c
description: 'Letzte Änderung: Montag, 9. März 2015'
ms.openlocfilehash: 5256efbff734d4555ac263dd330e3349c789cd74
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406976"
---
# <a name="dtblcombobox"></a>DTBLCOMBOBOX

  
  
**Gilt für**: Outlook 2013 | Outlook 2016 
  
Beschreibt ein Kombinationsfeld-Steuerelement, das in einem von einer Anzeigetabelle erstellten Dialogfeldverwendet wird.
  
|||
|:-----|:-----|
|Headerdatei  <br/> |Mapidefs. h  <br/> |
|Zugehöriges Makro:  <br/> |[SizedDtblComboBox](sizeddtblcombobox.md) <br/> |
   
```cpp
typedef struct _DTBLCOMBOBOX
{
  ULONG ulbLpszCharsAllowed;
  ULONG ulFlags;
  ULONG ulNumCharsAllowed;
  ULONG ulPRPropertyName;
  ULONG ulPRTableName;
} DTBLCOMBOBOX, FAR *LPDTBLCOMBOBOX;

```

## <a name="members"></a>Members

 **ulbLpszCharsAllowed**
  
> Ein Offset vom Anfang der **DTBLCOMBOBOX** -Struktur zu einem Zeichenfolgenfilter, der ggf. Einschränkungen für die Zeichen beschreibt, die in das Bearbeitungssteuerelement des Kombinationsfelds eingegeben werden können. Der Filter wird nicht als regulärer Ausdruck interpretiert, und auf jedes eingegebene Zeichen wird derselbe Filter angewendet. Das Format des Filters lautet wie folgt: 
    
|**Zeichen**|**Beschreibung**|
|:-----|:-----|
| `*` <br/> |Ein beliebiges Zeichen ist zulässig (Beispiels `"*"`Weise).  <br/> |
| `[ ]` <br/> |Definiert eine Gruppe von Zeichen (beispielsweise `"[0123456789]"`).  <br/> |
| `-` <br/> |Gibt einen Zeichentyp an (beispielsweise `"[a-z]"`).  <br/> |
| `~` <br/> |Gibt an, dass diese Zeichen nicht zulässig sind. (Beispiel: `"[~0-9]"`).  <br/> |
| `\` <br/> |Wird verwendet, um eines der vorherigen Symbole zu zitieren ( `"[\-\\\[\]]"` beispielsweise sind \, means-, [und] characters zulässig).  <br/> |
   
 **ulFlags**
  
> Bitmaske von Flags, die zum Festlegen des Formats des Zeichenfolgen Filters verwendet werden. Das folgende Flag kann festgelegt werden:
    
MAPI_UNICODE 
  
> Der Filter ist im Unicode-Format. Wenn das MAPI_UNICODE-Flag nicht festgelegt ist, ist der Filter im ANSI-Format.
    
 **ulNumCharsAllowed**
  
> Maximale Anzahl von Zeichen, die in das Textfeld des Kombinationsfelds eingegeben werden können.
    
 **ulPRPropertyName**
  
> Property-Tag für eine Eigenschaft vom Typ PT_TSTRING. 
    
 **ulPRTableName**
  
> Property-Tag für eine Eigenschaft vom Typ PT_OBJECT, auf der eine **IMAPITable** -Schnittstelle mithilfe eines **OpenProperty** -Aufrufs geöffnet werden kann. Die Tabelle muss eine Spalte mit einer Eigenschaft aufweisen, die denselben Typ hat wie die Eigenschaft, die vom **ulPRPropertyName** -Element angegeben wird. Die Zeilen der Tabelle werden zum Auffüllen der Liste verwendet. 
    
## <a name="remarks"></a>Bemerkungen

Eine **DTBLCOMBOBOX** -Struktur beschreibt ein Kombinationsfeld ein Steuerelement, das aus einer Liste und einem Auswahlfeld besteht. In der Liste werden die Informationen angezeigt, aus denen ein Benutzer auswählen kann, und das Feldauswahl zeigt die aktuelle Auswahl an. Das Auswahlfeld ist ein Bearbeitungssteuerelement, mit dem auch Text eingegeben werden kann, der noch nicht in der Liste aufgeführt ist. 
  
Die beiden Elemente des Property-Tags arbeiten zusammen, um die Listenanzeige mit dem Bearbeitungssteuerelement zu koordinieren. Wenn MAPI das Kombinationsfeld zuerst anzeigt, wird die **OpenProperty** -Methode der **IMAPIProp** -Implementierung aufgerufen, die der Anzeigetabelle zugeordnet ist, um die vom **ulPRTableName** -Element dargestellte Tabelle abzurufen. Diese Tabelle enthält eine Spalte eine Spalte mit Werten für die vom **ulPRPropertyName** -Element dargestellte Eigenschaft. Daher muss diese Spalte denselben Typ wie die **ulPRPropertyName** -Eigenschaft aufweisen, und beide Spalten müssen Zeichenfolgen sein. 
  
Die Werte für die Spalte werden im Listenabschnitt des Kombinationsfelds angezeigt. Daher ist **PR_NULL** ([pidtagnull (](pidtagnull-canonical-property.md)) kein gültiges Property-Tag für **ulPRPropertyName**. Wenn ein Benutzer eine der Zeilen auswählt oder neue Daten in das Textfeld eingibt, wird die **ulPRPropertyName** -Eigenschaft auf den ausgewählten oder eingegebenen Wert festgelegt. 
  
Um einen Anfangswert für das Bearbeitungssteuerelement anzuzeigen, ruft MAPI [IMAPIProp::](imapiprop-getprops.md) GetProps auf, um die Eigenschaftswerte für die Anzeigetabelle abzurufen. Wenn eine der abgerufenen Eigenschaften mit der vom **ulPRPropertyName** -Element dargestellten Eigenschaft übereinstimmt, wird deren Wert zum Anfangswert. 
  
Eine Übersicht über Anzeige Tabellen finden Sie unter [Display Tables](display-tables.md). Weitere Informationen zum Implementieren einer Anzeigetabelle finden Sie unter [Implementieren einer Anzeigetabelle](display-table-implementation.md).
  
## <a name="see-also"></a>Siehe auch



[DTCTL](dtctl.md)
  
[Kanonische Pidtagcontroltype (-Eigenschaft](pidtagcontroltype-canonical-property.md)


[MAPI-Strukturen](mapi-structures.md)

