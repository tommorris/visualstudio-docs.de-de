---
title: 'Vorbereitung zum Debuggen: Konsolenprojekte | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], console applications
- debugging console applications
- console applications, debugging
ms.assetid: 9641f1d9-2d5a-48b1-8731-6525e8f67892
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3829ba95f9c8885088487e62c9e5e0f2e29a7bb5
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44283989"
---
# <a name="debugging-preparation-console-projects"></a>Vorbereitung zum Debuggen: Konsolenprojekte
Mit Ausnahme einiger zusätzlicher Punkte ist die Vorbereitung für das Debuggen eines Konsolenprojekts der Vorbereitung für das Debuggen eines Windows-Projekts sehr ähnlich. Weitere Informationen finden Sie unter [Windows Forms-Anwendungen](../debugger/debugging-preparation-windows-forms-applications.md), und [Vorbereitung zum Debuggen: Windows Forms-Anwendungen (.NET)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/sez9z95a(v=vs.100)). Wegen der Ähnlichkeit aller Konsolenanwendungen deckt dieses Thema die folgenden Projekttypen ab:  
  
-   C#-Konsolenanwendung  
  
-   Visual Basic-Konsolenanwendung  
  
-   C++-Konsolenanwendung (.NET)  
  
-   C++-Konsolenanwendung (Win32)  
  
 Für die Konsolenanwendung müssen u. U. Befehlszeilenargumente angegeben werden. Weitere Informationen finden Sie unter [Projekteinstellungen für eine C++-Debugkonfiguration](../debugger/project-settings-for-a-cpp-debug-configuration.md), [Projekteinstellungen für eine Visual Basic-Debugkonfiguration](../debugger/project-settings-for-a-visual-basic-debug-configuration.md), oder [Projekteinstellungen für c# Debug Configurations ](../debugger/project-settings-for-csharp-debug-configurations.md).  
  
 Wie alle Projekteigenschaften bleiben diese Argumente über die Debug- und Visual Studio-Sitzungen hinweg erhalten. Aus diesem Grund ist die Konsolenanwendung eine, die Sie zuvor bereits debuggt wurde, denken Sie daran, dass möglicherweise Argumente aus früheren Sitzungen der  **\<Projekt > Eigenschaftenseiten** Dialogfeld.  
  
 Eine Konsolenanwendung verwendet die **Konsole** Fenster Eingaben akzeptieren und Anzeige von ausgabemeldungen. Zum Schreiben in die **Konsole** Fenster, die Ihre Anwendung verwenden muss die **Konsole** Objekt anstelle des Debug-Objekts. Zum Schreiben in die **Ausgabefenster von Visual Studio** Fenster, verwenden Sie wie gewohnt das Debug-Objekt. Sie sollten genau wissen, in welchem Fenster die Ausgabe erfolgt, da Sie ansonsten u. U. die Ausgabe im falschen Fenster überprüfen. Weitere Informationen finden Sie unter [Console-Klasse](/dotnet/api/system.console), [Debug-Klasse](/dotnet/api/system.diagnostics.debug), und [Fenster "Ausgabe"](../ide/reference/output-window.md).  
  
## <a name="starting-the-application"></a>Starten der Anwendung  
 Wenn einige Konsolenanwendungen gestartet werden, werden sie vollständig ausgeführt und dann beendet. Dieses Verhalten gibt Ihnen möglicherweise nicht genügend Zeit, um die Ausführung zu unterbrechen und einen Debugvorgang durchzuführen. Zum Debuggen einer Anwendung verwenden Sie eines der folgenden Verfahren, mit dem die Anwendung gestartet wird:  
  
-   Die Anwendung gestartet wird und wird ausgeführt, bis sie den Haltepunkt erreicht.  
  
-   Die Anwendung wird gestartet und sofort an der ersten Zeile des Quellcodes unterbrochen.  
  
-   In einem Quellcodefenster, klicken Sie auf eine Zeile aus, und wählen Sie **Ausführen bis Cursor**.  
  
     Die Anwendung wird gestartet und bis zur ausgewählten Zeile bzw. bis zu einem Haltepunkt ausgeführt, wenn der Haltepunkt vor der Zeile erreicht wird.  
  
 Beim Debuggen einer Konsolenanwendung möchten Sie die Anwendung möglicherweise über die Eingabeaufforderung und nicht von Visual Studio aus starten. In diesem Fall können Sie die Anwendung über die Eingabeaufforderung starten und den Visual Studio-Debugger an die Anwendung anfügen. Weitere Informationen finden Sie unter [Anfügen an ausgeführte Prozesse](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md).  
  
 Wenn Sie eine Konsolenanwendung in Visual Studio starten die **Konsole** Fenster, die manchmal hinter dem Visual Studio-Fenster wird angezeigt. Wenn Sie die Konsolenanwendung über Visual Studio starten und anscheinend nichts geschieht, versuchen Sie, das Visual Studio-Fenster zu verschieben.  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von nativem Code](../debugger/debugging-native-code.md)   
 [Debuggen von verwaltetem Code](../debugger/debugging-managed-code.md)   
 [Visual C++ Project Types (Visual C++-Projekttypen)](../debugger/debugging-preparation-visual-cpp-project-types.md)   
 [C#-, F#- und Visual Basic-Projekttypen](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)   
 [Projekteinstellungen für eine C++-Debugkonfiguration](../debugger/project-settings-for-a-cpp-debug-configuration.md)   
 [Debuggersicherheit](../debugger/debugger-security.md)