---
title: Debuggen von clientseitigen Skripts | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], client-side scripts
- client-side scripts, debugging
ms.assetid: bb668527-2288-47bd-a6c8-cecbad76dde2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: aa5a21a60ab95b6dbc9aeb27a0c7d6e27ab32773
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44283111"
---
# <a name="client-side-script-debugging"></a>Debuggen von clientseitigen Skripts
Der Visual Studio-Debugger stellt eine umfassende Debugumgebung zum Suchen und Beheben von Fehlern in clientseitigen Skripts auf ASP.NET-Seiten bereit.  
  
## <a name="opening-script-documents"></a>Öffnen von Skriptdokumenten  
Sie können Sie eine Liste der serverseitigen und clientseitigen Skriptdokumente in der **Projektmappen-Explorer** anzeigen. Sie können beliebige Skriptdokumente über den **Projektmappen-Explorer**öffnen. Weitere Informationen finden Sie unter [How to: View Script Documents](../debugger/how-to-view-script-documents.md).  
  
## <a name="breakpoint-mapping"></a>Zuordnen von Haltepunkten  
 In Visual Studio können Sie serverseitigen Code nicht direkt debuggen, Sie können jedoch einen Haltepunkt in einer serverseitigen Datei festlegen. Visual Studio ordnet den Haltepunkt automatisch einer entsprechenden Position in der clientseitigen Datei zu und erstellt einen zugeordneten Haltepunkt im clientseitigen Code.  
  
## <a name="manually-or-automatically-attaching-to-script"></a>Manuelles oder automatisches Anhängen an Skripts  
 Um mit dem Debuggen von Skripts in [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]zu beginnen, muss der Debugger an das Skript anhängt werden, das Sie debuggen möchten. Dies kann manuell oder automatisch geschehen.  
  
 Sie können den Debugger manuell über die [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] -Debuggerschnittstelle anhängen und dabei einen laufenden Skriptprozess auswählen, an den der Debugger angehängt werden soll. Weitere Informationen finden Sie unter [How to: Attach to Script](../debugger/how-to-attach-to-script.md).  
  
 Der Debugger wird automatisch an das Skript angehängt, wenn eine der folgenden Bedingungen zutrifft:  
  
-   Sie erreichen einen im Skript festgelegten Haltepunkt.  
  
-   Sie erreichen eine VBScript `Stop` -Anweisung oder JScript `debugger` -Anweisung im Skriptcode.  
  
-   Der Browser oder Server stellt einen Syntax- oder Laufzeitfehler im Skript fest. In diesem Fall wird ein Dialogfeld angezeigt, und Sie können mit dem Debuggen beginnen.  
  
 Wenn Sie den Debugger manuell an das Skript anhängen, wird der Skriptprozess weiterhin ausgeführt, bis er durch ein bestimmtes Ereignis angehalten wird. Sie können ihn anhalten, indem Sie im Menü **Debuggen** die Option **Unterbrechen** auswählen.  
  
 Wenn der Debugger automatisch angehängt wird, wird die Skriptausführung in der Zeile angehalten, in der der Haltepunkt, die `Stop` -Anweisung oder `debugger` -Anweisung bzw. der Fehler aufgetreten ist oder in der Sie das Debuggen in Internet Explorer ausgewählt haben.  
  
 Sie können jetzt die normalen Debuggerfunktionen verwenden, um das Debuggen zu starten. Beispielsweise können Sie die Befehle **Schritt** verwenden, um die Codeausführung zeilenweise fortzusetzen. Im Fenster **Aufrufliste** können Sie den Skriptfluss anzeigen und steuern. Sie können die Variablenfenster oder das **Direktfenster** verwenden, um Variablen und Eigenschaften anzuzeigen oder zu ändern.  
  
## <a name="enhanced-error-messages-for-script-debugging"></a>Verbesserte Fehlermeldungen für das Skriptdebuggen  
 Visual Studio enthält verbesserte Fehlermeldungen für allgemeine Probleme beim Skriptdebuggen. Diese Meldungen werden erst angezeigt, wenn Sie den Debugger manuell an Internet Explorer anhängen. Wenn Sie beim automatischen Öffnen von Internet Explorer einen Fehlerzustand feststellen, sollten Sie versuchen, den Debugger manuell anzuhängen, damit die Fehlermeldungen angezeigt werden.  
  
## <a name="debugging-ajax-script-applications"></a>Debuggen von AJAX-Skriptanwendungen  
 AJAX-fähige Webanwendungen machen umfangreichen Gebrauch von Skriptcode und stellen besondere Anforderungen an das Debuggen. Weitere Informationen zu den Verfahrensweisen beim AJAX-Debuggen finden Sie unter  
  
 [Debugging and Tracing Ajax Applications Overview](https://msdn.microsoft.com/Library/92684ea0-7bb4-4a34-9203-3aa6394ce375).  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von ASP.NET- und AJAX-Anwendungen](../debugger/debugging-aspnet-and-ajax-applications.md)   
 [Einschränkungen beim Skriptdebugging](../debugger/limitations-on-script-debugging.md)   
 [Variable Windows](../debugger/debugger-windows.md)   
 [Direktfenster](../ide/reference/immediate-window.md)   
 [Debugging and Tracing Ajax Applications Overview](https://msdn.microsoft.com/Library/92684ea0-7bb4-4a34-9203-3aa6394ce375)
