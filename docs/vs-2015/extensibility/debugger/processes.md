---
title: Prozesse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- debugging [Debugging SDK], processes
ms.assetid: a6a1efdc-b243-40c8-a778-6f69f6b018be
caps.latest.revision: 15
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 37aa4436baa449e702d5cb6f76078b2bb36311fd
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47523406"
---
# <a name="processes"></a>Prozesse
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [Prozesse](https://docs.microsoft.com/visualstudio/extensibility/debugger/processes).  
  
Im Hinblick auf die Debugger-Architektur eine **Prozess**:  
  
-   Ist ein Container für einen Satz von Programmen. Er ist eng an einen Windows-Prozess, der ein Container für eine Gruppe von Threads ist.  
  
-   Können selbst durch den Namen, Bezeichner oder Bezeichner der physischen identifizieren.  
  
-   Können alle ausgeführten Programme (und ihren Threads) auflisten.  
  
-   Beschreiben können selbst, den Port an, den er ausgeführt wird und der Computer, der sie enthält.  
  
-   Können, erstellen Sie eine oder mehr Programme beenden eines der Programme, die sie erstellt oder dazu führen, dass ein Programm zu beenden.  
  
-   Wird durch dargestellt eine [IDebugProcess2](../../extensibility/debugger/reference/idebugprocess2.md) -Schnittstelle, die erstellt wird, wenn der Prozess gestartet wird. Ein Prozess wird gestartet, indem Sie entweder die sitzungsbasierter Debug-Manager (SDM) oder [LaunchSuspended](../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md).  
  
 Das debugpaket kann eine Debug-Engine (DE) an einen Prozess anfügen, durch den Aufruf [Anfügen](../../extensibility/debugger/reference/idebugprocess2-attach.md). Dies bedeutet, dass die DE fügt alle möglichen Programme, die Ausführung im Prozess, den er verarbeiten kann. Wenn die common Language Runtime DE an einen Prozess angefügt wurde, fügt es z. B. nur für Programme, die verwalteten Code ausgeführt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Programme](../../extensibility/debugger/programs.md)   
 [Threads](../../extensibility/debugger/threads.md)   
 [Debuggerkonzepte](../../extensibility/debugger/debugger-concepts.md)   
 [Debug-Paket](../../extensibility/debugger/debug-package.md)   
 [Debug-Engine](../../extensibility/debugger/debug-engine.md)   
 [IDebugProcess2](../../extensibility/debugger/reference/idebugprocess2.md)   
 [LaunchSuspended](../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)   
 [Anfügen](../../extensibility/debugger/reference/idebugprocess2-attach.md)

