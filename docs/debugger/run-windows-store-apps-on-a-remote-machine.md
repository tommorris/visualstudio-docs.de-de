---
title: Ausführen von UWP-apps auf einem Remotecomputer | Microsoft-Dokumentation
ms.custom: ''
ms.date: 01/05/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: 0f6814d6-cd0d-49f3-b501-dea8c094b8ef
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: 2845057fe970299d249d580d97b557a5ed311fc0
ms.sourcegitcommit: c57ae28181ffe14a30731736661bf59c3eff1211
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38795971"
---
# <a name="run-uwp-apps-on-a-remote-machine-in-visual-studio"></a>Ausführen von UWP-apps auf einem Remotecomputer in Visual Studio
  
Um eine UWP-app auf einem Remotecomputer auszuführen, müssen Sie mithilfe der Remotetools für Visual Studio anfügen. Der Remoteserver-Verwaltungstools können Sie ausführen, Debuggen, profilerstellung und zum Testen einer UWP-Apps, die auf einem Gerät von einem zweiten Computer ausgeführt wird, die Visual Studio ausgeführt wird. Ausführen auf einem Remotegerät kann besonders effektiv sein, wenn Visual Studio-Computer, die spezifisch für UWP-apps, z.B. Fingereingabe, GeoLocation und physische Ausrichtung Funktion nicht unterstützt. In diesem Thema wird beschrieben, wie Sie eine Remotesitzung konfigurieren und starten.

In einigen Szenarien werden die Remotetools automatisch installiert, wenn Sie auf einem Remotegerät bereitstellen.

- Für Windows 10-PCs Creators Update oder spätere Versionen ausführen werden automatisch remote Tools installiert.
- Für Windows 10 Xbox, IOT und HoloLens-Geräte werden remote Tools automatisch installiert.
- Für Mobile Windows 10, Sie müssen physisch auf dem Telefon verbunden werden, müssen Sie aktivieren [Entwicklermodus](/windows/uwp/get-started/enable-your-device-for-development) und Sie müssen auswählen, **Gerät** als Debugziel. Remote-Tools sind nicht erforderlich oder unterstützt.

Für Windows 10-PCs ein Pre-Ersteller-Update-Version von Windows ausführen müssen Sie die Remoteserver-Verwaltungstools auf dem Remotecomputer manuell installieren, bevor Sie debuggen können. Befolgen Sie die Anweisungen in diesem Thema. 
  
##  <a name="BKMK_Prerequisites"></a> Erforderliche Komponenten  
 So debuggen Sie auf einem Remotegerät:  
  
- Das Remotegerät und der Visual Studio-Computer müssen über ein Netzwerk verbunden oder direkt über ein USB- oder Ethernet-Kabel verbunden. Das Debugging über das Internet wird nicht unterstützt.  

- Sie müssen die aktivieren [Entwicklermodus](/windows/uwp/get-started/enable-your-device-for-development). 
  
