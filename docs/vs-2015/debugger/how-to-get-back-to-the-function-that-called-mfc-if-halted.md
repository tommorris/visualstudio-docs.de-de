---
title: 'Vorgehensweise: Zurückkehren zur Funktion, die MFC aufgerufen hat, wenn angehalten | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.mfc
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- functions [C++], debugging
- function calls, returning to calling function
- debugging [MFC], returning to calling function
- debugging [MFC], functions
- Break command
- programs, halting
- functions [debugger]
ms.assetid: d254a5a9-afbd-4923-9d7a-7422d824cabf
caps.latest.revision: 21
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d9148fb0f3431f7edc0d4b69fdf83ef4b629789f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47515132"
---
# <a name="how-to-get-back-to-the-function-that-called-mfc-if-halted"></a>Gewusst wie: Zurückkehren zur Funktion, die MFC aufgerufen hat, wenn die Ausführung angehalten wurde
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [wie: Zurückkehren zur Funktion dieses Namens MFC Wenn angehalten](https://docs.microsoft.com/visualstudio/debugger/how-to-get-back-to-the-function-that-called-mfc-if-halted).  
  
HINWEIS]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü Extras auf Einstellungen importieren und exportieren, um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
 Bei Verwendung der **unterbrechen** Befehl die **Debuggen** im Menü des Programms angehalten jetzt in MFC, und Sie sind Sie sicher, dass das Problem in Ihrem Code können Sie das Fenster "Aufrufliste" zum Navigieren zu Ihrer Funktion zurück. Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden Sie das Fenster "Aufrufliste"](../debugger/how-to-use-the-call-stack-window.md).  
  
 Manchmal wird der Code in der Meldungsverteilschleife unterbrochen. In diesem Fall ist kein Benutzercode in der Aufrufliste vorhanden. Sie können Haltepunkte (möglicherweise mit Bedingungen und Trefferanzahl) anstelle von verwenden, um dieses Problem zu vermeiden, die **unterbrechen** Befehl. Weitere Informationen finden Sie unter [Haltepunkte und Ablaufverfolgungspunkte](http://msdn.microsoft.com/en-us/fe4eedc1-71aa-4928-962f-0912c334d583)).  
  
### <a name="to-navigate-to-the-function-from-which-mfc-was-called"></a>So navigieren Sie zu der Funktion, von der MFC aufgerufen wurde  
  
-   Verwenden der **Aufrufliste** Fenster.  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von nativem Code häufig gestellte Fragen](../debugger/debugging-native-code-faqs.md)   
 [Debuggen von nativem Code](../debugger/debugging-native-code.md)



