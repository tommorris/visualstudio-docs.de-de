---
title: IDebugStackFrame3 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugStackFrame3
helpviewer_keywords:
- IDebugStackFrame3 interface
ms.assetid: 39af2f57-0a01-42b8-b093-b7fbc61e2909
caps.latest.revision: 16
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1f032ac6b5fb348916c51f8cc98e1726b0795e21
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47510722"
---
# <a name="idebugstackframe3"></a>IDebugStackFrame3
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [IDebugStackFrame3](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugstackframe3).  
  
Diese Schnittstelle erweitert [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md) , abgefangene Ausnahmen zu behandeln.  
  
## <a name="syntax"></a>Syntax  
  
```  
IDebugStackFrame3 : IDebugStackFrame2  
```  
  
## <a name="notes-for-implementers"></a>Hinweise für Implementierer  
 Die Debug-Engine (DE) implementiert diese Schnittstelle für das gleiche Objekt, das implementiert die [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md) -Schnittstelle zur Unterstützung von abgefangenen Ausnahmen.  
  
## <a name="notes-for-callers"></a>Hinweise für Aufrufer  
 Rufen Sie [QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3) auf eine `IDebugStackFrame2` Schnittstelle, um diese Schnittstelle zu erhalten.  
  
## <a name="methods-in-vtable-order"></a>Methoden in Vtable-Reihenfolge  
 Zusätzlich zu den von geerbten Methoden [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md), `IDebugStackFrame3` macht die folgenden Methoden verfügbar.  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[InterceptCurrentException](../../../extensibility/debugger/reference/idebugstackframe3-interceptcurrentexception.md)|Behandelt eine Ausnahme für den aktuellen Stapelrahmen, bevor die reguläre Ausnahmebehandlung.|  
|[GetUnwindCodeContext](../../../extensibility/debugger/reference/idebugstackframe3-getunwindcodecontext.md)|Gibt einen Codekontext an zurück, wenn es sich bei eine stapelentladung ausgeführt wurden.|  
  
## <a name="remarks"></a>Hinweise  
 Eine abgefangene Ausnahme bedeutet, dass ein Debugger eine Ausnahme verarbeiten kann, bevor alle normalen Ausnahmebehandlung Routinen, die von der Laufzeit aufgerufen werden. Das Abfangen einer Ausnahme im Wesentlichen bedeutet, dass die Laufzeit nehmen, dass es ein Ausnahmehandler vorhanden, selbst wenn nicht vorhanden ist.  
  
 [InterceptCurrentException](../../../extensibility/debugger/reference/idebugstackframe3-interceptcurrentexception.md) während alle Ereignisse der normale Ausnahme-Rückruf aufgerufen wird (die einzige Ausnahme hierbei ist, wenn Sie in diesem Fall nicht die Ausnahme werden, während der abgefangen kann gemischten Code (verwaltet und nicht verwaltetem Code) Debuggen der letzte Gelegenheit Rückruf). Wenn die DE nicht implementiert `IDebugStackFrame3`, oder die DE gibt einen Fehler zurück, aus IDebugStackFrame3::`InterceptCurrentException` (wie z. B. `E_NOTIMPL`), und klicken Sie dann der Debugger normalerweise die Ausnahme behandelt.  
  
 Durch das Abfangen einer Ausnahme an, kann der Debugger kann den Benutzer Änderungen vornehmen, um den Status des gedebuggten Programm und dann die Ausführung an der Stelle, wo die Ausnahme ausgelöst wurde, fortgesetzt.  
  
> [!NOTE]
>  Abgefangene Ausnahmen sind nur in verwaltetem Code, also in einem Programm zulässig, die unter der Common Language Runtime (CLR) ausgeführt wird.  
  
 Eine Debug-Engine gibt an, dass es abfangender Ausnahmen unterstützt, durch Festlegen von "MetricExceptions" auf einen Wert von 1 zur Laufzeit mithilfe der `SetMetric` Funktion. Weitere Informationen finden Sie unter [SDK-Hilfsprogramme zum Debugging](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md).  
  
## <a name="requirements"></a>Anforderungen  
 Header: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Siehe auch  
 [Wichtige Schnittstellen](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)   
 [SDK-Hilfsprogramme für das Debugging](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)

