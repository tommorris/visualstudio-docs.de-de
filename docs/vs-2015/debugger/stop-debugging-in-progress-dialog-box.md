---
title: Beenden Sie das Debuggen im Dialogfeld Status | Microsoft-Dokumentation
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
- vs.debug.stopnow
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
- Stop Debugging in Progress dialog box
ms.assetid: ed7ef49d-e25f-4a4d-9396-9bc7b4143117
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e96e76f809f6c2f8f02267fe080e9e6742af4587
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47512382"
---
# <a name="stop-debugging-in-progress-dialog-box"></a>Debuggen wird beendet (Dialogfeld)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [beenden Debuggen im Statusdialogfeld](https://docs.microsoft.com/visualstudio/debugger/stop-debugging-in-progress-dialog-box).  
  
Dieses Dialogfeld wird angezeigt, wenn vom Debugger versucht wird, eine Debugsitzung zu beenden, der Beendigungsvorgang jedoch einige Zeit dauert. Das Beenden einer Debugsitzung erfolgt normalerweise sehr schnell, sodass dieses Dialogfeld nicht angezeigt wird. Manchmal dauert es jedoch eine Weile, bis alle derzeit debuggten Prozesse getrennt sind. Wenn das Beenden der Sitzung mehrere Sekunden dauert (bzw. ein Fehler beim Trennen auftritt), wird dieses Dialogfeld angezeigt. Bei wiederholtem Auftreten kann dies auf ein internes Problem hindeuten. Nehmen Sie ggf. Kontakt zum Produktsupport auf.  
  
 Sie können warten, bis alle Prozesse getrennt und dieses Dialogfeld nicht mehr angezeigt, oder die **jetzt beenden** Schaltfläche, um die sofortige Beendigung zu erzwingen.  
  
 **Jetzt beenden**  
 Klicken Sie auf diese Schaltfläche, um die Debugsitzung sofort zu beenden. Mithilfe von **jetzt beenden**wird beendet, anstatt die debuggten Prozesse getrennt. Wenn Sie Systemprozesse debuggen, beenden Sie die Prozesse mit **jetzt beenden** können unerwartete und unerwünschte Auswirkungen.  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggersicherheit](../debugger/debugger-security.md)   
 [Trennen von Programmen](http://msdn.microsoft.com/en-us/f2c756c2-8079-474b-94c2-01c19a141a01)



