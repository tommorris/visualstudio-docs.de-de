---
title: IDebugProgram2::Attach | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugProgram2::Attach
helpviewer_keywords:
- IDebugProgram2::Attach
ms.assetid: de069fbf-a565-4905-b102-f5658c55aacd
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: aff1e5f6c887b42b6f49e0c8cfa426cade814006
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
ms.locfileid: "31117959"
---
# <a name="idebugprogram2attach"></a>IDebugProgram2::Attach
Fügt an die Anwendung.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Attach(   
   IDebugEventCallback2* pCallback  
);  
```  
  
```csharp  
int Attach(   
   IDebugEventCallback2 pCallback  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pCallback`  
 [in] Ein [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md) Objekt für die Debug-ereignisbenachrichtigung verwendet werden soll.  
  
## <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall gibt `S_OK`ist, andernfalls wird ein Fehlercode zurückgegeben. Die folgende Tabelle zeigt einige mögliche Fehlercodes.  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`E_ATTACH_DEBUGGER_ALREADY_ATTACHED`|Das angegebene Programm ist bereits an den Debugger angefügt.|  
|`E_ATTACH_DEBUGGEE_PROCESS_SECURITY_VIOLATION`|Eine sicherheitsverletzung bei der die Prozedur anfügen.|  
|`E_ATTACH_CANNOT_ATTACH_TO_DESKTOP`|Ein desktop-Programm kann nicht an den Debugger angefügt werden.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Debugging-Modul (DE) hat diese Methode zum Anfügen an ein Programm nie aufgerufen. Wenn DE im Adressraum des Programms, führt der [OnAttach](../../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md) -Methode aufgerufen wird. Wenn die DE ausgeführt wird in des Sitzung Debug-Managers (SDM) Adressraums, den [Anfügen](../../../extensibility/debugger/reference/idebugengine2-attach.md) Methode wird aufgerufen.  
  
## <a name="see-also"></a>Siehe auch  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugEventCallback2](../../../extensibility/debugger/reference/idebugeventcallback2.md)   
 [OnAttach](../../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md)   
 [Anfügen](../../../extensibility/debugger/reference/idebugengine2-attach.md)