---
title: Gemischter Code und fehlende Daten im Aufruflistenfenster | Microsoft-Dokumentation
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- SQL
- VB
- CSharp
- C++
helpviewer_keywords:
- managed code, stepping
- Call Stack window, mixed-mode debugging
- Call Stack window, troubleshooting
- native frames
- managed call stacks
- mixed-mode debugging, call stack
- stepping, out of managed code
ms.assetid: dd628427-e8d6-4fc2-b524-9d6393ea5376
caps.latest.revision: 23
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c91b2e49dc94057ab7929380ad1b819cd01731d6
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47514936"
---
# <a name="mixed-code-and-missing-information-in-the-call-stack-window"></a>Gemischter Code und fehlende Daten im Fenster "Aufrufliste"
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [Gemischter Code und fehlende Daten in das Fenster "Aufrufliste"](https://docs.microsoft.com/visualstudio/debugger/mixed-code-and-missing-information-in-the-call-stack-window).  
  
Da es zwischen den Aufruflisten von verwaltetem Code und nativem Code Unterschiede gibt, kann der Debugger bei vermischten Codetypen nicht immer die vollständige Aufrufliste anzeigen. Wenn nativer Code verwalteten Code aufruft, können Sie feststellen, dass die folgenden Diskrepanzen in den **Aufrufliste** Fenster:  
  
-   Der systemeigene Rahmen direkt über den verwalteten Code möglicherweise fehlen die **Aufrufliste** Fenster. Weitere Informationen finden Sie unter [Vorgehensweise: Prozedurschritt aus verwaltetem Code, wenn systemeigene Rahmen im Aufruflistenfenster fehlen](../debugger/how-to-step-out-of-managed-code-when-native-frames-are-missing-from-the-call-stack-window.md).  
  
-   Anwendungen außerhalb des Debuggers im gemischten Modus die **Aufrufliste** Fenster kann nur den verwalteten Code anzuzeigen und der systemeigenen Rahmen nicht sichtbar.  
  
 Beide Fälle treten relativ selten ein. In den meisten Fällen, in denen verwalteter Code durch systemeigenen Code aufgerufen wird, werden die Aufruflisten richtig angezeigt.  
  
## <a name="see-also"></a>Siehe auch  
 [Gewusst wie: Verwenden des Fensters „Aufrufliste“](../debugger/how-to-use-the-call-stack-window.md)