- Für Windows 10-PCs mit einer Version von Windows 10 als Windows 10 creators Update, müssen Sie [installieren und Ausführen von Komponenten für das Remotedebuggen](#BKMK_download).
  
##  <a name="BKMK_Security"></a> Sicherheit  
In der Standardeinstellung **universell (unverschlüsseltes Protokoll)** auf Windows 10 verwendet wird. Dieses Protokoll sollten nur in vertrauenswürdigen Netzwerken verwendet werden. Die debugging-Verbindung ist anfällig für böswillige Benutzer, die abfangen und Ändern von Daten zwischen der Entwicklung und einen Remotecomputer übergeben werden konnte.
  
> [!WARNING]
>  Es gibt keine Netzwerksicherheit, wenn Sie den Authentifizierungsmodus, um festlegen **universell (unverschlüsseltes Protokoll)** oder **keine**. Wählen Sie diese Modi, nur dann, wenn Sie sicher sind, dass das Netzwerk nicht durch von bösartigen oder feindlichen Datenverkehr gefährdet ist.  
  
##  <a name="BKMK_DirectConnect"></a> Gewusst wie: Herstellen einer Verbindung direkt mit einem USB-Kabel 

Unter Windows 10 können Sie auf einem Gerät über USB angeschlossene bereitstellen, durch Auswahl **Gerät** anstelle von **Remotecomputer** als Bereitstellungsziel (hierzu können Sie der **Standard** Symbolleiste oder auf der Eigenschaftenseite Debuggen).

##  <a name="BKMK_ConnectVS"></a> Konfigurieren Sie das Visual Studio-Projekt für das Remotedebuggen  
 In den Eigenschaften des Projekts geben Sie das Remotegerät an, mit dem eine Verbindung hergestellt werden soll. Das Verfahren unterscheidet sich je nach Programmiersprache. Können Sie den Netzwerknamen des Remotegeräts eingeben, oder Sie können auswählen, aus der **Remoteverbindung** Dialogfeld.  
  
 ![Select Remotedebuggerverbindung Dialogfeld](../debugger/media/vsrun_selectremotedebuggerdlg.png "VSRUN_SelectRemoteDebuggerDlg")  
  
 Im Dialogfeld werden nur die Geräte aufgelistet, die sich im lokalen Teilnetz von Visual Studio-Computers befinden und die den Remotedebugger ausführen.  
  
> [!TIP]
>  Sollten Sie Probleme beim Herstellen einer Verbindung mit einem Remotegerät haben, versuchen Sie, die IP-Adresse des Geräts einzugeben. Um die IP-Adresse eines Geräts zu bestimmen, öffnen Sie ein Befehlsfenster, und geben Sie dann **ipconfig**ein. Die IP-Adresse wird als **IPv4 Address**aufgeführt.  
  
###  <a name="BKMK_Choosing_the_remote_device_for_C__and_Visual_Basic_projects"></a> Auswählen des Remotegeräts für c# und Visual Basic-Projekte  
  
1.  Wählen Sie im Projektmappen-Explorer den Projektnamen aus und gehen Sie anschließend im Kontextmenü auf **Eigenschaften** .  
  
2.  Wählen Sie **Debuggen**aus.  
  
3.  Wählen Sie in der Liste **Zielgerät** die Option **Remotecomputer** aus.  
  
4.  Geben Sie den Netzwerknamen des Remotegeräts im Feld **Remotecomputer** ein, oder wählen Sie **Suchen** aus, um das Gerät im Dialogfeld **Remotedebuggerverbindung auswählen** auszuwählen. 

    ![Verwaltete Projekteigenschaften für Remotedebugging](../debugger/media/vsrun_managed_projprop_remote.png "VSRUN_Managed_ProjProp_Remote")  
  
###  <a name="BKMK_Choosing_the_remote_device_for_JavaScript_and_C___projects"></a> Auswählen des Remotegeräts für JavaScript- und C++-Projekte  
  
1.  Wählen Sie im Projektmappen-Explorer den Projektnamen aus und gehen Sie anschließend im Kontextmenü auf **Eigenschaften** .  
  
2.  Erweitern Sie den Knoten **Konfigurationseigenschaften** , und wählen Sie dann **Debuggen**aus.  
  
3.  Wählen Sie **Remote Debugger** in der Liste **Zu startender Debugger** aus.  
  
4.  Geben Sie im Feld **Computername** den Netzwerknamen des Remotegeräts ein, oder wählen Sie im Feld den Pfeil nach unten aus, um im Dialogfeld **Remotedebuggerverbindung auswählen** das Gerät auszuwählen.  

    ![C&#43; &#43; Projekteigenschaften für das Remotedebuggen](../debugger/media/vsrun_cpp_projprop_remote.png "VSRUN_CPP_ProjProp_Remote")
  
## <a name="BKMK_download"></a> Herunterladen und installieren Sie die Remoteserver-Verwaltungstools (vor Creators Update)

Wenn Sie ein Pre-Ersteller-Update-Versionen von Windows 10 verwenden, dann führen Sie diese Anweisungen. Andernfalls können Sie diesen Abschnitt überspringen.

[!INCLUDE [remote-debugger-download](../debugger/includes/remote-debugger-download.md)]
  
### <a name="BKMK_setup"></a> Einrichten des Remotedebuggers

[!INCLUDE [remote-debugger-configuration](../debugger/includes/remote-debugger-configuration.md)]  
  
##  <a name="BKMK_RunRemoteDebug"></a> Starten einer Remotedebugsitzung  
 Sie starten, beenden und navigieren eine Remotedebugsitzung genauso wie eine lokale Sitzung. Pre-creators Update-Versionen von Windows 10 Stellen Sie sicher, dass der Remotedebugmonitor auf dem Remotegerät ausgeführt wird.  
  
 Wählen Sie anschließend im Menü **Debuggen** (Tastatur: F5) die Option **Debuggen starten** aus. Das Projekt wird neu kompiliert, anschließend für das Remotegerät bereitgestellt und darauf gestartet . An Haltepunkten unterbricht der Debugger die Ausführung, und Sie können Ihren Code schrittweise ausführen, ihn überspringen oder verlassen. Wählen Sie **Debuggen beenden** aus, um Ihre Debugsitzung zu beenden, und schließen Sie die Remoteapp.
  
## <a name="see-also"></a>Siehe auch  
 [Erweiterte Optionen für die remote-Bereitstellung](/windows/uwp/debug-test-perf/deploying-and-debugging-uwp-apps#advanced-remote-deployment-options)  
 [Testen von UWP-Apps mit Visual Studio](../test/testing-store-apps-with-visual-studio.md)   
 [Debuggen von apps in Visual Studio](../debugger/debug-store-apps-in-visual-studio.md)
