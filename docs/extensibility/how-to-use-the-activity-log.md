---
title: 'Vorgehensweise: Verwenden des Aktivitätsprotokolls | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSPackages, debugging
- VSPackages, troubleshooting
ms.assetid: bb3d3322-0e5e-4dd5-b93a-24d5fbcd2ffd
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3b5647a62064857bca6a6352a14fe56eff4386f9
ms.sourcegitcommit: 1c2ed640512ba613b3bbbc9ce348e28be6ca3e45
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/03/2018
ms.locfileid: "39497995"
---
# <a name="how-to-use-the-activity-log"></a>Gewusst wie: Verwenden des Aktivitätsprotokolls
VSPackages können Nachrichten in das Aktivitätsprotokoll zu schreiben. Dieses Feature ist besonders nützlich zum Debuggen von VSPackages im Einzelhandel-Umgebungen.  
  
> [!TIP]
>  Das Aktivitätsprotokoll ist immer aktiviert. Visual Studio behält einen kontinuierlichen Puffer, der die letzten 100 Einträge sowie die ersten 10 Einträge, die allgemeine Konfigurationsinformationen haben.  
  
## <a name="to-write-an-entry-to-the-activity-log"></a>Zum Schreiben eines Eintrags im Aktivitätsprotokoll  
  
1.  Fügen Sie diesen Code in die <xref:Microsoft.VisualStudio.Shell.Package.Initialize%2A> Methode oder in eine andere Methode, mit Ausnahme der VSPackage-Konstruktor:  
  
    ```csharp  
    IVsActivityLog log = GetService(typeof(SVsActivityLog)) as IVsActivityLog;  
    if (log == null) return;  
  
    int hr = log.LogEntry((UInt32)__ACTIVITYLOG_ENTRYTYPE.ALE_INFORMATION,  
        this.ToString(),  
        string.Format(CultureInfo.CurrentCulture,  
        "Called for: {0}", this.ToString()));  
    ```  
  
     Dieser Code Ruft die <xref:Microsoft.VisualStudio.Shell.Interop.SVsActivityLog> service auf und wandelt ihn um ein <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog> Schnittstelle. <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog.LogEntry%2A> Schreibt einen Informationseintrag in das Aktivitätsprotokoll, die unter Verwendung des Kontexts der aktuellen Kultur.  
  
2.  Wenn das VSPackage geladen wird (in der Regel, wenn ein Befehl aufgerufen wird, oder ein Fenster geöffnet ist), wird der Text in das Aktivitätsprotokoll geschrieben.  
  
## <a name="to-examine-the-activity-log"></a>Das Aktivitätsprotokoll untersuchen  
  
1.  Führen Sie Visual Studio mit der [/Log](../ide/reference/log-devenv-exe.md) Befehlszeilenschalter ActivityLog.xml während einer Sitzung auf dem Datenträger zu schreiben.

2.  Suchen Sie nach dem Schließen von Visual Studio, das Aktivitätsprotokoll im Unterordner für Visual Studio-Daten: **% appdata%* \Microsoft\VisualStudio\15.0\ActivityLog.xml*.  
  
3.  Öffnen Sie das Aktivitätsprotokoll mit einem beliebigen Texteditor ein. Hier ist ein typischer Eintrag ein:  
  
    ```  
    Called for: Company.MyApp.MyAppPackage ...  
    ```  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Da das Aktivitätsprotokoll auf einen Dienst handelt, ist das Aktivitätsprotokoll in der VSPackage-Konstruktor nicht verfügbar.  
  
 Sie sollten das Aktivitätsprotokoll abrufen, unmittelbar vor der in den sie schreiben. Zwischenspeichern Sie und speichern Sie das Aktivitätsprotokoll für die zukünftige Verwendung nicht.  
  
## <a name="see-also"></a>Siehe auch
 [/ Log (devenv.exe)](../ide/reference/log-devenv-exe.md)   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog>   
 <xref:Microsoft.VisualStudio.Shell.Interop.__ACTIVITYLOG_ENTRYTYPE>   
 [Problembehandlung bei VSPackages](../extensibility/troubleshooting-vspackages.md)   
 [VSPackages](../extensibility/internals/vspackages.md)
