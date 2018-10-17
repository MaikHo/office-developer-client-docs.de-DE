---
title: GetRows-Methode (Beispiel) (VC++)
TOCTitle: GetRows Method Example (VC++)
ms:assetid: cfb28f6c-b2f0-2afb-f9ce-336f5a99104c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250034(v=office.15)
ms:contentKeyID: 48547817
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 8ac21076c9a6e3dc2a578e6790be051f2ffd9bcc
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2018
ms.locfileid: "25473505"
---
# <a name="getrows-method-example-vc"></a>GetRows-Methode (Beispiel) (VC++)


**Betrifft**: Access 2013 | Office 2013

In diesem Beispiel wird die GetRows-Methode verwendet, um eine angegebene Anzahl von Zeilen aus einem Recordset-Objekt abzurufen und um ein Array mit den resultierenden Daten aufzufüllen. Die GetRows-Methode gibt in zwei Fällen weniger als die gewünschte Anzahl von Zeilen zurück: wenn EOF erreicht wurde oder wenn GetRows versucht hat, einen Wert abzurufen, der von einem anderen Benutzer gelöscht wurde. Die Funktion gibt nur im zweiten Fall False zurück. Die GetRowsOK-Funktion ist erforderlich, damit dieser Vorgang ausgeführt werden kann.

