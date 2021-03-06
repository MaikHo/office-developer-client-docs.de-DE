---
title: Integrieren von Verwaltbarkeit-Anwendungen mit Office 365 Klick-und-Los-Installationsprogramm
manager: lindalu
ms.date: 10/22/2017
ms.audience: ITPro
localization_priority: Normal
ms.assetid: c0fa8fed-1585-4566-a9be-ef6d6d1b4ce8
description: Hier erfahren Sie, wie Sie das Office 365 Klick-und-Los-Installationsprogramm mit einer Software Verwaltungslösung integrieren.
ms.openlocfilehash: 0c695d538a0a906bce19719c2735cb39740ff6a2
ms.sourcegitcommit: 31b0a7373ff74fe1d6383c30bc67d7675b73d283
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2020
ms.locfileid: "41773736"
---
# <a name="integrating-manageability-applications-with-office-365-click-to-run-installer"></a>Integrieren von Verwaltbarkeit-Anwendungen mit Office 365 Klick-und-Los-Installationsprogramm

Hier erfahren Sie, wie Sie das Office 365 Klick-und-Los-Installationsprogramm mit einer Software Verwaltungslösung integrieren.
  
Das Office 365 Klick-und-Los-Installationsprogramm stellt eine COM-Schnittstelle bereit, die IT-Spezialisten und Software Verwaltungslösungen die programmgesteuerte Steuerung der Updateverwaltung ermöglicht. Diese Schnittstelle stellt zusätzliche Verwaltungsfunktionen bereit, die über das Office-Bereitstellungs Tool hinausgehen.
  
> [!NOTE]
> Dieser Artikel bezieht sich auf Office 2016 und höher, Office 365. 
  
## <a name="integrating-with-the-click-to-run"></a>Integrieren in das Klick-und-Los

Um diese Schnittstelle zu verwenden, ruft eine verwaltbare Anwendung die COM-Schnittstelle auf und ruft freigegebene APIs auf, die direkt mit dem Klick-und-Los-Installationsdienst kommunizieren. 
  
