---
title: BP_REQUEST_INFO2 | Microsoft-Dokumentation
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
- BP_REQUEST_INFO2
helpviewer_keywords:
- BP_REQUEST_INFO2 structure
ms.assetid: 008c87f7-a76e-43d3-8904-11b225d6a9a5
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5568e696f8463e2a8e5c64467bc82f192d790b5e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "47509808"
---
# <a name="bprequestinfo2"></a>BP_REQUEST_INFO2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Die neueste Version dieses Themas finden Sie unter [BP_REQUEST_INFO2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/bp-request-info2).  
  
Enthält die Informationen erforderlich, um einen Haltepunkt, einschließlich Anbieter-GUID, Einschränkung und Ablaufverfolgungspunkt zu implementieren.  
  
## <a name="syntax"></a>Syntax  
  
```cpp#  
typedef struct _BP_REQUEST_INFO2 {  
   BPREQI_FIELDS   dwFields;  
   GUID            guidLanguage;  
   BP_LOCATION     bpLocation;  
   IDebugProgram2* pProgram;  
   BSTR            bstrProgramName;  
   IDebugThread2*  pThread;  
   BSTR            bstrThreadName;  
   BP_CONDITION    bpCondition;  
   BP_PASSCOUNT    bpPassCount;  
   BP_FLAGS        dwFlags;  
   GUID            guidVendor;  
   BSTR            bstrConstraint;  
   BSTR            bstrTracepoint;  
} BP_REQUEST_INFO2;  
```  
  
```csharp  
public struct BP_REQUEST_INFO2 {  
   public uint           dwFields;  
   public Guid           guidLanguage;  
   public BP_LOCATION    bpLocation;  
   public IDebugProgram2 pProgram;  
   public string         bstrProgramName;  
   public IDebugThread2  pThread;  
   public string         bstrThreadName;  
   public BP_CONDITION   bpCondition;  
   public BP_PASSCOUNT   bpPassCount;  
   public uint           dwFlags;  
   public Guid           guidVendor;  
   public string         bstrConstraint;  
   public string         bstrTracepoint;  
};  
```  
  
## <a name="members"></a>Member  
 `dwFields`  
 Eine Kombination von Flags aus der [BPREQI_FIELDS](../../../extensibility/debugger/reference/bpreqi-fields.md) Enumeration, der angibt, welche Felder ausgefüllt sind.  
  
 `guidLanguage`  
 Die Sprachen-GUID.  
  
 `bpLocation`  
 Die [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md) -Struktur, die den Typ der Haltepunktposition angibt.  
  
 `pProgram`  
 Die [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) Objekt, das die Anwendung darstellt, in dem sich der Breakpoint auftritt.  
  
 `bstrProgramName`  
 Der Name der Anwendung in der der Breakpoint auftritt.  
  
 `pThread`  
 Die [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md) -Objekt, das den Thread darstellt, in dem sich der Breakpoint auftritt.  
  
 `bstrThreadName`  
 Der Name des Threads in der der Breakpoint auftritt.  
  
 `bpCondition`  
 Die [BP_CONDITION](../../../extensibility/debugger/reference/bp-condition.md) -Struktur, die beschreibt die Bedingungen, unter dem der Haltepunkt ausgelöst wird.  
  
 `bpPassCount`  
 Die [BP_PASSCOUNT](../../../extensibility/debugger/reference/bp-passcount.md) -Struktur, die die Pass-Count-Informationen des Haltepunkts enthält.  
  
 `dwFlags`  
 Eine Kombination von Flags aus der [BP_FLAGS](../../../extensibility/debugger/reference/bp-flags.md) Enumeration, die die Flags für den angeforderten Haltepunkt angibt.  
  
 `guidVendor`  
 GUID des Anbieters. Dies kann ein null-Wert sein.  
  
 `bstrConstraint`  
 Name der Haltepunkt-Einschränkung. Dies kann ein null-Wert sein.  
  
 `bstrTracepoint`  
 Name der Ablaufverfolgungspunkt. Dies kann ein null-Wert sein.  
  
## <a name="remarks"></a>Hinweise  
 Diese Struktur wird zurückgegeben, durch die [GetRequestInfo2](../../../extensibility/debugger/reference/idebugbreakpointrequest3-getrequestinfo2.md) Methode.  
  
## <a name="requirements"></a>Anforderungen  
 Header: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen und Unions](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetRequestInfo2](../../../extensibility/debugger/reference/idebugbreakpointrequest3-getrequestinfo2.md)   
 [BPREQI_FIELDS](../../../extensibility/debugger/reference/bpreqi-fields.md)   
 [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [BP_CONDITION](../../../extensibility/debugger/reference/bp-condition.md)   
 [BP_PASSCOUNT](../../../extensibility/debugger/reference/bp-passcount.md)   
 [BP_FLAGS](../../../extensibility/debugger/reference/bp-flags.md)