```cpp 
 
// BeginGetRowsCpp 
#import "C:\Program Files\Common Files\System\ADO\msado15.dll" no_namespace rename("EOF", "EndOfFile") 
 
#include <stdio.h> 
#include <ole2.h> 
#include <conio.h> 
 
// Function Declarations 
inline void TESTHR(HRESULT x) {if FAILED(x) _com_issue_error(x);}; 
void GetRowsX(void); 
bool GetRowsOK(_RecordsetPtr pRstTemp,int intNumber, 
 _variant_t& avarData); 
void PrintProviderError(_ConnectionPtr pConnection); 
void PrintComError(_com_error &e); 
 
void main() 
{ 
 if(FAILED(::CoInitialize(NULL))) 
 return; 
 
 GetRowsX(); 
 
 ::CoUninitialize(); 
} 
 
/////////////////////////////////////////////////////////// 
// // 
// GetRowsX Function // 
// // 
/////////////////////////////////////////////////////////// 
 
void GetRowsX(void) 
{ 
 HRESULT hr = S_OK; 
 
 // Define string variables. 
 _bstr_t strCnn("Provider='sqloledb';Data Source='MySqlServer';" 
 "Initial Catalog='pubs';Integrated Security='SSPI';"); 
 
 // Define ADO object pointers. 
 // Initialize pointers on define. 
 // These are in the ADODB:: namespace. 
 _RecordsetPtr pRstEmployees = NULL; 
 
 try 
 { 
 // Open recordset with names and hire dates from employee table. 
 TESTHR(pRstEmployees.CreateInstance(__uuidof(Recordset))); 
 
 pRstEmployees->Open("SELECT fName, lName, hire_date " 
 "FROM Employee ORDER BY lName",strCnn, 
 adOpenStatic, adLockReadOnly,adCmdText); 
 
 
 while (true) //continuous loop 
 { 
 int intLines = 0; 
 
 // Get user input for number of rows. 
 printf("\nEnter number of rows to retrieve (0 to exit): "); 
 int intRows; 
 scanf("%d", &intRows); 
 
 if (intRows <= 0) 
 break; 
 
 //Clear the screen for the next display 
 system("cls"); 
 
 
 // If GetRowsOK is successful, print the results, 
 // noting if the end of the file was reached. 
 _variant_t avarRecords; 
 
 if (GetRowsOK(pRstEmployees, intRows, avarRecords)) 
 { 
 long lUbound; 
 HRESULT hr = SafeArrayGetUBound(avarRecords.parray, 
 2,&lUbound); 
 
 if (hr == 0) 
 { 
 if (intRows > lUbound + 1) 
 { 
 printf("\n(Not enough records in Recordset to " 
 "retrieve %d rows)\n", intRows); 
 } 
 } 
 printf("%d records found.", lUbound+1); 
 
 // Print the retrieved data. 
 for (int intRecords = 0;intRecords < lUbound+1; 
 intRecords++) 
 { 
 printf("\n "); 
 
 long rgIndices[2]; 
 rgIndices[0] = 0; 
 rgIndices[1] = intRecords; 
 _variant_t result; 
 result.vt = VT_BSTR; 
 
 hr= SafeArrayGetElement(avarRecords.parray, 
 rgIndices, &result); 
 
 if (hr == 0){printf("%s ",(LPCSTR)(_bstr_t)result);} 
 
 rgIndices[0] = 1; 
 
 hr= SafeArrayGetElement(avarRecords.parray, 
 rgIndices, &result); 
 
 if (hr == 0){printf("%s, ",(LPCSTR)(_bstr_t)result);} 
 
 rgIndices[0] = 2; 
 
 hr= SafeArrayGetElement(avarRecords.parray, 
 rgIndices, &result); 
 
 if (hr == 0){printf("%s",(LPCSTR)(_bstr_t)result);} 
 
 intLines ++; 
 
 if (intLines % 10 == 0) 
 { 
 printf("\nPress any key to continue..."); 
 getch(); 
 
 intLines = 0; 
 
 //Clear the screen for the next display 
 system("cls"); 
 } 
 } 
 } 
 else 
 { 
 // Assuming the GetRows error was due to data 
 // changes by another user, use Requery to 
 // refresh the Recordset and start over. 
 printf("GetRows failed--retry?\n"); 
 char chKey; 
 do 
 { 
 chKey = getch(); 
 }while(toupper(chKey) != 'Y' && toupper(chKey) != 'N'); 
 
 if(toupper(chKey) == 'Y') 
 { 
 pRstEmployees->Requery(adOptionUnspecified); 
 } 
 else 
 { 
 printf("GetRows failed!\n"); 
 break; 
 } 
 } 
 
 // Because using GetRows leaves the current 
 // record pointer at the last record accessed, 
 // move the pointer back to the beginning of the 
 // Recordset before looping back for another search. 
 pRstEmployees->MoveFirst(); 
 } 
 } 
 catch(_com_error &e) 
 { 
 // Notify the user of errors if any. 
 // Pass a connection pointer accessed from the Recordset. 
 _variant_t vtConnect = pRstEmployees->GetActiveConnection(); 
 
 // GetActiveConnection returns connect string if connection 
 // is not open, else returns Connection object. 
 switch(vtConnect.vt) 
 { 
 case VT_BSTR: 
 PrintComError(e); 
 break; 
 case VT_DISPATCH: 
 PrintProviderError(vtConnect); 
 break; 
 default: 
 printf("Errors occured."); 
 break; 
 } 
 } 
 
 //Clean up objects before exit. 
 if (pRstEmployees) 
 if (pRstEmployees->State == adStateOpen) 
 pRstEmployees->Close(); 
} 
 
bool GetRowsOK(_RecordsetPtr pRstTemp,int intNumber, 
 _variant_t& avarData) 
{ 
 // Store results of GetRows method in array. 
 avarData = pRstTemp->GetRows(intNumber); 
 
 // Return False only if fewer than the desired 
 // number of rows were returned, but not because the 
 // end of the Recordset was reached. 
 long lUbound; 
 HRESULT hr = SafeArrayGetUBound(avarData.parray,2,&lUbound); 
 if (hr == 0) 
 { 
 if ((intNumber > lUbound + 1) && (!(pRstTemp->EndOfFile))) 
 return false; 
 else 
 return true; 
 } 
 else 
 { 
 printf ("\nUnable to Get the Array's Upper Bound\n"); 
 return false; 
 } 
} 
 
/////////////////////////////////////////////////////////// 
// // 
// PrintProviderError Function // 
// // 
/////////////////////////////////////////////////////////// 
 
void PrintProviderError(_ConnectionPtr pConnection) 
{ 
 // Print Provider Errors from Connection object. 
 // pErr is a record object in the Connection's Error collection. 
 ErrorPtr pErr = NULL; 
 
 if( (pConnection->Errors->Count) > 0) 
 { 
 long nCount = pConnection->Errors->Count; 
 // Collection ranges from 0 to nCount -1. 
 for(long i = 0; i < nCount; i++) 
 { 
 pErr = pConnection->Errors->GetItem(i); 
 printf("\t Error number: %x\t%s", pErr->Number, 
 (LPCSTR) pErr->Description); 
 } 
 } 
} 
 
/////////////////////////////////////////////////////////// 
// // 
// PrintComError Function // 
// // 
/////////////////////////////////////////////////////////// 
 
void PrintComError(_com_error &e) 
{ 
 _bstr_t bstrSource(e.Source()); 
 _bstr_t bstrDescription(e.Description()); 
 
 // Print Com errors. 
 printf("Error\n"); 
 printf("\tCode = %08lx\n", e.Error()); 
 printf("\tCode meaning = %s\n", e.ErrorMessage()); 
 printf("\tSource = %s\n", (LPCSTR) bstrSource); 
 printf("\tDescription = %s\n", (LPCSTR) bstrDescription); 
} 
// EndGetRowsCpp 
```
