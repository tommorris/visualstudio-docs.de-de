---
title: BP_FLAGS | Microsoft-Dokumentation
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
- BP_FLAGS
helpviewer_keywords:
- BP_FLAGS enumeration
ms.assetid: c45dfc74-5e7f-4f1e-a147-ab2a55dccbd0
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b6feb965c564e74dbb026a66a964d233b3ed75fb
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47509358"
---
# <a name="bpflags"></a>BP_FLAGS
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [BP_FLAGS](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/bp-flags).  
  
Bietet optionale Kennzeichen, die verwendet werden können, um zusätzliche Informationen angeben, wenn Sie einen Haltepunkt festlegen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp#  
enum enum_BP_FLAGS {   
   BP_FLAG_NONE            = 0x0000,  
   BP_FLAG_MAP_DOCPOSITION = 0x0001,  
   BP_FLAG_DONT_STOP       = 0x0002  
};  
typedef DWORD BP_FLAGS;  
```  
  
```csharp  
public enum enum_BP_FLAGS {   
   BP_FLAG_NONE            = 0x0000,  
   BP_FLAG_MAP_DOCPOSITION = 0x0001,  
   BP_FLAG_DONT_STOP       = 0x0002  
};  
```  
  
## <a name="members"></a>Member  
 BP_FLAG_NONE  
 Gibt kein Flag Haltepunkt an.  
  
 BP_FLAG_MAP_DOCPOSITION  
 Gibt an, der den Haltepunkt, der die Dokumentposition mithilfe die Debug-Engine (DE) zugeordnet werden sollen. Dies gilt nur für Haltepunkte, die in den Skript-orientierten Quelldateien wie z. B. Active Server Pages (ASP).  
  
 BP_FLAG_DONT_STOP  
 Gibt an, dass der Haltepunkt von der Debug-Engine verarbeitet werden sollen, aber die Debug-Engine letztlich nicht es beendet werden soll (d. h. eine [IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md) Ereignisobjekt sollte nicht gesendet werden). Dieses Flag dient in erster Linie mit Ablaufverfolgungspunkten verwendet werden.  
  
## <a name="remarks"></a>Hinweise  
 Verwendet für die `dwFlags` Mitglied der [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md) und [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md) Strukturen.  
  
 Diese Werte können kombiniert werden, mit einer bitweisen `OR`.  
  
## <a name="requirements"></a>Anforderungen  
 Header: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Siehe auch  
 [Enumerationen](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)   
 [BP_REQUEST_INFO2](../../../extensibility/debugger/reference/bp-request-info2.md)   
 [IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md)