> [!NOTE]
> Das Office-Klick-und-Los-Installationsprogramm kann über die Befehlszeile mit Parametern ausgeführt werden, die das Verhalten steuern können, wie im [Office-Bereitstellungs Tool für Klick-und-Los](https://www.microsoft.com/download/details.aspx?id=49117)dokumentiert. 
  
**Es folgt ein konzeptionelles Diagramm der COM-Schnittstelle.**

![A diagram of using the COM interface on  the Office Click-To-Run installer.](media/e7ac2523-e67b-4a44-ae67-c048709f872a.png "Ein Diagramm zur Verwendung der COM-Schnittstelle im Office-Klick-und-Los-Installationsprogramm")
  
Das Office 365 Klick-und-Los-Installationsprogramm implementiert eine COM-basierte Schnittstelle, die für CLSID- **CLSID_UpdateNotifyObject**registriert **IUpdateNotify** .
  
Diese Schnittstelle kann wie folgt aufgerufen werden:
  
```cpp
hr = CoCreateInstance(CLSID_UpdateNotifyObject, NULL, CLSCTX_ALL,
       IID_IUpdateNotify, 
      (void **)&p); 
```

Der Anruf ist nur erfolgreich, wenn der Anrufer unter erhöhten Rechten ausgeführt wird, da das Installationsprogramm für die Klick-und-Los-Installation mit erhöhten Rechten ausgeführt werden muss.
  
Die **IUpdateNotify** -com-Schnittstelle stellt drei asynchrone Funktionen zur Verfügung, die für die Überprüfung der Befehle und Parameter und die Planung der Ausführung mit dem Klick-und-Los-Installationsdienst verantwortlich sind. 
  
```cpp
HRESULT Download([in] LPWSTR pcwszParameters) // Download update content.
HRESULT Apply([in] LPWSTR pcwszParameters) // Apply update content.
HRESULT Cancel() // Cancel the download action.

```

Eine Forth-Methode, **Status**, kann verwendet werden, um Informationen über den Status des zuletzt ausgeführten Befehls oder den Status des derzeit ausgeführten Befehls abzurufen (also Erfolg, Fehler, detaillierte Fehlercodes).
  
```cpp
HRESULT status([out] _UPDATE_STATUS_REPORT* pUpdateStatusReport) // Get status of current action. 
typedef struct _UPDATE_STATUS_REPORT  
{  
UPDATE_STATUS status;  
UINT error; 
BSTR contentid;  
} UPDATE_STATUS_REPORT;

```

Es gibt vier Zustände, in denen der Klick-und-Los-Installationsdienst während seines Lebenszyklus möglicherweise vorliegt, während dessen **IUpdateNotify** -Methoden aufgerufen werden können. Neustarten, Leerlauf, herunterladen und anwenden. 
  
**Im folgenden finden Sie das Diagramm "Statuscomputer" der COM-Schnittstelle**

![A state diagram for the COM interface.](media/a409003e-6876-4ab3-bb4c-cd0c0fed5cbb.png "Ein Statusdiagramm für die COM-Schnittstelle")
  
> [!NOTE]
> **Neustart: beim**Booten des Computers gibt es einen Zeitraum, in dem der Klick-und-Los-Installationsdienst nicht verfügbar ist. Ein erfolgreicher Aufruf der Status-Methode nach einem Neustart wird eUPDATE_UNKNOWN zurückgegeben. 
  
**Leerlauf:** Wenn sich das Klick-und-Los-Installationsprogramm im Leerlauf befindet, können Sie Folgendes aufrufen: 
  
- **Apply**: Installieren Sie zuvor heruntergeladenen Inhalt.
    
- **Cancel**: gibt `0x800000e`zurück, "eine Methode wurde zu einem unerwarteten Zeitpunkt aufgerufen."
    
- **Download**: lädt neue Inhalte zur späteren Installation auf den Client herunter.
    
- **Status**: gibt das Ergebnis der letzten abgeschlossenen Aktion oder eine Fehlermeldung zurück, wenn die Aktion mit einem Fehler beendet wurde. Wenn keine vorherige Aktion vorliegt, **** wird der `eUPDATE_UNKNOWN`Status zurückgegeben.
    
**Herunterladen:** Wenn sich das Klick-und-Los-Installationsprogramm im Download Zustand befindet, können Sie Folgendes aufrufen: 
  
- **Apply**: gibt ein **HRESULT** mit dem Wert `0x800000e`"eine Methode wurde zu einem unerwarteten Zeitpunkt aufgerufen." zurück.
    
- **Abbrechen**: beendet den Download und entfernt die teilweise heruntergeladenen Inhalte.
    
- **Download**: gibt ein **HRESULT** mit dem Wert `0x800000e`"eine Methode wurde zu einem unerwarteten Zeitpunkt aufgerufen." zurück. 
    
- **Status**: gibt **DOWNLOAD_WIP** zurück, um anzugeben, dass die Download Arbeit ausgeführt wird. 
    
**Anwendung:** Wenn das Klick-und-Los-Installationsprogramm den Download Inhalt bereits installiert hat: 
  
- **Apply**: gibt ein **HRESULT** mit dem Wert `0x800000e`"eine Methode wurde zu einem unerwarteten Zeitpunkt aufgerufen." zurück.
    
- **Cancel**: gibt `0x800000e`zurück, die Apply-Aktion kann nicht abgebrochen werden.
    
- **Download**: gibt ein **HRESULT** mit dem Wert `0x800000e`"eine Methode wurde zu einem unerwarteten Zeitpunkt aufgerufen." zurück. 
    
- **Status**: gibt **APPLY_WIP** zurück, um anzugeben, dass die Anwendung "Arbeit" ausgeführt wird. 
    
> [!NOTE]
> Da OfficeC2RCOM ein com+-Dienst ist und dynamisch geladen wird, müssen Sie **CoCreateInstance** jedes Mal aufrufen, wenn Sie eine Methode für diese Klasse aufrufen, um sicherzustellen, dass Sie das erwartete Ergebnis erhalten. Der com+-Dienst behandelt das Erstellen einer neuen Instanz, wenn dies erforderlich ist. Wenn eine der Methoden zum ersten Mal aufgerufen wird, lädt com+ das **IUpdateNotify** -Objekt und führt es in einer der dllhost. exe-Instanzen aus. Das neue Objekt bleibt im Leerlauf etwa 3 Minuten aktiv. Wenn ein anschließender Aufruf innerhalb von drei Minuten nach dem letzten Aufruf erfolgt, bleibt das **IUpdateNotify** -Objekt geladen, und es wird keine neue Instanz erstellt. Wenn innerhalb von drei Minuten kein Aufruf erfolgt, wird das IUpdateNotify-Objekt entladen, und ein neues **IUpdateNotify** -Objekt wird erstellt, wenn der nächste Aufruf erfolgt. 
  
## <a name="click-to-run-installer-com-api-reference-guide"></a>Leitfaden zur com-API-Referenz für Klick-und-Los-Installer

In der folgenden API-Referenzdokumentation:
  
- Parameter befinden sich in einem Schlüssel-Wert-Paar Format, das durch ein Leerzeichengetrennt ist.
    
- Bei den Parametern wird die Groß-/Kleinschreibung nicht beachtet.
    
- Es gibt eine [Liste von Parametern](https://blogs.technet.microsoft.com/odsupport/2014/03/03/the-new-update-now-feature-for-office-2013-click-to-run-for-office365-and-its-associated-command-line-and-switches/) mit verfügbarer Dokumentation. 
    
- Zusammenfassung der IUpdateNotify2-Schnittstelle ist jetzt enthalten.
    
### <a name="apply"></a>Anwenden

```cpp
HRESULT Apply([in] LPWSTR pcwszParameters) // Apply update content.
```

#### <a name="parameters"></a>Parameter

-  _Display Level_: **true** , um den Installationsstatus, einschließlich Fehlern, während des Updateprozesses anzuzeigen; **false** , um den Installationsstatus, einschließlich Fehlern, während des Aktualisierungsvorgangs auszublenden. Der Standardwert ist **false**.
    
-  _forceappshutdown_: **true** , um zu erzwingen, dass Office-Anwendungen sofort heruntergefahren werden, wenn die **Apply** -Aktion ausgelöst wird; **false** , wenn ein Fehler auftritt, wenn Office-Anwendungen ausgeführt werden. Der Standardwert ist **false**. Weitere Informationen finden Sie unter [Hinweise](#bk_ApplyRemark) . 
    
  Wenn eine Office-Anwendung ausgeführt wird, wenn die **Apply** -Aktion ausgelöst wird, tritt in der Regel die **Apply** -Aktion nicht mehr auf. Die `forceappshutdown=true` Übergabe an die **Apply** -Methode führt dazu, dass der **OfficeClickToRun** -Dienst die Anwendungen sofort herunterfährt und das Update anwendet. Der Benutzer kann in diesem Fall Datenverlust auftreten. 
    
#### <a name="return-results"></a>Ergebnisse zurückgeben

|||
|:-----|:-----|
|**S_OK** <br/> |Aktion wurde erfolgreich an den Klick-und-Los-Dienst zur Ausführung übermittelt.  <br/> |
|**E_ACCESSDENIED** <br/> |Der Aufrufer wird nicht mit erhöhten Rechten ausgeführt.  <br/> |
|**E_INVALIDARG** <br/> |Ungültige Parameter wurden übergeben.  <br/> |
|**E_ILLEGAL_METHOD_CALL** <br/> |Die Aktion ist zu diesem Zeitpunkt nicht zulässig. Weitere Informationen finden Sie unter [Hinweise](#bk_ApplyRemark) .  <br/> |

<a name="bk_ApplyRemark"></a>

#### <a name="remarks"></a>Bemerkungen

- Wenn eine Office-Anwendung ausgeführt wird, wenn die **Apply** -Aktion ausgelöst wird, tritt bei der **Apply** -Aktion ein Fehler auf. Die `forceappshutdown=true` Übergabe an die **Apply** -Methode führt dazu, dass der **OfficeClickToRun** -Dienst sofort alle Office-Anwendungen herunterfährt, die ausgeführt werden und das Update anwenden. Dem Benutzer treten möglicherweise Daten auf, da Sie nicht zum Speichern von Änderungen an geöffneten Dokumenten aufgefordert werden.. 
    
- Diese Aktion kann nur ausgelöst werden, wenn der com-Status einer der folgenden ist: 
    
  - **eUPDATE_UNKNOWN**
    
  - **eDOWNLOAD_CANCELLED**
    
  - **eDOWNLOAD_FAILED**
    
  - **eDOWNLOAD_SUCCEEDED**
    
  - **eAPPLY_SUCCEEDED**
    
  - **eAPPLY_FAILED**
    
- Wenn Sie die **Apply** -Methode aufrufen, ohne Inhalt zuvor herunterzuladen, wird die **Apply** -Methode den Bericht **erfolgreich ausgeführt** , da Sie festgestellt hat, dass nichts angewendet und der **Apply** -Prozess erfolgreich abgeschlossen wurde. 
    
### <a name="cancel"></a>Abbrechen

```cpp
HRESULT Cancel() // Cancel the download action.
```

#### <a name="return-results"></a>Ergebnisse zurückgeben

|||
|:-----|:-----|
|S_OK  <br/> |Aktion wurde erfolgreich an den Klick-und-Los-Dienst zur Ausführung übermittelt.  <br/> |
|E_ILLEGAL_METHOD_CALL  <br/> |Die Aktion ist zu diesem Zeitpunkt nicht zulässig. Weitere Informationen finden Sie im Abschnitt " [Hinweise](#bk_CancelRemarks) ".  <br/> |

<a name="bk_CancelRemarks"></a>

#### <a name="remarks"></a>Bemerkungen

- Diese Methode kann nur ausgelöst werden, wenn die com-Status-ID **eDOWNLOAD_WIP**. Es wird versucht, die aktuelle Download Aktion abzubrechen. Der com-Status wechselt in **eDOWNLOAD_CANCELLING** und ändert sich schließlich in **eDOWNLOAD_CANCELED**. Der com-Status gibt **E_ILLEGAL_METHOD_CALL** zurück, wenn Sie zu einem anderen Zeitpunkt ausgelöst wird. 
    
### <a name="download"></a>Download

```cpp
HRESULT Download([in] LPWSTR pcwszParameters) // Download update content.
```

#### <a name="parameters"></a>Parameter

-  _Display Level_: **true** , um den Installationsstatus, einschließlich Fehlern, während des Updateprozesses anzuzeigen; **false** , um den Installationsstatus, einschließlich Fehlern, während des Aktualisierungsvorgangs auszublenden. Der Standardwert ist **false**.
    
-  _updatebaseurl_: URL zur alternativen Download Quelle.
    
-  _updatetoversion_: die Version, auf der Office aktualisiert werden soll. Definieren Sie diesen Parameter, wenn Sie eine ältere Version als die aktuell installierte Version aktualisieren möchten.
    
-  _downloadsource_: CLSID der angepassten **IBackgroundCopyManager** -Implementierung (Bits-Manager). 
    
-  _Content_-Kennung: gibt den Inhalt an, der vom Inhaltsserver über den angepassten Bits-Manager heruntergeladen werden soll. Dieser Wert wird über die Bits-Schnittstelle zur Interpretation übergeben.
    
#### <a name="return-results"></a>Ergebnisse zurückgeben

|||
|:-----|:-----|
|**S_OK** <br/> |Aktion wurde erfolgreich an den Klick-und-Los-Dienst zur Ausführung übermittelt.  <br/> |
|**E_ACCESSDENIED** <br/> |Der Aufrufer wird nicht mit erhöhten Rechten ausgeführt.  <br/> |
|**E_INVALIDARG** <br/> |Ungültige Parameter wurden übergeben.  <br/> |
|**E_ILLEGAL_METHOD_CALL** <br/> |Die Aktion ist zu diesem Zeitpunkt nicht zulässig. Weitere Informationen finden Sie unter [Hinweise](#bk_DownloadRemark) .  <br/> |

<a name="bk_DownloadRemark"></a>

#### <a name="remarks"></a>Bemerkungen

- Sie müssen _downloadsource_ und _Content_ -Nr als Paar angeben. Wenn dies nicht der Fall ist, gibt die **Download** -Methode einen **E_INVALIDARG** Fehler zurück. 
    
- Wenn _downloadsource_, _Content_-und _updatebaseurl_ bereitgestellt werden, wird _updatebaseurl_ ignoriert. 
    
- Diese Aktion kann nur ausgelöst werden, wenn der com-Status einer der folgenden ist: 
    
  - **eUPDATE_UNKNOWN**
    
  - **eDOWNLOAD_CANCELLED**
    
  - **eDOWNLOAD_FAILED**
    
  - **eDOWNLOAD_SUCCEEDED**
    
  - **eAPPLY_SUCCEEDED**
    
  - **eAPPLY_FAILED**
    
- Wenn Sie die **Apply** -Methode ohne zuvor heruntergeladenen Inhalt aufrufen, wird die **Apply** -Methode den Bericht **erfolgreich ausgeführt** , da Sie festgestellt hat, dass nichts angewendet und der **Apply** -Prozess erfolgreich abgeschlossen wurde. 
    
#### <a name="examples"></a>Beispiele

- So laden Sie den Inhalt aus dem angepassten Bits-Manager herunter: Rufen Sie die **Download ()** -Funktion auf, indem Sie die folgenden Parameter übergeben: 
    
  ```cpp
  "downloadsource=CLSIDofBITSInterface contentid=BITSServerContentIdentifier"
  ```

- Zum Herunterladen des Inhalts aus dem Microsoft CDN: Rufen Sie die **Download ()** -Funktion ohne Angabe der Parameter _downloadsource_, _contentbar_oder _updatebaseurl_ . 
    
- So laden Sie die Inhalte von einem benutzerdefinierten Speicherort herunter: Rufen Sie die **Download ()-** Funktion auf, indem Sie den folgenden Parameter übergeben: 
    
  ```cpp
  "updatebaseurl=yourcontentserverurl"
  ```

### <a name="status"></a>Status

```cpp
typdef struct _UPDATE_STATUS_REPORT
{
    UPDATE_STATUS status;
    UINT error;
    LPCWSTR contentid;
}UPDATE_STATUS_REPORT;
HRESULT status([out] _UPDATE_STATUS_REPORT& pUpdateStatusReport) // Get status of current action
```

#### <a name="parameters"></a>Parameter

|||
|:-----|:-----|
| _pUpdateStatusReport_ <br/> |Zeiger auf eine UPDATE_STATUS_REPORT Struktur.  <br/> |
   
#### <a name="return-results"></a>Ergebnisse zurückgeben

|||
|:-----|:-----|
|**S_OK** <br/> |Die **Status** -Methode gibt immer dieses Ergebnis zurück. Überprüfen `UPDATE_STATUS_RESULT` Sie die Struktur auf den Status der aktuellen Aktion.  <br/> |
   
#### <a name="remarks"></a>Bemerkungen

- Das Feld Status des `UPDATE_STATUS_REPORT` enthält den Status der aktuellen Aktion. Einer der folgenden Statuswerte wird zurückgegeben: 
    
  ```cpp
  typedef enum _UPDATE_STATUS
  {
  eUPDATE_UNKNOWN = 0,
  eDOWNLOAD_PENDING,
  eDOWNLOAD_WIP,
  eDOWNLOAD_CANCELLING,
  eDOWNLOAD_CANCELLED,
  eDOWNLOAD_FAILED,
  eDOWNLOAD_SUCCEEDED,
  eAPPLY_PENDING,
  eAPPLY_WIP,
  eAPPLY_SUCCEEDED,
  eAPPLY_FAILED,
  } UPDATE_STATUS;
  
  ```

- Wenn der letzte Befehl zu einem Fehler geführt hat, `UPDATE_STATUS_REPORT` enthält das Feld Error des-Fehlers detaillierte Informationen zu dem Fehler. Zwei Arten von Fehlercodes werden von der **Status** -Methode zurückgegeben. 
    
- Wenn der Fehler kleiner als `UPDATE_ERROR_CODE::eUNKNOWN`ist, ist der Fehler einer der folgenden vordefinierten Fehlercodes:
    
  ```cpp
  typedef enum _UPDATE_ERROR_CODE
  {
  eOK = 0,
  eFAILED_UNEXPECTED,
  eTRIGGER_DISABLED,
  ePIPELINE_IN_USE,
  eFAILED_STOP_C2RSERVICE,
  eFAILED_GET_CLIENTUPDATEFOLDER,
  eFAILED_LOCK_PACKAGE_TO_UPDATE,
  eFAILED_CREATE_STREAM_SESSION,
  eFAILED_PUBLISH_WORKING_CONFIGURATION,
  eFAILED_DOWNLOAD_UPGRADE_PACKAGE,
  eFAILED_APPLY_UPGRADE_PACKAGE,
  eFAILED_INITIALIZE_RSOD,
  eFAILED_PUBLISH_RSOD,
  // Keep this one as the last
  eUNKNOWN
  } UPDATE_ERROR_CODE;
  
  ```

  Wenn der Rückgabefehlercode größer als `UPDATE_ERROR_CODE::eUNKNOWN` der **HRESULT** -Wert eines fehlgeschlagenen Funktionsaufrufs ist. So extrahieren Sie das HRESULT `UPDATE_ERROR_CODE::eUNKNOWN` subtrahieren aus dem Wert, der im Feld Error `UPDATE_STATUS_REPORT`von zurückgegeben wird.
    
  Die vollständige Liste der Status-und Fehlerwerte kann angezeigt werden, indem die in OfficeC2RCom. dll eingebettete **IUpdateNotify** -Typbibliothek überprüft wird. 
    
- Das Feld "Content-Nr" wird für Aufrufe von **Status** verwendet, nachdem der **Download** initiiert wurde, und gibt die Inhalts-Nr zurück, die an den **Download** Aufruf übergeben wurde. Es wird empfohlen, dieses Feld vor dem Aufrufen der **Status** -Methode auf **null** zu initialisieren und anschließend den Wert nach dem Zurückgeben des **Status** zu überprüfen. Wenn der Wert immer noch **null**ist, bedeutet dies, dass keine Inhalts-Nr vorhanden ist, die zurückgegeben werden soll. Wenn der Wert nicht **null**ist, müssen Sie ihn mit einem Aufruf von **sysfree String ()** freigeben. Im folgenden finden Sie einen Codeausschnitt zum Aufrufen des **Status** nach dem **Download**.
    
  ```cpp
  std::wstring contentID;
  UPDATE_STATUS_REPORT statusReport;
  statusReport.status = eUPDATE_UNKNOWN;
  statusReport.error = eOK;
  statusReport.contentid = NULL;
  hr = p->Status(&statusReport);
  if (statusReport.contentid != NULL)
  {
  contentID = statusReport.contentid;
  SysFreeString(statusReport.contentid);
  }
  wprintf(L"ContentID: %s, Status: %d, LastError: %d", contentID.c_str(), statusReport.status, statusReport.error);
  
  ```

### <a name="summary-of-iupdatenotify2-interface"></a>Zusammenfassung der IUpdateNotify2-Schnittstelle

> [!NOTE]
> Diese Zusammenfassung wird als Kompliment zur [Integration von Verwaltbarkeit-Anwendungen mit dem Office 365 Klick-und-Los-Installationsprogramm](https://docs.microsoft.com/office/client-developer/shared/manageability-applications-with-the-office-365-click-to-run-installer)bereitgestellt. Sobald das öffentliche Dokument aktualisiert wurde, kann dieses Dokument als veraltet betrachtet werden. 
  
Von C2RTenant [16.0.8208.6352](https://oloop/BuildGroup/Details/tenantc2rclient#3519/1255278) (erstes öffentlich verfügbares Build sollte June Fork Build--8326. *) Wir haben eine neue **IUpdateNotify2** -Schnittstelle hinzugefügt. Hier finden Sie einige grundlegende Informationen zu dieser Schnittstelle: 
  
- CLSID_UpdateNotifyObject2, {52C2F9C2-F1AC-4021-BF50-756A5FA8DDFE}
    
- Diese Schnittstelle hat auch die ursprüngliche IUpdateNotify-Schnittstelle gehostet, um Abwärtskompatibilität zu gewährleisten. Das heißt, wenn Sie diese Schnittstelle verwenden, haben Sie Zugriff auf alle Methoden, die in der **UpdateNotifyObject** -Schnittstelle bereitgestellt werden. 
    
- Neue Methoden zu IUpdateNotify2 hinzugefügt:
    
  - **HRESULT** GetBlockingApps (BSTR \* -appsliste). Updates blockieren apps-Liste abrufen. Bei diesem Aufruf werden ausgeführte Office-Apps zurückgegeben, wodurch der Aktualisierungsprozess blockiert wird. 
    
  - **HRESULT** GetOfficeDeploymentData ([in] int DataType, [in] **ein LPCWSTR** pcwszName, [out] BSTR * OfficeData). Abrufen von Office-Bereitstellungsdaten 
    
- Wenn Sie die neuen Methoden verwenden möchten, müssen Sie Folgendes sicherstellen:
    
  - Ihre C2R-Version ist neuer als der obige Build\>(= June Fork Build).
    
  - Verwenden Sie UpdateNotifyObject2 anstelle von **UpdateNotifyObject** , um **CoCreateInstance**aufzurufen.
    
Wenn Sie keine der neuen Methoden verwenden, müssen Sie nichts ändern. Alle vorhandenen Methoden funktionieren genauso genau wie zuvor.
  
## <a name="implementing-the-bits-interface"></a>Implementieren der Bits-Schnittstelle

Der [intelligente Hintergrundübertragungsdienst (Background Intelligent Transfer Service](https://docs.microsoft.com/windows/win32/bits/background-intelligent-transfer-service-portal) , Bits) ist ein von Microsoft bereitgestellter Dienst zum Übertragen von Dateien zwischen einem Client und einem Server. Bits ist einer der Kanäle, die von einem Office-Klick-und-Los-Installationsprogramm zum Herunterladen von Inhalten verwendet werden können. Standardmäßig verwendet das Office-Klick-und-Los-Installationsprogramm die in der Implementierung von Bits integrierte Windows-Datei, um den Inhalt aus dem CDN herunterzuladen. 
  
Durch die Bereitstellung einer angepassten Bits-Implementierung für die **Download ()** -Methode der **IUpdateNotify** -Schnittstelle kann Ihre Verwaltbarkeit-Software steuern, wo und wie der Client den Inhalt herunterlädt. Eine angepasste Bits-Schnittstelle ist nützlich, wenn ein benutzerdefinierter Inhalts Verteilungskanal als die integrierten Klick-und-Los-Kanäle bereitgestellt wird, beispielsweise die Office CDN-, IIS-Server oder Dateifreigaben. 
  
Die Mindestanforderung für eine angepasste Bits-Schnittstelle für die Verwendung des Office C2R-Diensts lautet:
  
- Für **IBackgroundCopyManager**:
    
  ```cpp
  HRESULT _stdcall CreateJob(
                      [in] LPWSTR DisplayName, 
                      [in] BG_JOB_TYPE Type, 
                      [out] GUID* pJobId, 
                      [out] IBackgroundCopyJob** ppJob)
  HRESULT _stdcall GetJob(
                      [in] GUID* jobID, 
                      [out] IBackgroundCopyJob** ppJob)
  HRESULT _stdcall EnumJobs(
                      [in] unsigned long dwFlags, 
                      [out] IEnumBackgroundCopyJobs** ppenum)
  
  ```

- Für **IBackgroundCopyJob**:
    
  ```cpp
  HRESULT _stdcall AddFile(
                      [in] LPWSTR RemoteUrl, 
                      [in] LPWSTR LocalName)
  HRESULT _stdcall Resume()
  HRESULT _stdcall Complete()
  HRESULT _stdcall Cancel();
  HRESULT _stdcall GetState([out] BG_JOB_STATE* pVal);
  HRESULT GetProgress( [out] BG_JOB_PROGRESS *pProgress);
  
  ```

- Für **IBackgroundCopyJob3**:
    
  ```cpp
  HRESULT _stdcall AddFileWithRanges(
                      [in] LPWSTR RemoteUrl, 
                      [in] LPWSTR LocalName,
                      [in] DWORD RangeCount,
                      [in] BG_FILE_RANGE Ranges[])
  
  ```

- Für die `Addfile` - `AddFileWithRanges` und-Funktionen hat die Remote-URL folgendes Format: 
    
  ```cpp
  cmbits://<contentid>/<relative path to target file>
  ```

  - cmbits ist hart codiert und steht für angepasste Bits.
    
  -  Content-Wert ist der _Content_ -Parameter für die **Download ()** -Methode. _ \<\> _ 
    
  -  _Relative Path to target file\> enthält den Speicherort und den Dateinamen der Datei, die heruntergeladen werden soll. \<_ 
    
    Wenn Sie beispielsweise eine _Inhalts_ `f732af58-5d86-4299-abe9-7595c35136ef` -Nr für die **Download ()** -Methode bereitgestellt haben und Office C2R die Version der CAB-Datei (beispielsweise `v32.cab` Datei) herunterladen möchte, wird **AddFile ()** mit folgendem `RemoteUrl`Aufruf aufgerufen:
    
  ```cpp
  cmbits://f732af58-5d86-4299-abe9-7595c35136ef/Office/Data/V32.cab
  ```

- Für **IBackgroundCopyError**:
    
  ```cpp
  HRESULT _stdcall GetErrorDescription(
        [in]  DWORD  LanguageId,
        [out] LPWSTR *ppErrorDescription);
  
  ```

- Für **IBackgroundCopyFile**:
    
  ```cpp
  HRESULT _stdcall GetLocalName([out] LPWSTR *ppName); 
  HRESULT _stdcall GetRemoteName([out] LPWSTR *ppName);
  
  ```

<!--## Automating content staging

IT administrators can choose to have desktop clients enabled to automatically receive updates when they are available directly from the Microsoft Content Delivery Network (CDN) or they can choose to control the deployment of updates available from the [update channels](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus) using the [Office 2016 Deployment Tool](https://www.microsoft.com/download/details.aspx?id=49117) or [System Center Configuration Manager](https://docs.microsoft.com/deployoffice/manage-office-365-proplus-updates-with-configuration-manager).
  
The service supports the ability for management tools to recognize and automate the download of the content when updates are made available.
  
**Following is a diagram showing the overview of downloading a custom image**

![An overview of downloading Office updates from the CDN.](media/9afac230-6b22-4526-a800-0562708cc436.png "An overview of downloading Office updates from the CDN")
  
In the above diagram you see that a new Office 365 ProPlus image is available on the Office Content Distribution Network (CDN). Along with the Office 365 ProPlus image, an XML-formatted file list is also available which has the information needed to enable manageability software to directly create customized images replacing the need for using the Office Deployment Tool.
  
An enterprise configures their WSUS to sync the Office 365 Client Updates. These updates do not contain the actual image payload but does allow the manageability software to recognize when new content is available. The manageability software can then read the Client Update metadata to understand what version of Office the update applies to.
  
If the update is applicable, the manageability software can use the CDN content and the file list to create the custom image and store it onto the file share location that it is configured to use.
  
### Format of the XML file list

There are two file lists available in a cab file on the CDN. One lists the files for the 32-bit version of Office and one for the 64-bit version of Office. The URL of the location of the Office File List (OFL.CAB) file is [https://officecdn.microsoft.com/pr/wsus/ofl.cab](https://officecdn.microsoft.com/pr/wsus/ofl.cab). The two file lists are called:
  
- O365Client_32bit.xml
    
- O365Client_64bit.xml
    
Within the XML for each of the file lists is an  `UpdateFiles` node which contains a version attribute.  `UpdateFiles version="1.4"`.
  
This version is incremented if changes are made to the file lists.
  
There are two parameters that need to be combined with the XML to make a custom image: 
  
- Replace  _%version%_ with the build version of Office. This can be derived from the Client Update metadata  `MoreInfoURL` field, see below. 
    
- Define  _baseURL_ by using the URL value associated with the branch the image is being created for. This can be derived from the Client Update metadata, see below. 
    
The steps for creating an image are:
  
1. Open the XML file list.
    
2. Replace occurrences of  _%version%_ with the applicable Office build version. The build version can be acquired from releasehistory.xml as described later in this article. 
    
3. Read the URL attribute for the target branch.
    
4. Remove language nodes for any languages not required in the custom image.
    
   > [!NOTE]
   > Nodes with language='0' are language neutral and must be included in the image. 
  
5. Construct a local image of the CDN by iterating through the XML file list and copying the CDN files, while creating the folder structure as needed. 
    
   - If the  _rename_ attribute is provided, then rename the copied file to the value provided in the  _rename_ attribute. This used to create the top-level default v64.cab and v32.cab files. These are the renamed versions of the top-level build cab file and are used as the default installation version if the version is not specified. 
    
   - Use URL + relativePath + filename to construct the CDN location.
    
The following examples use the Monthly channel (as defined by the  `baseURL` node) and build version 16.0.4229.1004 from releasehistory.xml. 
  
```cpp
baseURL branch="Monthly" URL="https://officecdn.microsoft.com/pr/492350f6-3a01-4f97-b9c0-c7c6ddf67d60" /
```

- The following is a language neutral file needed for all languages. The name of the file is v64_16.0.4229.1004.cab and it should be copied from https://officecdn.microsoft.com/pr/492350f6-3a01-4f97-b9c0-c7c6ddf67d60/office/data/v64_16.0.4229.1004.cab and renamed to …/office/data/v64.cab.
    
  ```cpp
  baseURL branch="Business" URL="https://officecdn.microsoft.com/pr/7ffbc6bf-bc32-4f92-8982-f9dd17fd3114" /
  File name="v64_%version%.cab" rename="v64.cab" relativePath="/office/data/" language="0"/
  
  ```

- The following is a file to be included in the en-US image as designated by the language LCID=1033. The name of the file is s641033.cab and it should be copied from https://officecdn.microsoft.com/pr/492350f6-3a01-4f97-b9c0-c7c6ddf67d60/office/data/16.0.4229.1004/s641033.cab and not renamed.
    
  ```cpp
  File name="s641033.cab" relativePath="/office/data/%version%/" language="1033" /
  ```

### Hash verification of data files

Image creation tools may verify the integrity of the downloaded .dat files by comparing a computed HASH value with the supplied HASH value associated with each of the .dat files. Below is an example of a .dat file from the Monthly channel with build version 16.0.4229.1004 and language set to Bulgarian.
  
```cpp
File name="stream.x64.bg-bg.dat" hashLocation="s641026.cab/stream.x64.bg-bg.hash" hashAlgo="Sha256" relativePath="/office/data/%version%/" language="1026"
```

- The  _hashLocation_ attribute specifies the relative path location of the stream.x64.bg-bg.hash for the stream.x64.bg-bg.dat file. Construct the hash file location by concatenating URL + relativePath + hashLocation. In this example the stream.x64.bg-bg.hash location would be https://officecdn.microsoft.com/pr/492350f6-3a01-4f97-b9c0-c7c6ddf67d60/office/data/16.0.4229.1004/s641026.cab/stream.x64.bg-bg.hash 
    
- The  _hashAlgo_ attribute specifies what hashing algorithm was used. In this case the Sha256 algorithm was used. 
    
To validate the integrity of the stream.x64.bg-bg.dat file, open the stream.x64.bg-bg.hash and read the hash value from the first line of text in the hash file. Compare this to the has value that you computed using the specified hashing algorithm to verify that the values match. Use the following C# code to read the hash.
  
```cs
string[] readHashes = System.IO.File.ReadAllLines(tmpFile, Encoding.Unicode);
string readHash = readHashes.First();

```

### Office 365 Client Updates

Office 365 Client Updates enable manageability software to treat the Office 365 Client Updates in a manner very similar to any other WU update with one exception; the client updates do not contain an actual payload. The Office 365 Client Updates should not be installed on any clients but rather used to trigger the workflows with the manageability software replacing the installation command with the COM based installation mechanism shown above.
  
**Office 365 Client Update workflow**

![Workflow diagram for O365PP client updates.](media/bc8092b0-62b8-402c-a5c0-04d55cca01d4.png "Workflow diagram for O365PP client updates")
  
Each Office 365 Client Update that is published includes metadata about the update. This metadata includes a parameter called  _MoreInfoUrl_ which can be used to derive the following information: 
  
-  _Ver_: Identifies the Office version associated with this update. For example 16.0.4229.1004.
    
-  _Branch_: Identifies the Update Channel for this update. Values include InsiderFast, Insiders, Monthly, Targeted, Broad. Additional values may be added in the future.
    
-  _Arch_: Identifies the processor architecture associated with this update.
    
-  _xmlVer_: Identifies the version of the XML file lists to use to construct the base image for this update.
    
-  _xmlPath_: Path to the OFL.CAB file that contains the XML file lists.
    
-  _xmlFile_: The name of the file list that should be used for this update. The value will be  `O365Client_32bit` or  `O365Client_64bit` and will match the value in  _Arch_.
    
The following is an example of the  _MoreInfoURL_ parameter which refers to the Office 365 Client Update for the 32-bit version of Office with build version of 16.0.2342.2343 on the Current channel. 
  
```http
https://officecdn.microsoft.com/pr/wsus/ofl.cab is the location of the XML file lists for this update, specifically the O365Client_32bit.xml from within the OFL.CAB.
https://go.microsoft.com/fwlink/?LinkId=626090&Ver=16.0.8326.2096&Branch=Current&Arch=64&XMLVer=1.4&xmlPath=https://officecdn.microsoft.com/pr/wsus/ofl.cab&xmlFile=O365Client_64bit.xml 

```
THE ABOVE SECTION APPEARS TO BE A DUPLICATE OF THE FOLLOWING SECTION; TEMPORARILY COMMENTING IT OUT.-->

## <a name="automating-content-staging"></a>Automatisieren der Inhaltsbereitstellung

IT-Administratoren können festlegen, dass Desktop Clients automatisch Updates erhalten, wenn Sie direkt im Microsoft Content Delivery Network (CDN) zur Verfügung stehen, oder Sie können auswählen, ob die Bereitstellung von Updates gesteuert werden soll, die im Update verfügbar sind. Kanäle mit dem Office-Bereitstellungs Tool oder System Center Configuration Manager.
  
Der Dienst unterstützt die Möglichkeit für Verwaltungstools, den Download der Inhalte zu erkennen und zu automatisieren, wenn Updates zur Verfügung gestellt werden.
  
**Die folgende Abbildung ist eine Übersicht über das Herunterladen eines benutzerdefinierten Bilds.**

![A diagram of using the COM interface on  the Office Click-To-Run installer.](media/e7ac2523-e67b-4a44-ae67-c048709f872a.png "Ein Diagramm zur Verwendung der COM-Schnittstelle im Office-Klick-und-Los-Installationsprogramm")
  
### <a name="overview-of-downloading-a-custom-image"></a>Übersicht über das Herunterladen eines benutzerdefinierten Bilds
  
Im vorherigen Diagramm sehen Sie, dass ein neues Office 365 ProPlus-Bild im Office-Inhalts Verteilungsnetzwerk (CDN) zur Verfügung steht. Zusammen mit dem Office 365 ProPlus-Bild ist auch eine XML-formatierte Dateiliste verfügbar, die über die erforderlichen Informationen verfügt, um die Verwaltbarkeit von Software zu ermöglichen, um direkt angepasste Bilder zu erstellen, die die Verwendung des Office-Bereitstellungstools ersetzen.
  
Ein Unternehmen konfiguriert seine WSUS so, dass die Office 365 Client Updates synchronisiert werden. Diese Updates enthalten nicht die tatsächliche Bild Nutzlast, aber die Verwaltungssoftware kann erkennen, wenn neue Inhalte verfügbar sind. Die Verwaltungssoftware kann dann die Client Update Metadaten lesen, um zu verstehen, für welche Version von Office das Update gilt.
  
Wenn das Update anwendbar ist, kann die Verwaltbarkeit-Software den CDN-Inhalt und die Dateiliste verwenden, um das benutzerdefinierte Abbild zu erstellen und es auf dem Dateifreigabespeicherort zu speichern, der für die Verwendung konfiguriert ist.
  
### <a name="format-of-the-xml-file-list"></a>Format der XML-Dateiliste

In einer CAB-Datei auf dem CDN stehen zwei Dateilisten zur Verfügung. Eine Liste enthält die Dateien für die 32-Bit-Version von Office und eine für die 64-Bit-Version von Office. Die URL des Speicherorts der Office-Dateiliste (ofl. CAB)-Datei [https://officecdn.microsoft.com/pr/wsus/ofl.cab](https://officecdn.microsoft.com/pr/wsus/ofl.cab)ist. Die beiden Dateilisten werden aufgerufen:
  
- O365Client_32bit. XML
    
- O365Client_64bit. XML
    
Innerhalb des XML-Code für jede der Dateilisten ist <UpdateFiles> ein Knoten, der ein Version-Attribut enthält.  `<UpdateFiles version="1.4">`. Diese Version wird inkrementiert, wenn Änderungen an den Dateilisten vorgenommen werden.
  
Es gibt zwei Parameter, die mit dem XML-Code kombiniert werden müssen, um ein benutzerdefiniertes Bild zu erstellen: 
  
- Ersetzen Sie *% Version%* durch die Buildversion von Office. Dies kann von den Client Update-Metadaten abgeleitet werden (siehe nächster Abschnitt). 
    
- Definieren Sie *baseURL* mit dem URL-Wert, der der Verzweigung zugeordnet ist, für die das Bild erstellt wird. Dies wird von den Client Update-Metadaten abgeleitet, die im folgenden Abschnitt erläutert werden. 
    
Die Schritte zum Erstellen eines Bilds lauten wie folgt:
  
1. Öffnen Sie die Liste XML-Datei.
    
2. Ersetzen Sie Vorkommen von *% Version%* durch die entsprechende Office Build-Version. Die Buildversion kann aus releasehistory. XML abgerufen werden, wie weiter unten in diesem Artikel beschrieben. 
    
3. Lesen Sie das URL-Attribut für die Zielverzweigung.
    
4. Entfernen Sie Sprachknoten für alle Sprachen, die im benutzerdefinierten Bild nicht erforderlich sind.
    
   > [!NOTE]
   > Knoten mit Sprache = ' 0 ' sind sprachneutral und müssen in das Bild aufgenommen werden. 
  
5. Erstellen Sie ein lokales Image des CDN, indem Sie die XML-Dateiliste durchlaufen und die CDN-Dateien kopieren, während Sie die Ordnerstruktur nach Bedarf erstellen. 
    
   - Wenn das Attribut *Rename* angegeben wird, *benennen* Sie die kopierte Datei in den im Attribut Rename angegebenen Wert um. Dies wird verwendet, um die standardmäßigen V64. cab-und V32. CAB-Dateien auf oberster Ebene zu erstellen. Hierbei handelt es sich um die umbenannten Versionen der Build-CAB-Datei auf oberster Ebene, die als Standard Installationsversion verwendet werden, wenn die Version nicht angegeben ist. 
    
   - Verwenden Sie URL + relativePath + filename, um den CDN-Speicherort zu erstellen.
    
Im folgenden sind Beispiele aufgeführt, die den monatlichen Kanal (wie vom `<baseURL>` Knoten definiert) und die Buildversion 16.0.4229.1004 aus releasehistory. XML verwenden. 
  
```xml
<baseURL branch="Monthly" URL="https://officecdn.microsoft.com/pr/492350f6-3a01-4f97-b9c0-c7c6ddf67d60" />
```

- Im folgenden finden Sie eine sprachneutrale Datei, die für alle Sprachen erforderlich ist. Der Name der Datei lautet v64_16.0.4229.1004. cab und sollte aus `https://officecdn.microsoft.com/pr/492350f6-3a01-4f97-b9c0-c7c6ddf67d60/office/data/v64_16.0.4229.1004.cab` kopiert und in `…/office/data/v64.cab`umbenannt werden. 
    
  ```xml
  <File name="v64_%version%.cab" rename="v64.cab" relativePath="/office/data/" language="0"/>
  
  ```

- Im folgenden finden Sie eine Datei, die in das en-US-Bild aufgenommen werden soll, wie von der Sprache LCID = 1033 angegeben. Der Name der Datei lautet s641033. cab und sollte aus `https://officecdn.microsoft.com/pr/492350f6-3a01-4f97-b9c0-c7c6ddf67d60/office/data/16.0.4229.1004/s641033.cab` kopiert und nicht umbenannt werden.
    
  ```xml
  <File name="s641033.cab" relativePath="/office/data/%version%/" language="1033" />
  ```

### <a name="hash-verification-of-dat-files"></a>Hash Überprüfung von DAT-Dateien

Bilder Erstellungstools können die Integrität der heruntergeladenen DAT-Dateien überprüfen, indem Sie einen berechneten Hashwert mit dem bereitgestellten Hashwert vergleichen, der den einzelnen DAT-Dateien zugeordnet ist. Im folgenden finden Sie ein Beispiel für eine DAT-Datei aus dem monatlichen Kanal mit 16.0.4229.1004 der Buildversion und der auf Bulgarisch festgelegten Sprache:
  
```xml
<File name="stream.x64.bg-bg.dat" hashLocation="s641026.cab/stream.x64.bg-bg.hash" hashAlgo="Sha256" relativePath="/office/data/%version%/" language="1026"/>
```

- Das **hashLocation** -Attribut gibt den relativen Pfadspeicherort des Stream.x64.bg-bg. Hash für die Datei Stream.x64.bg-bg. dat an. Erstellen Sie den Speicherort der Hash Datei, indem Sie URL + relativePath + hashLocation verketten. Im folgenden Beispiel wäre der Speicherort Stream.x64.bg-bg. Hash wie folgt: 
    
  ```http
  https://officecdn.microsoft.com/pr/492350f6-3a01-4f97-b9c0-c7c6ddf67d60/office/data/16.0.4229.1004/s641026.cab/stream.x64.bg-bg.hash 
  ```

- Das **hashAlgo** -Attribut gibt an, welcher Hashalgorithmus verwendet wurde. In diesem Fall wurde SHA256 verwendet. 
    
  Um die Integrität der Datei Stream.x64.bg-bg. dat zu überprüfen, öffnen Sie den Stream.x64.bg-bg. Hash und lesen Sie den Hashwert, der die erste Textzeile in der Hash Datei ist. Vergleichen Sie diesen Wert mit dem berechneten Hashwert (mithilfe des angegebenen Hashalgorithmus), um die Integrität der heruntergeladenen DAT-Datei zu überprüfen.
    
  Im folgenden Beispiel wird der C#-Code zum Lesen des Hashs gezeigt.
    
  ```cs
    string[] readHashes = System.IO.File.ReadAllLines(tmpFile, Encoding.Unicode);
    string readHash = readHashes.First();
  ```

### <a name="office-365-client-updates"></a>Office 365 von Client Updates

Alle Office 365 Client Updates werden im [Microsoft Update-Katalog](https://www.catalog.update.microsoft.com/Search.aspx?q=office+365+client)veröffentlicht.
  
Mit Office 365 Clientupdates kann die Verwaltbarkeit von Software für die Office 365-Clientupdates auf eine Art und Weise behandelt werden, die mit einer Ausnahme ähnlich wie bei anderen Wu-Updates aussieht. die Clientupdates enthalten keine tatsächliche Nutzlast. Die Office 365 Client Updates sollten nicht auf allen Clients installiert werden, sondern verwendet werden, um die Workflows mit der Verwaltungssoftware auszulösen, die den Installationsbefehl durch den oben gezeigten com-basierten Installationsmechanismus ersetzt. 
  
**In der folgenden Abbildung ist ein Diagramm des Office 365-Client Update Workflows dargestellt.**

![Workflow diagram for O365PP client updates.](media/bc8092b0-62b8-402c-a5c0-04d55cca01d4.png "Workflow Diagramm für O365PP-Clientupdates")
  
Jedes Office 365-Client Update, das veröffentlicht wird, enthält Metadaten zum Update. Diese Metadaten enthalten einen Parameter namens *MoreInfoUrl* , der verwendet werden kann, um die folgenden Informationen abzuleiten: 
  
-  *Ver*: gibt die Office-Version an, die diesem Update zugeordnet ist. 
    
-  *Branch*: identifiziert den Update Kanal für dieses Update. Zu den Werten zählen InsiderFast, Insider, Monthly, Targeted, Broad. Weitere Werte können in der Zukunft hinzugefügt werden. 
    
-  *Arch*: identifiziert die Prozessorarchitektur, die diesem Update zugeordnet ist. 
    
-  *xmlVer*: die Version der XML-Dateilisten, die zum Erstellen des Basis Bilds für dieses Update verwendet werden sollte. 
    
-  *xmlpath*: Pfad zum ofl. CAB-Datei, die die XML-Dateilisten enthält. 
    
-  *mlFile*: der Name der Dateiliste, die für dieses Update verwendet werden soll. Der Wert ist O365Client_32bit oder O365Client_64bit und wird mit dem Bogen übereinstimmen. 
    
Die folgende URL ist ein Beispiel für den *MoreInfoUrl* -Parameter, der auf die Office 365 Client Updateversionen für die 32-Bit-Version von Office mit der Buildversion von 16.0.2342.2343 im aktuellen Kanal verweist. 
  
https://officecdn.microsoft.com/pr/wsus/ofl.cabist der Speicherort der XML-Dateilisten für dieses Update, insbesondere die O365Client_32bit. XML in der ofl. CAB.
  
[Office 365-Clientupdate-Kanalversionen](https://go.microsoft.com/fwlink/?LinkId=626090&Ver=16.0.8326.2096&Branch=Current&Arch=64&XMLVer=1.4&xmlPath=https://officecdn.microsoft.com/pr/wsus/ofl.cab&xmlFile=O365Client_64bit.xml)
  
### <a name="additional-metadata-for-automating-content-staging"></a>Zusätzliche Metadaten zum Automatisieren der Inhaltsbereitstellung

Zusätzlich zu den veröffentlichten Metadaten, die definieren, gibt es auch zusätzliche XML-Dateien, die im CDN veröffentlicht werden und zusätzliche Informationen zu den Office 365 Clients bereitstellen können, die im Office CDN zur Verfügung stehen.
  
**SKUs. XML**
  
Diese XML-Datei ist in einem signierten CAB-Code enthalten und wird im Office CDN unter der [https://officecdn.microsoft.com/pr/wsus/skus.cab](https://officecdn.microsoft.com/pr/wsus/skus.cab)folgenden URL veröffentlicht:.
  
Die in dieser XML-Datei veröffentlichten Metadaten sind nützlich, um zu ermitteln, welche Produkte für die Bereitstellung und Wartung aus dem Office CDN zur Verfügung stehen, zusammen mit verschiedenen Optionen. 
  
```XML
<?xml version="1.0" encoding="utf-8"?>
<ReleaseInfo PublishedDate="08/07/2017 16:34">
  <!-- Suite / App catalog -->
  <Suite>
    <SKU Name="Office 365 ProPlus" ProductID="O365ProPlusRetail" Default="True">
      <Apps>
        <App Name="Access" AppID="Access" />
        <App Name="Excel" AppID="Excel" />
        <App Name="OneDrive for Business (Groove)" AppID="Groove" />
        <App Name="OneDrive for Business (Next Gen Sync Client)" AppID="OneDrive" />
        <App Name="OneNote" AppID="OneNote" />
        <App Name="Outlook" AppID="Outlook" />
        <App Name="PowerPoint" AppID="PowerPoint" />
        <App Name="Publisher" AppID="Publisher" />
        <App Name="Skype for Business" AppID="Lync" />
        <App Name="Word" AppID="Word" />
      </Apps>
      <Channels>
        <Channel ID="Monthly"/>
        <Channel ID="Insiders"/>
        <Channel ID="Targeted"/>
        <Channel ID="Broad"/>
      </Channels>
    </SKU>
```

ReleaseInfo-Stammknoten enthält das PublishedDate-Attribut, das das Datum angibt, an dem diese Datei veröffentlicht wurde. ** \<\> ** 
  
SKU-Knoten identifiziert eine einzelne SKU. ** \<\> ** 
  
- Das *ProductID* -Attribut identifiziert die ID, die als ID-Attribut in der Datei Configuration. XML übergeben wird, wenn das ODT verwendet wird. Beispiel: `<Product ID="O365ProPlusRetail">`. 
    
- Das *Standard* Attribut, bei Festlegung auf "true", gibt die empfohlene SKU an. 
    
App-Knoten werden verwendet, um die einzelnen Office-Apps zu definieren, die jede SKU unterstützt. ** \<\> ** 
  
- Das *Name* -Attribut ist der angezeigte Anwendungsname. 
    
- Bei Verwendung des ODT-Attributs handelt es sich um das ID *-Attribut,* das in der Datei Configuration. XML für den ** \<ExcludeApp\> ** -Knoten übergeben wird. Beispiel: `<ExcludeApp ID="Publisher" />`. 
    
**RELEASEHISTORY. XML**
  
Diese XML-Datei ist in einem signierten CAB-Code enthalten und wird im Office CDN an folgendem Speicherort veröffentlicht: [https://officecdn.microsoft.com/pr/wsus/releasehistory.cab](https://officecdn.microsoft.com/pr/wsus/releasehistory.cab). 
  
Die in dieser XML-Datei veröffentlichten Metadaten sind nützlich, um zu ermitteln, welche Kanäle für die Wartung von Updates aus dem Office CDN unterstützt werden, zusammen mit Informationen zum Build-Verlauf für jeden der unterstützten Kanäle.
  
```XML
<?xml version="1.0" encoding="utf-8"?>
<ReleaseHistory PublishedDate="10/22/2017 00:48">
  <UpdateChannel Name="Current" ID="Monthly" DisplayName="Monthly Channel">
    <Update Latest="True" Version="1709" LegacyVersion="16.0.8528.2139" Build="8528.2139" PubTime="2017-10-16T19:45:50.743Z" />
    <Update Latest="False" Version="1708" LegacyVersion="16.0.8431.2107" Build="8431.2107" PubTime="2017-10-11T01:52:33.793Z" />
    <Update Latest="False" Version="1708" LegacyVersion="16.0.8431.2079" Build="8431.2079" PubTime="2017-09-18T22:26:13.673Z" />
    <Update Latest="False" Version="1707" LegacyVersion="16.0.8326.2107" Build="8326.2107" PubTime="2017-09-12T18:56:53.657Z" />
    <Update Latest="False" Version="1707" LegacyVersion="16.0.8326.2096" Build="8326.2096" PubTime="2017-08-30T00:10:25.253Z" />
    <Update Latest="False" Version="1707" LegacyVersion="16.0.8326.2076" Build="8326.2076" PubTime="2017-08-19T00:13:01.787Z" />
    <Update Latest="False" Version="1707" LegacyVersion="16.0.8326.2073" Build="8326.2073" PubTime="2017-08-11T19:35:42.173Z" />
  </UpdateChannel>
```

Der ** \<ReleaseHistory\> ** -Stammknoten enthält das PublishedDate-Attribut, das das Datum angibt, an dem diese Datei veröffentlicht wurde. 
  
Der ** \<UpdateChannel\> ** -Knoten definiert einen unterstützten Kanal. 
  
- Das *Name* -Attribut definiert die Kanal-ID, die verwendet wird, um in der Datei Configuration. XML als Kanal Attribut an das ODT zu übergeben. 
    
  Beispiel: `<Add SourcePath="\\Server\Share" OfficeClientEdition="32" Channel="Current">` 
    
  > [!NOTE] 
  > Dieses Attribut ist veraltet und wird nur aus Gründen der Abwärtskompatibilität verwendet. Verwenden Sie das ID-Attribut anstelle des Name-Attributs. 
    
- Das *ID-* Attribut definiert die Kanal-ID, die verwendet wird, um in der Datei Configuration. XML als Kanal Attribut an das ODT zu übergeben. 
    
  Beispiel: `<Add SourcePath="\\Server\Share" OfficeClientEdition="32" Channel="Deferred">` 
    
- Das **Display** Name-Attribut wird als Anzeigename verwendet. 
    
Der ** \<Knoten\> Update** wird verwendet, um jedes Update zu definieren, das für diesen bestimmten Kanal veröffentlicht wurde. 
  
- Bei Festlegung auf "true" definiert das **neueste** Attribut die Version, die die neueste Version dieses Kanals ist. 
    
- Das **Version** -Attribut definiert die Versionsnummer für diese bestimmte Aktualisierung. 
    
- Das **LegacyVersion** -Attribut definiert die vollständige Versionsnummer für diese bestimmte Aktualisierung. 
    
- Das **Build** -Attribut definiert die Buildnummer für dieses bestimmte Update. 
    
- Das **PubTime** -Attribut definiert das Datum und die Uhrzeit, zu der dieses Update im Office CDN veröffentlicht wurde. 
    

